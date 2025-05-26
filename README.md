Simplified Guide for the Grid Trading Bot on Solana
Overview
The Grid Trading Bot is an automated trading tool for the Solana Blockchain. It leverages the Jupiter API to execute token swaps and trades automatically to profit from price fluctuations. Written in JavaScript (Node.js), the bot is licensed for personal use only.
Key Features

Grid Trading Strategy: Buys at lower prices (e.g., 5% below market price) and sells at higher prices (e.g., 6% above buy price).
Individual Trade Management: Each position has its own buy and sell prices.
Customizable Parameters:
Buy/Sell Spread (e.g., 5%/6%)
Swap Amount (automatically adjusted based on volatility)
Slippage Tolerance (e.g., 0.5%)
Refresh Interval (e.g., 5 seconds)
Stop-Loss (e.g., -20%)


Stop-Loss Protection: Halts trading at a defined loss threshold.
Logging: All actions recorded in gridbot.log.
Solana & Jupiter: Utilizes Solana’s speed and Jupiter for swaps.

Requirements

Linux Server (e.g., Ubuntu) with Node.js
Solana Wallet with SOL (min. 0.5 SOL for trading + fees)
Jupiter API Key (https://portal.jup.ag)
Node.js Packages: async-retry, axios, bs58, chalk, dotenv, inquirer, winston, @project-serum/anchor, @solana/spl-token, @solana/web3.js

Setup and Start

Download:

Windows: Download the .exe file and run it.
Linux: Download the bot file and make it executable:chmod +x Gridstart.js




Prepare Server (Linux):

Log in via SSH:ssh root@your-server-ip


Install Node.js:apt update
apt install -y nodejs npm




Create Directory:
mkdir ~/grid
cd ~/grid


Create Bot File:

Create Gridstart.js with the bot code (using nano Gridstart.js or copy it).
Alternatively: Download the pre-built file.


Install Dependencies:
npm init -y
npm install async-retry axios bs58 chalk dotenv inquirer winston @project-serum/anchor @solana/spl-token @solana/web3.js


Configure Environment Variables:

Create .env:nano .env


Add:PRIVATE_KEY=your_private_key_in_base58
RPC_ENDPOINT=https://api.mainnet-beta.solana.com


Optional: Use Helius RPC (https://dashboard.helius.dev/) for better performance.




Install tmux:
apt install -y tmux


Start the Bot:

Start tmux:tmux new -s gridbot


Run the bot:node Gridstart.js


Configure:
Token Mint Address (e.g., USDC: EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v)
Buy Spread (e.g., 5), Sell Spread (e.g., 6), Swap Amount (e.g., 0.1 SOL), Slippage (e.g., 0.5), Interval (e.g., 5), Stop-Loss (e.g., -20)


Detach tmux: Ctrl+B, then D.


Monitor:

Reconnect:tmux attach -t gridbot


Check logs:tail -f ~/grid/gridbot.log




Stop the Bot:

Reconnect to tmux, press Ctrl+C, then:exit





Additional Notes

Recommended Tokens: USDC or USDT for high liquidity (see mint addresses above).
SOL Balance: Min. 0.5 SOL for 5 grid layers + fees.
API Key: Without a key, rate limits may occur (https://portal.jup.ag).
SolanaTracker API: For advanced data (https://www.solanatracker.io/?ref=R8X7VORV).

