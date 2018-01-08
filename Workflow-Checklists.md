### NOTE: This checklist does not represent all known workflows. It is a WIP and additions are welcome.


* Generate Wallet
    - Keystore
        - Stage 1
            Password should be at least 9 characters
                Create New Wallet button is disabled when not valid
            Eye toggle shows/hides password
        - Stage 2
            Continue button is disabled until keystore is downloaded
        - Stage 3
            Private key is valid, does not contain 0x prefix
            Print paper wallet shows both address and private key in QR and string format
                Test scanning both address and private key QR code to ensure matches up with text private key
        - Stage 4
            Unlock takes you to send view
    - Mnemonic
        - Stage 1
            Regenerate shows new wordslist
        - Stage 2
            Eye toggle shows word, but still requires each of the 12 words to be typed in manually
        - Stage 3
            Unlock takes you to send view
        - Misc:
            12 word mnemonic should be compatible with MetaMask. 
            Attempt to import mnemonic into metamask and ensure compatability
* Send
    - Functionality Testing: https://github.com/MyEtherWallet/MyEtherWallet/issues/482
    - Promos
        - Ensure coinbase widget works
        - Ensure Bity referral works
        - Ensure Trezor/Ledger Promo links to knowledgebase
    - Tokens
        - Ensure resolution of https://github.com/MyEtherWallet/MyEtherWallet/issues/704 is used for token testing
* Swap
    - When ShapeShift unavailable, bity pairs continue to work
    - When Bity unavailable, shapeshift pairs continue to work
    - Send-lite
        - When origin balance is smaller than amount required for transfer, and origin kind is ether/token, show warning / prevent transfer.
* Mobile
    - https://www.reddit.com/r/ethtrader/comments/7h8eob/crosspost_nano_s_wallet_now_works_with/?st=JAQYKG8Q&sh=c2ef6289 should continue to work on V4.