# 🎮 Bitcoin SDK
<b>API for accepting Bitcoin (BTC) payments. Easy, instant, fully automated.</b>

## 🌴 Easy
Now you don't need to set up your own <b>Bitcoin payment infrastructure</b> or use any other expensive services. Our infrastructure is just perfect. Zero communication with humans, unless you want it. <b>Setting up is very easy</b> and needs to be done <b>only once</b>.

## 🌿 Lowest cost in the market (0.75%)
We charge you flat and fixed <code>0.75%</code> fee.

## ⚡️ Instant
We detect the payment immediately once it hits the Bitcoin network. By default <b>we notify your URL</b> (via webhook callback) 2 times:
- when transaction with BTC payment to your address appears in Bitcoin blockchain mempool (unconfirmed, 0 confirmations)
- when transaction with BTC payment to your address gets 1 confirmation.

We consider <b>payment made</b> when it gets <b>1 confirmation</b>. ✅ However you may prefer to deliver your service to a client with unconfirmed payment on 0 confirmation. Usually such services (like subscriptions) can be cancelled to a client by you later if transaction with payment to your address doesn't confirm.

## 🌒 Fully automated
Once you set the API connection, it works on it's own.

## 💚 Friendly support
Support is provided by the <b>owner of the service</b> to every client in need. Just drop me a message via <b>Telegram</b>.



# 🦚 Setting up Bitcoin SDK



# 🌲 Using Bitcoin SDK

### Checking your balances
<code>balance</code> or <code>bal</code> to show your BTC balances.

Query: <code>bal</code>

Response: array

### Requesting new address for payment
<code>address</code> or <code>new</code> with optional <code>bech32</code> flag. Short <code>segwit</code> address by default is used.

Query: <code>new</code>

Response: array

Query: <code>new [bech32]</code>

Response: array

### Withdrawing BTC
<code>withdraw</code> or <code>wtdr</code> with <code>[address, amount]</code> to withdraw BTC to your address. Flat fee for withdrawal is <code>0.0004 BTC</code>.

Query: <code>wtdr [3LBYDn5NhiFBi1cZ6yBSdNZWCLyujz1Ybg, 0.2355]</code>
Query: <code>wtdr [bc1qvzpvnshms3gd9ap7dsnt8afxlv8pvt0mhehnfy, 0.2355]</code>

Response: array
