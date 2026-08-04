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

```
##  Screenshots

## Workflow

![Workflow](screenshots/workflow-overview.png)



### Knowledge Base

![Knowledge Base](screenshots/google-sheet.png)



### API Request

![Request](screenshots/postman-request.png)



### API Response

![Response](AI customer support Agent/<img width="1920" height="1080" alt="postman-response png" src="https://github.com/user-attachments/assets/e3c35e91-8d08-4199-92c7-d5ee36061470" />
<img width="1920" height="1080" alt="postman-request png" src="https://github.com/user-attachments/assets/0ea9c68c-5427-4f2f-b27f-e825c2edc8da" />
<img width="1920" height="1080" alt="google-sheet png" src="https://github.com/user-attachments/assets/f03a02a5-ffc7-4801-9d3b-d4b884a13218" />
<img width="1920" height="1080" alt="workflow-overview png" src="https://github.com/user-attachments/assets/18032654-f884-466b-b51f-f5910c27bb45" />
screenshots/postman-response.png)



##  Project Structure

``
Ai customer support agent/
│
├── README.md
├── LICENSE
├── workflow/
│   └── AI Customer Support Agent.json
├── screenshots/
│   ├── workflow-overview.png
│   ├── google-sheet.png
│   ├── postman-request.png
│   └── postman-response.png
└── docs/
```

```
## Future Improvements

 Add conversation memory
 Integrate WhatsApp Business API
 Add Slack and Microsoft Teams notifications
 Store conversations in PostgreSQL
 Add confidence scoring
 Escalate unknown requests to a human agent
 Replace Google Sheets with a vector database for semantic search
 Add authentication and rate limiting.

 
 ##  Author

Olumide Tolani

AI Automation Engineer passionate about building intelligent workflow automations using AI, APIs, and modern automation tools.

- LinkedIn: (https://www.linkedin.com/in/tolani-olumide-541823243/)
- Portfolio: (https://lummyportfolio-phi.vercel.app/)
- Email: (holumidetolani@gmail.com)
