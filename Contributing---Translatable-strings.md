# Translatable strings

Warning: the purpose of this guide is to teach developers how to make sure new features are translatable. For translating an existing feature, please see [this guide](https://github.com/MyCryptoHQ/MyCrypto/wiki/Contributing-%E2%80%90-Providing-Translations).

## How to add a new translatable string

### Step 1: Thinking of an identifier

Every translatable string is identified by a simple name, formatted all uppercase in snake_case. For example, a good identifier for the following text: 
`"Lorem ipsum dolor sit amet"` would simply be `LOREM_IPSUM`. 

### Step 2: Adding your string to the default language file

The English language file, located in [common/v2/translations/lang/en.json](https://github.com/MyCryptoHQ/MyCrypto/blob/master/common/v2/translations/lang/en.json) contains a JSON-formatted list of every translatable string. In your PR, add your identifier + string to the language file, in the following format: 
```
{
  "code": "en",
  "data": {
    "LOREM_IPSUM": "Lorem ipsum dolor sit amet"
  }
}
```

Please make sure to check if your string has already been added to the language file!

### Step 3: Implementing your translatable string

In order to implement your newly-created translatable string into any React component, either import the `translate` function or the `translateRaw` function from `v2/translations`. While the `translate` function supports markdown in your string, the `translateRaw` function does not. If you do not need markdown formatting in your string, please use `translateRaw`.

Example use of the `translateRaw` function:
```jsx
import React, { FunctionComponent } from 'react';

import { translateRaw } from 'v2/translations';

const Example: FunctionComponent = () => (
    <p>{translateRaw('LOREM_IPSUM')}</p>
);

export default Example;
```

Example use of the `translate` function:

```jsx
import React, { FunctionComponent } from 'react';

import translate from 'v2/translations';

const Example: FunctionComponent = () => (
    <p>{translate('LOREM_IPSUM')}</p>
);

export default Example;
```


## What you should **not** do


You should **not** directly provide strings in your React components. 
```jsx
import React, { FunctionComponent } from 'react';

const Example: FunctionComponent = () => (
    <p>Lorem ipsum dolor sit amet</p>
);

export default Example;
```

## What you **should** do
In [CreateWallet.tsx](https://github.com/MyCryptoHQ/MyCrypto/blob/master/common/v2/features/CreateWallet/CreateWallet.tsx#L70), instead of providing a direct string, the `translateRaw` function is called in order to retrieve the `CREATE_ACCOUNT_TITLE` string:
```jsx
<ExtendedContentPanel
    onBack={() => history.push(ROUTE_PATHS.ROOT.path)}
    heading={translateRaw('CREATE_ACCOUNT_TITLE')}
>
```

This identifier is found in the [en.json](https://github.com/MyCryptoHQ/MyCrypto/blob/master/common/v2/translations/lang/en.json#L422) file:


```json
"CREATE_ACCOUNT_TITLE": "Create New Account",
```

In order to provide translations for other languages, please see [this guide](https://github.com/MyCryptoHQ/MyCrypto/wiki/Contributing-%E2%80%90-Providing-Translations).