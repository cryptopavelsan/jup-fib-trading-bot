# Jupiter Swap Fibonacci Trading Bot
This trading bot swaps between two pairs buying and selling based on the side and defined Fibonacci range for buying and selling. It will sell above a certain Fib level and buy below it for the two selected tokens. Deviation from the levels/mean can be set to impact the size of the swap to help taking advantage of the local crest and trough within the time period.

It utilizes Jupiter Aggregator, a swap aggregator on Solana using their SDK V4. It has built in rudimentary retry logic for failed transactions.

This code has not been thoroughly tested and is **unaudited**. **Please use at your own risk!**

It is best practice not to store tokens on the wallet used with this bot apart from what is needed for swapping. Setting up a schedule to move tokens (not needed on the wallet) to a cold-storage hardware backed wallet (aka Ledger wallet) should be implemented to secure the DCA tokens being collected.

## Install
```
yarn install
```
## Configure
1. Create an `.env` file at the project root. See `.env-example`. 
Private key can be obtained from Phantom via Settings -> Export Private Key.

As the private key is stored in the .env file it is important to secure access to this file (on top of severly limiting funds stored on this wallet). Remove other/group access as a starting point to this file to only allow the owner and root user to be able to read the file (chmod 600 .env), use a secure password for the user for accessing the server it runs on and follow other best practices to reduce risk here including frequently moving swapped dca tokens to a hardware backed wallet.

2. Create your own `dcaconfig.ts`. See `dcaconfig-example.ts` for a template. 

Remove the entires you do not need from the sample file. Always start with a very small amount to see it is doing what is expected before you test further. Use at your own risk.

To see example cron expressions, check out [crontab.guru](https://crontab.guru/).
Note: the minimum interval is one minute.
## Run
```
yarn trade
```
