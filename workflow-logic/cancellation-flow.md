# Cancellation Workflow

1. Receive email.
2. Classify as cancellation with sufficient confidence.
3. Extract cancellation details.
4. Validate that the appointment can be safely identified.
5. If details are missing, request clarification.
6. If complete, send a cancellation acknowledgement or confirmation.
7. Store the cancellation in Google Sheets.
8. Notify clinic staff.
9. If calendar cancellation is later enabled, locate the event by stored event ID before deleting or updating it.
