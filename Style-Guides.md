### Table of Contents

1. [Prettier](#prettier)
1. [Common Patterns](#common-patterns)
    * [Render Callbacks](#render-callbacks)
    * [Component Factories](#component-factories)
1. [Typescript](#typescript)
    * [Event Handlers](#event-handlers)
    * [Typing Redux-Connected Components](#typing-redux-connected-components)
    * [Typing Injected Props](#typing-injected-props)
1. [Redux & Actions](#redux--actions)
    * [Reducers](#reducers)
    * [Actions](#actions)
1. [Styling](#styling)
    * [Classnames](#classnames)
    * [Global Styles](#global-styles)
    * [Variables & Mixins](#variables--mixins)
    * [Adding Icon-fonts](#adding-icon-fonts)

<br/>

## Prettier

For all purely stylistic aspects of the codebase (Spaces vs tabs, semicolons, brackets on newlines etc.) we use a prettier config, and a pre-commit hook to pretty up your code for you. This is enforced by CI, so the Javascript codebase should be entirely consistent, except for a few build scripts and configs.



<br/>



## Common Patterns

There are a set of common patterns used throughout the codebase that can be a little tricky to understand at first glance. We'll try to explain them in detail here.

### Render Callbacks

Mostly contained in the `components/renderCbs` directory, we use render callbacks to provide a consistent set of props that sometimes only render on certain conditions. While each one is different, they usually either take in a `render` prop function, or a `with*` prop function, that send certain variables for rendering. Sometimes this is used to enforce typing props that could otherwise be null / undefined, such as the wallet instance if the component is on a page that allows you to unlock it. For example,

```
import { FullWalletOnly } from 'components/renderCbs';

<FullWalletOnly
  withFullWallet={(wallet) => /* render something that uses wallet */}
  withoutFullWallet={() => /* render something for unlocking a wallet */}
/>
```


### Component Factories

Similar to render callbacks, a few components are actually factories for rendering different styles of the same component. This is most often the case for form inputs, as they commonly require somewhat different markup, and it's tedious to have dozens of props that just toggle the way it looks. Almost all of these factories also have a component in `components/*` that implement them for a base-case of the component. For example,

```
import { GasLimitFieldFactory } from 'components';
<GasLimitFieldFactory withProps={({ gasLimit, onChange }) => (
  <React.Fragment>
    <h1>Enter gas here!</h1>
    <input value={gasLimit.raw} onChange={onChange} />
  </React.Fragment>
)}/>
```

But you could and should just use the component if you have no special markup needs

```
import { GasLimitField } from 'components';
<GasLimitField/>
```


<br/>


## Typescript

All app code should be written in typescript files (`.ts` or `.tsx`) and attempt to type everything. There may be a few quirks or tricky parts to typing that we'll try to outline here.

### Event Handlers

Event handlers such as `onChange` and `onClick`, should be properly typed using React's event handlers, not the normal Javascript ones. For example, if you have an event listener on an input element inside a form:

```ts
public onValueChange = (e: React.FormEvent<HTMLInputElement>) => {
  this.props.onChange(
    e.currentTarget.value,
    this.props.unit
  );
};
```

### Typing Redux-Connected Components

Components that receive props directly from redux as a result of the `connect`
function should use AppState for typing, rather than manually defining types.
This makes refactoring reducers easier by catching mismatches or changes of
types in components, and reduces the chance for inconsistency. It's also less
code overall.

```
// Do this
import { AppState } from 'reducers';

interface Props {
	wallet: AppState['wallet']['inst'];
	rates: AppState['rates']['rates'];
	// ...
}

// Not this
import { IWallet } from 'libs/wallet';
import { Rates } from 'libs/rates';

interface Props {
	wallet: IWallet;
	rates: Rates;
	// ...
}
```

However, if you have a sub-component that takes in props from a connected
component, it's OK to manually specify the type. Especially if you go from
being type-or-null to guaranteeing the prop will be passed (because of a
conditional render.)

### Typing Injected Props

Props made available through higher order components can be tricky to type. You can inherit the injected props, and in the case of react router, specialize the generic in `withRouter` so it can omit all of its injected props from the component.

```ts
import { RouteComponentProps } from 'react-router-dom';

interface MyComponentProps extends RouteComponentProps<{}> {
  name: string;
  countryCode?: string;
}
```

```ts
class MyComponent extends React.Component<MyComponentProps, {}> {

  render() {
    const { name, countryCode, location } = this.props; // location being the one of the injected props from the withRouter HOC
    ...
  }
}

export default withRouter<Props>(MyComponent);
```



<br/>



## Redux & Actions

Each reducer has one file in `reducers/[namespace].ts` that contains the reducer
and initial state, one file in `actions/[namespace].ts` that contains the action
creators and their return types, and optionally one file in
`sagas/[namespace].ts` that handles action side effects using
[`redux-saga`](https://github.com/redux-saga/redux-saga).

The files should be laid out as follows:

### Reducers

* State should be explicitly defined and exported
* Initial state should match state typing, define every key

```ts
import { NamespaceAction } from "actions/[namespace]";
import { TypeKeys } from 'actions/[namespace]/constants';

export interface State { /* definition for state object */ };
export const INITIAL_STATE: State = { /* Initial state shape */ };

export function [namespace](
	state: State = INITIAL_STATE,
	action: NamespaceAction
): State {
	switch (action.type) {
		case TypeKeys.NAMESPACE_NAME_OF_ACTION:
			return {
				...state,
				// Alterations to state
			};
		default:
			return state;
	}
}
```

### Actions

* Define each action creator in `actionCreator.ts`
* Define each action object type in `actionTypes.ts`
  * Export a union of all of the action types for use by the reducer
* Define each action type as a string enum in `constants.ts`
* Export `actionCreators` and `actionTypes` from module file `index.ts`

```
├── common
    ├── actions - application actions
        ├── [namespace] - action namespace
            ├── actionCreators.ts - action creators
            ├── actionTypes.ts - action interfaces / types
            ├── constants.ts - string enum
            ├── index.ts - exports all action creators and action object types
```

#### constants.ts

```ts
export enum TypeKeys {
  NAMESPACE_NAME_OF_ACTION = 'NAMESPACE_NAME_OF_ACTION'
}
```

#### actionTypes.ts

```ts
/*** Name of action ***/
export interface NameOfActionAction {
  type: TypeKeys.NAMESPACE_NAME_OF_ACTION;
  /* Rest of the action object shape */
}

/*** Action Union ***/
export type NamespaceAction = ActionOneAction | ActionTwoAction | ActionThreeAction;
```

#### actionCreators.ts

```ts
import * as interfaces from './actionTypes';
import { TypeKeys } from './constants';

export interface TNameOfAction = typeof nameOfAction;
export function nameOfAction(): interfaces.NameOfActionAction {
	return {
		type: TypeKeys.NAMESPACE_NAME_OF_ACTION,
		payload: {}
	};
};
```

#### index.ts

```ts
export * from './actionCreators';
export * from './actionTypes';
```




<br/>





## Styling

MyEtherWallet uses Bootstrap for its base styles. We're still on version 3.3, so if you're looking for docs, you'll need to refer to [the old ones here](getbootstrap.com/docs/3.3/css/).

Custom styles are written in SCSS (Not pure SASS, for backwards compatibility.) Most styles are limited to the component they style. They're inside of a file that shares the name of the component in the same folder. A typical styled component would look something like:

```ts
import React from 'react';
import './MyComponent.scss';

export default class MyComponent extends React.component<{}, {}> {
  render() {
    return (
      <div className="MyComponent">
        <div className="MyComponent-child">Hello!</div>
      </div>
    );
  }
}
```

### Classnames

These style modules classnames adhere to [SuitCSS naming convention](https://github.com/suitcss/suit/blob/master/doc/naming-conventions.md):

```scss
.MyComponent {
  /* Styles */

  &-child {
    /* Styles */

    &.is-hidden {
      display: none;
    }
  }
}
```

All elements inside of a component should extend its parent class namespace, or
create a new namespace (Potentially breaking that out into its own component.)

If you have a complex classname with conditionals or variables, consider using the `classnames` components instead of complex template strings.

### Global Styles

While you should strive to keep your styles to a single component, sometimes there's a need for global styles. In those cases, we put them in `common/sass/styles` and import them in `common/sass/styles.scss`. These should be limited to global element selectors (i.e. styling all `blockquote` or `code` tags) or things that are not rendered in React (Like `<noscript>` tags.) Otherwise, a component should be made.

### Variables & Mixins

Variables and mixins can be imported from the files in `common/sass`. Sass's module resolution is a little weird though, so you need to do `common/sass/*` for whatever you want.

```scss
@import 'common/sass/variables';
@import 'common/sass/mixins';

code {
  color: $code-color;
  @include clearfix;
}
```

### Legacy Styles

Legacy styles are housed under `common/assets/styles` and written with LESS. When working on a module that has styling in Less, try to convert it by following these steps:

* Screenshot the component in question
* Create a new SCSS file in the same directory as the component
* Remove styling from LESS file, convert it to the SCSS file (Mostly just `s/@/$` for variables)
* Convert class names to SuitCSS naming convention
* Convert any utility classes from `etherewallet-utilities.less` into mixins
* Convert as many element selectors (e.g. `span { ... }`) to class name selectors as possible
* Convert any `<br/>` tags or `&nbsp;`s to margins or paddings
* Ensure that there has been little to no deviation from screenshot

### Adding Icon-fonts

1. Download chosen icon-font
1. Declare css font-family:
   ```
   @font-face {
   	font-family: 'social-media';
   	src: url('../assets/fonts/social-media.eot');
   	src: url('../assets/fonts/social-media.eot') format('embedded-opentype'),
   		url('../assets/fonts/social-media.woff2') format('woff2'),
   		url('../assets/fonts/social-media.woff') format('woff'),
   		url('../assets/fonts/social-media.ttf') format('truetype'),
   		url('../assets/fonts/social-media.svg') format('svg');
   	font-weight: normal;
   	font-style: normal;
   }
   ```
1. Create classes for each icon using their unicode character
   ```
   .sm-logo-facebook:before {
       content: '\ea02';
     }
   ```
   * [How to get unicode icon values?](https://stackoverflow.com/questions/27247145/get-the-unicode-icon-value-from-a-custom-font)
1. Write some markup:
   ```
   <a href="/">
   	<i className={`sm-icon sm-logo-${text} sm-24px`} />
   	Hello World
   </a>
   ```