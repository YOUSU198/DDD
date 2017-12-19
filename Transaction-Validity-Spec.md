# Valid Ether transactions

| Standard | Standard | Standard | Standard | NonStandard | NonStandard |
| -------- | -------- | -------- | -------- | ----------- | ----------- |
| Nonce    | Nonce    | Nonce    | Nonce    | Nonce       | Nonce       |
| GasPrice | GasPrice | GasPrice | GasPrice | GasPrice    | GasPrice    |
| GasLimit | GasLimit | GasLimit | GasLimit | GasLimit    | GasLimit    |
| To       | To       | To       | To       |             |             |
| Value    | Value    |          |          |             | Value       |
| Data     |          |          | Data     | Data        | Data        |


All other permutations of a ether transaction are invalid

# Valid Token Transactions

| Standard     |
| ------------ |
| Nonce        |
| GasPrice     |
| GasLimit     |
| To           |
|              |
| Data         |
| \*TokenTo    |
| \*TokenValue |

All other permutations of a token transaction are invalid

* These are 'meta' units that are encoded into the data, they describe the recepient address and how many tokens to send
