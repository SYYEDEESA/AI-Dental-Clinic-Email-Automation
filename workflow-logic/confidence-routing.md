# Confidence Routing

## Rule

- Confidence >= 0.90: Continue to automatic category routing.
- Confidence < 0.90: Stop automatic processing and send the email for human review.

## Purpose

The confidence gate prevents uncertain classification from triggering the wrong operational branch.

## Human Review Notification

The review message should include:

- Original sender
- Subject
- Email content or snippet
- Predicted category
- Confidence score
- Classification reason

A human can then decide whether to process the message manually or replay it through the correct branch.
