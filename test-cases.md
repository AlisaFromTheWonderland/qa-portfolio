**Module:** Registration / Authentication  
**Platform:** Web  
**Test Level:** Functional  
**Test Design Techniques:** Positive, Negative, Validation, Role-based testing

- [Test Data](#test-data)
- [Test Cases](#test-cases)
  - [FE-REG-01 — Successful user registration with valid data](#fe-reg-01--successful-user-registration-with-valid-data)
  - [FE-REG-02 — Email validation during registration](#fe-reg-02--email-validation-during-registration)
  - [FE-REG-09 — Missing document upload (volunteer / recipient)](#fe-reg-09--missing-document-upload-volunteer--recipient)
  - [FE-REG-11 — User approval by administrator](#fe-reg-11--user-approval-by-administrator)
  - [FE-REG-14 — Login with valid credentials](#fe-reg-14--login-with-valid-credentials)

---

# Test Data

| Field | Example Value |
|---|---|
| Full Name | John Smith |
| Valid Email | john.smith.qa@example.com |
| Invalid Email | usergmail.com |
| Valid Phone | +48123456789 |
| Valid Password | QaTest123! |
| Roles | Volunteer / Donor / Driver / Recipient |
| Document Example | volunteer_id.jpg / idp_certificate.pdf |

---

# Test Cases

## FE-REG-01 — Successful user registration with valid data

**Priority:** High  
**Tags:** `registration`, `roles`

**Preconditions:**  
The user does not have an existing account.

**Scenario Type:**  
Positive

**Steps:**
1. Open the registration page.
2. Fill in the fields: Full Name, email, phone number, password.
3. Select a role (Volunteer / Donor / Driver / Recipient).
4. Click **"Register"**.
5. Follow the link in the email to confirm the email address.

**Expected Result:**  
The profile is created, the email is confirmed, and the user status is **"Pending confirmation"**.

**Document Reference:**  
SRS 3.1.1–3.1.6; US/UC/AC 1.1.1, 3.1.1–3.1.5

---

## FE-REG-02 — Email validation during registration

**Priority:** High  
**Tags:** `registration`, `validation`

**Preconditions:**  
None.

**Scenario Type:**  
Negative

**Steps:**
1. Enter an invalid email, for example: `usergmail.com`.
2. Click **"Register"**.

**Expected Result:**  
The system highlights the field and displays the message **"Invalid email format"**.

**Document Reference:**  
SRS 3.1.3; AC 3.1.3

---

## FE-REG-09 — Missing document upload (volunteer / recipient)

**Priority:** High  
**Tags:** `registration`, `documents`, `validation`, `roles`

**Preconditions:**  
None.

**Scenario Type:**  
Negative

**Steps:**
1. Select the **"Volunteer"** or **"Recipient"** role.
2. Do not upload any documents.
3. Click **"Register"**.

**Expected Result:**  
The system highlights the document field or displays the message **"Please upload documents"**.

**Document Reference:**  
SRS 3.1.4–3.1.5

---

## FE-REG-11 — User approval by administrator

**Priority:** High  
**Tags:** `admin-verification`, `documents`

**Preconditions:**  
There is an application with the status **"Pending confirmation"**.

**Scenario Type:**  
Positive

**Steps:**
1. The admin opens the **"Applications"** section.
2. Reviews the user's documents.
3. Clicks **"Approve"**.

**Expected Result:**  
The user status changes to **"Verified"**, and an email notification is sent.

**Document Reference:**  
SRS 3.2.5.1; US/UC/AC 1.1.2, 3.1.6

---

## FE-REG-14 — Login with valid credentials

**Priority:** High  
**Tags:** `login`

**Preconditions:**  
The user is registered and has confirmed the email.

**Scenario Type:**  
Positive

**Steps:**
1. Enter the email and password.
2. Click **"Log in"**.

**Expected Result:**  
The user is successfully authenticated and redirected to the profile page.

**Document Reference:**  
SRS 3.1.3; UC 6
