# 🎮 Bitcoin SDK
<b>API for accepting Bitcoin (BTC) payments. Easy, instant, fully automated.</b>

### 🌲 Easy
Now you don't need to set up your own <b>Bitcoin payment infrastructure</b> or use any other expensive services. Our infrastructure is just perfect. Zero communication with humans, unless you want it. <b>Setting up is very easy</b> and needs to be done <b>only once</b>.

### 🌲 Lowest cost in the market (0%)
We charge you flat and fixed <code>0%</code> fee. :-)

### ⚡️ Instant
We detect the payment immediately once it hits the Bitcoin network. By default <b>we notify your URL</b> (via webhook callback) 2 times:
- when transaction with BTC payment to your address appears in Bitcoin network (unconfirmed, 0 confirmations)
- when transaction with BTC payment to your address gets 1 confirmation.

We consider <b>payment made</b> when it gets <b>1 confirmation</b>. ✅ However you may prefer to deliver your service to a client with unconfirmed payment on 0 confirmation. Usually such services (like subscriptions) can be cancelled to a client by you later if transaction with payment to your address doesn't confirm.

### 🌒 Fully automated
Once you set the API connection, it works on it's own.

### 💚 Friendly support
Support is provided by the <b>owner of the service</b> to every client in need. Just drop me a message via <b>Telegram</b>.



# 🦚 Setting up Bitcoin SDK

### Getting token (required)
The only required setting is getting <b>token</b> which is used by the BitcoinSDK for <b>identifying</b> and <b>authenticating</b> client.


# 🌲 Using Bitcoin SDK

### Checking your balances
Query <code>balance</code> to show your <b>BTC balance</b>.

Response example: <code>0.00520055</code>

### Requesting new address for payment
<code>new</code> with <b>optional</b> parameters <code>amount</code> and <code>type</code>. Short <b>segwit</b> address by default is used.

Query examples:
```
new
new ["type"="bech32"]
new ["amount"=0.2355]
new ["type"="bech32", "amount"=0.2355]
```

Response: array

### Withdrawing BTC
<code>wtdr</code> with <b>required</b> parameters <code>[address, amount]</code> to withdraw BTC to your address. Flat fee for withdrawal is <code>0.0002 BTC</code>.

Query examples:
```
wtdr ["address"="3LBYDn5NhiFBi1cZ6yBSdNZWCLyujz1Ybg", "amount"=0.2355]
wtdr ["address"="bc1qvzpvnshms3gd9ap7dsnt8afxlv8pvt0mhehnfy", "amount"=0.2355]
```

### Withdrawing RUB
<code>wtdr_RUB</code> with <b>required</b> parameters <code>[bank, card number, amount]</code> to withdraw your BTC paid in RUB to Russian banks <code>sberbank</code> or <code>tinkoff</code>.

Query examples:
```
wtdr_RUB ["bank"="sberbank", "card"=5200555533330000, "amount"=33000]
wtdr_RUB ["bank"="tinkoff", "card"=5200555533330000, "amount"=33000]
```

Response: array
