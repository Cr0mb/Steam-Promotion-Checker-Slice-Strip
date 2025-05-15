

![image](https://github.com/user-attachments/assets/4e1294fd-6c64-4553-82af-16e6e7f1d91b)

Here is a professional and clean `README.md` for your `promo.py` project:

---

# Steam Promotion Checker

**Slice Strip** – A 24/7 script that automatically monitors and notifies you via email when Steam games go on sale with discounts of **80% or more**, or become **100% free**.

## Features

* Scans the Steam store for special promotions and discounts.
* Filters promotions by:

  * Games that are free.
  * Games discounted by 80% or more.
* Sends an email notification with all new qualifying promotions.
* Avoids duplicate alerts using a local history file.
* Color-coded terminal output for quick readability.
* Automatically checks every 24 hours.

## Requirements

* Python 3.6+
* Required Python packages:

  * `requests`
  * `colorama`
  * `pyfiglet`

Install dependencies with:

```bash
pip install requests colorama pyfiglet
```

## Setup

1. **Email Credentials**:
   Set your Gmail sender and receiver emails and password in the script:

   ```python
   SENDER_EMAIL = "your_email@gmail.com"
   SENDER_PASSWORD = "your_app_password"
   RECEIVER_EMAIL = "receiver_email@gmail.com"
   ```

   > You must use a Gmail App Password (not your main password). See [Google App Passwords](https://support.google.com/accounts/answer/185833?hl=en) for instructions.

2. **Run the Script**:

   ```bash
   python promo.py
   ```

   The script will display all found promotions in the terminal and email them to the configured address.

3. **Seen Promotions Tracking**:
   Seen promotions are saved in `seen_promotions.txt` to avoid repeated alerts.

## How It Works

* Fetches promotions from the [Steam Specials page](https://store.steampowered.com/search/?specials=1).
* Uses app logos to extract Steam app IDs.
* Pulls detailed information via Steam's public API.
* Filters out low-discount or duplicate entries.
* Sends an email with formatted results.
* Sleeps for 24 hours and repeats.

## Customization

* Modify the `CHECK_INTERVAL` to change how often promotions are checked:

  ```python
  CHECK_INTERVAL = 24 * 60 * 60  # 24 hours in seconds
  ```

* Adjust the discount threshold inside `fetch_promotions()` to track different discount levels.


