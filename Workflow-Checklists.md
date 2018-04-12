### NOTE: This checklist does not represent all known workflows. It is a WIP and additions are welcome.

* **View & Send Tab**

    - Access wallet
        - Step 1
            - Verify that each **Access Wallet** button transitions to the next step correctly.
        - Step 2
            - Access account through each access method.
        - Step 3
            - Verify that the Advanced settings opens correctly.
        - Step 4
            - Ensure that **Scan for Tokens** button functions correctly. If it fails, test the **Retry** button.
        - Step 5
            - Verify that the calculated wallet values below the token scanner are reasonable.
        - Step 6
            - Create a new transaction to yourself using one of the non-hardware wallet access methods and click the **Send Transaction** button
        - Step 7
            - Create a new tab in your browser and navigate to: https://beta.mycrypto.com/sign-and-verify-message/sign.
            - Grab the text from the *Raw Data* text field from the transaction and verify that it is correct by signing it using the **Sign & Verify Message** tab.
        - Step 8
            - Broadcast the signed message from Step 7 using the **Broadcast Transaction** tab.
        - Step 9
            - Copy the transaction ID, and look up the status using the **Tx Status** tab

    - Further Testing:
        - Functionality Testing: https://github.com/MyCryptohq/MyCrypto/issues/482
            - Promos
                - Ensure that Coinbase widget works.
                - Ensure that Shapeshift widget works.
                - Ensure that Trezor/Ledger Promo links to knowledgebase
            - Tokens
                - Ensure resolution of https://github.com/MyCryptohq/MyCrypto/issues/704 is used for token testing


* **Create New Wallet Tab**

    - Keystore
        - Stage 1
            - Password should be at least 9 characters
            - **Create New Wallet** button is disabled when not valid
            - Eye toggle shows/hides password
        - Stage 2
            - Verify that **Continue** button is disabled until keystore is downloaded
        - Stage 3
            - Verify that the private key is valid, and it does not contain 0x prefix
            - Print paper wallet shows both address and private key in QR and string format
            - Test scanning both address and private key QR code to ensure matches up with text private key.
        - Stage 4
            - Verify that **Unlock** button takes you to send view.
    - Mnemonic
        - Stage 1
            - Verify that **Regenerate** button shows new wordlist.
        - Stage 2
            - Eye toggle shows word, but still requires each of the 12 words to be typed in manually.
        - Stage 3
            - Verify that **Unlock** button takes you to send view.
        - Misc:
            - 12 word mnemonic should be compatible with MetaMask.
            - Attempt to import mnemonic into MetaMask and ensure compatibility.


* **Swap Tab**

    - Check that the Shapeshift-offered swap options are displaying correctly with their icons.
    - When origin balance is smaller than amount required for transfer, and origin kind is ether/token, show warning / prevent transfer.
        - Verify that selecting your swap and the *Let's Do This!* button leads you to the next step. Complete the entire swap process to verify correct functionality.


* **Contracts Tab** *(Optional during patch version upgrades such as 1.1.0 -> 1.1.1)*

    - Interact with a Contract
        - Ex: Attempt to change a resolved public address for an ENS address.
    - Deploy a Contract
        - Attempt to deploy test contract (still needs to be created, will edit with gist link when this is ready).


* **ENS Tab**

    - Type in a valid ENS name and verify that the ENS lookup functions correctly.
    - Type in an invalid ENS (too short or containing special characters) and verify that it displays the correct error message.
        - Begin the process for ENS registration, and verify that the process isn't broken. *(Optional during patch version upgrades such as 1.1.0 -> 1.1.1)*


* **Miscellaneous**

    - Check that the Disclaimer Modal opens correctly in the pre-footer when clicked on.
    - Verify that the Help tab takes you to the correct Knowledge-base.
    - Verify Footer links aren't dead and lead to the correct locations.


* **Mobile**

    - https://www.reddit.com/r/ethtrader/comments/7h8eob/crosspost_nano_s_wallet_now_works_with/?st=JAQYKG8Q&sh=c2ef6289 should continue to work on V4.
