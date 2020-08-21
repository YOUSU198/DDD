A collection of conventions we follow when coding for core

When contributing new code to the codebase, please follow the following code style guide for consistency and continued ease-of-maintenance! Thank you for your help! :rocket:

# Table of Contents

1. [Imports](#imports)
1. [ToDos](#todos)
1. [New libraries](#libraries)
1. [Code](#code)
1. [Use aliases](#use-aliases-absolute-imports)
1. [File Structure](#file-structure)
1. [Linting](#linting)
1. [Typescript](#typescript)
1. [Styles](#styles)
1. [Naming](#naming)
1. [Testing](#testing)
1. [Dependencies](#dependencies)
1. [Version Control](#version-control)

## Imports

Keep to the ordered format for imports as follows:

1. External module imports
2. Absolute imports (Use the `@` alias to reference things in the `/src` directory)
3. Relative imports

ex:

```js
import React from "react";
import { Heading } from "@mycrypto/ui";

import { AccountContext, StoreContext } from "@services/Store";

import { actions } from "./constants";
import "./Dashboard.scss";
```

## ToDos

If you add a ToDo somewhere in the code, please use the format `@todo: <explanation>` so it's easily-searchable in the future.

## Code

**1. Prefer pure functions**

**2. Isolate side effects**

**3. Use conditional spread to extend object properties**
It's simple and elegant.

```tsx
/* Don't */
const tx = {
  gasLimit: tx.gasLimit.toString()
}
if (isTrue) {
  tx.anotherKey = 'value'
}
return tx;

/* Do */
return {
  gasLimit: tx.gasLimit.toString(),
  ...(isTrue && { key: <value> })
}
```

**4. Avoid nested conditionnels**

## File structure

Review [Codebase Outline](https://github.com/MyCryptoHQ/MyCrypto/wiki/Codebase-Outline)
We group .stories and .test with the target component.

To facilitate file switching when working on a component

```
/components
  | Account.tsx
  | Account.story.tsx
  | Account.test.tsx
```

## Linting

We use ESlint, Tslint, Prettier.
Activate the rules in your IDE for auto-correction.

## Typescript

We use TS and attempt to stay up to date with the latest version.

**1. Place shared typings in `@types`**

Whenever a type is shared place it in the `@types` directory. It will allow us to determine which types to place as globals.

**2. Favour type composition over redefinition**

It emphasises the relation between the types. Read `utility-types` to discover the helpers.

```
/* Don't */
interface Asset {
  uuid: TUuid;
  name: string;
  symbol: TSymbol;
  decimal: number;
}

interface ISwapAsset {
  uuid: TUuid;
  name: string;
  symbol: TSymbol;
}
```

```
/* Do */
interface Asset {
  uuid: TUuid;
  name: string;
  symbol: TSymbol;
  decimal: number;
}

type ISwapAsset = Omit<Asset, 'decimal'>
```

**3. Use `Brand<>` types for strings**

It allows type safety for strings that we can’t enumerate like `uuid`, `address`, `symbol` etc.

```
/* Don't */
interface Account {
  address: string;
}
```

```
/* Do */
import { Brand } from 'utility-types';
type TAddress = Brand<string, 'address'>
interface Account {
  address: TAddress;
}
```

**4. Use `React.ComponentProps<>` to access a components props So we can reduce the amount of imports**

```
/* Don't */
// Selector.tsx
export interface SelectorProps {...}
export const Selector = (): SelectorProps => {...}

// AssetSelector.tsx
import { Selector, SelectorProps } from '@components'
const AssetSelector = (props: SelectorProps & OwnProps) => (...)
```

```
/* Do */
// Selector.tsx
interface Props {...}
export const Selector = (): Props => {...}

// AssetSelector.tsx
import { Selector } from '@components'
const AssetSelector = (props: Pick<React.ComponentProps<Selector>, 'whatever' | 'you' | 'need'>) => (...)
```

**5. Use `unknown` over `any` (since TS 3.0).**

`unknown` is safer than `any` since it reminds us that we need to perform some sorts of type-checks before operating on our values.
[https://devblogs.microsoft.com/typescript/announcing-typescript-4-0/#unknown-on-catch](https://devblogs.microsoft.com/typescript/announcing-typescript-4-0/#unknown-on-catch)

**6. Use 4.0.0 assignment operators**
`&&=, ||=` and `??=`

**7. Use discriminate unions**
https://basarat.gitbook.io/typescript/type-system/discriminated-unions

## Styles

Currently there is a mix between `.css`, `.scss`, and `style` components.

Use theme over importing constants.

It helps reduce imports and anticipates theme switching.

```
const Wrapper = styled.div`
  color: ${({ theme }) => theme.brand }
`;
```

Use nested SC To reduce the number of intermediate components in JSX

Use `&&` for adding conditional styles

```
const SContainer = styled('div')`
  display: inline-flex;
  ${(p) => p.fontSize && `font-size: ${p.fontSize}`}
`;
```

## Naming

1. **Rule**: Prefix exported types

**Rationale**: Facilitate maintenance by making them searchable.

**Example**:

```
// Don't
interface SwapAssets {}
```

```
// Do
interface TSwapAssets {}
```

2. **Rule**: Prefix SC components with S

**Rationale**: When parsing JSX it's useful to know what is an SC

**Example**:

```
// Don't
const StyledWrapper = styled.div``
const Price = styled(Currency)``
```

```
// Do
const SWrapper = styled.div``
const SPrice = styled(Currency)``
```

## Testing

- For unit and functional tests we use `jest, jsDom, react-testing-library`.
- For E2E tests we use Testcafe and Ganache.

1. Use `Jest` watch mode when you code.
2. Test a page redirect with `history.push` see `MigrateLS`. eg. How to spy on a dependency called within an effect.
3. Test input. eg. `AssetSelector`
4. Test absence of element in DOM. eg. `Downloader`

### Ressources

- Intro to rtl https://kentcdodds.com/blog/introducing-the-react-testing-library/
- Write fewer longer tests. https://kentcdodds.com/blog/write-fewer-longer-tests
- Understand `act`. https://kentcdodds.com/blog/fix-the-not-wrapped-in-act-warning
- Avoid common mistakes when writing tests. https://kentcdodds.com/blog/common-mistakes-with-react-testing-library#not-using-screen

## Libraries and project dependencies

Please avoid adding new libraries. If you do add one, please note it in your PR and a short description of what it is used for so that the person reviewing has a simple time understanding what it is/what it is used for.

- bundle bloat: can the library tree-shake?
- duplication: is there a dep with similar functionnality wihtin the project?
- security: is the dep recent and has a sufficient amount of contributors to not become a supply-chain attack vector?

With that in mind:

1. Use react libraries that offer hooks. It simpler to use then overriding default styles
2. Use `ramda` over `lodash` _(Import the method rather then the default [to decrease bundle size])_
3. Use `datefns` over `moment`

## Version control

- PR reviews
- Atomic commits: https://dev.to/cbillowes/why-i-create-atomic-commits-in-git-kfi

## Releases

e.g. [Release Process](https://www.notion.so/Releases-38e5c6ee3b26409cbb14d0c479ea1371)

# Glossary

A List of common abbreviations used in the codebase and in our communication

- Tx | TX | tx: transaction
- MM: Metamask
- GHA: Github Actions
- Web3: corresponds to all web3 compatible wallets ie. Trust, MM.
