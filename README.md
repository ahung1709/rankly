# Face Recognition Brain – Rank Badge Serverless AWS Lambda

This repository contains a lightweight **serverless function** that converts a user’s face-detection entry count into a **visual rank badge (emoji)**.

This service is deployed on **AWS Lambda using the Serverless Framework** and is **invoked directly by the frontend**, demonstrating a scalable and decoupled architecture.

---

## 🧩 Related Repositories

- 🔗 **Frontend:** https://github.com/ahung1709/facerecognitionbrain

  User authentication, image submission, and UI rendering

- 🔗 **Backend API:** https://github.com/ahung1709/facerecognitionbrain-api

  JWT auth, Redis sessions, PostgreSQL persistence, Clarifai API integration

---

## 🛠 Tech Stack

- AWS Lambda
- Serverless Framework
- Node.js
- JavaScript

---

## 🚀 Live Role in the System

- Called **directly by the React frontend**
- Returns a rank emoji based on entry count
- Reduces backend workload
- Demonstrates **serverless-first design**

---

## 🧠 Function Overview

**Function Name:** `rank`

**Responsibility:**

- Accept a numeric `rank` (entry count) via query string
- Map the rank value to a corresponding emoji badge
- Safely cap values safely to prevent out-of-range access
- Return a JSON response with the selected emoji

---

## 🔌 API Contract

### Endpoint

```http
GET /rank?rank=<number>

```

### Example Request

```http
GET https://<lambda-url>/rank?rank=5
```

### Example Response

```json
{
  "message": "Go Serverless v4.0! Your function executed successfully!",
  "input": "😍"
}
```

Note: The input field represent the computed rank badge emoji

### HTTP Status Codes

- 200 OK - successful execution

---

## ⚙️ Local Development

### Install dependencies

```bash
npm install
```

### Invoke locally

```bash
serverless invoke local \
  --function rank \
  --data '{"queryStringParameters":{"rank":3}}'
```

---

## 🚀 Deployment

```bash
serverless deploy
```

---

## 🧠 Design Rationale

This Lambda function is intentionally isolated to:

- Demonstrate serverless architecture patterns
- Reduce backend responsibilities
- Improve scalability and fault isolation
- Showcase real-world cloud integration
