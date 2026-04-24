# Postman API Testing

This page demonstrates my practical work with **Postman collections** for API testing, request organization, authentication flows, CRUD coverage, and response validation.

According to Postman documentation, collections are reusable groups of requests that can store authorization, headers, params, bodies, scripts, variables, and documentation. Postman also recommends organizing requests with folders and enriching collections with examples and descriptions, which are then reflected in collection documentation. :contentReference[oaicite:1]{index=1}

---

## Overview

In this project, Postman was used for:

- testing API endpoints
- organizing requests into a structured collection
- validating registration and authentication flows
- testing authorized and unauthorized behavior
- checking CRUD operations
- preparing reusable request bodies and test data
- documenting API behavior in a portfolio-friendly format

---

## Collection Structure

The collection is organized by feature/module, which follows Postman’s recommendation to group related requests in folders and subfolders. In the screenshot, the main working folder is **Recipient**, and it includes the core requests for registration, authentication, user retrieval, and collect management. :contentReference[oaicite:2]{index=2}


| Method | Endpoint                 | Purpose                             |
| ------ | ------------------------ | ----------------------------------- |
| POST   | `/register-recipient/`   | Register a new recipient            |
| POST   | `/login/`                | Authenticate user and receive token |
| GET    | `/current-user/`         | Retrieve current authenticated user |
| POST   | `/register-collect/`     | Create a new collect                |
| GET    | `/collects/`             | Get all collects                    |
| GET    | `/collect/{collect_id}/` | Get collect details by ID           |
| PATCH  | `/collect/{collect_id}/` | Partially update collect            |
| PUT    | `/collect/{collect_id}/` | Fully update collect                |
| DELETE | `/collect/{collect_id}/` | Delete collect                      |

### Request body handling
```json
{
  "full_name": "testrecipient2",
  "phone": "+380501234500",
  "user": {
    "email": "test.recipient2@test.com",
    "password": "Password1!",
    "confirm_password": "Password1!"
  }
}
```
<img width="888" height="343" alt="image" src="https://github.com/user-attachments/assets/9b67e20e-ed72-4304-9353-7c16e5f06cf8" />
