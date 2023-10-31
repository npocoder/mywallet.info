Introducing myWallet - a TypeScript library that provides an easy-to-use interface for interacting with the blockchain.info My Wallet API in type script With myWallet, you can make outgoing payments from your wallet, fetch your wallet balance, list your addresses, generate new addresses, and more - all in a clean and simple TypeScript API.

To get started with myWallet, simply install the npm package and initialize a new wallet instance with your GUID and password, like this:

```typescript
import myWallet from "myWallet";

const sampleWallet = new myWallet({
  guid: "SECRET",
  password: "SECRET"
});
```

Then you can use the various methods available in myWallet to interact with your wallet. For example, here's how you can make an outgoing payment:

```typescript
sampleWallet.payment({
  // if double encryption is enabled
  second_password: "SECRET",
  // recipients bitcoin address
  to: "1AxqCZjGRwRNzqCvQyUEaFN5auxVbWBfdN",
  // amount to send in satoshi
  amount: 10000,
  // send from a specific bitcoin address *optional*
  from: "14D3Y424biYtx8RyJXQGtaNvDFhWGSJmxc",
  // "true" or "false" indicating whether the transaction should be sent through a shared wallet. fees apply *optional*
  shared: true,
  // transaction fee value in satoshi *optional*
  fee: 1000,
  // a public note to include with the transaction *optional*
  note: "i love you"
}, function(err, res) {
  if(err) throw err;

  // handle the response
});
```
