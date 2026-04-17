# n8n-lead-generation
This README provides a comprehensive overview of a Lead Generation Workflow built in n8n. This template is designed to automate the journey from initial contact to CRM entry, ensuring no potential client slips through the cracks.

🚀 n8n Lead Generation & Automation Workflow
This workflow automates the process of capturing, qualifying, and routing leads. It connects your front-end capture tools (like Typeform or Webhooks) with your backend CRM and communication stacks (like HubSpot, Slack, and Gmail).

🛠 Features
Multi-Channel Capture: Ingest leads via Webhooks, HTML forms, or Typeform.
Lead Enrichment: Automatically fetch company data using APIs like Clearbit or Apollo (optional nodes).
Smart Filtering: Uses If-Nodes to filter out "junk" emails (e.g., test@test.com) or non-business domains.
CRM Integration: Automatically creates or updates contacts in HubSpot/Salesforce/Pipedrive.
Instant Notifications: Alerts the sales team via Slack or Discord the moment a high-value lead arrives.
Email Auto-Responder: Sends a personalized "Thank You" or a scheduling link via Gmail/Outlook.
🏗 Workflow Architecture
Trigger: Webhook or Form Submission.
Data Cleaning: Format names (Capitalization) and normalize email addresses.
Qualification: Check if the lead meets specific criteria (e.g., Company Size > 10).
Branching: * Qualified: Push to CRM + Notify Sales.
Unqualified: Add to a "Nurture" list in Mailchimp/SendGrid.
Completion: Log the execution in a Google Sheet for reporting.

📋 Prerequisites
To use this workflow, you will need:
n8n (Self-hosted or Cloud version).
API Credentials for your specific tools:
CRM: HubSpot API Key / OAuth2.
Messaging: Slack Webhook URL.
Email: Gmail or SMTP credentials.
🚀 Setup Instructions
Import the Workflow:

Copy the JSON content of the workflow.
In n8n, click New -> Import from File/URL or simply paste the JSON into the canvas.
Configure Credentials:
Open each node with an orange warning icon.
Click "Select Credential" and add your specific API keys
Set the Webhook:
If using a Webhook trigger, copy the Production URL.
Point your lead source (e.g., Webflow form, Elementor) to this URL.

Test:
Switch to "Test" mode in n8n.
Submit a dummy lead and watch the data flow through the nodes.

⚙️ Customization

Pro Tip: You can easily add an OpenAI node after the capture trigger to "summarize" the lead's message or categorize their intent before it hits your CRM.
To change the threshold for "Hot Leads": Edit the If node logic.
To change the CRM: Swap the HubSpot node for a Pipedrive or Zoho node.
📊 Performance Tracking
The final node in this workflow appends data to a Google Sheet. This allows you to build a simple dashboard to track:
Total leads captured.
Conversion rate (Qualified vs. Unqualified).
Response time.
