### MyCrypto Overview:
The goal of MyCrypto is to act as a multi-account interface for the Ethereum blockchain. Almost all data in the app is fetched directly from an Ethereum node (we use [ethers.js](https://docs.ethers.io/v5/) to facilitate client-side load balancing and failover). In order to decrease infrastructure requirements, we have implemented some caching layers over certain data (primarily data that is time consuming to fetch from the node such as Decentralized Finance data and historical information). In instances where thousands of API calls would normally be required to fetch mass amounts of data from the node (such as when fetching erc20 token balances), we have opted to use a smart contract to aggregate read calls instead.

### General Outline & Tools:
The MyCrypto codebase is a React & Typescript front-end webapp and electron app. It utilizes Webpack and Babel for builds, Jest and Testcafe for unit, integration, and e2e tests, Storybook for UI/component development, and Styled Components for component styling syntax

To learn how to build development & production builds as well as required downloads, look at the [README](https://github.com/MyCryptoHQ/MyCrypto#mycrypto-beta-web-app) for most up-to-date information.

### Folder structure:
```
│
├── /jest_config
├── /webpack_config
├── /__tests__ - E2E tests
├── /.github - Github Actions Workflows CI/CD
├── /.storybook - Storybook config / build scripts
├── /.vscode - VSCode config/settings
├── /coverage - Test coverage reports
├── /electron-app - Electron-specific files (icons, electron window configs, etc)
├── /node-scripts - Standalone scripts
├── /shared - Types/scripts/configs shared between electron and web builds
├── /spec - Some tests (should be deprecated in favor of tests residing in the same folder as the code the test is covering)
├── /src - Majority of components/logic/routes/assets/static html - Accessible through absolute import with @
|   ├── /assets - Static visual assets
|   ├── /components - UI Components file
|   ├── /config - Static configs (links, absolute values, config objects, feature toggle, etc)
|   ├── /containers - UI Containers  (should probably be moved inside of @components)
|   ├── /database - Client-side DB hosted in user's session. Includes seed files, scripts for migrating between versions and tests
|   ├── /features - User-facing features (dashboard, send flow, add-account, buy-assets, etc). Most have their own routes as defined in @config
|   ├── /routing - Logic for routing (react-router). This includes protected routes and redirects
|   ├── /sass - .scss files/variables (this will probably be deprecated in the future in favor of styled-components and JS variables)
|   ├── /services - All services to fetch and provide data to the user including external APIs, user store providers, wallet logic, Ethereum node API wrappers, etc
|   ├── /theme - Static colors / font sizes / spacing sizes and other variables used to conform styling to specific styling standards.
|   ├── /translations - Contains the components and handlers necessary to conduct copy translations in the app
|   ├── /types - Types shared between multiple components/features/services
|   ├── /utils - Utility functions used to transform objects, conduct cryptographic operations and validation, etc
|   ├── /vendor - Vendor integrations & shared hooks (these may be moved)
|   ├── /workers - Service workers
├── /static - Static build files
└── /dist - Output build files

```