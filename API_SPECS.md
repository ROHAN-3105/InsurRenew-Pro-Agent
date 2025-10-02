# API Specification Summary

This document outlines the specifications for the APIs required by the InsurRenew Pro agent.

### Document Parsing API
* Purpose: Ingests a policy document to extract structured data.
* Method: POST
* Endpoint: /v1/policy/parse or https://webhook.site/beebaed7-34cc-438f-9ccf-d7bd89825723 ( test API request for datafetch )
* Request Body: { "file_url": "<URL>" }
* Response Body: { "policy_number": "...", "expiry_date": "...", ... }

### Payment API
* Purpose: Initiates a payment and generates a secure link.
* Method: POST
* Endpoint: /v1/payments/initiate
* Request Body: { "policy_number": "...", "amount": ..., "return_url": "..." }
* Response Body: { "payment_link": "https://...", "id": "..." }

### SMS Notification API (Twilio)
* Purpose: Sends an SMS to the customer.
* Provider: Twilio
* Method: POST
* Endpoint: (Uses the official Twilio Messaging API endpoint)
* Logical Request Body: { "to": "+91...", "text": "..." }

### Slack Notification API
* Purpose: Sends a real-time alert to an internal Slack channel for human agent handoffs.
* Provider: Slack (Incoming Webhook)
* Method: POST
* Endpoint: https://hooks.slack.com/services/...
* Request Body: { "text": "Human agent requested! Customer: Riya Sharma..." }

