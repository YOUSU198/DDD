# Release Process

1. Release Frequency

Releases are tagged every two weeks, typically on a Thursday though occasionally on a Friday. Holidays and extenuating circumstances will result in delayed releases.
                 
2. Release Notes
    - At a minimum, summarized release notes via [dternyak/GitHub-Project-Management](https://github.com/dternyak/GitHub-Project-Management) will be released alongside new releases.

    - Particularly major releases can include a more technical write-up published to Medium to help with user engagement.

3. Release Validation / Release Approval
    - A QA Lead will be designated to validate releases before publishing to the beta channel. 
        - Release validation will include manual testing of user-facing functionality via workflow checklists, as well as static analysis on the the build. 
    - QA lead will be made a "code owner" on both the staging and production repo's as described in https://github.com/MyCryptoHQ/MyCrypto/issues/499. 
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

HTML builds must be publicly verified by two non-infrastructure-controlling team members via Drawbridge. 

Drawbridge is a tool that checks the hashes of the proposed release against build on independent members computers. The release can only go live once two people verify the hashes match.

## Electron

### Building

To create the Electron build(s), run
```
npm run build:electron
```

This will build Electron against all 3 platforms (OSX, Windows, Linux). Currently this process only works on OSX, as it can build Windows and Linux, but they cannot build OSX. Hopefully this gets moved to CI soon

### Releasing

The official Electron builds for release must be built, signed via airgapped machine, and uploaded to via Github releases along with a checksum and signed checksum file. 

- checksums.txt
- checksums.txt.gpg
- linux-i386_[version]_MyCrypto.AppImage
- linux-x86-64_[version]_MyCrypto.AppImage
- mac_[version]_MyCrypto.dmg
- standalone_[version]_MyCrypto.zip
- windows_[version]_MyCrypto.exe
