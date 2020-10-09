## Introduction
MyCrypto Typography system is based on `styled-system` and `styled-components`. It features a theme containing all our style properties and a variant set defining our main typography types.

<br>

## Why styled-system ?
`styled-system` allow us to inject style props to `styled-components` definition. It features a large API englobing all CSS's properties.

:bulb: **DOC**: https://styled-system.com/api

<br>

### Example
```tsx
import React from 'react';
import styled from 'styled-components';
import { color, ColorProps } from 'styled-system';

const SDiv = styled.div<ColorProps>`
	${color}
`

const Component = () => (
	<SDiv color='blue'>
		I'm blue dabedi dabeda
	</SDiv>
)
```
<br>

## Theme
A `styled-components` theme can be found at `theme/theme.ts`. Inside are defined all the default / useful style variables such as `colors`, `fontSizes`, `lineHeights` and various other.

To add any style variables to the theme be sure to follow styled-system rules ([https://styled-system.com/theme-specification](https://styled-system.com/theme-specification)). 

The theme is injected in components through the `ThemeProvider`, no need to import the theme inside any components.

<br>

### Example
```
// theme.ts

const theme = {
  colors: {
    BLUE_BRIGHT: '#1eb8e7',
	  ...
  },
  fontSizes: ['12px', '16px', '18px', '24px', '40px'],
  lineHeights: ['16px', '24px', '30px', '32px', '48px'],
	...
});
```
<br>

```
// Root.tsx

import React from 'react';
import { ThemeProvider } from 'styled-components';

const Root = () => (
	<ThemeProvider theme={theme}>
		[...]
	</ThemeProvider>
)
```
<br>

```
// Component.tsx

import React from 'react';

/*
	This case will consume the color BLUE_BRIGHT and change the font size to 16px which is the at index 1 of the font-sizes theme's array
*/

const Component = () => (
	<div>
		<Header color='BLUE_BRIGHT' fontSize={1}>Component</Header>
	<div>
)
```
<br>

## Typography Styles
Various Typographies are pre-defined and available, they can be easily imported from `@components`
- Heading
- SubHeading
- Body
- InlineLink
- Link
<br>

The style of those components are defined in the `variant` object at `theme.ts`.

All of those components utilize a `as` prop to define the tag they will be rendered with. A pre-selected tag is set on them but you can change it by passing the wanted tag through this `as` prop.

### Styles
| Component Name | Usage | Default Tag | Variant Name|
| -------------- | ------- | ----------- | ------------ |
| **Heading** | For a page or panel heading | `h1` | `heading` |
| **SubHeading** | For a section heading | `h2` | `subHeading |
| **Body** | Default paragraph text | `p` | `body` |
| **InLineLink** | For a links in paragraphs | `a` | `inLineLink` |
| **Link** | For a isolated CTA | `a` | `link` |

### Example
```
import React from React;

import { Heading, Text } from '@components'

const Example = () => (
	<div>
		<Heading>A nice Heading</Heading>
		<Body>lorem ipsum sir dolot emmet</Body>
	<div>
)
```
<br>

## Variants
:bulb: Before adding a new variant or a new Component to the Typography system, please discuss it with Dev Team

To add a variant create a new object inside the `variant` constant defined in `theme.ts` .

<br>

### Creating a variant
```
// theme.ts
import { variant } from 'styled-system';

// Variables are added to the variant method provided by styled-system

export const variants = variant({
  myNewVariant: {
    fontSize: { _: 3, sm: 4 },
    lineHeight: { _: 2, sm: 4 }, // theme values contained in arrays can be accessed through their array's index
    fontWeight: { _: 900, sm: 'bold' }, // To create a responsive variant use an object with breakpoint keys, '_' will define the base value when screen size is under smallest defined breakpoint
    color: 'BLUE_DARK_SLATE' // Color keys from theme can be used
  }
});
```
### Using a variant
```
import React from 'react';
import { variants } from '@theme';

const SText = styled.p`
	${variants}
`

const Component = () => (
	<SText variant='myNewVariant'>
		I'm using my new variant
	</SText>
)
```
<br>

## Customizing Typographies
styled-system provides a quick and easy way to customise default style from our Typographies components. A variety of properties can be passed through component props such as :

| Name | Description | API Documentation |
| ---- | ----------- | ----------------- |
| **Space** | Spacing props such as margin, padding, ect. | https://styled-system.com/api#space |
| **Typography** | Text based properties such as font-size, font-weight, ect. | https://styled-system.com/api#typography |
| **Color** | Color properties | https://styled-system.com/api#color |
| **Size** | Width / Height properties | https://styled-system.com/api#layout|

All styled-system api props imported for the base typography component can be found at Typography/Text.tsx. 

### Example
```
import React from React;

import { Heading, Text } from '@components'

const Example = () => (
	<div>
		<Heading mb='20px' color='BLUE_BRIGHT'>A nice Heading</Heading>
		<Body>lorem ipsum sir dolot emmet</Body>
	<div>
)
```