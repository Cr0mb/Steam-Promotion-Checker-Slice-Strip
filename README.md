# Slice Strip Steam Promotion Checker 

A Python script that continuously monitors Steam for **high-discount promotions (80% or more)** and notifies you via email when new deals appear.

---

![image](https://github.com/user-attachments/assets/4e1294fd-6c64-4553-82af-16e6e7f1d91b)


## Features

* Automatically fetches daily Steam promotions with large discounts.
* Filters promotions with at least 80% discount.
* Sends email notifications with details of new promotions.
* Avoids duplicate notifications by keeping track of seen promotions.
* Runs continuously, checking once every 24 hours.

---

## Requirements

* Python 3.x
* `requests` library
* Access to an SMTP email server (tested with Gmail SMTP)

Install dependencies with:

```bash
pip install requests
```

---

## Configuration

Before running the script, edit the following variables in the script to your own credentials and preferences:

```python
SENDER_EMAIL = "your_email@gmail.com"
SENDER_PASSWORD = "your_email_password_or_app_specific_password"
RECEIVER_EMAIL = "receiver_email@example.com"
```

> **Note:** For Gmail accounts, you may need to generate an [App Password](https://support.google.com/accounts/answer/185833) if you have 2FA enabled.

---

## How It Works

1. The script fetches the current Steam promotions JSON from the Steam store.
2. Extracts app IDs from promotion logos to get detailed app information.
3. Checks the discount percentage and price.
4. If the discount is 80% or more and the promotion hasn't been seen before, it sends an email notification.
5. Stores seen promotions in a local text file `seen_promotions.txt` to avoid duplicate alerts.
6. Repeats this process every 24 hours.

---

## Usage

Simply run the script with Python:

```bash
python promo.py
```

The script will print status messages to the console and send email alerts when new high-discount promotions are found.

---

## Files

* `promo.py`: Main script file.
* `seen_promotions.txt`: Automatically generated file that stores already notified promotions.

---

## Troubleshooting

* **Email not sending?**

  * Check your SMTP credentials.
  * For Gmail, ensure "Less secure app access" is enabled or use an app password.
* **API errors or no promotions found?**

  * Steam may have changed their API or endpoint — check the URL and JSON structure.

---


