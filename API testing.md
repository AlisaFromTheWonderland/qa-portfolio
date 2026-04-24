# API Testing Portfolio

- [Positive Test Cases](#Positive-Test-Cases)
  - [TC-POS-01 — Register recipient with valid data](#tc-pos-01--register-recipient-with-valid-data)
  - [TC-POS-02 — Login with valid credentials](#tc-pos-02--login-with-valid-credentials)
  - [TC-POS-03 — Get current user data](#tc-pos-03--get-current-user-data)
  - [TC-POS-04 — Create a new collect with valid data](#tc-pos-04--create-a-new-collect-with-valid-data)
  - [TC-POS-07 — Partially update collect data](#tc-pos-07--partially-update-collect-data)
- [Negative Test Cases](#Negative-Test-Cases)
  - [TC-NEG-01 — Register recipient with empty request body](#tc-neg-01--register-recipient-with-empty-request-body)
  - [TC-NEG-05 — Register recipient with duplicate email](#tc-neg-05--register-recipient-with-duplicate-email)
  - [TC-NEG-07 — Login with incorrect password](#tc-neg-07--login-with-incorrect-password)
  - [TC-NEG-12 — Create collect when active collect limit is reached](#tc-neg-12--create-collect-when-active-collect-limit-is-reached)
  - [TC-NEG-18 — Delete collect owned by another user](#tc-neg-18--delete-collect-owned-by-another-user)

---

# Positive Test Cases

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

---

## TC-POS-02 — Login with valid credentials

| Field | Value |
|---|---|
| **Priority** | High |
| **Tags** | `api`, `positive`, `login`, `authentication` |
| **Endpoint** | `/login/` |
| **Method** | `POST` |
| **Scenario Type** | Positive |

**Preconditions**
- User is registered
- User has confirmed email

**Steps**
1. Send a `POST` request with the correct email and password.

**Expected Status Code**  
`200 OK`

**Expected Result**  
The API returns a valid authorization token (**JWT**).

**Request Body Example**
```json
{
  "email": "test.recipient1@test.com",
  "password": "Password1!"
}
```

---

## TC-POS-03 — Get current user data

| Field | Value |
|---|---|
| **Priority** | High |
| **Tags** | `api`, `positive`, `authentication`, `authorization` |
| **Endpoint** | `/current-user/` |
| **Method** | `GET` |
| **Scenario Type** | Positive |

**Preconditions**
- User is authenticated
- Valid Bearer token is available

**Steps**
1. Send a `GET` request with a valid Bearer token in the header.

**Expected Status Code**  
`200 OK`

**Expected Result**  
The response returns the current authenticated user's data.

---

## TC-POS-04 — Create a new collect with valid data

| Field | Value |
|---|---|
| **Priority** | High |
| **Tags** | `api`, `positive`, `collects`, `create` |
| **Endpoint** | `/register-collect/` |
| **Method** | `POST` |
| **Scenario Type** | Positive |

**Preconditions**
- User is authenticated
- User has the status **"Verified"**

**Steps**
1. Send a `POST` request with valid collect data.
2. Include all required fields according to the API contract.

**Expected Status Code**  
`201 Created`

**Expected Result**  
A new collect is created with the status **"Under review"**.

**Request Body Example**
```json
{
  "description": "test collection",
  "type_collect": 1,
  "urgency": 1,
  "city": "Vinnytsia",
  "district": "city center",
  "contact_number": "+380501234567"
}
```

---

## TC-POS-07 — Partially update collect data

| Field | Value |
|---|---|
| **Priority** | High |
| **Tags** | `api`, `positive`, `collects`, `patch`, `update` |
| **Endpoint** | `/collect/{collect_id}` |
| **Method** | `PATCH` |
| **Scenario Type** | Positive |

**Preconditions**
- User is authenticated
- User is the owner of the collect

**Steps**
1. Send a `PATCH` request with updated fields, for example:
   - description
   - status

**Expected Status Code**  
`200 OK`

**Expected Result**  
The collect is updated successfully and changes are saved.

**Request Body Example**
```json
{
  "description": "some description",
  "type_collect": 1,
  "urgency": 1,
  "status": 1,
  "city": "Kropyvnytskyi",
  "district": "Pid Palcem",
  "contact_number": "+380991234567"
}
```

---

# Negative Test Cases

## TC-NEG-01 — Register recipient with empty request body

| Field | Value |
|---|---|
| **Priority** | High |
| **Tags** | `api`, `negative`, `registration`, `validation` |
| **Endpoint** | `/register-recipient/` |
| **Method** | `POST` |
| **Scenario Type** | Negative |

**Preconditions**
- API is available
- User is not registered

**Steps**
1. Send a `POST` request with an empty request body.

**Expected Status Code**  
`422 Unprocessable Entity`

**Expected Result**  
Validation error is returned because required fields are missing.

---

## TC-NEG-05 — Register recipient with duplicate email

| Field | Value |
|---|---|
| **Priority** | High |
| **Tags** | `api`, `negative`, `registration`, `validation` |
| **Endpoint** | `/register-recipient/` |
| **Method** | `POST` |
| **Scenario Type** | Negative |

**Preconditions**
- API is available
- A user with this email already exists

**Steps**
1. Send a `POST` request with an already registered email.

**Expected Status Code**  
`409 Conflict`

**Expected Result**  
The API returns **"User with this email already exists"**.

**Request Body Example**
```json
{
  "name": "testrecipient1",
  "phone": "+380501234500",
  "email": "test.recipient1@test.com",
  "password": "Password1!"
}
```

---

## TC-NEG-07 — Login with incorrect password

| Field | Value |
|---|---|
| **Priority** | High |
| **Tags** | `api`, `negative`, `login`, `authentication` |
| **Endpoint** | `/login/` |
| **Method** | `POST` |
| **Scenario Type** | Negative |

**Preconditions**
- API is available
- User exists

**Steps**
1. Send a `POST` request with the correct email and incorrect password.

**Expected Status Code**  
`401 Unauthorized`

**Expected Result**  
The API returns **"Invalid credentials"**.

**Request Body Example**
```json
{
  "email": "test.recipient1@test.com",
  "password": "Password2!"
}
```

---

## TC-NEG-12 — Create collect when active collect limit is reached

| Field | Value |
|---|---|
| **Priority** | High |
| **Tags** | `api`, `negative`, `collects`, `limits` |
| **Endpoint** | `/register-collect/` |
| **Method** | `POST` |
| **Scenario Type** | Negative |

**Preconditions**
- User is authenticated
- User already has 3 active collects

**Steps**
1. Send a `POST` request to create one more collect after reaching the active limit.

**Expected Status Code**  
`403 Forbidden`

**Expected Result**  
The API returns **"Limit reached"**.

---

## TC-NEG-18 — Delete collect owned by another user

| Field | Value |
|---|---|
| **Priority** | High |
| **Tags** | `api`, `negative`, `authorization`, `permissions`, `collects` |
| **Endpoint** | `/collect/{collect_id}` |
| **Method** | `DELETE` |
| **Scenario Type** | Negative |

**Preconditions**
- User is authenticated
- Collect exists
- User is not the owner of the collect

**Steps**
1. Send a `DELETE` request for a collect owned by another user.

**Expected Status Code**  
`403 Forbidden`

**Expected Result**  
The API returns **"Permission denied"**.
