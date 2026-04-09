Google-Form-auto-email
This Google Apps Script automates the registration process for events by handling ticket package limits, waitlists, and automated email confirmations directly from a Google Form and its associated spreadsheet.

🚀 Features
Automated Email Confirmation: Sends personalized HTML emails to participants upon form submission.

Per-Package Limit Handling: Automatically manages registration status based on predefined ticket capacities (e.g., Package A vs. Package B).

Waitlist Logic: Once a package hits its limit, subsequent registrants are automatically moved to a backup waitlist.

Quota & Error Handling: Includes logic to handle Google’s daily email quota limits by marking failed sends as "Pending" and alerting admins to script errors.

Bulk Send Tool: Features a manual function (sendPendingEmails) to bulk-process any registrations that were marked as pending due to quota exhaustion.

🛠 Configuration
The script uses a CONFIG object to manage event-specific details:

FORM_ID: The unique ID of your Google Form.

RESPONSE_SHEET_NAME: The exact name of the tab in your spreadsheet where responses are stored.

TICKETS: Define your packages, prices, confirmed capacity, and waitlist limits.

BANK: Information for fee collection, including account holder and DuitNow details.

📋 Functions
onFormSubmit(e): The primary trigger function that runs every time a form is submitted.

processSubmission(...): Core logic that calculates a participant's position in the queue and generates their specific email content.

sendPendingEmails(): A maintenance tool to re-attempt sending emails to users currently marked with a "Pending" status.

checkQuota(): A utility function to log your remaining daily Google email quota.

🔧 Setup Instructions
Open the Google Sheet linked to your Google Form.

Navigate to Extensions > Apps Script.

Copy the code from main.js into the script editor.

Update the CONFIG constants with your specific event details (ID, dates, and package limits).

Set up an "On form submit" trigger for the onFormSubmit function in the Apps Script Triggers dashboard.

Ensure your spreadsheet headers include a "Status" column (the script will attempt to create it if it's missing).

Developed for MAID 2026 by MMI Young Medics.# Google-Form-auto-email
