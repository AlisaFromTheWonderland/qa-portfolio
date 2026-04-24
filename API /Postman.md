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

### Example structure

```text
Postman Collection
├── Recipient
│   ├── POST   /register-recipient/
│   ├── POST   /login/
│   ├── GET    /current-user/
│   ├── POST   /register-collect/
│   ├── GET    /collects/
│   ├── GET    /collect/{collect_id}/
│   ├── PATCH  /collect/{collect_id}/
│   ├── PUT    /collect/{collect_id}/
│   └── DELETE /collect/{collect_id}/
└── Reg/Auth v2
```

