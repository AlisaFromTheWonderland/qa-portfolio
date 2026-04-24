# Registration Test Cases

A structured set of **manual test cases** covering the **registration, email confirmation, verification, and login flows** for a role-based platform.

---

## Table of Contents

- [Scope](#scope)
- [Test Data](#test-data)
- [Priority Legend](#priority-legend)
- [Tags Used](#tags-used)
- [Test Cases](#test-cases)
  - [FE-REG-01 — Successful user registration with valid data](#fe-reg-01--successful-user-registration-with-valid-data)
  - [FE-REG-02 — Email validation during registration](#fe-reg-02--email-validation-during-registration)
  - [FE-REG-03 — Phone number validation](#fe-reg-03--phone-number-validation)
  - [FE-REG-04 — Volunteer registration with documents](#fe-reg-04--volunteer-registration-with-documents)
  - [FE-REG-05 — Recipient registration with documents](#fe-reg-05--recipient-registration-with-documents)
  - [FE-REG-06 — Submission is not possible without required fields](#fe-reg-06--submission-is-not-possible-without-required-fields)
  - [FE-REG-07 — Re-registration with an already existing email](#fe-reg-07--re-registration-with-an-already-existing-email)
  - [FE-REG-08 — Email confirmation after registration](#fe-reg-08--email-confirmation-after-registration)
  - [FE-REG-09 — Missing document upload (volunteer / recipient)](#fe-reg-09--missing-document-upload-volunteer--recipient)
  - [FE-REG-10 — Reminder to admin after 48 hours if verification is not completed](#fe-reg-10--reminder-to-admin-after-48-hours-if-verification-is-not-completed)
  - [FE-REG-11 — User approval by administrator](#fe-reg-11--user-approval-by-administrator)
  - [FE-REG-12 — User rejection by administrator with reason provided](#fe-reg-12--user-rejection-by-administrator-with-reason-provided)
  - [FE-REG-13 — Rejection without a reason](#fe-reg-13--rejection-without-a-reason)
  - [FE-REG-14 — Login with valid credentials](#fe-reg-14--login-with-valid-credentials)
  - [FE-REG-15 — Login with incorrect password](#fe-reg-15--login-with-incorrect-password)
  - [FE-REG-16 — Login attempt by a non-existing user](#fe-reg-16--login-attempt-by-a-non-existing-user)
  - [FE-REG-17 — Verification of selecting multiple roles](#fe-reg-17--verification-of-selecting-multiple-roles)
  - [FE-REG-18 — Display of the Pending confirmation status in the profile](#fe-reg-18--display-of-the-pending-confirmation-status-in-the-profile)
  - [FE-REG-19 — Re-attempt to confirm email after the confirmation link has expired](#fe-reg-19--re-attempt-to-confirm-email-after-the-confirmation-link-has-expired)
  - [FE-REG-20 — User cannot be verified without documents](#fe-reg-20--user-cannot-be-verified-without-documents)

---

## Scope

This document covers the following functional areas:

- user registration
- field validation
- role selection
- document upload
- email confirmation
- administrator verification flow
- rejection flow
- login flow
- profile status display
- reminder logic for pending verification

---

## Test Data

Sample test data used in registration and login scenarios:

| Field | Example Value |
|---|---|
| Full Name | John Smith |
| Valid Email | john.smith.qa@example.com |
| Invalid Email | usergmail.com |
| Existing Email | existing.user@example.com |
| Valid Phone | +48123456789 |
| Invalid Phone | 12345 |
| Valid Password | QaTest123! |
| Wrong Password | WrongPass123 |
| Roles | Volunteer / Donor / Driver / Recipient |
| Document Example | volunteer_id.jpg / idp_certificate.pdf |

> Replace test data values according to your environment, test account strategy, and validation rules.

---

## Priority Legend

- **High** — critical core functionality, blocks user flow or core business logic
- **Medium** — important behavior, but not system-blocking
- **Low** — supportive or informational functionality

---

## Tags Used

- `registration`
- `validation`
- `documents`
- `email-confirmation`
- `admin-verification`
- `login`
- `roles`
- `status`
- `notification`

---

## Test Cases

---

## FE-REG-01 — Successful user registration with valid data

**Priority:** High  
**Tags:** `registration`, `email-confirmation`, `roles`

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

## FE-REG-03 — Phone number validation

**Priority:** High  
**Tags:** `registration`, `validation`

**Preconditions:**  
None.

**Scenario Type:**  
Negative

**Steps:**
1. Enter a phone number in an invalid format, for example: `12345`.
2. Click **"Register"**.

**Expected Result:**  
The system displays the message **"Invalid phone number format"**.

**Document Reference:**  
SRS 3.1.3; AC 3.1.3

---

## FE-REG-04 — Volunteer registration with documents

**Priority:** High  
**Tags:** `registration`, `documents`, `roles`

**Preconditions:**  
None.

**Scenario Type:**  
Positive

**Steps:**
1. Select the **"Volunteer"** role.
2. Fill in all required fields.
3. Upload a photo of the volunteer ID.
4. Click **"Register"**.

**Expected Result:**  
The file is uploaded successfully, the profile is created, and the status is **"Pending confirmation"**.

**Document Reference:**  
SRS 3.1.4; AC 3.1.4

---

## FE-REG-05 — Recipient registration with documents

**Priority:** High  
**Tags:** `registration`, `documents`, `roles`

**Preconditions:**  
None.

**Scenario Type:**  
Positive

**Steps:**
1. Select the **"Aid Recipient"** role.
2. Upload a passport / IDP certificate.
3. Click **"Register"**.

**Expected Result:**  
The documents are saved, the profile is created, and the status is **"Pending confirmation"**.

**Document Reference:**  
SRS 3.1.5; AC 3.1.4

---

## FE-REG-06 — Submission is not possible without required fields

**Priority:** High  
**Tags:** `registration`, `validation`

**Preconditions:**  
None.

**Scenario Type:**  
Negative

**Steps:**
1. Leave one of the required fields empty, for example: email.
2. Click **"Register"**.

**Expected Result:**  
The **"Register"** button is disabled or the message **"Please fill in all required fields"** is displayed.

**Document Reference:**  
AC 3.1.2

---

## FE-REG-07 — Re-registration with an already existing email

**Priority:** High  
**Tags:** `registration`, `validation`

**Preconditions:**  
A user with this email already exists.

**Scenario Type:**  
Negative

**Steps:**
1. Enter an already registered email.
2. Click **"Register"**.

**Expected Result:**  
The message **"A user with this email already exists"** is displayed.

**Document Reference:**  
SRS 3.1.6

---

## FE-REG-08 — Email confirmation after registration

**Priority:** High  
**Tags:** `registration`, `email-confirmation`

**Preconditions:**  
The user is registered and has received the email.

**Scenario Type:**  
Positive

**Steps:**
1. Open the email.
2. Click the confirmation link.
3. Log in.

**Expected Result:**  
The email is confirmed, and the user status changes to **"Pending administrator verification"**.

**Document Reference:**  
SRS 3.1.6; AC 3.1.3

---

## FE-REG-09 — Missing document upload (volunteer / recipient)

**Priority:** High  
**Tags:** `registration`, `documents`, `validation`

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

## FE-REG-10 — Reminder to admin after 48 hours if verification is not completed

**Priority:** Medium  
**Tags:** `admin-verification`, `notification`

**Preconditions:**  
There are unverified applications.

**Scenario Type:**  
Positive

**Steps:**
1. Register a user.
2. Do not verify the application by an administrator within 48 hours.

**Expected Result:**  
The system sends a reminder to the administrator.

**Document Reference:**  
SRS 3.1.8; AC 3.5.2

---

## FE-REG-11 — User approval by administrator

**Priority:** High  
**Tags:** `admin-verification`, `documents`, `status`

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

## FE-REG-12 — User rejection by administrator with reason provided

**Priority:** High  
**Tags:** `admin-verification`, `notification`

**Preconditions:**  
There is an application awaiting verification.

**Scenario Type:**  
Positive

**Steps:**
1. Open the user's application.
2. Click **"Reject"**.
3. Enter the reason for rejection.
4. Confirm the action.

**Expected Result:**  
The user receives an email: **"Your application has been rejected. Reason: [comment]"**.

**Document Reference:**  
SRS 3.2.5.3; US/UC/AC 1.1.2

---

## FE-REG-13 — Rejection without a reason

**Priority:** High  
**Tags:** `admin-verification`, `validation`

**Preconditions:**  
There is an application under review.

**Scenario Type:**  
Negative

**Steps:**
1. The admin clicks **"Reject"** without filling in the **"Comment"** field.

**Expected Result:**  
The system does not allow the action to be completed and displays the message **"Reason is required"**.

**Document Reference:**  
SRS 3.2.5.3; UC 3

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

---

## FE-REG-15 — Login with incorrect password

**Priority:** High  
**Tags:** `login`, `validation`

**Preconditions:**  
The user exists.

**Scenario Type:**  
Negative

**Steps:**
1. Enter the correct email but an incorrect password.
2. Click **"Log in"**.

**Expected Result:**  
The message **"Incorrect password"** is displayed.

**Document Reference:**  
UC 6

---

## FE-REG-16 — Login attempt by a non-existing user

**Priority:** High  
**Tags:** `login`, `validation`

**Preconditions:**  
None.

**Scenario Type:**  
Negative

**Steps:**
1. Enter a non-existing email.
2. Click **"Log in"**.

**Expected Result:**  
The message **"User not found"** is displayed.

**Document Reference:**  
SRS 3.1.3

---

## FE-REG-17 — Verification of selecting multiple roles

**Priority:** Medium  
**Tags:** `registration`, `roles`

**Preconditions:**  
None.

**Scenario Type:**  
Positive

**Steps:**
1. On the registration screen, select **"Volunteer"** and **"Driver"**.
2. Click **"Register"**.

**Expected Result:**  
Both roles are added to the profile, and the status is **"Pending confirmation"**.

**Document Reference:**  
SRS 3.1.2; AC 3.1.1

---

## FE-REG-18 — Display of the Pending confirmation status in the profile

**Priority:** Medium  
**Tags:** `status`, `profile`

**Preconditions:**  
The user is registered but has not yet been approved by the administrator.

**Scenario Type:**  
Positive

**Steps:**
1. Log in to the profile.
2. Check the status block.

**Expected Result:**  
The status **"Pending confirmation"** is displayed.

**Document Reference:**  
AC 3.1.5

---

## FE-REG-19 — Re-attempt to confirm email after the confirmation link has expired

**Priority:** Medium  
**Tags:** `email-confirmation`, `validation`

**Preconditions:**  
The user received the email more than 24 hours ago.

**Scenario Type:**  
Negative

**Steps:**
1. Click the old link in the email.
2. Try to confirm the email.

**Expected Result:**  
The message **"The link is invalid, please request a new confirmation email"** is displayed.

**Document Reference:**  
SRS 3.1.6

---

## FE-REG-20 — User cannot be verified without documents

**Priority:** High  
**Tags:** `admin-verification`, `documents`, `validation`

**Preconditions:**  
The admin reviews an application without attached files.

**Scenario Type:**  
Negative

**Steps:**
1. Open the application without documents.
2. Click **"Approve"**.

**Expected Result:**  
The message **"Verification is not possible without documents"** is displayed.

**Document Reference:**  
SRS 3.1.4–3.1.5; UC 3
