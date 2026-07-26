# Calendar Event Creation

## Purpose

Create a confirmed appointment in Google Calendar after validation and availability checks.

## Event Fields

- Title: Patient name and requested service or reason
- Start: Confirmed appointment date and time
- End: Start time plus configured duration
- Description: Contact details, reason for visit, email source, and relevant notes
- Calendar: Clinic-selected appointment calendar
- Time zone: Clinic's configured time zone

## Post-Creation Actions

- Send confirmation to the patient.
- Append appointment data to Google Sheets.
- Notify clinic staff.

## Safety Rules

- Never create the event if required patient details are missing.
- Never create the event before checking availability.
- Store the calendar event ID if later cancellation automation will delete or update events.
