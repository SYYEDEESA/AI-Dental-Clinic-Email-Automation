# Appointment Details Extractor Specification

## Purpose

Extract structured appointment-booking data from emails classified as appointment requests.

## Input

The original Gmail message content.

## Recommended Attributes

### `patient_name`
Full name explicitly provided by the sender.

### `appointment_date`
Requested date exactly as written. Relative expressions such as "next Tuesday" may be preserved unless the workflow separately normalizes dates.

### `appointment_time`
Requested time exactly as written.

### `reason_for_appointment`
Dental problem, symptom, procedure, or reason for the visit.

### `phone_number`
Telephone number explicitly supplied.

### `email_address`
Email address available from the message or stated in the content.

### `preferred_doctor`
Requested dentist, if mentioned.

### `requested_service`
Requested service such as cleaning, filling, root canal, consultation, extraction, whitening, or aligners.

### `additional_notes`
Relevant preferences, urgency, accessibility needs, or contextual information.

## Required Fields for Automatic Scheduling

At minimum, the workflow currently validates:

- Patient name
- Appointment date
- Appointment time
- Reason for appointment

If any required value is empty, the workflow sends a request for additional information and does not create a calendar event.

## Extraction Rules

- Extract only explicitly stated information.
- Do not guess missing details.
- Preserve names, dates, and times as written.
- Return null or an empty value when data is absent.
- Do not create medical diagnoses.
