When contributing new code to the codebase, please follow the following code style guide for consistency and continued ease-of-maintenance! Thank you for your help! :rocket: 

# Table of Contents
1. [Imports](#imports)
1. [ToDos](#todos)
1. [New libraries](#libraries)

## Imports
Keep to the ordered format for imports as follows:
1) External module imports
2) Absolute imports (Use the `@` operator to reference things in the `/src` directory)
3) Relative imports

ex:
```js
import React from 'react';
import { Heading } from '@mycrypto/ui';

import { AccountContext, StoreContext } from '@services/Store';

import { actions } from './constants';
import './Dashboard.scss';
```

## Libraries

Please avoid adding new libraries. If you do add one, please note it in your PR and a short description of what it is used for so that the person reviewing has a simple time understanding what it is/what it is used for.

## ToDos

If you add a ToDo somewhere in the code, please use the format `@todo: <explanation>` so it's easily-searchable in the future.