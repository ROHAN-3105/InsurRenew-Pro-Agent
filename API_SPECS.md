# API Specification Summary

[cite_start]This document outlines the specifications for the APIs required by the InsurRenew Pro agent[cite: 53].

### 1. Document Parsing API
* **Method:** `POST`
* [cite_start]**Endpoint:** `/v1/policy/parse` [cite: 59]
* [cite_start]**Request Body:** `{ "file_url": "<URL>" }` [cite: 60]
* [cite_start]**Response Body:** `{ "policy_number": "...", "expiry_date": "...", ... }` [cite: 61]

### 2. Intent Detection API
* **Method:** `POST`
* [cite_start]**Endpoint:** `/v1/nlp/intent` [cite: 62]
* [cite_start]**Request Body:** `{ "text": "I will renew today" }` [cite: 63]
* [cite_start]**Response Body:** `{ "intent": "renew_now", "confidence": 0.94 }` [cite: 64]

### 3. Sentiment Analysis API
* **Method:** `POST`
* [cite_start]**Endpoint:** `/v1/nlp/sentiment` [cite: 65]
* **Request Body:** `{ "text": "Sounds good. Go ahead." [cite_start]}` [cite: 66]
* [cite_start]**Response Body:** `{ "sentiment": "positive", "score": 0.81 }` [cite: 67]

### 4. Payment API
* **Method:** `POST`
* [cite_start]**Endpoint:** `/v1/payments/initiate` [cite: 68]
* [cite_start]**Request Body:** `{ "policy_number": "...", "amount": ..., "return_url": "..." }` [cite: 70]
* [cite_start]**Response Body:** `{ "payment_link": "https://...", "id": "..." }` [cite: 72]

### 5. Notifications API (SMS)
* **Method:** `POST`
* [cite_start]**Endpoint:** `/v1/notify/sms` [cite: 73]
* [cite_start]**Request Body:** `{ "to": "+91...", "text": "..." }` [cite: 74]
* [cite_start]**Response Body:** `{ "status": "sent", "id": "..." }` [cite: 75]