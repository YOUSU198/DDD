### NOTE: This checklist does not represent all known workflows. It is a WIP and additions are welcome.


# View & Send Tab

## MetaMask
1. Verify that it says “Connect & sign via your browser or extension”
    * Mousing over the MetaMask box should make it “pop” and change MetaMask title color to blue
    * Check that mousing over the bottom right corner symbols show pop up text
        * Shield: “This wallet type is secure”
        * Question Mark: “More info”
            * Check that the Question Mark links to the correct page: https://support.mycrypto.com/migration/moving-from-private-key-to-metamask
2. Verify that clicking MetaMask will transition to the correct page
3. Verify that the “Download MetaMask” button works (https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn?hl=en)
4.  Verify that you can go back to homepage with “Change Wallet” link in left corner
5. Verify that the “Connect to MetaMask” button works 
    * Ensure that the wallet unlocks correctly


## Once wallet is unlocked with MetaMask: 
1. Check under “Account Address” that the address matches with the address shown in MetaMask 
    - Check that “copy address” copies address to clipboard
    - Ensure that Account Balance is correct - check on Etherscan.io
    - Ensure that the refresh balance button works
    - Check that the “Transaction history” links work
        - Tokens can be accessed by Etherscan and Etherchain
    - Check the Widget 
        - Ensure that it transitions to all 3 ads
            - On its own and on a timer 
            - Ensure that all the ads open up in a new window
        1. Ad: Trezor/ledger: https://support.mycrypto.com/getting-started/protecting-yourself-and-your-funds.html 
        2. Ad: Coinbase: https://buy.coinbase.com/?code=60c05061-3a76-57be-b1cd-a7afa97bcb8c&address=0x9A2617927f187B4D631DBe29B04062b0F7bb24af&crypto_currency=ETH&currency=USD 
        3. Shapeshift: https://beta.mycrypto.com/swap
2. Check Token Balances:
    - Ensure that “Scan For Tokens” button works
        - Verify that you can check and uncheck tokens that you wish to keep track of
        - Check that the “Save” button works and actually saves the tokens you checked
3. Verify that the “Add Custom Token” works
    - Ensure that it expands current box with 3 input boxes for information 
        1. Token Symbol
            - Ensure that it accepts a combination of numbers and letters
                - Check that when you enter a valid Token Symbol that the box highlights to green
                - Check that when you enter an already existing token that you are given the error "A token with this symbol already exists"
        2. Address
            - Ensure that it only accepts a valid Address/Contract address
                - Red box highlight if address is invalid
                - Green box highlight if address is valid
        3. Decimals
            - Ensure that it only accepts numbers
            - Red box highlight if letters are entered
            - Green box highlight if address if its only numbers
            - Verify that any other weird value is shown as invalid
    - Check that the “Cancel” button indeed cancels the process of adding a new Token and closes the expanded box
    - Check that the link for “Need help?” works: https://support.mycrypto.com/tokens/adding-new-token-and-sending-custom-tokens.html
    - Verify that adding a token with all correct information works 
        - Correct token appears with correct balance
        - Verify you can’t add 2 of the same tokens
    - Check that you can indeed delete the custom token from the interface
        - Check that you can re-add the token

## Send Ether & Tokens Tab
1. Verify that you can enter an address into the “To Address” field
    - Ensure that only a valid ETH address is accepted 
    - Invalid addresses - the box is outlined in red
    - Valid addresses - the box is outlined green
    - Ensure that the To Address Icon is also correct and matches with the address receiving
2. Verify that you can only type in positive integers into the “Amount” field
3. Verify that you can toggle from ETH to tokens
    - Verify that toggling from different coins refreshes the “Amount” field
4. For sending Ether
    - Ensure that the “send all button” (shown as 2 upward arrows) actually inputs complete ETH account balance
    - Ensure that you can send whole numbers and fractions of ETH
    - Ensure that typing in a number that is more than ETH in the wallet is not allowed
    - Ensure that adding past 18 decimals is not allowed
    - Make sure nothing else weird is allowed to be inputted
5. For sending a Token
    - Ensure that the “send all button” (shown as 2 upward arrows) actually inputs complete Token account balance
    - Ensure that you can send whole numbers and fractions of Tokens 
        - Check that tokens with different decimals follow their own rules (some tokens don’t allow fractions to be sent)
        - Ensure that the decimal places follow the Token’s correct decimal places
    - Ensure that typing in a number that is more than the Token balance in the wallet is not allowed
    - Make sure nothing else weird is allowed to be inputted
6. Verify that the “Transaction Fee” toggle updates as you slide up and down
    - Verify that the ETH equivalent price in USD updates as you toggle up and down the scale
7. Verify that “ + Advanced” opens up new section to sending a transaction
8. Verify that “ - Simple” closes up the advanced section 
    - Ensure that opening up advanced or closing advanced options does not refresh the values in “To Address”/”Amount”/Coin 
9. Verify that when changing either Gas Price or Gas limit the final price of the fee in equivalent USD is recalculated at the bottom in the grey box
10. Ensure that you can select and deselect “Automatically Calculate Gas Limit” 
    - Verify that when deselecting it, it also gets rid of the light grey highlight of the “Gas Limit” box
    - Ensure that after the highlight is gone, that you can manually type in your own values
    - Verify that re-selecting it will automatically recalculate appropriate Gas limit
        - Ensure that the Gas Limit does not recalculate to something whack
        - Verify that the grey highlight re-appears when you re-select it
    - Verify that you can’t manually type in own values on top of the automatically calculated value
11. Ensure that you can type into the “Gas Price” box
    - Ensure that you can’t spend more gas than your wallet has
    - Ensure that you can’t input weird values into the box
12. Check that the question mark beside “Nonce” pops up text “More info”
    - Ensure that it links to the correct support article: https://support.mycrypto.com/transactions/what-is-nonce.html
    - Ensure that the refresh button for Nonce works
    - Ensure that you can’t put in weird values into the boxit using the **Sign & Verify Message** tab.
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
