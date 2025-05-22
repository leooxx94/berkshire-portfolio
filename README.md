# 📰 Berkshire Hathaway 13F Tracker

This script automatically checks the latest 13F-HR filings submitted by Berkshire Hathaway, compares the last 3 filings, highlights portfolio changes (new positions, closed, increased, decreased), and exports everything to Excel. It can also send notifications via email and Telegram.

## 🔧 What It Does

- Fetches the 3 most recent 13F-HR filings.
- Parses and compares portfolio data.
- Calculates share and value changes (absolute and %).
- Saves the results into Excel files.
- Sends updates via:
  - 📧 Email (with files attached)
  - 📲 Telegram bot

## 📤 Outputs

- Full portfolio of latest 13F filing.
- Comparison tables:
  - Latest vs Previous
  - Previous vs Third-latest

## 🖥️ How to Run

You can run the script manually or schedule it (e.g. with `cron`).


## 📩 Configuration: Email and Telegram

The script **does not use `.env`**, so you must manually edit the script and replace emails, password and token.


🔐 Gmail with 2-Step Verification

If your Gmail has 2FA (two-factor authentication), you must use an App Password:

    Visit: https://myaccount.google.com/apppasswords

    Select app: Mail

    Select device: Other → name it (e.g., "13F script")

    Google will generate a 16-character password → use that as password

    Regular Gmail passwords won’t work if 2FA is enabled.



🤖 Telegram Notifications

    Create a bot via @BotFather on Telegram

        Use /newbot and follow the instructions

        Save the bot token

    Get your chat ID

        Send a message to your bot

        Visit: https://api.telegram.org/bot<YourBotToken>/getUpdates

        Find your chat.id in the JSON response



## 📦 Requirements

Install dependencies with:

pip install -r requirements.txt



## 🕒 Automation with cron (Linux/Raspberry Pi)

To run the script every hour between the 13th and 25th of every month:

0 * 13-25 * * /usr/bin/python3 /path/to/berkshire_script.py >> /path/to/log.txt 2>&1
