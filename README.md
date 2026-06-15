# 📋 Lead Collection Automation (n8n Workflow)

[![n8n](https://img.shields.io/badge/n8n-Cloud-FF6C37?style=flat&logo=n8n&logoColor=white)](https://n8n.io/)
[![Google Sheets](https://img.shields.io/badge/Google%20Sheets-API-34A853?style=flat&logo=google-sheets&logoColor=white)](https://developers.google.com/sheets/api)
[![Webhook](https://img.shields.io/badge/Trigger-Webhook-blueviolet?style=flat)](https://n8n.io/)

A production-ready **n8n automation workflow** that serves as an instant lead capturing system. It completely replaces manual data entry by exposing a dynamic Webhook endpoint that listens for incoming leads and appends them to Google Sheets in real time.

---

## ⚙️ What It Does

This workflow acts as a bridge between your lead generation sources (landing pages, forms, ads) and your database. As soon as a user submits their contact information, the workflow triggers instantly, parses the payload, and logs the details without any delay.

### 📊 Data Captured
*   👤 **Name** (Full Name of the prospect)
*   📧 **Email Address** (For direct marketing/follow-ups)
*   📞 **Phone Number** (For sales outreach)

### 💼 Key Use Cases
*   **Landing Page Forms:** Directly sync Elementor, Webflow, or custom forms to your sales sheet.
*   **Paid Ad Campaigns:** Capture incoming leads from Facebook or Google Lead Ads instantly.
*   **CRM Ingestion:** Pre-populate your pipeline before the sales team starts sorting data.

---

## 🛠️ Built With

*   **n8n Cloud:** The cloud infrastructure powering the seamless transfer of data.
*   **Google Sheets API:** Secure API communication to append rows asynchronously.

### Nodes Architecture
1.  **Webhook Trigger Node:** Listens for `POST` or `GET` requests containing user objects from any front-end form.
2.  **Google Sheets Node:** Connects via Google OAuth2 to securely write and organize rows inside the specified spreadsheet.

---

## 🚀 How to Setup & Import

Follow these steps to deploy this workflow in your own environment:

### 1. Import the Workflow
*   Copy the raw JSON content from the `workflow.json` file in this repository.
*   Open your **n8n canvas** and press `Ctrl + V` (Windows) or `Cmd + V` (Mac) to paste the nodes.

### 2. Configure the Webhook
*   Open the **Webhook Node** and copy the **Production URL** (or Test URL for debugging).
*   Paste this URL into your form provider's integration settings (e.g., WordPress Webhooks, Typeform, or custom JS fetch).

### 3. Connect Google Sheets
*   Click on the **Google Sheets Node**.
*   Link your Google Account using **OAuth2**.
*   Select the **Resource:** `Document` and **Operation:** `Append Row`.
*   Choose your specific Spreadsheet and Map the incoming Webhook keys (Name, Email, Phone) to your Sheet's headers.

### 4. Go Live
*   Test the connection with dummy data to verify routing.
*   Toggle the workflow status from **Inactive** to **Active** (Top Right Corner).

---

## 🔒 Security Note
> **Note:** The `workflow.json` file uploaded here does **not** contain any personal credentials, spreadsheet IDs, or webhook tokens. n8n automatically strips sensitive configurations during export, making it safe to share publicly on GitHub.
