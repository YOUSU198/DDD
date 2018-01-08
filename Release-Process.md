## Release Process

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


  
  
  