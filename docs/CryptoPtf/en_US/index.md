# Plugin Crypto Portfolio

This plugins retrieves informations from your cryptocurrencies portfolio / wallets.
Currently the plugin connects to the following wallets:
- JustMining
- Binance
- Wallet Ethereum

For the above wallets, an equipment represents one cryptocurrency.

The wallets are described below:

## JustMining

A Just Mining equipment can retrieve informations from:
- a stacking contract
- a masternode contract
- a wallet contract

### Equipment description
The plugin returns, the tokens / rewards from your Stacking / Masternode / Wallet contract
The plugin can return the price rate valuation of your wallet in EUR / USDT
The plugin can also return the perfomance of your portfolio / wallet for:
- 24 hours
- 1 week
- 1 month
- 1 year

If you input the price you bougth the tokens, the plugin will calculate the capital gain.

### Equipment configuration
First you will have to define the refresh rate. Without it the equipment commands will not e refreshed

In the wallet dropdown, choose Just Mining.

<img src="IMGS/config_justmining_paramspe.PNG" alt="hi" class="inline"/>

You must then configure the API KEY you will find on the Just Mining website.

Copy Paste the API KEY in the plugin configuration. The API KEY only gives READ rights on your account. You will find more informations ont he following link:
<a href="https://docs.just-mining.com/">Documentation API Just Mining</a>

You can now choose your Just Mining contract type:
- Stacking
- Masternode
- Wallet

If the API KEY is correct and you have contracts on Just Mining, the plugin will offer you the possibility to choose between your different contracts

Two more options are available:
- Retrieve the Token price rate on Binance your two currency (EUR, USDT)
- Force input the symbol for Binance to retrieve the token price rate. Look below of the documentation for more informations

You can also:
- give the plugin the price you bought these tokens (in the correct currency), and the plugin will calculate your gains.
- give the plugin the number of decimals it has to use to calculate the price valuation.

SAVE to create all the commands

## Binance
A Binance equipment wan retrieve the informations from your Spot Wallet

### Equipment description
The plugin returns the number of tokens free and locked in your Spot Wallet.
The plugin can return the price rate valuation of your wallet in EUR / USDT
The plugin can also return the perfomance of your portfolio / wallet for:
- 24 hours
- 1 week
- 1 month
- 1 year

If you input the price you bougth the tokens, the plugin will calculate the capital gain.

### configuration de l'équipement
First you will have to define the refresh rate. Without it the equipment commands will not e refreshed

In the wallet dropdown, choose Binance.

Input the API KEY and the API SECRET that you can find on your Binance account on the website.
Be sure to create a new api key for your Jeedom and only give READ permission to this key. The plugin will never do any transactions

Choose Spot on the dropdown

If the API KEY and the API SECRET are corrects, the plugin will ask you to choose betwenn the cryptocurrencies you own.

Two more options are available:
- Retrieve the Token price rate on Binance your two currency (EUR, USDT)
- Force input the symbol for Binance to retrieve the token price rate. Look below of the documentation for more informations

You can also:
- give the plugin the price you bought these tokens (in the correct currency), and the plugin will calculate your gains.
- give the plugin the number of decimals it has to use to calculate the price valuation.

SAVE to create all the commands

## Wallet Ethereum
This equipment will retrieve the number of tokens you own in an Ethereum Wallet

### Equipment description
The plugin returns the number of token in your Ethereum wallet.
The plugin can return the price rate valuation of your wallet in EUR / USDT
The plugin can also return the perfomance of your portfolio / wallet for:
- 24 hours
- 1 week
- 1 month
- 1 year

If you input the price you bougth the tokens, the plugin will calculate the capital gain.

### Equipment settings
First you will have to define the refresh rate. Without it the equipment commands will not e refreshed

In the wallet dropdown, choose Wallet Ethereum.


For this equipment, you will have to provide an Infura API KEY:
<a href="https://infura.io/dashboard/ethereum">Infura.io</a>
This key is free and will llow you to do 100 000 request per days
The key is equivalent to the PROJECT ID

Input your wallet Ethereum adress and the token contract adress you wish to retrieve.
For exemple for MTO, you can find the contract adress below:
<a href="https://etherscan.io/token/0xe66b3aa360bb78468c00bebe163630269db3324f">MTO Contract Adress</a>

Two more options are available:
- Retrieve the Token price rate on Binance your two currency (EUR, USDT)
- Force input the symbol for Binance to retrieve the token price rate. Look below of the documentation for more informations

You can also:
- give the plugin the price you bought these tokens (in the correct currency), and the plugin will calculate your gains.
- give the plugin the number of decimals it has to use to calculate the price valuation.

SAVE to create all the commands

## Currency rate settings
For all the equipment you can configure the currency to convert the token value.
You will have to check the correct option during the configuration and set the currency (EUR, USDT)

If the plugin cannot retrieve the correct currency for this symbol you can still for input the symbol that Binance has to use to convert the token value
