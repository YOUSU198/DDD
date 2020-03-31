## What are feature flags?

Feature flagging is a technique that can be used to turn features on/off. Thats it. Specifically for our use-case, feature flags are used to allow us to develop and commit WIP features to `master` so that we can easily have multiple people collaborate on the features at the same time, while not needing many branches-of-branches-of-branches. For our purposes, our feature flag panel is [here](https://github.com/MyCryptoHQ/MyCrypto/blob/master/common/v2/config/isActiveFeature.ts#L29-L49). You can see most of the features are toggled to `true`. This means that those features are currently active. There are also `IS_DEV` features which are available only in development builds (`yarn dev`). These features will NOT show up in mycryptobuilds.com because mycryptobuilds is meant to publish a staged-production build.

## How are feature flags used?

Once you've made the feature flag, you can use the flag's boolean state in order to do a few things:

- Attach the feature's route status to the feature flag: https://github.com/MyCryptoHQ/MyCrypto/blob/master/common/v2/routing/routes.tsx#L243 which also will display/hide the route in the header dropdowns.

- Attach the feature's CTAs on the Dashboard to the status of the feature flag: https://github.com/MyCryptoHQ/MyCrypto/blob/master/common/v2/features/Dashboard/Dashboard.tsx#L51-L55

- Hide/display sections of components using [component props](https://github.com/MyCryptoHQ/MyCrypto/blob/master/common/v2/features/Settings/Settings.tsx#L54).
This means that effectively, you can "hide" a feature. Since you can "hide" a feature, you can publish code for new features without necessarily making it live in production.

## How do I enable/disable/add/remove a feature flag?

All current feature flags are located in [common/v2/config/isActiveFeature.ts](https://github.com/MyCryptoHQ/MyCrypto/blob/master/common/v2/config/isActiveFeature.ts).