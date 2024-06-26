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
```

# 5. Login

**Endpoint:** `POST <base_url>/login`

**Description:**
Authenticate a user and obtain an access token.

### Request Headers

| Header       | Type   | Description       |
|--------------|--------|-------------------|
| Content-Type | string | application/json  |

### Request Body
```json
{
  "email": "user1@gmail.com",
  "password": "user1@gmail.com"
}
```
`There are 20 user credentials like user1@gmail.com, user2@gmail.com, user3@gmail.com, ….. user20@gmail.com and the password is the same as the email for login.`


### Response
### Success

```json
{
  "error": "0",
  "msg": "success"
  "data": {
    "token": "xo1gAl1E5NhQL2nPSC8bIObIcwAfd/EJ/WXjt/OIhPQ="
  }
}

```

