# 🤖 AI-Powered Resume Screening & Recruitment Automation (n8n)

An **end-to-end AI recruitment automation workflow built with n8n**.  
This system automatically screens candidate resumes received via email, compares them with job descriptions using an AI agent, scores candidates, stores results, and sends interview invitations to shortlisted candidates.

---

## 🚀 Overview

Hiring at scale is time-consuming. This workflow automates the **entire resume screening and pre-interview process** using **AI automation, n8n workflows, and OpenAI-powered agents**.

The flow is triggered whenever a candidate emails a resume. Only emails containing CV or resume attachments are processed.

---

## 🧩 Workflow Architecture

### 1️⃣ Gmail Trigger – Resume Intake
- Triggers when a new email is received
- Filters emails that contain **resume/CV attachments**
- Ignores irrelevant emails automatically

---

### 2️⃣ Upload Resume to Google Drive
- Uploads candidate resumes to Google Drive
- Keeps all CVs organized in one centralized location
- Generates a file reference for processing

---

### 3️⃣ Download Resume from Google Drive
- Downloads the resume back into the n8n workflow
- Ensures consistent and secure file access

---

### 4️⃣ Resume Text Extraction
- Extracts text from PDF, DOCX, and other supported formats
- Converts resume content into **HTML/Text format** for AI processing

---

### 5️⃣ Data Standardization
- Cleans and standardizes extracted resume text
- Ensures consistent input for AI analysis
- Uses n8n standardization logic (manual mapping)

---

### 6️⃣ Job Description Retrieval
- Downloads job description files from Google Drive
- Supports PDF, Google Docs, and CSV formats
- Extracts full job description text

---

## 🧠 AI Recruitment Agent

### 7️⃣ AI Resume vs Job Comparison
- Uses an **OpenAI-powered Recruitment AI Agent**
- Compares:
  - Resume content
  - Job description requirements
- Applies structured evaluation logic

---

### 8️⃣ Structured Output Parser
The AI returns **structured, machine-readable output**, including:

- Candidate Strengths  
- Candidate Weaknesses  
- Risk Factors  
- Reward Factors  
- Overall Fit Rating (0–10)  
- Justification for Rating  

This ensures consistent scoring and explainable decisions.

---

## 📌 Candidate Information Extraction

### 9️⃣ Information Extractor
- Extracts **Candidate Name**
- Extracts **Candidate Email Address**
- Ensures no critical candidate data is missed

---

## 📊 Data Storage & Automation Logic

### 🔟 Google Sheets Integration
All candidate evaluations are stored in Google Sheets, including:
- Name
- Email
- Resume link
- AI evaluation score
- Strengths and weaknesses
- AI justification

This creates a complete recruitment database.

---

### 1️⃣1️⃣ Conditional Logic (IF Node)
- **If Overall Fit Score < 5**
  - No response is sent
- **If Overall Fit Score ≥ 5**
  - Candidate is shortlisted

---

### 1️⃣2️⃣ Interview Invitation Email
- Sends an automated email to shortlisted candidates
- Includes a **calendar scheduling link** for interviews

---

## 🛠️ Tech Stack

- **n8n AI Automation**
- **OpenAI (AI Agent)**
- Gmail Trigger
- Google Drive
- Google Sheets
- Structured Output Parser
- PDF & Document Text Extraction

---

## 🎯 Use Cases

- HR Teams & Recruiters  
- Startups & SaaS Companies  
- High-volume hiring pipelines  
- Automated ATS pre-screening  
- AI-driven candidate evaluation  

---

## ⭐ Key Features

- Fully automated resume screening
- AI-powered candidate scoring
- Structured and explainable AI output
- Centralized candidate records
- Automatic interview scheduling
- Scalable and customizable workflow

---

## 🔧 Customization Options

You can easily:
- Adjust fit score thresholds
- Modify AI evaluation prompts
- Add multiple job roles
- Integrate Slack, WhatsApp, or CRM tools
- Connect ATS systems

---

## 📂 Repository Contents

- `workflow.json` – n8n workflow export  
- `README.md` – Documentation  
- `screenshots/` – Workflow screenshots  
- `prompts/` – AI agent prompts (optional)

---

## 📬 Contact

For customization, deployment, or consulting related to **AI automation, n8n workflows, or AI agents**, feel free to reach out.

---

> 🚀 Built with n8n AI Automation to scale recruitment intelligently.

## ⚙️ Setup & Configuration

### Prerequisites
Before using this workflow, ensure you have:
- An active **n8n instance** (cloud or self-hosted)
- A **Gmail account** with API access
- A **Google Drive & Google Sheets** account
- An **OpenAI API key**

---

### 1️⃣ Import the Workflow
- Download the `workflow.json` file from this repository
- Import it into your n8n instance

---

### 2️⃣ Configure Credentials
Create and connect the following credentials in n8n:
- Gmail OAuth2
- Google Drive OAuth2
- Google Sheets OAuth2
- OpenAI API

> ⚠️ Do not commit credentials to this repository.

---

### 3️⃣ Gmail Trigger Setup
- Connect your Gmail account
- Set filters to only process emails containing **CV / Resume attachments**
- Adjust subject or sender filters if required

---

### 4️⃣ Google Drive Configuration
- Select a parent folder to store candidate resumes
- Upload job description files to a separate Drive folder
- Ensure n8n has access to both folders

---

### 5️⃣ Job Description File
- Maintain job descriptions in Google Drive
- Supported formats: PDF, DOC, CSV
- Update or replace the file to switch job roles

---

### 6️⃣ AI Agent Configuration
- Update the AI prompt inside the Recruitment Agent node
- Adjust evaluation criteria or scoring logic as needed
- Ensure the Structured Output Parser matches the prompt output

---

### 7️⃣ Google Sheets Setup
Create a Google Sheet with columns such as:
- Name
- Email
- Resume Link
- Overall Fit Score
- Strengths
- Weaknesses
- Risk Factors
- Reward Factors
- AI Justification

---

### 8️⃣ Interview Scheduling Email
- Add your calendar booking link in the email node
- Customize email content and sender details

---

### 9️⃣ Activation
- Enable the workflow
- Send a test resume email
- Verify results in Google Sheets and email delivery

---

## 🛡️ Security Notes
- Never store API keys in code
- Use OAuth where possible
- Limit Google Drive folder access

---

## 📌 Notes
This workflow is designed to be modular and easily extendable for multiple roles, ATS systems, or notification channels.
