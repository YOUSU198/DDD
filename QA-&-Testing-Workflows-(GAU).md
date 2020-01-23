WORK IN PROGRESS. This will eventually be updated for all new GAU flows. Currently it is still the legacy stuff that we are using as a base.

---

## View & Send Tab:
* [MetaMask](#meta-mask)
* [Ledger](#ledger)
    * [Address Verification on Ledger](#address-verification-on-ledger)
* [Trezor](#trezor)
* [Parity Signer](#parity-signer)
* [MetaMask](#meta-mask)
* [Private Key](#private-key)
* [Keystore File](#keystore-file)
* [Sending a Transaction](#sending-a-transaction)

## Token Balance
* [Token Balance Check](#token-balance-check)
* [Auto Add Token Details](#auto-add-token-details)

## Swap
* [Swap General Check](#swap-general-check)

## Promotions
* [Simplex Promo](#simplex-promo)

## Create New Wallet Tab
* [Create a New Keystore Wallet](#create-a-new-wallet-via-keystore-file)

## Swap
* [Swap Support](#swap-support)

## Contract Tab
* [Interacting with Contracts with ETH Network](#interacting-with-contracts-with-eth-network)
* [Interacting with the Consensys Multisig Contract](#interacting-with-the-consensys-multisig-contract)
* [Changing Tabs](#changing-tabs)
* [Contract Bool Values](#contract-bool-values)
* [Sending a Transaction to a Contract](#sending-a-transaction-to-a-contract)
* [Contract Support for Undefined Input Names](#contract-support-for-undefined-input-names)

### Other Nodes Contract Tab
* [RSK Contract Interaction](#rsk-contract-interaction)

## ENS
* [ENS General Check](#ens-general-check)

## Nodes
* [Testnet Balance Display](#testnet-balance-display)
* [Changing Nodes](#changing-nodes)
* [Custom Node](#custom-node)
* [Other Nodes Check](#other-nodes-check)
* [Node Failure to Load](#node-failure-to-load-check)
* [Auto Node](#auto-node)
* [MetaMask Network Change](#metamask-network-change)
* [RSK Node](#rsk-node)

## Address Book Feature
* [Address Book](#address-book)

## Desktop App Workflow
* [Desktop App](#desktop-app)
* [Right Click](#right-click)

## Preserving Query Params of Redirect URL
* [Network Redirect URL](#network-redirect-url)
* [Transaction Params of URL](#transaction-params-of-url)

## Offline App
* [Offline Status Checker](#offline-status-checker)

## App Settings
* [Language Selection](#language-selection)
* [Browser Back Button Interaction](#browser-back-button-interaction)
* [Removal of Private Keys](#removal-of-private-keys)
* [Consolelog Print](#consolelog-print)

## Other Internet Browsers
* [Firefox](#firefox)
* [Internet Explorer](#internet-explorer)

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

### Address Verification on Ledger

1. Connect Ledger to Computer (Ensure that the Ethereum App is running and web browser setting is enabled)
2. Ensure that you can connect to Ledger wallet via MyCrypto.com
3. Ensure that after Ledger is unlocked that the window which allows you to pick a wallet to open appears
    1. Verify that you can Toggle “More” and “Back” to access various addresses available on your Ledger
    2. Verify that you can Select a Node in the drop down menu ‘
    3. Verify that you can pick a token in the drop down
    4. Verify that the link under “More” works
    5. Verify that you can only select one address at a time
    6. Ensure that once an address is selected, that the unlock button becomes available, and not before an address is chosen
4. From the "Addresses" drop down menu, select "Custom"
    - Enter ``` m/44'/60'/0'/0```
    - Ensure that clicking the green tick button opens up a new list of wallets
5. Ensure that you can select any address from the list
    - Ensure that the "Unlock" button works and unlocks appropriate wallet
6. Ensure that you can click "Display Address on Ledger"
7. Ensure that the address is displayed correctly on the Ledger and that you can confirm with the checkmark 

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
4. Verify that the “Don’t have a TREZOR? Order one now” button works https://shop.trezor.io/?offer_id=10&aff_id=1735
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

### Sending a Transaction
1. Access a wallet
2. On intial opening of the wallet, ensure that the gas price silder is at recommened price after loading

---
## Swap

### Swap Support  

1. Navigate to the Swap tab
2. Ensure that there is a button that says: "Issue with your Swap? Contact support"
    1. Verify that there is a backup link that says: "Click here if link doesn't work"
3. Ensure that the following information is included in the email:

```
To: support@shapeshift.zendesk.com,support@mycrypto.com
Subject: Issue regarding my Swap via MyCrypto
Message:
Provider: Shapeshift
REF ID#: 
Amount to send:  BTC
Amount to receive:  ETH
Payment Address: 
Receiving Address: 
Rate: 14.07223796 BTC/ETH
```
---

## Token Balance Check

### Token Balance Failure to Load When Node is offline

1. Set the network to "ETH (AUTO)"
2. Unlock a wallet containing a token like EOS (example wallet:```0xcD009D5d5b7e68F4C36Da5C21F646AfAA83075E2```)
3. Ensure that the token balance loads correctly

### Auto Add Token Details
1. Access a wallet with a token that is not yet a default token
2. Scan for Tokens
3. Ensure that you can start adding a custom token
    1. Verify that when you click "Add Custom Token"
        1. Ensure that 4 text input boxes appear
        2. Ensure that there is a help link on how to add custom tokens - https://support.mycrypto.com/tokens/adding-new-token-and-sending-custom-tokens.html
        3. Ensure that there is a button to "Cancel" adding a custom token 
            1. verify that clicking "Cancel" closes the box and still retains saved tokens
        4. Ensure that the "Save" button is not enabled until a valid token address is inputted
        5. Ensure that the text boxes for:
            - Decimals
            - Token Symboll
            - Balance
        Are barred off from inputting custom details
        6. Input the address of the non-default token
            1. Ensure that the decimals/Token Symbol/Balance are all automatically filled in with the correct values]
            2. Verify that invalid addresses give you the error: "Not a valid address:
            3. Ensure that you can successfully save new custom token

---
### Swap General Check
1. Verify that you can navigate to the swap tab
2. Ensure that you see current rates of coins that are randomly chosen
    1. verify that you can type in a number to compare the coins where the (1) is
3. Ensure that you can pick all coins listed for deposit and Receive
4. Once you have inputted a value for deposit, ensure that the amount to receive is automatically calculated
5. Ensure that the button to start swap becomes enabled only after a valid deposit number has been entered. 
6. On next Swap page, you should be able to input your Receiving address
    1. Ensure that the ```Start Swap``` button only becomes enabled after a valid receiving address for that coin is entered
7. Make sure on next screen you are shown your reference number, time remaining for the transfer, amount you are receiving and at which rate the swap is taking place
8. Ensure that you are given all wallet options to access to finish the trade
9. Once you are logged into the wallet, ensure that the address and amount to send fields are automatically fillled in for you correctly. 
10. Ensure that you can successfully send the transaction. 
11. Verify that the Swap completion bar updates as the swap progresses
12. Ensure that you get your swapped coin

---

## Promotions

### Simplex Promo

1. Change system clock to European time
2. Access a wallet
3. Ensure that once the wallet is unlocked, check that the Simplex promo is visible
4. Ensure that the promo links you to: https://buy.mycrypto.com/

---
## Contract Tab


### Interacting with Contracts with ETH Network
#### Interacting with the Consensys Multisig Contract

1. Access Contract tab
2. Verify that you can toggle between the “Interact” and “Deploy” sub tabs
3. Interact tab:
    1. Verify that there is a drop down menu labelled “Select Existing Contract” 
        1. Ensure that there is a placeholder value saying “Select a Contract”
        2. Ensure that when the drop down menu is selected, you can type into it to search for the contract you are looking for
    2. Verify that there is a text input box available for entering a “Contract Address”
        1. Ensure that there is a placeholder value saying “ensdomain.eth or 0x4bbeEB066...”
    4. Verify that there is a larger text input box labelled “ABI / JSON Interface”
    5. Verify that the “Access” button is not clickable and slightly washed out
4. Ensure that selecting the Consensys Multisig contract works correctly
    1. Ensure that you can input your own contract address (ex. 0x0F4a28085713c1a5DEdc5D6f471c79AFe2d9321e)
    2. Selecting it should automatically fill in the contract address to 0x101010101...
    3. Verify that you can’t input a regular wallet address
    4. Verify that you can’t input any weird text
    5. Verify that the identicon displays correctly
    6. Verify that when a valid Contract Address is entered, the box is highlight green
    7. Verify that when the Existing Contract is selected the ABI / JSON Interface is automatically filled in: 
        1. ```json [{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"owners","outputs":[{"name":"","type":"address"}],"payable":false,"type":"function"},{"constant":false,"inputs":[{"name":"owner","type":"address"}],"name":"removeOwner","outputs":[],"payable":false,"type":"function"},{"constant":false,"inputs":[{"name":"transactionId","type":"uint256"}],"name":"revokeConfirmation","outputs":[],"payable":false,"type":"function"},{"constant":true,"inputs":[{"name":"","type":"address"}],"name":"isOwner","outputs":[{"name":"","type":"bool"}],"payable":false,"type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"},{"name":"","type":"address"}],"name":"confirmations","outputs":[{"name":"","type":"bool"}],"payable":false,"type":"function"},{"constant":true,"inputs":[{"name":"pending","type":"bool"},{"name":"executed","type":"bool"}],"name":"getTransactionCount","outputs":[{"name":"count","type":"uint256"}],"payable":false,"type":"function"},{"constant":false,"inputs":[{"name":"owner","type":"address"}],"name":"addOwner","outputs":[],"payable":false,"type":"function"},{"constant":true,"inputs":[{"name":"transactionId","type":"uint256"}],"name":"isConfirmed","outputs":[{"name":"","type":"bool"}],"payable":false,"type":"function"},{"constant":true,"inputs":[{"name":"transactionId","type":"uint256"}],"name":"getConfirmationCount","outputs":[{"name":"count","type":"uint256"}],"payable":false,"type":"function"},{"constant":true,"inputs":[{"name":"","type":"uint256"}],"name":"transactions","outputs":[{"name":"destination","type":"address"},{"name":"value","type":"uint256"},{"name":"data","type":"bytes"},{"name":"executed","type":"bool"}],"payable":false,"type":"function"},{"constant":true,"inputs":[],"name":"getOwners","outputs":[{"name":"","type":"address[]"}],"payable":false,"type":"function"},{"constant":true,"inputs":[{"name":"from","type":"uint256"},{"name":"to","type":"uint256"},{"name":"pending","type":"bool"},{"name":"executed","type":"bool"}],"name":"getTransactionIds","outputs":[{"name":"_transactionIds","type":"uint256[]"}],"payable":false,"type":"function"},{"constant":true,"inputs":[{"name":"transactionId","type":"uint256"}],"name":"getConfirmations","outputs":[{"name":"_confirmations","type":"address[]"}],"payable":false,"type":"function"},{"constant":true,"inputs":[],"name":"transactionCount","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"constant":false,"inputs":[{"name":"_required","type":"uint256"}],"name":"changeRequirement","outputs":[],"payable":false,"type":"function"},{"constant":false,"inputs":[{"name":"transactionId","type":"uint256"}],"name":"confirmTransaction","outputs":[],"payable":false,"type":"function"},{"constant":false,"inputs":[{"name":"destination","type":"address"},{"name":"value","type":"uint256"},{"name":"data","type":"bytes"}],"name":"submitTransaction","outputs":[{"name":"transactionId","type":"uint256"}],"payable":false,"type":"function"},{"constant":true,"inputs":[],"name":"MAX_OWNER_COUNT","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"constant":true,"inputs":[],"name":"required","outputs":[{"name":"","type":"uint256"}],"payable":false,"type":"function"},{"constant":false,"inputs":[{"name":"owner","type":"address"},{"name":"newOwner","type":"address"}],"name":"replaceOwner","outputs":[],"payable":false,"type":"function"},{"constant":false,"inputs":[{"name":"transactionId","type":"uint256"}],"name":"executeTransaction","outputs":[],"payable":false,"type":"function"},{"inputs":[{"name":"_owners","type":"address[]"},{"name":"_required","type":"uint256"}],"payable":false,"type":"constructor"},{"payable":true,"type":"fallback"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_sender","type":"address"},{"indexed":true,"name":"_transactionId","type":"uint256"}],"name":"Confirmation","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_sender","type":"address"},{"indexed":true,"name":"_transactionId","type":"uint256"}],"name":"Revocation","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_transactionId","type":"uint256"}],"name":"Submission","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_transactionId","type":"uint256"}],"name":"Execution","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_transactionId","type":"uint256"}],"name":"ExecutionFailure","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_sender","type":"address"},{"indexed":false,"name":"_value","type":"uint256"}],"name":"Deposit","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_owner","type":"address"}],"name":"OwnerAddition","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"_owner","type":"address"}],"name":"OwnerRemoval","type":"event"},{"anonymous":false,"inputs":[{"indexed":false,"name":"_required","type":"uint256"}],"name":"RequirementChange","type":"event"}]```
5. Verify that only after selecting a contract, entering a valid contact address and valid ABI that the Access button becomes available to select
6. Selecting Access should bring up a new drop down menu labelled “Read / Write Contract” alongside appropriate Contract address in grey
7. Verify that the drop down menu is scrollable and has a value placeholder saying “Select a function”
    1. Verify that you can also type into the bar to search for the function 
        1. Verify that once a function is selected, the appropriate text box inputs appear
        2. Verify that you can click the x in the left side of the “Read / Write Contract” box to clear all
    2. Select - submitTransaction 
        1. Verify that 3 more text inputs appear below it
            1. Destination Address (ex. ```0xba2184520A1cC49a6159c57e61E1844E085615B6```)
            2. Value uint256 (ex. 0)
            3. Data Bytes (ex. ```0xa9059cbb0000000000000000000000005c842a4f93bbd06b73a69c5cb12a1430c6f37ba30000000000000000000000000000000000000000000000000000067e6929e800```)
            4. transactionId uint256
8. Verify that at the end of entering the data for the contract that you are given the option to access your wallet (Looks comparable to View & Send tab)
9. Accessing with MetaMask (or anything other wallet type should not affect end result)
10. Ensure that you can select and deselect “Automatically Calculate Gas Limit”
    1. When it is not selected, ensure that you can type into the gas Limit text box
        1. Ensure that only numbers > 0 are accepted
11. Check that you can enter a custom Gas Price, only numbers > 0
12. Check that the Nonce refresh button works correctly
13. Ensure that the “Write” button works

### Sending a Transaction to a Contract

1. Go to send a transaction via MyCrypto
2. Enter the address ```0x37f25bd26848cf02614c29338dd71a4d03b62218``` (is a contract)
3. Ensure that the gas limit estimates correctly
### Changing Tabs

1. Fill out the Interact page with any contract information
2. As you get to signing the transaction, swicth to the Deploy tab
3. Ensure that switching erases all data from Interact when you switch

### Contract Bool Values

1. Access the Contract tab
2. Enter ABI as: 
```
[
    {
        "constant": false,
        "inputs": [
            {
                "name": "x",
                "type": "bool"
            }
        ],
        "name": "test",
        "outputs": [
            {
                "name": "",
                "type": "bool"
            }
        ],
        "payable": false,
        "stateMutability": "nonpayable",
        "type": "function"
    }
]
```
3. Enter this Contract Address ```0xCdCFc0f66c522Fd086A1b725ea3c0Eeb9F9e8814```
4. Verify that the Access button is selectable only after filling in the 2 text boxes
5. Verify that a text box appears after cliking "Access", that is labelled "Read / Write Contract"
    1. verify that the inputted Contract address is also shown to the right hand side of this label
6. Verify that the dropdown menu has a place holder "Select Function"
7. Verify that you can select a function from the dropdown menu
8. Verify that you can select the "test" function
9. Ensure that after selecting the "test" function that you are presented with another dropdown menu that is labelled "x bool"
    1. Select false
        1. Ensure that you can access a wallet to generate transaction
        2. Use default Gas Price/Gas Limit
        3. Ensure that you can click "Write"
        4. After, you should be presented with another button "Sign Transaction"
            1. Raw Transaction Data: 
            ```
            {
            "value": "0x0",
            "data": "0x36091dff0000000000000000000000000000000000000000000000000000000000000000",
            "to": "0xcdcfc0f66c522fd086a1b725ea3c0eeb9f9e8814",
            "nonce": "0x0",
            "gasPrice": "0x4a817c800",
            "gasLimit": "0x5208",
            "chainId": 1
            }
            ```
        2. Ensure that since bool was set to false, false = 0 (Check that there isn't any 1's in the data)
    2. Select true
        1. Ensure that you can access a wallet to generate transaction
        2. Use default Gas Price/Gas Limit
        3. Ensure that you can click "Write"
        4. After, you should be presented with another button "Sign Transaction"
            1. ```
                {
                "value": "0x0",
                "data": "0x36091dff0000000000000000000000000000000000000000000000000000000000000001",
                "to": "0xcdcfc0f66c522fd086a1b725ea3c0eeb9f9e8814",
                 "nonce": "0x0",
                "gasPrice": "0x4a817c800",
                 "gasLimit": "0x5208",
                "chainId": 1
                }
                ```
        2. Since the bool was set to True, ensure that there is a 1 in the data (true = 1)

### Contract Support for Undefined Input names

1. Go to Contracts tab -> Interact
2. Use the following ABI:
```
[ 
   {
      "constant": true,
      "inputs": [{ "name": "", "type": "uint256" }, { "name": "", "type": "address" }],
      "name": "whitelist",
      "outputs": [{ "name": "", "type": "bool" }],
      "payable": false,
      "stateMutability": "view",
      "type": "function"
   }
]
```
3. Use address: ```0xB8BF791166eed1A94B3a19bEE0d7dbb2A98b504E```
4. Fill in each field under the whitelist function
5. Make sure you're able to fill each field seperately (except for "bool")

## Other Nodes Contracts Tab

### RSK Contract Interaction

1. Change network to RSK(mycrypto.rsk.co)
2. Navigate to the Contracts Tab
3. Select the Bridge contract
4. Ensure that you can correctly execute the Bridge contract
5. Validate that you get the correct response
    - Bridge contract (0x000000...)
    - Contract Address: ```0x0000000000000000000000000000000001000006```
    - ABI: ```[{ "name": "getFederationAddress", "type": "function", "constant": true, "inputs": [], "outputs": [{ "name": "", "type": "string" }] }]```
    - Function: getFederationAddress
    - String should read: ```39AHNvUmzaYgewA8yCtBtNsfRz7QD7ZJYi```
---

## ENS

### ENS General Check 
1. Verify that you can navigate to the ENS page
2. Ensure that the page title reads "Ethereum Name Service"
    1. Check that ENS link is correct and valid
        1. Ethereum Name Service - https://ens.readthedocs.io/en/latest/introduction.html
    2. Ensure that the text reads : ```"The Ethereum Name Service (ENS) is a distributed, open, and extensible naming system based on the Ethereum blockchain. Once you have a name, you can tell your friends to send ETH to ensdomain.eth instead of 0x4bbeEB..."```
    3. Ensure that there is a text input box with a premanent block of text that contains ".eth"
        1. Ensure that there is greyed out text in the text input box that reads "mycrypto"
    4. Ensure that the button is not clickable until valid input
        1. Ensure that gibberish does to enable to button ex. i.ert.45.ert
            1. Error given: "Must be at least 7 characters, no special characters"
        2. Ensure that only "-" are allowed in the name
    5. Ensure that ENS domains that are already owned, are shown as already owned:
        1. Ensure that relevant information is included about the already owned ENS domain in Hex:
            1. Name:
            2. Labelhash __name:
            3. Namehash __name.eth:
            4. Owner:
            5. Highest Bid:
            6. Resolved Address:
    6. Ensure that domains that are not yet owned are shown as available
        1. Ensure that you are shown that the ENS domain is available and redirects you to MyCrypto v3 to start the auction
## Nodes
 
### Testnet Balance Display
 
1. In the node drop down menu, select a test network.
2. Ensure that switching the node works correctly.
3. Verify that you can access a regular Ether address on the test network.
4. Access the wallet type as you regularly would.
5. Ensure that the Account Balance displays the correct amount of test Ether with "(Testnet)" displays beside it
 
### Changing Nodes
1. Verify that you can switch nodes before even accessing your wallet, and that it loads (blinking of the drop down menu means it is loading)
2. Access a wallet (not via MetaMask)
3. Ensure that you can switch nodes of the same network
    1. Ethereum - Test all 4 nodes to see if they connect properly/load
        1. MyCrypto
        2. Etherscan
        3. infura
        4. Blockscale
    2. Ethereum Classic
        1. Epool.io 
        2. Ethereum Commonwealth
        3. Chainkorea
    3. Ropsten (testnet)
        1. Infura (testnet)
        2. Kocan (testnet)
        3. Rinkeby (testnet)
    4. Other Networks
4. Verify that all the account information loads correctly
5. Now, ensure that connecting via MetaMask/web3 works correctly
    1. Ensure that all account information is correct and loads 
 
### Custom Node
1. In the top right drop down menu, ensure that you can select "Add Custom Node"
2. Ensure that after cliking custom node, a pop up window appears that is titled "Set Up Your Custom Node"
    1. Veryif that you are given a warning:
    ```Your node must be HTTPS in order to connect to it via MyCrypto.com. You can download the MyCrypto repo & run it locally to connect to any node. Or, get free SSL certificate via LetsEncrypt```
3. Ensure that the first drop down menu is titled "Default Nodes Found" (as long as you have a valid node running on your computer simultaneously)
4. Ensure that your custom node is listed
5. Verify that once your custom node is selected, that the rest of the fields are filled in correctly
6. Ensure that you can select the option "HTTP Basic Authentication"
    1. Ensure that this opens up 2 more text boxes for a username and a password
7. Check that the Cancel button works
8. Check that the "Save & Use Custom Node" work
9. Verify that you can access your wallet
    1. Ensure that your wallet address and balance are displayed correctly
10. Ensure that you can send a transaction

### Other Nodes Check

1. Select the node you are testing 
2. Access a wallet of any type
    1. Can't select MetaMask unless testing an Ethereum node/network
3. Ensure that the wallet unlocks correctly
4. Ensure that your Account Balance is correctly displayed followed by the appropriate coin name
    1. ex. 1.092 ETC 
    2. ex. 35.80 MUSIC


### Node Failure to Load Check

1. Run MyCrypto offline or mistype one of the node URLs in libs/nodes/config.ts
2. Attempt to switch nodes
3. Confirm that it fails, but that the node selector stops flashing
    1. Ensure that you are also given this error:
        - You’ve lost your connection to the network, check your internet connection or try changing networks from the dropdown at the top right of the page.
        - Could not connect to the node. Refresh your page, try a different node (upper right corner), check your firewall settings. If custom node, check your configs.

### Auto Node

1. Confirm (AUTO) is shown when a network is selected in place of a specific node on the network

### MetaMask Network Change
1. Access a wallet via MetaMask
2. In the MetaMask chrome extension itself, switch networks
3. Ensure that you are logged out from the current wallet

### RSK Node
1. Ensure that the ENS and Swap tab are not visible when switching to this network

---

## Address Book
 
1. Access a wallet.
2. Verify that there are 2 text input boxes
3. Verify that the box labelled "Address", only accepts valid ETH addresses
    1. Verify that there is greyed out text placeholder that says "New Address"
    2. When you are in process of inputting an valid ETH address, box highlight is blue.
    3. When you enter a valid ETH address the box highlight turns green.
    4. When you enter an invalid ETH address the box highlight turns red.
        1. When an invalid ETH address is inputted the error "Please enter a valid ETH address." is shown
4. Verify that when a valid ETH address is entered, the Identicon appears and matches the address
5. Verify that the text box labelled "Label" accepts any kind of characters
    1. Check that it has a greyed out placeholder that says "New label"
    2. Ensure that when the inputted label is less than 2 or more than 50 you are given the error "An address label must be between 2 and 50 characters."
6. Verify that after having both value inputs filled in, that clicking the plus sign will "save" it to your account.
7. Verify that after saving the address, under the Account Address section, the name is updated as well
8. Verify that you can edit the label in the Account Address section
    1. Verify that doing so also updates the field "Label" in the Address boox tab of the logged in wallet
9. Verify that on the Send Ether & Tokens page of the logged in wallet displays the save address    
    1. Start typing the label of the account into the "To Address"
        1. The saved address, as well as Identicon and label appears below it
    2. Ensure that you can select the popped up account and that it fills in the address correctly
    3. Ensure that when the address is selected from the address book pop up, that below the "To Address" field box, there is green text displaying that you are sending to the saved address

---

## Desktop app

### Expiry Date Update 

1. Ensure that https://download.mycrypto.com/ loads correct 
2. Verify that you can download the app (Windows, macOS, Linux, Stand Alone)
3. Once downlaoded and installed, ensure that the expiry notice has been updated
    1. As of May 6th, 2018, the expiration date is set to July 24th, 2018

### Right click
1. Open up the desktop App
2. Ensure that when you right click items, you are given a menu for the appropriate TransactionActions

---
## URL Redirects
## Preserving Query Params of Redirect URL

### Network Redirect URL
1. Visit https://mycrypto.com/?network=etc
2. Ensure that the url re-directs you to the appropriate link
3. Ensure that the network has been swicthed automatically to the ETC network

### Transaction Params of URL

1. Visit mycrypto.com/account/send?to=0x4bbeEB066eD09B7AEd07bF39EEe0460DFa261520&value=1&limit=50000&data=0xa
2. Access a wallet like you normally would
3. Ensure that you are given a pop up that says:
    - You arrived via a link that has the address, value, gas, data fields, or transaction type (send mode) filled in for you. You can change any information before sending. Unlock your wallet to get started.
4. Ensure that the values are filled in according to the URL 
5. Ensure that you can still change values on the transaction
6. Ensure that you can send the transaction 

---
## Offline Status Checker

1. Load app while online
2. Ensure that the online indicator should still be green
3. Go to dev tools - Network Tab
4. Check `offline` box
5. Verify that the App should go offline, but that it is still checking if it can reach any nodes
    1. Ensure that you are also given this warning: 
        - "You are currently offline. Some features will be unavailable."
6. If it can reach a node, it will go back online
7. Uncheck `offline` box, app should still remain online if steps 6 completed successfully
    1. Ensure that you are given this pop up when connection is made:
        - "Your connection to the network has been restored!"
8. Completely disable your network connection 
9. Verify that the App should go completely offline, node checks should fail, so app should stay offline while network connection is disabled
10. Re-enable your network connection
11. After a short period, if a node is online, app should regain connection to network and display being connected back to network
12. Login with wallet
    1. Ensure that you can still log in correctly
    2. Verify the "Advanced" section shows correct nonce or that nonce is not empty
13. Go offline again
    1. Loing with wallet
    2. Verify that you can still log in correctly
    3. Verify that the "Advanced" section shows Nonce field highlighyed in a red border and is visible immediately

---

### Language Selection

1. Verify that the language selector drop down menu opens up all available languages
2. Ensure that after selecting a language that the app refreshes and now displays selected language

### Browser Back Button Interaction
1. Access any wallet
2. Click the "back" button of the web Browser
3. Ensure that you are redirected to the home landing page of MyCrypto and are logged out of the wallet

### Removal of Private Keys
1. Check the online web app
    1. Ensure that you can not access a wallet via:
        1. Private Key
        2. Keystore File 
        3. Mnemonic Phrase
    2. Verify that instead of being able to log in you are redirected to Download the MyCrypto Desktop App
        1. Ensure that the link to the desktop app download works
        2. Ensure that the Arrow to go back to wallet selection page works
        3. Ensure that there is a light greyed out box of text which reads "I'm a dev, override this"
            1. Ensure that selecting the button allows you to continue accessing the wallet as one normally would previously
    3. Ensure that you can not create a new wallet via private Keys (on mycyryptobuilds this is possible because of how it is rendered)
        1. Verify that visiting the "Create New Wallet" tab does not allow you to make private key wallets (privatekey/Keystore/mnemonic)
        2. Verify that it gives you the option to create secure wallets 
            1. Order a hardware wallet
            2. Download MetaMask
            3. Download Parity
        3. Verify that it also shows you that you still can generate a private key wallet via the desktop app (check all links)
            1. Ensure that there is a button that redirects you to the download page for the desktop app
2. Check the Desktop app
    1. Verify that you can still access wallets via all private key options and create a private key wallet

### Consolelog Print
1. Open up Console
2. Ensure that you see the MyCrypto logo and a link to ```https://about.mycrypto.com/jobs ```

--- 

## Other Internet Browsers

### Firefox
1. Try connecting to Ledger on Mozilla
2. Ensure that you can't and are given this error ```TransportError: U2F browser support is needed for Ledger. Please use Chrome, Opera or Firefox with a U2F extension. Also make sure you're on an HTTPS connection```

### Internet Explorer
1. Try accessing MyCrypto with IE
2. Ensure you are given this error ```Your Browser is Out of Date. MyCrypto requires certain features that your browser doesn't offer. Your browser may also be missing security updates that could open you up to vulnerabilities. Please update your browser, or switch to one of the following browsers to continue using MyCrypto. ```