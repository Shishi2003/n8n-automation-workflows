# Algorithmic Thinking 

## Overview

This workflow demonstrates how conditional logic and algorithmic thinking can be applied within n8n to build an intelligent email automation system.

The workflow accepts a user's name and email through an n8n form, determines whether the submitted email belongs to a company or a personal email provider, and automatically follows different execution paths based on that decision.

For company email addresses, the workflow enriches the contact using the People Data Labs API before sending a personalized proposal email.

For personal email addresses, the workflow skips enrichment and immediately sends a generic welcome message.

This project demonstrates the use of decision-making algorithms, JavaScript processing, API integration, and automated email communication.

---

## Workflow Architecture

```text
Form Submission
        │
        ▼
JavaScript Domain Check
        │
        ▼
      IF Node
   ┌───────────────┐
   │               │
Company        Personal
Email          Email
   │               │
   ▼               ▼
People Data     Welcome Email
Labs API
   │
   ▼
Personalized Email
```

---

## Workflow Components

### 1. Form Submission

The workflow begins with an n8n Form Trigger where the user submits:

- Name
- Email Address

The submitted data becomes the input for the automation.

---

### 2. Email Domain Processing

A JavaScript Code node extracts the domain from the submitted email address.

Example:

```
john@gmail.com
```

becomes

```
gmail.com
```

The script compares the extracted domain against a predefined list of public email providers.

Example list:

- gmail.com
- yahoo.com
- hotmail.com
- outlook.com
- icloud.com

If the domain is not found in the list, it is treated as a company email.

---

### 3. Decision Making (IF Node)

The IF node acts as the workflow's decision engine.

Two possible paths exist:

### Company Email

- Continue to People Data Labs
- Retrieve professional information
- Send personalized proposal

### Personal Email

- Skip enrichment
- Send generic welcome email

---

### 4. Company Email Enrichment

For business email addresses, the workflow calls the People Data Labs API.

The API retrieves publicly available professional information, including:

- Full Name
- Company Name
- Job Title
- Work Email
- Professional Profile Information

These details are then prepared for personalization.

---

### 5. Personalized Proposal Email

Using the enriched profile information, the workflow generates a customized email containing:

- Recipient's name
- Company name
- Job title
- Personalized proposal

This makes the communication more relevant and professional.

---

### 6. Generic Welcome Email

If the submitted email belongs to a public email provider, the workflow skips enrichment.

Instead, a simple welcome email is sent thanking the user for signing up.

---

## Algorithm

### Step 1

Receive name and email from the form.

↓

### Step 2

Extract the email domain using JavaScript.

↓

### Step 3

Compare the domain against known public email providers.

↓

### Step 4

IF the email belongs to a company

- Retrieve professional details from People Data Labs
- Build personalized email
- Send proposal

ELSE

- Skip API call
- Send generic welcome email

↓

### Step 5

Email is delivered to the user.

---

## Technologies Used

| Technology | Purpose |
|------------|----------|
| n8n | Workflow Automation |
| JavaScript | Domain Extraction & Logic |
| IF Node | Conditional Decision Making |
| People Data Labs API | Contact Enrichment |
| Gmail API | Email Delivery |
| HTML Email | Personalized Communication |

---

## Decision Logic

```javascript
Extract Email Domain

↓

Is domain in public email list?

↓

Yes ----------------------► Generic Welcome Email

↓

No

↓

Retrieve Professional Profile

↓

Generate Personalized Proposal

↓

Send Email
```

---

## Key Features

- Email domain validation
- JavaScript automation
- Conditional workflow execution
- External API integration
- Dynamic email personalization
- Automated welcome messages
- Business lead identification

---

## Screenshots

### Workflow Overview

Displays the complete automation workflow.



---

## Learning Outcomes

Through this workflow I learned:

- Algorithmic thinking in workflow automation
- Implementing decision-making logic
- Writing JavaScript inside n8n
- Email domain classification
- Conditional branching using IF nodes
- Integrating external APIs
- Dynamic email personalization
- Building intelligent automation workflows

---

## Real-World Applications

This workflow can be adapted for:

- Lead qualification
- CRM automation
- Marketing automation
- Customer onboarding
- Sales prospecting
- Email personalization
- Intelligent contact routing
- Business workflow automation


---

## Conclusion

This workflow demonstrates how algorithmic thinking can be combined with workflow automation to create intelligent business processes. By integrating JavaScript logic, conditional branching, external APIs, and automated email delivery, the workflow responds differently based on user input, making the automation more dynamic, personalized, and practical for real-world use.
