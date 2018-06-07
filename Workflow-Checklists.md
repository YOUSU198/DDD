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

## Contract Tab
* [Contract Consensys](#contract-consensys)
* [Changing Tabs](#changing-tabs)
* [Contract Bool Values](#contract-bool-values)

## Nodes
* [Testnet Balance Display](#testnet-balance-display)
* [Changing Nodes](#changing-nodes)

## Address Book Feature
* [Address Book](#address-book)

## Desktop App Workflow
* [Desktop App](#desktop-app)

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
## Contract Tab

### Contract Consensys
#### Interacting with the Consensys Multisig Contract - submitTransaction

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
---

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
