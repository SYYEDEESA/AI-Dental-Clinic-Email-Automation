# Cancellation Details Extractor Specification

## Purpose

Extract structured information from emails requesting cancellation or rescheduling.

## Input

The original Gmail message content.

## Recommended Attributes

### `patient_name`
Name associated with the appointment.

### `appointment_date`
Date of the appointment being cancelled.

### `appointment_time`
Time of the appointment being cancelled.

### `cancellation_reason`
Reason supplied by the sender, if any.

### `phone_number`
Contact number, if supplied.

### `email_address`
Sender's email address.

### `reschedule_requested`
Boolean or text value indicating whether the sender wants another appointment.

### `preferred_reschedule_date`
Preferred replacement date, if provided.

### `preferred_reschedule_time`
Preferred replacement time, if provided.

### `additional_notes`
Any other useful cancellation or rescheduling information.

## Validation

The cancellation branch must have enough information to identify the appointment safely. If the details are incomplete, the sender receives a request for clarification instead of the workflow proceeding automatically.

## Rules

- Do not assume which appointment should be cancelled.
- Do not fabricate dates or times.
- Preserve the sender's wording.
- A cancellation reason is optional unless the clinic requires it.
