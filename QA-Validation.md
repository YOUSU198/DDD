## QA Validation

1. Once the a sprint is considered finished and `develop` has been merged into `master`, the maintainer will provide a mycryptobuilds.com link that includes the git commit hash that serves a mirror of the production candidate. Alternatively, the production candidate will be served on beta.mycrypto.com and testing can begin there.
2. QA will begin running regression tests (all existing workflow checklist items).
3. QA will will be given [list of PRs](https://github.com/MyCryptoHQ/MyCrypto/pull/1885) to form additional workflow checklist items. Most PRs will be self-explanatory or have detailed testing instructions, but if not, QA will communicate with development to learn how to reproduce the issue/build up state to test the new functionality adding in the latest release.
4. QA will create issues as needed while validating, provide daily updates with the status of validation, and finally give a go/no-go on the health of the build once testing is finished.
    - what PRs were tested
    - what workflows were added
    - if show-stopped issues were discovered during validation
    - estimations on remaining time needed before validation is complete

On-Going Tasks:
1. Isolate "happy-path" workflow checklist items to their own sections, so that smoke-tests can be performed more easily.

