This page encompasses some of the useful tips and tricks we discover along the way that help with debugging.

## Useful Extensions

If you're planning on debugging anything in the app, you'll have a much easier time with the [React DevTools](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en) and [Redux DevTools](https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd?hl=en) Chrome extensions. The former shows minified components, and the latter isn't enabled in production.

## Electron Production Logging

If an issue is only reproducible in the production build of the Electron app, simply run it from the command line with the logging flag enabled. For example:

```
./dist/electron-builds/mac/MyCrypto.app/Contents/MacOS/MyCrypto --enable-logging
```

It may differ from OS to OS.

## TREZOR Electron Integration

If something's not working and you're not sure what, be sure to flip on `debug: true` in `shared/enclave/server/wallets/trezor.ts` with the Trezor.js library. It'll spit out much more information.