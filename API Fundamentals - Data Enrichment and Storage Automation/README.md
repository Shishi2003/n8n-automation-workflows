# API Fundamentals - Data Enrichment and Storage Automation

## Overview

This workflow demonstrates how external APIs can be integrated into an automation pipeline to enrich user data and store the results for future use.

The workflow accepts an email address through an n8n form, uses the People Data Labs API to retrieve publicly available professional and profile information associated with that email, and stores the enriched data in JSONBin.io.

The result is a simple but powerful data enrichment system that transforms a single email address into a structured user profile without requiring any manual research.

---

## Workflow Architecture

```text
Form Submission
       ↓
People Data Labs API
       ↓
Retrieve Existing JSONBin Data
       ↓
Transform & Append Data
       ↓
Update JSONBin Storage
```

---

## Workflow Components

### 1. Form Submission Trigger

The workflow begins with an n8n form that collects an email address from the user.

#### Input Example

```json
{
  "email": "bill.gates@microsoft.com"
}
```

The submitted email becomes the primary identifier used for profile enrichment.

---

### 2. People Data Labs API Enrichment

The workflow sends the submitted email address to the People Data Labs Person Enrichment API.

The API searches publicly available professional information and returns a structured profile.

#### Information Retrieved

* Full Name
* First Name
* Last Name
* Gender
* LinkedIn Profile
* Social Media Profiles
* Job Information
* Industry Information
* Professional Details

#### Example Output

```json
{
  "full_name": "Bill Gates",
  "first_name": "Bill",
  "last_name": "Gates",
  "linkedin_url": "linkedin.com/in/billgates",
  "industry": "Computer Software"
}
```

---

### 3. Retrieve Existing JSONBin Data

Before storing new data, the workflow retrieves the current contents of a JSONBin database.

This step ensures that previously stored records are preserved.

The existing dataset is loaded into memory and prepared for updates.

---

### 4. Data Transformation

The workflow uses an Edit Fields node to merge the newly enriched profile with the existing JSON structure.

The submitted email address is used as a unique identifier.

Example structure:

```json
{
  "bill.gates@microsoft.com": {
    "full_name": "Bill Gates",
    "industry": "Computer Software"
  }
}
```

---

### 5. JSONBin Storage Update

After merging the new profile data, the workflow updates the JSONBin database using an HTTP PUT request.

This effectively creates a continuously growing directory of enriched user profiles.

Benefits:

* Persistent storage
* Structured JSON format
* Easy retrieval for future workflows
* No database setup required

---

## Technologies Used

| Technology           | Purpose             |
| -------------------- | ------------------- |
| n8n                  | Workflow Automation |
| People Data Labs API | Data Enrichment     |
| JSONBin.io           | Data Storage        |
| REST APIs            | Data Exchange       |
| JSON Processing      | Data Transformation |

---

## Workflow Logic

### Step 1

User submits an email address.

### Step 2

People Data Labs API receives the email.

### Step 3

Professional and profile information is retrieved.

### Step 4

Existing JSONBin records are fetched.

### Step 5

New profile information is merged into the dataset.

### Step 6

Updated data is stored back in JSONBin.

---

## Example Use Case

### Input

```json
{
  "email": "bill.gates@microsoft.com"
}
```

### Enriched Output

```json
{
  "full_name": "Bill Gates",
  "first_name": "Bill",
  "last_name": "Gates",
  "linkedin_url": "linkedin.com/in/billgates",
  "industry": "Computer Software"
}
```

### Storage Result

The profile is appended to the JSONBin dataset and becomes available for future automation workflows.

---

## Screenshots

### Workflow Overview

Displays the complete workflow architecture and node sequence.



---

## Learning Outcomes

Through this project I learned:

* Working with REST APIs in n8n
* API authentication and query parameters
* Data enrichment techniques
* JSON data manipulation
* HTTP GET and PUT requests
* Persistent cloud-based data storage
* Workflow debugging and testing
* Building reusable automation pipelines

---

## Real-World Applications

This workflow can be adapted for:

* Lead enrichment systems
* CRM data enhancement
* Sales prospecting workflows
* User profile aggregation
* Contact intelligence platforms
* Marketing automation systems

---


## Conclusion

This workflow demonstrates how APIs can be used to enrich raw user data and convert simple inputs into valuable structured information. By combining People Data Labs with JSONBin and n8n, the system creates an automated data enrichment pipeline that can serve as the foundation for CRM systems, lead generation tools, and business intelligence workflows.
