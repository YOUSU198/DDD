#### NOTE: This checklist does not represent all known workflows. It is a WIP and additions are welcome.

## View & Send Tab:
* [MetaMask](#meta-mask)
* [Ledger](#ledger)
* [Trezor](#trezor)
* [Parity Signer](#parity-signer)
* [MetaMask](#meta-mask)
* [Private Key](#private-key)
* [Keystore File](#keystore-file)


## Create New Wallet Tab
* [Create a New Keystore Wallet](#create-a-new-wallet-via-keystore-file)




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


## Once wallet is unlocked With MetaMask: 
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

## Send Ether & Tokens Tab: Wallet Unlocked with MetaMask
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
    - Ensure that you can’t put in weird values into the box
13. Ensure that the "Data" field only accepts hexidecimal values
    - Invalid values are highlighted as red
    - Valid values are highlighted in green
14. Ensure that the "Send Transaction" button works
    - When you click transaction:
        - Ensure that a new window pops up with the correct information regarding the transaction
            - The From address is the same as the logged in wallet
            - The To address is the same address as inputted
            - "You'll Send" will show the value that you inputted in ETH and in USD format
            - Transaction fee" will show the value of the fee that you chose in ETH and USD format
            - It will show the Total of ETH require for the transaction 
                - "You'll send" + "Transaction Fee"
            - Ensure that the "Details" button works
                - Expands the current pop up transaction verification window
                - Ensure that the correct Network is shown
                    - WEB3_ETH network - provided by MetaMask / Mist
                - Ensure that "Raw Transaction" shows all the correct information
                    - Value
                    - Data
                    - To
                    - Nonce
                    - gasPrice
                    - gasLimit
                    -chainId
                - Ensure that is shows you "Signed Transaction"
        - Ensure that the "Cancel" button closes the curent transaction pop up window
            - It returns you back to your logged in wallet with all the information you entered for the transaction still there
        - Ensure the "Send" Button works
            - Ensure that the MyCrypto transaction popup window now shows that it is loading(waiting for MetaMask confirmation)
            - Ensure that a MetaMask pop up windows shows up for Transaction Confirmation
                - Ensure that all the information in the MetaMask confirmation box shows the same values that you inputted previously
                - Ensure that the "Reset" button resets information of the transaction 
                - Ensure that the "Submit" button processes the transaction
                    - The MetaMask popup closes 
                    - The MyCrypto loading transaction window closes
                    - Ensure that a green bar with a thumbs up pops up from the bottom of the screen
                        - Shows "Your TX has been broadcast to the network. It is waiting to be mined & confirmed. During ICOs, it may take 3+ hours to confirm. Use the Verify & Check buttons below to see."
                        - Shows you the correct TxHash of your transaction
                        - Shows you links of your Txhash to:
                            1. Etherscan
                            2. Etherchain
                            3. MyCrypto's TX Status
                        - Check that you can close the green bar with the "X" in the right bottom corner
                - Ensure the "Reject" button cancels the transaction 
                    - It should close the Metamask pop up
                    - It should close the MyCrypto Transaction pop up
                    - This error message is shown at the bottom of the screen in red - 
                         - Error: Request timed out for web3

### Request Payment Tab - MetaMask

1. Ensure that the "To Address" is the same Address as the logged in wallet
    - Ensure that the Icon matches too
2. Ensure that you can input a value into the "Amount" field
    - Any number above 0 
3. Ensure that you can select what Coin to request
    - Ensure that you can select Ether
    - Ensure that you can select a token 
        - Check that you can type in a token symbol and have it shown in the dropdown menu (autocomplete)
        - Ensure that the gas limit updates
        - Ensure that the gas limit gets included in the payment qr request and code

### Wallet Info Tab 
1. Verify that the address shown in "Your Address" is the same as the current logged in wallet
2. Verify that the address Icon is the same as the current logged in wallet
3. Verify with your phone that the QR code shows the same address as the current logged in wallet.

### Recent Transactions Tab
1. Verify that there there are 3 coloumns that consist of: 
    - To Address
    - Amount
    - SENT
2. Ensure that you can click on a transaction and takes to the to correct page showing all of the correct transaction details
    - Ensure that you can click on:
        - TX Hash
        - Block Number
        - From Address
        - To Address
    - Ensure that they all link you to the correct page on Etherscan and open up in a new window
3. Ensure that you can click "Back to Recent Transactions" and it will take you back to the list of all transactions
3. Ensure that the text at the bottom of the list says: "Only recent transactions sent from this address via MyCrypto on the ETH network are listed here. If you don't see your transaction, you can view all of them on Etherscan." 
    - Ensure that the link to Etherscan takes you to the current logged in wallet transaction history page
---

## Ledger
1. Verify that it says “Connect & sign via your hardware wallet”
    - Mousing over the Ledger box should make it “pop” and change Ledger title color to blue
    - Check that mousing over the bottom right corner symbols show pop up text
        - Shield: “This wallet type is secure”
        - Question Mark: “More info”
            - Check that the Question Mark links to the correct page: https://support.ledgerwallet.com/hc/en-us/articles/115005200009 
2. Verify that clicking Ledger will transition to the correct page
    - Verify that the “Don’t Have a Ledger? Order one Now!” button works (https://www.ledgerwallet.com/r/1985?path=/products/ )
    - Verify that the link at the bottom works“How to use MyCrypto with your Nano S” (https://support.ledgerwallet.com/hc/en-us/articles/115005200009 )
3. Verify that you can go back to homepage with “Change Wallet” link in left corner
4. Verify that the “Connect to Ledger Wallet” button works
    - Once clicked, button shows loading icon and “Unlocking”
5. Ensure that after Ledger is unlocked that the window which allows you to pick a wallet to open appears
    - Verify that you can Toggle “More” and “Back” to access various addresses available on your Ledger
    - Verify that you can Select a Node in the drop down menu ‘
    - Verify that you can pick a token in the drop down
    - Verify that the link under “More” works
    - Verify that you can only select one address at a time
    - Ensure that once an address is selected, that the unlock button becomes available, and not before an address is chosen
6. Ensure that after the wallet is chosen and unlocked, it transitions to the correct page and displays all the correct information

---

## Trezor
1. Verify that it says “Connect & sign via your hardware wallet”
    - Mousing over the Trezor box should make it “pop” and change Trezor title color to blue
    - Check that mousing over the bottom right corner symbols show pop up text
        -  Shield: “This wallet type is secure”
        - Question Mark: “More info”
            - Check that the Question Mark links to the correct page: https://support.mycrypto.com/accessing-your-wallet/how-to-use-your-trezor-with-mycrypto.html 
2. Verify that clicking Trezor will transition to the correct page
3. Verify that you can go back to homepage with “Change Wallet” link in left corner
4. Verify that the “Don’t have a TREZOR? Order one now” button works https://shop.trezor.io/?a=mycrypto.com
5. Verify that the “Connect to TREZOR” button works 
    - Once clicked, a window pops up asking to Export public key for Ether Account	
    - Ensure that the cancel button cancels request and closes the window
    - Clicking export will take you to the next step which is entering the pin
    - Entering the pin correctly closes the window and opens up a new window which asks for you to “Select an Address” 
    - Ensure that you can only select one address at a time
    - Ensure that you can change the Network in the drop down menu
    - Ensure that you can select a token in the drop down menu (Is this really useful though, what if I want to view multiple tokens, and besides opening the wallet with MyCrypto will show my tokens anyway. This is kind of redundant). 
    - Ensure that the links under “More” work
6. Ensure that after the wallet is chosen and unlocked, it transitions to the correct page and displays all the correct information

---
## Parity Signer
1. Verify that it says “Connect & sign via your Parity Signer mobile app”
    - Mousing over the Parity Signer box should make it “pop” and change Parity Signer title color to blue
    - Check that mousing over the bottom right corner symbols show pop up text
        -  Shield: “This wallet type is secure”
        - Question Mark: “More info”
            - Check that the Question Mark links to the correct page: https://wiki.parity.io/Parity-Signer-Mobile-App-MyCrypto-tutorial
2. Verify that clicking Parity Signer will transition to the correct page
3. Check that once it transitions, and you have accepted MyCrypto to use the webcam that it works
    - The window for the camera is shown with a red box outline that is smaller than the whole webcamera frame
4. Verify that you can go back to homepage with “Change Wallet” link in left corner
5. Verify that the “For more information” button works https://wiki.parity.io/Parity-Signer-Mobile-App-MyCrypto-tutorial
6. Verify that the links for downloading the app work (on phone): 
    - iOS - https://itunes.apple.com/us/app/parity-signer/id1218174838
    - Android - https://play.google.com/store/apps/details?id=com.nativesigner
7. Verify that you can download the app onto your phone correctly
    a. Check that the app opens correctly on your phone
    b. Verify that you can select the "Accounts" option in the bottom right corner of the app
    c. Check that you can "Create Account"
	1. Check that it takes you to the next screen to pick a wallet Icon
		- Check that you can select "More" for more wallet icon choices
	2. Verify that once you select the wallet Icon that you want, that it takes you to the "New Account" page
		- Check that you can enter an Account Name
	3. Check that your Recovery Phrase of 11 words is given
	4. Check that it also displays your public addres
	5. Verify that the button "Set Up Pin" takes you to the next correct page
		- Check that you can enter a pin and that it asks you to enter it twice
	6. Ensure that the new wallet creates correctly
8. Verify that you can select "Transaction QR" in app, on the bottom left corner
9. Verify that when the QR code of the wallet on your phone's app is shown to your computer's webcam, that the wallet unlocks properly 
    - Check that the wallet Icon and addresses match 
---

## Private Key
1. Verify that the box displays an example of a private Key
2. Mousing over the Private Key box should make it “pop” and change Private Key title color to blue
3. Check that mousing over the bottom right corner symbols show pop up text
    - Shield: “This wallet type is insecure”
    - Question Mark: “More info”
        = Check that the Question Mark links to the correct page: https://support.mycrypto.com/private-keys-passwords/difference-beween-private-key-and-keystore-file.html 
3. Verify that clicking Private Key will transition to the correct page
4. Verify that you can go back to homepage with “Change Wallet” link in left corner
    - Verify that there aren’t any typos in the warning
    - Check that all the links are working and correct
    - Check that you can only press “Continue” when all 3 check boxes are marked
5. Check that the “Change Wallet” option works in the top left corner
6. Verify that pressing “Continue” goes to the correct page to enter Private key
7. Verify that the link to “run MyCrypto Locally” works: https://download.mycrypto.com/ 
8. Check to see if an invalid Private key error is handled
    - Ensure that once a valid Private key is entered, the unlock button becomes available
9. Verify that the “Unlock” button works correctly and unlocks the correct wallet 
    - All wallet information is available once unlocked

---

## Keystore File
1. Verify that the KeyStore box displays an example of a Keystore file name save
    - Mousing over the Keystore file box should make it “pop” and change Keystore file title color to blue
2. Check that mousing over the bottom right corner symbols show pop up text
    - Shield: “This wallet type is insecure”
    - Question Mark: “More info”
        - Check that the Question Mark links to the correct page: https://support.mycrypto.com/private-keys-passwords/difference-beween-private-key-and-keystore-file.html 
3. Verify that clicking Keystore will transition to the correct page
    - Verify that there aren’t any typos in the warning
    - Check that all the links are working and correct
4. Check that the “Change Wallet” option works in the top left corner
5. Check that you can only press “Continue” when all 3 check boxes are marked
6. Verify that pressing “Continue” goes to the correct page to select Keystore
7. Verify that the link to “run MyCrypto Locally” works: https://download.mycrypto.com/ 
8. Ensure that clicking “Select Wallet File” works
    - Opens up a new window to access your file
        - Ensure that only a valid Keystore file is able to open	
            -Error handling : This is not a valid wallet file
    -Ensure that inputting incorrect password handles properly 
        -Error: Please enter a valid password 
9. Ensure that correct file and password transition to correct page after clicking “Unlock”
    - All wallet information is available once unlocked
       
---
## Create New Wallet

1. Ensure that clicking on "Create New Wallet" tab takes you to the correct page
	- Check that the warning in the orange box has no typos and reads: "Warning: Managing your own keys can be risky and a single mistake can lead to irrecoverable loss. If you are new to cryptocurrencies, we strongly recommend using MetaMask or purchasing a Ledger or TREZOR hardware wallet. Learn more about different wallet types & staying secure"
	- Check that the links in the Warning link to the correct page
		- MetaMask: https://metamask.io/
		- Ledger: https://www.ledgerwallet.com/r/1985?path=/products/
		- Trezor: https://shop.trezor.io/?a=mycrypto.com
		- Learn more: https://support.mycrypto.com/private-keys-passwords/difference-beween-private-key-and-keystore-file.html

### Create a New Wallet via Keystore File

1. Check that the description is as follows and without typos: 
	- An encrypted JSON file, protected by a password
	- Back it up on a USB drive
	- Cannot be written, printed, or easily transferred to mobile
	- Compatible with Mist, Parity, Geth
	- Provides a single address for sending and receiving
2. Check that the "Create New Wallet" is faded out and unclickable until valid matching passwords are inputted
3. Ensure that the "Generate a Keystore File" button works and transitions you to the correct page
4. Check that the "Back" link in the top left corner takes you back to previous page
5. Check that the says "Generate a Keystore File"
6. Ensure that there are two text input boxes.
	- Password
		- Ensure that there is greyed out text saying "Password must use at least 12 characters"
		- Ensure that you can toggle password visibility with the eye icon
	- Confirm Password
		- Ensure that there is greyed out text saying "Do NOT forget to save this!"
		- Ensure that you can toggle password visibility with the eye icon
7. Check that the text at the bottom has no typos and says "This password encrypts your private key. This does not act as a seed to generate your keys. You will need this password + your keystore file to unlock your wallet."
8. Check that when you start typing in a password that the box highlight turns red until the appropriate length of characters has been reached
	- Check that if you use a very simple and common password such as "1234567890123" that the error: This password isn't strong enough. This is a very common password is shown, and box highlight stays red
9. Check that when you have typed in a long enough password that the box highlight turns green
10. Check that when you mistype the password in the "Confirm Password" box that is stays red
11. Ensure that when the password matches in both input text boxes that the button "Create New Wallet" becomes selectable and defined
12. Verify that clicking "Create New Wallet" transitions to the "Save Your Keystore File" page
13.Ensure that you can not click the "Continue" button until you have downloaded the Keystore File first
14. Check that the "Download Keystore File" works and you are able to download and save the file
	- Check that the file is a valild JSON file
15. Ensure that there are no typos in the text below and reads:
	- Don't lose it! It can't be recovered if you lose it.
	- Don't share it! Your funds will be stolen if you use this file on a malicious site.
	- Make a Backup! Secure it like the millions of dollars it may one day be worth.
16. Check that the "Continue" button takes you the next page correctly
17. Ensure that the next page says "Save Your Private Key"
18. Ensure that a valid private key is displayed
19. Verify that a Paper Wallet is displayed
	- Check that it properly displays: 
		- MyCrypto Logo and webURL
		- QR code of public address
		- A space for writing Amount/Notes
		- QR code for the private key 
		- Identicon and text beside it that says "Always look for this icon when sending to this wallet"
		- Your Address:
		- Your Private Key:
20. Verify that the button "Print Paper Wallet" saves to your computer correctly
21. Check that the warning has no typos and reads:
	- Don't lose it! It can't be recovered if you lose it.
	- Don't share it! Your funds will be stolen if you use this file on a malicious site.
	- Make a Backup! Secure it like the millions of dollars it may one day be worth.
22. Check that the button "Wallet Info ->" takes you to the correct page
23. Verify that the next page correctly displays information about how to unlock your new wallet with pictures
	1. Open Mycrypto
	2. Go to View & Send
	3. Select your wallet type
	4. Provide file & password
24. Verify that the link in the top left corner "Back" takes you back to previous page
25. Verify that the button "Go to Account" takes you to the View & Send Tab

---

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
