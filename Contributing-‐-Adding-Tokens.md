### Adding Tokens 

MyCrypto ships with a [default token list](https://github.com/MyCryptoHQ/MyCrypto/blob/develop/common/config/tokens/eth.json) that allows our Token Scanner functionality to check balances for a pre-determined set of tokens and display them to the user.

If a token is a not in the list, users are still able to add their desired token manually through our Custom Token functionality.

If your token is not yet included in our default token list, you can add it at https://github.com/ethereum-lists/tokens, which is synced with the MyCrypto codebase before each release. 

We ask that you do not PR the token directly to our default token list at https://github.com/MyCryptoHQ/MyCrypto/blob/develop/common/config/tokens/eth.json, as we have an [automated script](scripts/update-tokens) that pulls from https://github.com/ethereum-lists/tokens instead.



