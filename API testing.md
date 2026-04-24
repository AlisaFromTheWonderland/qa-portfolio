# API Testing Portfolio

> A curated set of representative API test cases covering core user and collect management flows.  
> This document demonstrates validation coverage, authentication, authorization, CRUD behavior, and business rule verification.

---

## Table of Contents

- [Overview](#overview)
- [Scope](#scope)
- [Test Approach](#test-approach)
- [Environment](#environment)
- [Test Data](#test-data)
- [Priority Legend](#priority-legend)
- [Positive API Test Cases](#positive-api-test-cases)
  - [TC-POS-01 — Register recipient with valid data](#tc-pos-01--register-recipient-with-valid-data)
  - [TC-POS-02 — Login with valid credentials](#tc-pos-02--login-with-valid-credentials)
  - [TC-POS-03 — Get current user data](#tc-pos-03--get-current-user-data)
  - [TC-POS-04 — Create a new collect with valid data](#tc-pos-04--create-a-new-collect-with-valid-data)
  - [TC-POS-07 — Partially update collect data](#tc-pos-07--partially-update-collect-data)
- [Negative API Test Cases](#negative-api-test-cases)
  - [TC-NEG-01 — Register recipient with empty request body](#tc-neg-01--register-recipient-with-empty-request-body)
  - [TC-NEG-05 — Register recipient with duplicate email](#tc-neg-05--register-recipient-with-duplicate-email)
  - [TC-NEG-07 — Login with incorrect password](#tc-neg-07--login-with-incorrect-password)
  - [TC-NEG-12 — Create collect when active collect limit is reached](#tc-neg-12--create-collect-when-active-collect-limit-is-reached)
  - [TC-NEG-18 — Delete collect owned by another user](#tc-neg-18--delete-collect-owned-by-another-user)
- [Summary](#summary)

---

## Overview

This file contains a **selected set of API test cases** designed for portfolio presentation.  
The goal is to demonstrate a clear understanding of:

- API request/response validation
- authentication and authorization flows
- positive and negative scenario coverage
- business rule verification
- ownership and permission checks

---

## Scope

The following functional areas are covered:

- recipient registration
- user authentication
- current user retrieval
- collect creation
- collect update
- duplicate prevention
- limit validation
- permission restriction

---

## Test Approach

This document includes:

- **Positive test cases** — to verify expected behavior with valid data
- **Negative test cases** — to verify validation, error handling, and business restrictions

Testing focus:

- request body validation
- response status codes
- business logic
- access control
- data integrity

---

## Environment

| Parameter | Value |
|---|---|
| API Type | REST API |
| Authorization | Bearer Token / JWT |
| Format | JSON |
| Tools | Postman, Swagger |
| Test Level | API / Integration |
| Status | Designed / Portfolio Example |

> Replace the environment details with your actual project setup if needed.

---

## Test Data

### User Data Example

```json
{
  "name": "testrecipient1",
  "phone": "+380501234500",
  "email": "test.recipient1@test.com",
  "password": "Password1!"
}
```

# API Test Cases

## Positive Test Cases

---

## TC-POS-01 — Register recipient with valid data

| Field | Value |
|---|---|
| **Priority** | High |
| **Tags** | `api`, `positive`, `registration` |
| **Endpoint** | `/register-recipient/` |
| **Method** | `POST` |
| **Scenario Type** | Positive |

**Preconditions**
- API is available
- User is not registered yet

**Steps**
1. Send a `POST` request with valid recipient data.
2. Attach required documents if supported by the endpoint.

**Expected Status Code**  
`201 Created`

**Expected Result**  
The user is successfully created and receives the status **"Pending confirmation"**.

**Request Body Example**
```json
{
  "name": "testrecipient1",
  "phone": "+380501234500",
  "email": "test.recipient1@test.com",
  "password": "Password1!"
}
```
