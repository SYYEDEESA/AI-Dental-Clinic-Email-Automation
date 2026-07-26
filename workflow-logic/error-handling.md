# Error Handling Workflow

## Trigger

The dedicated Error Trigger workflow runs when the main workflow fails, provided it is selected as the main workflow's Error Workflow.

## Logged Fields

- Timestamp: `{{ $now.toISO() }}`
- Workflow: `{{ $json.workflow.name }}`
- Failed node: `{{ $json.execution.lastNodeExecuted }}`
- Error message: `{{ $json.execution.error.message }}`
- Execution ID: `{{ $json.execution.id }}`

## Recommended Additional Action

Send an internal alert email to the workflow maintainer or clinic administrator.

## Retry Strategy

Enable Retry on Fail for AI-dependent nodes.

Typical built-in values:

- Max tries: 3
- Wait between tries: 5000 ms

Longer provider rate limits may still require manual review or a future custom wait-and-retry branch.
