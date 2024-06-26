# Flutter Candidate Exam API Documentation

## Introduction
This documentation details the Development API endpoints for user authentication, retrieving user details, and changing passwords.

## Base URL
### https://flutter.vmx.link


## Endpoints
- `<base_url>/login`
- `<base_url>/details`
- `<base_url>/passwordchange`

## Error Responses
- **error (int)**: Indicates the result of the operation.
  - 1 = Operation failed
  - 0 = Operation successful
- **msg (string)**: A descriptive error message.

### Example Error Response
```json
{
  "error": 1,
  "msg": "Invalid token",
  "data": []
}
