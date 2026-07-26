# Alternative Slot Generation

## Purpose

Recover gracefully when a requested appointment time is unavailable.

## Current Logic

1. Generate a set of candidate time slots near the requested date and time.
2. Check each candidate against Google Calendar.
3. Keep only candidates that are available.
4. Select the best three slots.
5. Format the slots into a patient-friendly message.
6. Send the alternatives to the sender.

## Recommended Candidate Rules

- Remain within clinic working hours.
- Exclude past dates and times.
- Exclude weekends or closed days unless the clinic permits them.
- Respect appointment duration and buffer time.
- Prefer slots closest to the patient's original request.
- Avoid duplicate options.
- Present dates and times in the clinic's local time zone.

## Failure Handling

If fewer than three slots are available:

- Send the available slots only.
- If no slots are available, notify clinic staff for manual scheduling.
