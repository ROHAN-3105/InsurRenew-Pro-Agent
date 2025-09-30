# API Specification Summary

[cite_start]This document outlines the specifications for the APIs required by the InsurRenew Pro agent[cite: 53].

### Document Parsing API
* [cite_start]*Purpose:* Ingests a policy document to extract structured data[cite: 59].
* *Method:* POST
* [cite_start]*Endpoint:* /v1/policy/parse [cite: 59]
* [cite_start]*Request Body:* { "file_url": "<URL>" } [cite: 60]
* [cite_start]*Response Body:* { "policy_number": "...", "expiry_date": "...", ... } [cite: 61]

### Payment API
* [cite_start]*Purpose:* Initiates a payment and generates a secure link[cite: 68].
* *Method:* POST
* [cite_start]*Endpoint:* /v1/payments/initiate [cite: 68]
* [cite_start]*Request Body:* { "policy_number": "...", "amount": ..., "return_url": "..." } [cite: 70]
* [cite_start]*Response Body:* { "payment_link": "https://...", "id": "..." } [cite: 72]

### SMS Notification API (Twilio)
* [cite_start]*Purpose:* Sends an SMS to the customer[cite: 73].
* *Provider:* Twilio
* *Method:* POST
* *Endpoint:* (Uses the official Twilio Messaging API endpoint)
* [cite_start]*Logical Request Body:* { "to": "+91...", "text": "..." } [cite: 74]

### Slack Notification API
* *Purpose:* Sends a real-time alert to an internal Slack channel for human agent handoffs.
* *Provider:* Slack (Incoming Webhook)
* *Method:* POST
* *Endpoint:* https://hooks.slack.com/services/...
* *Request Body:* { "text": "Human agent requested! Customer: Riya Sharma..." }