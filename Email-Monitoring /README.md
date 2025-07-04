# 📧 Email Monitoring & Refund Request Automation (n8n)

This n8n workflow monitors a Gmail inbox for emails with the subject **"Refund Request Form"**, extracts structured data using OpenAI (GPT-4.1-mini), and logs the results in a connected Google Sheet. It also detects and optionally handles attachments.

## 🔧 Features

- ✅ Gmail polling every minute
- 🧠 GPT-powered field extraction from email content
- 📄 Appends data to Google Sheets (auto updates if entry exists)
- 📎 Detects and logs attachment presence
- 🧼 Cleans OpenAI response and parses it into structured JSON

## 📥 Extracted Fields

- `name`
- `phone`
- `email`
- `address`
- `pickup_address`
- `delivery_address`
- `amount_charged`
- `payment_person_name`
- `payment_method`
- `transaction_date`
- `refund_reason`
- `todays_date`
- `has_attachments`

## 🔗 Requirements

- Gmail account with OAuth2 credentials connected to n8n
- OpenAI API key (GPT-4.1-mini or GPT-3.5)
- Google Sheet with matching column headers
- n8n instance (self-hosted or cloud)

## 📁 Optional Attachment Handling

Attachments are detected and can be:

- Logged into the Google Sheet (`has_attachments`)
- Uploaded to Google Drive (with additional setup)

## Demo

<img width="1317" alt="Screenshot 2025-07-04 at 6 00 21 PM" src="https://github.com/user-attachments/assets/1bb7dceb-4fe8-42b1-8d3b-1fd93be5f564" />

## 📌 Notes

- Emails are filtered using Gmail's search query:  
  `subject:"Refund Request Form"`
- OpenAI is instructed to return **pure JSON only**, no explanations or prose
- JSON parsing includes error handling for malformed responses

---
