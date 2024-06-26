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

### Response
### Error

```json
{
  "error": "1",
  "msg": "Invalid email or password"
  "data": []
}
```
# 5. Details

Endpoint
**Endpoint:** `Get <base_url>/details`


You should include an Authorization token in the request header for this endpoint. This Bearer token, obtained after logging in, is necessary to retrieve user details.

##### Authorization: Bearer token

`Example: Authorization: Bearer xo1gAl1E5NhQL2nPSC8bIObIcwAfd/EJ/WXjt/OIhPQ=`

#### Description
Retrieve the details of the authenticated user.

| Header       | Type   | Description       |
|--------------|--------|-------------------|
| Authorization | string | `Bearer <token>` |

#### Response
#### Success
```json

{
  "error": "0",
  "msg": "success"
  "data": {
    "info": {
       "Name": "success"
       "email": "user1@gmail.com"
       "avatar": "https://i.ibb.co/C9m1p0C/profile-picture.png"
       "phone": "01775051603"
       "birth_date": "1990-07-17T03:18:31.177769-04:00"
       "address": "Gulshan, Dhaka"
    },
    "hobbies": {
        {
          "Name": "Cricket"
          "image": "https://i.ibb.co/JjGWDjn/cricket.png"
        },
        {
          "Name": "Traveling"
          "image": "https://i.ibb.co/w4vGSVQ/traveling.png"
        },
        {
          "Name": "Cycling"
          "image": "https://i.ibb.co/YZCkQfW/cycling.png"
        },
        {
          "Name": "Gardening"
          "image": "https://i.ibb.co/GMpKrdb/gardening.png"
        }
     },
    "skills": [
       "Flutter",
       "Dart",
       "PHP",
       "Python"
    ]
   }
}
```
#### Response
#### Error
```json
{
  "error": "1",
  "msg": "Invalid token"
  "data": []
}
```

