# JavaScript for Automation - Lead Qualification and Data Transformation

## Overview

This workflow demonstrates how JavaScript can be used within n8n to process, filter, and transform structured JSON data into meaningful business information.

The workflow retrieves enriched user profile data stored in JSONBin from the previous module and processes it using a custom JavaScript Code node. The script recursively extracts lead records, filters out personal email providers such as Gmail, Yahoo, and Hotmail, and generates a clean dataset containing only qualified business leads.

The resulting output is a structured list of professional contacts with company-related information that can be used for CRM systems, lead generation, or sales automation.

---

## Workflow Architecture

```text
Retrieve JSON Data (JSONBin)
            ↓
     JavaScript Code Node
            ↓
Filter & Transform Leads
            ↓
Formatted Qualified Leads
```

---

## Workflow Components

### 1. Retrieve Lead Data

The workflow begins by retrieving enriched profile information stored in JSONBin during Module 3.

The JSON contains multiple user profiles indexed by email address.

---

### 2. JavaScript Data Processing

A custom JavaScript Code node processes the retrieved JSON.

The script performs several operations:

* Recursively traverses nested JSON objects
* Extracts all lead records
* Converts object entries into an array
* Filters out personal email providers
* Maps relevant company information
* Produces a clean output structure

---

### 3. Lead Qualification

Only business email addresses are retained.

The workflow excludes common public email providers such as:

* gmail.com
* yahoo.com
* hotmail.com

This ensures the output focuses only on professional contacts.

---

### 4. Data Transformation

For every qualified lead, the workflow extracts the following business attributes:

* Email
* Company Name
* Company Domain
* Employee Count
* Industry
* Company Location

The output is formatted into a clean JSON array suitable for downstream automation.

---

## JavaScript Logic

The workflow uses JavaScript to automate lead qualification and data transformation.

### Main Functions

* Recursive JSON traversal
* Object flattening
* Email domain filtering
* Company information extraction
* JSON formatting

### Business Rules

* Ignore public email providers
* Retain only professional/company emails
* Extract company information from experience data when available
* Produce standardized output fields

---

## Sample Output

```json
[
  {
    "email": "bharat@jivrus.com",
    "company_name": "Jivrus Technologies",
    "company_domain": "jivrus.com",
    "employee_count": "11-50",
    "industry": "Computer Software",
    "location": "Kadugodi, Karnataka, India"
  },
  {
    "email": "sundar@google.com",
    "company_name": "Google",
    "company_domain": "google.com",
    "employee_count": "10001+",
    "industry": "Computer Software",
    "location": "Mountain View, California, United States"
  }
]
```

---

## Technologies Used

| Technology       | Purpose             |
| ---------------- | ------------------- |
| n8n              | Workflow Automation |
| JavaScript       | Data Processing     |
| JSONBin          | Data Source         |
| JSON             | Data Transformation |
| Custom Code Node | Business Logic      |

---

## Workflow Logic

### Step 1

Retrieve enriched lead data from JSONBin.

### Step 2

Traverse the JSON recursively to locate all lead records.

### Step 3

Convert nested objects into a flat array.

### Step 4

Filter out leads using public email domains.

### Step 5

Extract company-related information from each professional profile.

### Step 6

Generate a standardized JSON output containing qualified business leads.

---

## Why This Workflow Matters

Raw API data is often deeply nested and difficult to use directly.

This workflow demonstrates how custom JavaScript can transform complex JSON into business-ready datasets that are easier to analyze and integrate into other systems.

---

## Workflow Overview

Shows the complete automation pipeline.


---

## Learning Outcomes

Through this project I learned:

* Writing JavaScript inside n8n Code nodes
* Recursive JSON traversal
* Array mapping and filtering
* Business rule implementation
* Data transformation techniques
* Lead qualification logic
* Working with nested JSON structures
* Building reusable automation scripts

---

## Real-World Applications

This workflow can be adapted for:

* CRM lead qualification
* Sales prospecting
* Marketing automation
* Customer segmentation
* Data cleansing pipelines
* Business intelligence workflows
* Lead scoring systems

---


## Conclusion

This workflow demonstrates how JavaScript can extend the capabilities of low-code automation platforms by implementing custom business logic. By combining recursive JSON processing, lead qualification rules, and structured data transformation, the workflow converts complex API responses into clean, actionable business data suitable for real-world automation scenarios.
