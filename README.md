

<p align="center">
  <img src="assets/banner.png" alt="AI Dental Clinic Email Automation Banner">
</p>
<p align="center">

![n8n](https://img.shields.io/badge/n8n-Workflow_Automation-EA4B71?style=for-the-badge&logo=n8n&logoColor=white)
![Groq](https://img.shields.io/badge/Groq-AI-000000?style=for-the-badge)
![Gmail](https://img.shields.io/badge/Gmail-API-EA4335?style=for-the-badge&logo=gmail&logoColor=white)
![Google Calendar](https://img.shields.io/badge/Google_Calendar-API-4285F4?style=for-the-badge&logo=googlecalendar&logoColor=white)
![Google Sheets](https://img.shields.io/badge/Google_Sheets-API-34A853?style=for-the-badge&logo=googlesheets&logoColor=white)

</p>




# AI Dental Clinic Email Automation

A production-ready n8n workflow that acts as a 24/7 AI-powered email receptionist for dental clinics.

## Current Capabilities

- Gmail-based email intake
- AI email classification
- Confidence-based routing and human review
- Appointment information extraction
- Missing-information handling
- Google Calendar availability checks
- Automatic appointment event creation
- Alternative appointment slot generation
- Appointment confirmation emails
- Cancellation information extraction
- Cancellation confirmation and clinic notification
- Job enquiry acknowledgement and logging
- FAQ / general enquiry handling using an AI Agent
- Spam logging
- Google Sheets data storage
- Dedicated error workflow
- Retry-on-failure settings for AI nodes

- ## 🏗️ System Architecture

This diagram provides a high-level overview of how the AI Dental Clinic Email Automation workflow processes incoming emails and routes them through specialized automation branches.

![System Architecture](assets/workflow-architecture.png)

## Main Workflow

```text
Gmail Trigger
  -> Get Full Email Message
  -> Email Classifier
       -> Low confidence: Human review notification
       -> High confidence: Switch
            -> Appointment
            -> Cancellation
            -> Job enquiry
            -> General enquiry / FAQ
            -> Spam
```
## 📸 Workflow Showcase

### Complete Workflow

The complete n8n automation retrieves the full email content, classifies each email using AI, routes requests based on confidence, manages appointments and cancellations, answers FAQs, processes job enquiries, filters spam, integrates with Google Calendar and Google Sheets, and includes dedicated error handling for reliable operation.

![Complete Workflow](screenshots/main-workflow.png)

---

### Appointment Scheduling Automation

This branch extracts appointment details, checks Google Calendar availability, creates the appointment when the slot is available, and generates alternative options when the requested time is unavailable.

![Appointment Scheduling Automation](screenshots/appointment-branch.png)
## Appointment Branch

```text
Get Full Email Message
  -> Appointment Details Extractor
  -> Missing Details Check
       -> Missing: Ask sender for more information
       -> Complete: Check Google Calendar
            -> Available: Create event
                 -> Send confirmation
                 -> Store appointment
                 -> Notify clinic
            -> Unavailable: Generate alternative slots
                 -> Check alternatives
                 -> Select best three
                 -> Format alternatives
                 -> Send alternatives to sender
```

## Cancellation Branch

```text
Cancellation Details Extractor
  -> Missing Details Check
       -> Missing: Request more information
       -> Complete:
            -> Send cancellation confirmation
            -> Store cancellation
            -> Notify clinic
```

## Job Enquiry Branch

```text
Send acknowledgement
  -> Store job enquiry
  -> Notify clinic
```

## General Enquiry Branch

```text
FAQ AI Agent
  -> Send reply
  -> Log interaction
```

## Spam Branch

```text
Store spam record
```

## Reliability Features

- AI confidence threshold before automatic action
- Human review route for uncertain classifications
- Required-field validation
- Calendar conflict detection
- Alternative-slot recovery path
- Retry-on-fail settings
- Centralized error logging workflow

- # ❗ Business Problem

Dental clinics receive a continuous stream of emails related to appointment requests, cancellations, job applications, and general enquiries. Managing these emails manually can lead to:

- Delayed responses to patients
- Double-booked or conflicting appointments
- Increased administrative workload
- Inconsistent handling of enquiries
- Missed opportunities due to human error
- Time spent on repetitive administrative tasks

As patient volume increases, these challenges reduce operational efficiency and negatively impact the patient experience.

- # 💼 Business Value

This automation is designed to reduce the administrative workload of dental clinics by automating repetitive email-based tasks.

### Benefits

- 📧 Automatically classifies incoming emails using AI.
- 📅 Schedules appointments without manual intervention.
- 🔄 Handles appointment cancellations efficiently.
- ⏰ Suggests alternative appointment slots when schedules are full.
- 📋 Logs appointment and enquiry data into Google Sheets.
- 🤖 Answers frequently asked questions automatically.
- 👨‍💼 Routes uncertain emails for human review.
- 🚫 Separates spam from genuine patient enquiries.

### Business Impact

- Reduce receptionist workload
- Faster patient response times
- Fewer scheduling conflicts
- Improved appointment management
- Better record keeping
- Scalable clinic operations

## Technology Stack

- n8n
- Gmail API
- - Gmail Get Message (Full Email Retrieval)
- Google Calendar API
- Google Sheets API
- Groq-compatible chat models
- n8n Information Extractor
- n8n AI Agent

## Repository Structure

```text
documentation/
prompts/
extractor-specifications/
calendar-logic/
workflow-logic/
client-resources/
demo-emails/
screenshots/
assets/
deliverables/
workflows/
```

The exported n8n workflow JSON files should be placed in `workflows/`.

## Deployment Summary

1. Import the main workflow and error workflow.
2. Connect Gmail, Google Calendar, Google Sheets, and AI credentials.
3. Replace clinic-specific information.
4. Configure spreadsheet and calendar selections.
5. Test all branches.
6. Publish and activate both workflows.

## Security

Never upload API keys, OAuth client secrets, access tokens, passwords, patient data, or private clinic information to a public repository.

## Author

**Syyed Eesa**  
AI Automation Developer
