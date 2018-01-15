# Release Process

1. Release Frequency 
Releases will be published every other Monday. Holidays and extenuating circumstances will result in delayed releases.
     - A staggered release schedule with a release candidate published live for 1 week before "full" release will be employed to allow relatively wide-scale testing 
         - Holidays / extenuating circumstances resulting in delayed beta releases will result in a similarly delayed production release to ensure that the beta release candidate is live for at least 1 week.
     - A Header/Banner with solicitation for feedback via GitHub and Email will be shown on the beta site to ensure users are aware on how to provide feedback.

2. Release Notes
    - At a minimum, summarized release notes via [dternyak/GitHub-Project-Management](https://github.com/dternyak/GitHub-Project-Management) will be released alongside new releases.

    - Particularly major releases can include a more technical write-up published to Medium to help with user engagement.

3. Release Validation / Release Approval
    - A QA Lead will be designated to validate releases before publishing to the beta channel. 
        - Release validation will include manual testing of user-facing functionality via workflow checklists, as well as static analysis on the the build. 
    - QA lead will be made a "code owner" on both the staging and production repo's as described in https://github.com/MyEtherWallet/MyEtherWallet/issues/499. 
    - QA Lead's approval will be required for merging "dist" patches to both staging and production.
    - An approval by at least one other non-maintainer will be required for merge. 

<br/>

## Production Site Build

To create the production site build that's meant to run behind a web server, run
```
npm run build
```
This folder can be hosted anywhere as-is. It must be run as the root of a site, so `xyz.com` or `subdomain.xyz.com`, NOT `xyz.com/mew`.

## HTML Build

### Building

To create the downloadable HTML version of the site, run
```
npm run build:downloadable
```

### Releasing

Zip up the folder created by this build, and that's it. It runs standalone.

## Electron

### Building

To create the Electron build(s), run
```
npm run build:electron
```
This will build Electron against all 3 platforms (OSX, Windows, Linux). Currently this process only works on OSX, as it can build Windows and Linux, but they cannot build OSX. Hopefully this gets moved to CI soon

### Releasing

A lot of files will be generated from the build, but you'll only want to upload the following files to the release:
  * MyEtherWallet-[version]-mac.zip (OSX)
  * MyEtherWallet-setup-[version].exe (Windows)
  * MyEtherWallet-setup-[version].blockmap (Windows)
  * MyEtherWallet-[version]-x86_64.AppImage (Linux)
  * latest-mac.yml (OSX)
  * latest-linux.yml (Linux)
  * latest.yml (Windows)