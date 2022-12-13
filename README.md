# Jupiter Swap Moving Average Trading Bot
This trading bot swaps between two pairs buying and selling based on the side and devaiation between the selected moving average.

It utilizes Jupiter Aggregator, a swap aggregator on Solana using their SDK V3. It has built in rudimentary retry logic for failed transactions.

This code has not been thoroughly tested and is **unaudited**. Please use at your own risk!

It is best practice not to store tokens on the wallet used with this bot apart from what is needed for swapping. Setting up a schedule to move tokens (not needed on the wallet) to a cold-storage hardware backed wallet (aka Ledger wallet) should be implemented to secure the DCA tokens being collected.
