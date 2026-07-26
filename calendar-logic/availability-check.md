# Calendar Availability Check

## Purpose

Prevent double booking before an appointment is created.

## Input

- Requested date
- Requested time
- Appointment duration
- Selected Google Calendar
- Clinic time zone

## Process

1. Convert the requested date and time into a calendar-compatible start timestamp.
2. Calculate the end timestamp using the configured appointment duration.
3. Query Google Calendar for overlapping events.
4. Route the item based on whether the requested interval is free.

## Available Path

If the slot is available:

- Create the calendar event.
- Send the patient a confirmation.
- Store the appointment in Google Sheets.
- Notify the clinic.

## Unavailable Path

If the slot is occupied:

- Generate nearby alternative slots.
- Check those alternatives against Google Calendar.
- Select the best available options.
- Send the options to the patient.

## Clinic-Specific Settings

- Time zone
- Calendar ID
- Working days
- Opening and closing hours
- Default appointment duration
- Buffer time
- Holidays and blocked periods
