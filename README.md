
# Feedback Collector & Notifier (n8n Workflow)

This n8n workflow collects feedback via a webhook, stores it in a Google Sheet, and sends a notification email.

📌 Workflow Summary
- Trigger: Webhook (`POST`)
- Input Fields: `name`, `email`, `message`
- Set Node: Adds timestamp (`submittedAt`) to the data
- Google Sheets Node: Appends data to a specific sheet
- Gmail Node: Sends an email with the collected feedback

✅ How to Use

1. Webhook Setup
   - Use the Webhook URL: `POST /webhook/feedback-collector`
   - Send a JSON body like:
     ```json
     {
       "name": "Ashley",
       "email": "ashley@example.com",
       "message": "Great experience!"
     }
     ```

2. Set Node
   - Adds a timestamp `submittedAt` using `new Date().toISOString()`

3. Google Sheets Node
   - Connect to your Google Sheets account
   - Set sheet to log: `name`, `email`, `message`, `submittedAt`

4. Gmail Node
   - Sends an email to `ashleymathias100@gmail.com`
   - Subject: `New Feedback from <name>`
   - Message includes all collected data

🔐 Credentials Required
- Google Sheets OAuth2 (with access to your target spreadsheet)
- Gmail OAuth2 (for sending emails)

📂 Files
- `feedback_collector_n8n_workflow.json`: Contains the complete workflow



© 2025 | Ashley Mathias | For learning and development purposes.
