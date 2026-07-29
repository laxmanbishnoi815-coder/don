🦇 Card Sorter Bot
Telegram bot that extracts card numbers, looks up BIN/bank info, and sorts them into clean `.txt` files.
Deploy on Railway
Upload this zip to Railway (or connect your GitHub repo)
Railway auto-detects Python from `requirements.txt`
Set these environment variables in Railway → Variables:
Variable	Required	Description
`BOT\_TOKEN`	✅	Your Telegram bot token from @BotFather
`WEBHOOK\_URL`	Optional	Your Railway app URL (enables webhook mode)
`OWNER\_ID`	Optional	Your Telegram user ID (for `/clear` command)
Deploy — the bot starts automatically
Commands
Command	Description
Send cards / file	Extract, look up BIN, save to DB, get `.txt`
`/bin 411111`	BIN info + card count
`/bank Chase`	Bank search + card count
`/separate bin 411111`	Get `.txt` file for a BIN
`/separate bank Chase`	Get `.txt` file for a bank
`/stats`	Full database stats
`/clear`	Wipe database (owner only)
Webhook vs Polling
No `WEBHOOK\_URL`: bot runs in long-polling mode — works everywhere, slightly slower
`WEBHOOK\_URL` set: Telegram pushes updates directly — faster, recommended for production
After first deploy, copy your Railway URL (e.g. `https://xyz.up.railway.app`) and add it as `WEBHOOK\_URL`, then redeploy.
