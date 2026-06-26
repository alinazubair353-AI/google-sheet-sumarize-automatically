# 📧 Google Sheets → Gmail Automation | n8n Workflow

> Automatically send Gmail emails whenever a new row is added to Google Sheets — built with n8n as part of the **Learn AI Automation** course.

---

## 🔥 What This Workflow Does

| Step | Node | Action |
|------|------|--------|
| 1️⃣ | **Google Sheets Trigger** | Watches for new rows (`rowAdded` event) |
| 2️⃣ | **Send a Message (Gmail)** | Sends email automatically to each new entry |
<img width="1365" height="724" alt="image" src="https://github.com/user-attachments/assets/880f6876-8a45-42f7-a6cb-c116074fdb95" />

When a new employee/record is added to Google Sheets → Gmail instantly sends a message. No manual work needed!

---

## 🛠️ Tech Stack

- **n8n** (local instance — `localhost:5678`)
- **Google Sheets API** (OAuth2)
- **Gmail API** (OAuth2)
- **Google Cloud Console** (for credentials)

---

## ⚙️ Setup Instructions

### 1. Prerequisites
- n8n installed locally (`npm install -g n8n`)
- Google Cloud Console project with:
  - Google Sheets API enabled
  - Gmail API enabled
  - OAuth2 credentials created

### 2. Configure Credentials in n8n
1. Go to **Settings → Credentials**
2. Add **Google Sheets OAuth2** credential
3. Add **Gmail OAuth2** credential
4. Authorize both with your Google account

### 3. Import Workflow
1. Download `workflow.json` from this repo
2. Open n8n → **Workflows → Import from File**
3. Select the downloaded file

### 4. Set Up Google Sheets Trigger
- Connect your Google Sheet
- Set trigger event to: `Row Added`
- Select the correct sheet/tab

### 5. Configure Gmail Node
- Set **To**, **Subject**, and **Body** fields
- Map values from Google Sheets columns using expressions like:
  ```
  {{ $json["Email"] }}
  {{ $json["Name"] }}
  ```

### 6. Activate Workflow
- Click **Publish** toggle (top right)
- Workflow is now live! ✅

---

## 📊 Workflow Output (Test Result)

Successfully processed **2 items** in **4.069 seconds**:

```
Gmail Message 1: SENT ✓ (also in INBOX)
Gmail Message 2: SENT ✓
```

---

## 📁 Project Structure

```
📦 n8n-sheets-gmail-automation
 ┣ 📄 README.md          ← You are here
 ┣ 📄 workflow.json      ← n8n workflow export
 ┗ 📄 screenshot.png     ← Workflow canvas screenshot
```

---

## 💡 Use Cases

- **Employee onboarding** — auto email when new employee added to sheet
- **Order notifications** — alert when new order recorded
- **Event registrations** — confirm signup via email automatically
- **Lead follow-ups** — instant email to new leads in CRM sheet

---

## 🎓 Course Context

This project is part of my **Learn AI Automation** journey using n8n.

**Skills practiced:**
- n8n workflow building
- Google API OAuth2 integration
- Trigger-based automation
- Data mapping between nodes

---
## 👩‍💻 Author

Alina Zubair
