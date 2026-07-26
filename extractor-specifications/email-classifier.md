# Email Classifier Specification

## Purpose

Classify every incoming email before any branch-specific action is performed.

## Input

The Gmail message content or snippet.

## Attributes

### `message_type`
- Type: Text
- Allowed values: `appointment`, `cancellation`, `job_query`, `enquiry`, `spam`
- Description: The category that most accurately represents the sender's main intent.

### `confidence`
- Type: Number
- Range: 0.00 to 1.00
- Description: The estimated certainty of the classification.
- Processing rule: Values below 0.90 are routed to human review.

### `reason`
- Type: Text
- Description: A concise one-sentence explanation identifying the evidence used for classification.

## Validation Rules

- The category must match one allowed value exactly.
- The confidence value must be numeric.
- Ambiguous emails must not receive confidence of 0.90 or higher.
- No business action should occur before the confidence gate.
