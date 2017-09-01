# CryptoTill
Accept cryptocurrencies just like cash.
Try the [live demo](http://ehsanrahman.com/cryptotill/CryptoTill.html) (feel free to donate using it too!).

![AcceptCryptos](https://github.com/EMRahman/CryptoTill/blob/master/Images/AcceptCryptos.jpeg)

Introduction
============
This is a simple web page used for accepting bitcoin and altcoin (Dash, Ethereum & Litecoin) payments. While it is used for demonstration purposes of how cryptocurrencies can be used to accept payment with several free Web APIs; it is used live at
[khybertandoori.com](https://khybertandoori.com) for customers dining.

Before taking payment
===========================================================
Public addresses are created to accept crypto payments. These are usually generated by wallets. There is a section in the source file on "Default Addresses". PLEASE UPDATE THESE BEFORE ACCEPTING ANY PAYMENTS! I.E. Set them to the public addresses that you own and know the private key to; otherwise the payment will be going to an address that you don't own (!). In this basic version; we are reusing the same public keys provided for all transactions (as opposed to a new public key for each transaction).

General Usage
==============
After entering an amount to charge a customer; the various cryptocurrency amounts are determined using a live FX rate (via [CoinMarketCap.com](http://CoinMarketCap.com)). The FX rate and [estimated transaction fee](https://bitinfocharts.com/comparison/transactionfees-btc-eth-ltc-dash.html#1y) is displayed. Fee's are based on [jaxx.io](http://jaxx.io)'s static rates.

You must then select the desired amount of the crypto the customer wishes to pay in. A QR code will be displayed containing the crypto type, address and amount (using [Google Charts API](https://developers.google.com/chart/infographics/docs/qr_codes)).

Once the customer has scanned the QR code using their wallet app (e.g. [jaxx.io](http://jaxx.io)), we can check for payments using the "Check Blockchain For Payment" button, this is provided by [blockcypher.com](http://blockcypher.com) and by default they have a 200 requests per hour limit at the time of writing. 

The payment should appear within 1 second in the "Unconfirmed" list. Depending on the [confirmation time](https://bitinfocharts.com/comparison/confirmationtime-btc-eth-ltc-dash.html#1y) (Bitcoin 10 min, Ethereum 15 seconds, Dash/Litecoin 2-2.5 minutes at the time of writing); the payment won't be confirmed until 6 confirmations. Aspects of blockchain confirmations are outside the scope of this README; but please research this if you are not familiar. There is a small chance one could be defrauded if taking payment with 0 confirmations; however if you trust a regular customer; the risk is substantially lowered for accepting unconfirmed transactions.

If a customer is sending money to an already known address; the buttons "View Payments" can be used to see such recent payments. No more of a customer having to divulge long credit/debit card numbers and 3 digit pins over the phone begrudgingly!
