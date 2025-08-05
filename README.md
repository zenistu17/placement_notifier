# VIT Placement & Internship Notifier Bot

<p align="center">
  <img src="https://img.shields.io/badge/platform-Telegram-blue.svg?style=for-the-badge" alt="Platform: Telegram">
  <img src="https://img.shields.io/badge/built%20with-Google%20Apps%20Script-orange.svg?style=for-the-badge" alt="Built with Google Apps Script">
  <img src="https://img.shields.io/github/license/zenistu17/placement_notifier?style=for-the-badge" alt="License: MIT">
</p>

<p align="center">
  <i>Never miss a placement opportunity again. An intelligent Google Apps Script bot that parses emails from VIT's Career Development Centre (CDC) and instantly forwards them to a Telegram channel.</i>
</p>

---

## Key Features

This bot is designed to be a reliable, fire-and-forget solution for staying updated with placement news.

-   🧠 **Intelligent Parsing:** Accurately extracts key details like Company Name, CTC, Stipend, Role, Eligibility, and Deadlines from complex email formats.
-   📢 **Instant Notifications:** Forwards new placement and internship opportunities to your Telegram channel the moment they are sent by the CDC.
-   🔔 **Automatic Deadline Reminders:** Schedules and sends reminders **6 hours** and **1 hour** before a registration deadline closes.
-   📅 **Daily Summaries:** Sends a consolidated summary of all the day's activities every night at 11:59 PM, ensuring you never miss a thing.
-   🗂️ **Categorized Alerts:** Automatically identifies and tags opportunities as `Super Dream`, `Dream`, `Core`, or `Normal`.
-   ✅ **Handles All Email Types:** Differentiates between new registrations, test schedules, selection lists, and general updates.
-   🛡️ **Robust & Resilient:** Built-in retry logic for sending messages and detailed error logging to ensure high reliability.

---

## Demo

Here's an example of what the notifications look like in Telegram:

<p align="center">
<pre>
🚨 <b>NEW PLACEMENT OPPORTUNITY</b> 🚨
· · ─────── ·𖥸· ─────── · ·
🌟 <b>Company:</b> <b>ExampleCorp</b>
💼 <b>Role:</b> Software Engineer
📊 <b>Category:</b> SUPER DREAM

💰 <b>CTC:</b> 25 LPA
💵 <b>Stipend:</b> 75,000 per month
📍 <b>Location:</b> Bengaluru
⏰ <b>Registration Deadline:</b> <b>10th August 2025 (11.00 pm)</b>
· · ─────── ·𖥸· ─────── · ·
🎓 <b>Eligible Branches:</b>
<code>B.Tech - Computer Science and Engineering
B.Tech - Information Technology
M.Tech - Software Engineering</code>

➡️ All interested and eligible students must register on the portal before the deadline.
· · ─────── ·𖥸· ─────── · ·
📧 <b>Subject:</b> <i>ExampleCorp : Registration : Super Dream Placement - 2026 Batch</i>
🕐 <b>Received:</b> 05/08/2025 15:20
</pre>
</p>

---

## Setup & Deployment

You can deploy your own instance of this bot in just a few minutes.

### Prerequisites

1.  A **Google Account** (for Google Apps Script).
2.  A **Telegram Bot**. Talk to [@BotFather](https://t.me/BotFather) on Telegram to create one and get your **Bot Token**.
3.  A **Telegram Channel** where the bot will send messages. Add your bot to the channel as an administrator. Get your **Channel ID** (e.g., `@your_channel_name`).
4.  **Node.js and npm** installed on your local machine.
5.  **`clasp`** installed globally (`npm install -g @google/clasp`).

### Installation Steps

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/zenistu17/placement_notifier.git](https://github.com/zenistu17/placement_notifier.git)
    cd placement_notifier
    ```

2.  **Log in to `clasp`:**
    Authorize `clasp` to manage your Google Apps Script projects.
    ```bash
    clasp login
    ```

3.  **Create a new Apps Script Project:**
    ```bash
    clasp create --type standalone --title "VIT Placement Notifier"
    ```
    This will create a new script in your Google Drive and link it to your local folder by creating a `.clasp.json` file.

4.  **Set Up Secret Variables:**
    This project uses **Script Properties** to securely store your bot token.
    -   Open the newly created Apps Script project in your browser (`clasp open`).
    -   Go to **Project Settings** (⚙️ icon).
    -   Under **Script Properties**, click **"Add script property"**.
    -   Add the following property:
        -   **Property:** `TELEGRAM_BOT_TOKEN`
        -   **Value:** `your_telegram_bot_token_here`
    -   Click **"Save script properties"**.

5.  **Push Your Code:**
    Upload the code from your local machine to the Apps Script project.
    ```bash
    clasp push
    ```

6.  **Run the Setup Function:**
    -   In the Apps Script editor, select the `setupNotifier` function from the dropdown menu and click **▶ Run**.
    -   You will be asked to grant permissions for the script to access Gmail and other services. **Allow** these permissions.
    -   This will set up the time-based triggers that run the script automatically. A welcome message will be sent to your channel to confirm that the setup was successful.

That's it! Your bot is now live and will monitor your Gmail for placement emails.

---

## License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.
