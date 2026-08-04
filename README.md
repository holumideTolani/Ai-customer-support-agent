# AI Customer Support Agent

An AI powered customer support automation built with n8n, Google Gemini, and Google Sheets.

The workflow receives customer messages through a webhook, identifies the customer's intent using AI, retrieves the correct answer from a Google Sheets knowledge base, generates a natural and professional response, and returns the result through an API.

## Features
 Accepts customer messages through a Webhook (API)
 Uses Google Gemini to classify customer intent
 Searches a Google Sheets knowledge base
 Generates professional AI responses
 Returns structured JSON responses
 Designed using scalable workflow architecture

 ## Tech Stack
 n8n
 Google Gemini AI
 Google Sheets
 Webhooks
 REST API
 JSON


## Architecture System Design for AI Customer Support Agent


``text
                Customer
                    │
                    ▼
            Webhook (API)
                    │
                    ▼
             Data Shaping
                    │
                    ▼
      Gemini AI Intent Classifier
                    │
                    ▼
     Google Sheets Knowledge Base
                    │
                    ▼
      Gemini AI Response Generator
                    │
                    ▼
          Respond to Webhook
                    │
                    ▼
             JSON API Response

``  
## Separation of Responsibilities.
| Node                      | Responsibility                   |
| ------------------------- | -------------------------------- |
| Webhook                   | Receive incoming requests        |
| Data Shaping              | Extract and clean the data       |
| Gemini Intent Classifier  | Understand the customer's intent |
| Google Sheets             | Retrieve the approved answer     |
| Gemini Response Generator | Rewrite the answer naturally     |
| Respond to Webhook        | Return the API response          |


## Workflow

1. The customer sends a message through a Webhook.
2. The workflow extracts the customer's name and message.
3. Gemini AI classifies the customer's intent.
4. Google Sheets searches the knowledge base for the matching intent.
5. Gemini AI generates a professional response using the retrieved answer.
6. The workflow returns a structured JSON response.

## API Example

## Request

``json
{
  "customerName": "Olumide Tolani",
  "message": "I forgot my password"
}
`

## Response

``json
{
  "success": true,
  "customer": "Olumide Tolani",
  "intent": "Password Reset",
  "response": "Hi Olumide Tolani, I understand you're having trouble accessing your account. To reset your password, click the 'Forgot Password' link on the login page and follow the instructions sent to your email. Please let us know if you need any further assistance."
}
```
