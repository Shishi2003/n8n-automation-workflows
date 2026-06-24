# LM-002: AI-Powered Email Automation with n8n and Gemini AI

## Overview

This workflow demonstrates how Artificial Intelligence can be integrated into business automation using **n8n**, **Google Gemini AI**, and **Gmail**.

The workflow automatically generates and sends personalized email responses based on user submissions from an online form. When a user enters their name, email address, and message, the data is processed by a Gemini Large Language Model (LLM), which creates a context-aware reply. The generated response is then delivered to the user through Gmail without requiring any manual intervention.

This project showcases the practical application of AI-powered workflow automation and dynamic content generation.

---

## Workflow Architecture

```text
Form Submission
       ↓
Google Gemini LLM
       ↓
Gmail Auto Reply
```

---

## Workflow Components

### 1. Form Submission Trigger

The workflow begins with an n8n Form Trigger node that collects user input.

#### Fields Captured

* Name
* Email Address
* Message

#### Example Input

```json
{
  "name": "Aryan",
  "email": "aryanma777@gmail.com",
  "message": "Fantastic"
}
```

The submitted information becomes available to subsequent workflow nodes for processing.

---

### 2. Gemini AI Processing

The submitted form data is passed to a Gemini LLM Chain node.

The AI model receives a prompt instructing it to generate a professional and friendly email response based on the user's message.

#### Prompt Objective

* Generate a personalized reply
* Maintain a professional tone
* Reference the user's message
* Create natural human-like communication

#### Example AI Output

```text
Hello Aryan,

Thank you for your fantastic message! We truly appreciate your positive feedback.

Warm regards,
```

This enables dynamic content generation instead of relying on predefined email templates.

---

### 3. Gmail Email Delivery

The generated response is sent automatically using the Gmail node.

#### Features

* OAuth Authentication
* Dynamic recipient mapping
* AI-generated email body
* Automated delivery

The recipient email address is obtained directly from the form submission data.

---

## Technologies Used

| Technology         | Purpose                  |
| ------------------ | ------------------------ |
| n8n                | Workflow orchestration   |
| Google Gemini AI   | Email content generation |
| Gmail API          | Automated email delivery |
| OAuth 2.0          | Secure authentication    |
| Prompt Engineering | Response customization   |

---

## Workflow Logic

### Step 1

User submits a form containing:

* Name
* Email
* Message

### Step 2

The form data is passed to the Gemini AI node.

### Step 3

Gemini generates a personalized response based on the submitted message.

### Step 4

The generated content is forwarded to the Gmail node.

### Step 5

An email is automatically sent to the submitted email address.

---

## Sample Execution

### User Submission

```json
{
  "name": "Aryan",
  "email": "aryanma777@gmail.com",
  "message": "Fantastic"
}
```

### AI Generated Response

```text
Hello Aryan,

Thank you for your fantastic message! We truly appreciate your positive feedback.

Warm regards,
```

### Email Delivery

The generated message is automatically sent through Gmail to the user's email address.

---

## Screenshots

### Workflow Overview

Displays the complete workflow architecture and node connections.

### Form Submission Node

Shows the form trigger configuration and captured input data.

### Gemini LLM Chain

Demonstrates AI prompt processing and response generation.

### Gmail Node

Shows automated email delivery using Gmail integration.

---

## Key Learning Outcomes

Through this project I learned:

* Building event-driven workflows using n8n
* Integrating Large Language Models into automation pipelines
* Using prompt engineering for dynamic content generation
* Passing data between workflow nodes
* Configuring Gmail OAuth authentication
* Designing automated communication systems
* Testing and debugging workflow executions

---

## Real-World Applications

This workflow can be adapted for:

* Customer support automation
* Contact form auto-responses
* Feedback acknowledgment systems
* Lead engagement workflows
* AI-powered email assistants
* Business inquiry handling

---

## Live Demo

**Form URL**

https://n8n.srv965596.hstgr.cloud/form/9f449660-323e-4f07-8289-c0892074eab2

---

## Conclusion

This project demonstrates how AI can be combined with workflow automation to create intelligent communication systems. By integrating Google Gemini AI with n8n and Gmail, the workflow automatically generates personalized responses and delivers them instantly, reducing manual effort while improving user engagement.


