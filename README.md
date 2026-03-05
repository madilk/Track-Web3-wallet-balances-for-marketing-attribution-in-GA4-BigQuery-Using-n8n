# Track-Web3-wallet-balances-for-marketing-attribution-in-GA4-BigQuery-Using-n8n-Send-Whale-Alert-To-Discord
It captures wallet connections via a webhook, enriches the data with real-time USD balances from the Zerion API, and syncs the results to both Google Analytics 4 and BigQuery for advanced attribution analysis.

This workflow bridges the gap between anonymous website traffic and on-chain wallet activity. It captures wallet connections via a webhook, enriches the data with real-time USD balances from the Zerion API, and syncs the results to both Google Analytics 4 and BigQuery for advanced attribution analysis.

This directly helps marketing acquisition teams in web3 to understand in real-time if the users who are connecting wallets have any usd balance to be able to spend on your protocol.

How it works

Video tutorial: https://youtu.be/2_wuTRzRpkg

Webhook: Receives the wallet address, hashed ID, GA Client ID, and Session ID from your website via GTM.

Zerion API: Queries the real-time USD balance for the specific connected wallet.


GA4 Push: Sends the wallet_usd_balance as a custom metric to GA4 via the Measurement Protocol to maintain session continuity.

BigQuery Insert: Records the original wallet address and hashed wallet address into a secure table for SQL joining with raw GA4 data.

If the wallet balance exceeds a chosen amount, it also sends a whale alert message to Discord.

Prerequisites

Zerion API Key: Required for fetching real-time balance data.

Google Cloud Project: A project with BigQuery enabled and a dataset in the same project as your GA4 export.

GA4 BigQuery Link: You must enable the BigQuery export in your GA4 Admin panel to access raw event logs.
