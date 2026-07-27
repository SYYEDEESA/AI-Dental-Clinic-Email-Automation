# Changelog

All notable changes to this project are documented in this file.

---

## [1.1.0] - Latest

### Added
- Added Gmail **Get Message** node to retrieve the full email body.
- Improved workflow reliability by processing complete email content instead of Gmail snippets.

### Improved
- Updated Email Classifier prompt with clearer category definitions and confidence rules.
- Updated Appointment Details Extraction prompt to process the full email body.
- Updated FAQ Agent prompt to use the full email text.
- Improved extraction accuracy for patient names, appointment reasons, dates, and times.
- Refreshed prompt documentation to match the latest workflow implementation.

### Fixed
- Fixed missing patient information caused by using Gmail snippets instead of the complete email body.
- Improved appointment classification reliability for realistic patient emails.

---

## [1.0.0]

### Initial Release
- AI-powered email classification.
- Appointment scheduling.
- Appointment cancellation.
- FAQ handling.
- Job enquiry handling.
- Google Calendar integration.
- Google Sheets logging.
- Human review workflow.
- Spam detection.
- Automated confirmation emails.
