# Appointment Workflow

1. Receive email from Gmail Trigger.
2. Classify as appointment with sufficient confidence.
3. Extract appointment details.
4. Check required fields.
5. If details are missing, request additional information.
6. If complete, check Google Calendar availability.
7. If available, create a calendar event.
8. Send confirmation to the patient.
9. Store appointment details in Google Sheets.
10. Notify clinic staff.
11. If unavailable, generate and validate alternatives.
12. Select and format the best three alternatives.
13. Send alternatives to the patient.
