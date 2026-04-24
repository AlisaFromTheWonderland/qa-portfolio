# Registration Test Cases

## FE-REG-01 — Successful user registration with valid data

**Preconditions:**  
The user does not have an existing account.

**Scenario type:**  
Positive

**Steps:**
1. Open the registration page.
2. Fill in the fields: Full Name, email, phone number, password.
3. Select a role (volunteer / donor / driver / recipient).
4. Click **“Register”**.
5. Follow the link in the email to confirm the email address.

**Expected Result:**  
The profile is created, the email is confirmed, and the user status is **“Pending confirmation”**.

**Document Reference:**  
SRS 3.1.1–3.1.6; US/UC/AC 1.1.1, 3.1.1–3.1.5

---

## FE-REG-02 — Email validation during registration

**Preconditions:**  
—

**Scenario type:**  
Negative

**Steps:**
1. Enter an invalid email, for example: `usergmail.com`.
2. Click **“Register”**.

**Expected Result:**  
The system highlights the field and displays the message **“Invalid email format”**.

**Document Reference:**  
SRS 3.1.3; AC 3.1.3

---

## FE-REG-03 — Phone number validation

**Preconditions:**  
—

**Scenario type:**  
Negative

**Steps:**
1. Enter a phone number in an invalid format, for example: `12345`.
2. Click **“Register”**.

**Expected Result:**  
The system displays the message **“Invalid phone number format”**.

**Document Reference:**  
SRS 3.1.3; AC 3.1.3

---

## FE-REG-04 — Volunteer registration with documents

**Preconditions:**  
—

**Scenario type:**  
Positive

**Steps:**
1. Select the **“Volunteer”** role.
2. Fill in all required fields.
3. Upload a photo of the volunteer ID.
4. Click **“Register”**.

**Expected Result:**  
The file is uploaded successfully, the profile is created, and the status is **“Pending confirmation”**.

**Document Reference:**  
SRS 3.1.4; AC 3.1.4

---

## FE-REG-05 — Recipient registration with documents

**Preconditions:**  
—

**Scenario type:**  
Positive

**Steps:**
1. Select the **“Aid Recipient”** role.
2. Upload a passport / IDP certificate.
3. Click **“Register”**.

**Expected Result:**  
The documents are saved, the profile is created, and the status is **“Pending confirmation”**.

**Document Reference:**  
SRS 3.1.5; AC 3.1.4

---

## FE-REG-06 — Submission is not possible without required fields

**Preconditions:**  
—

**Scenario type:**  
Negative

**Steps:**
1. Leave one of the required fields empty, for example: email.
2. Click **“Register”**.

**Expected Result:**  
The **“Register”** button is disabled or the message **“Please fill in all required fields”** is displayed.

**Document Reference:**  
AC 3.1.2

---

## FE-REG-07 — Re-registration with an already existing email

**Preconditions:**  
A user with this email already exists.

**Scenario type:**  
Negative

**Steps:**
1. Enter an already registered email.
2. Click **“Register”**.

**Expected Result:**  
The message **“A user with this email already exists”** is displayed.

**Document Reference:**  
SRS 3.1.6

---

## FE-REG-08 — Email confirmation after registration

**Preconditions:**  
The user is registered and has received the email.

**Scenario type:**  
Positive

**Steps:**
1. Open the email.
2. Click the confirmation link.
3. Log in.

**Expected Result:**  
The email is confirmed, and the user status changes to **“Pending administrator verification”**.

**Document Reference:**  
SRS 3.1.6; AC 3.1.3

---

## FE-REG-09 — Missing document upload (volunteer / recipient)

**Preconditions:**  
—

**Scenario type:**  
Negative

**Steps:**
1. Select the **“Volunteer”** or **“Recipient”** role.
2. Do not upload any documents.
3. Click **“Register”**.

**Expected Result:**  
The system highlights the document field or displays the message **“Please upload documents”**.

**Document Reference:**  
SRS 3.1.4–3.1.5

---

## FE-REG-10 — Reminder to admin after 48 hours if verification is not completed

**Preconditions:**  
There are unverified applications.

**Scenario type:**  
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

**Preconditions:**  
There is an application with the status **“Pending confirmation”**.

**Scenario type:**  
Positive

**Steps:**
1. The admin opens the **“Applications”** section.
2. Reviews the user's documents.
3. Clicks **“Approve”**.

**Expected Result:**  
The user status changes to **“Verified”**, and an email notification is sent.

**Document Reference:**  
SRS 3.2.5.1; US/UC/AC 1.1.2, 3.1.6

---

## FE-REG-12 — User rejection by administrator with reason provided

**Preconditions:**  
There is an application awaiting verification.

**Scenario type:**  
Positive

**Steps:**
1. Open the user's application.
2. Click **“Reject”**.
3. Enter the reason for rejection.
4. Confirm the action.

**Expected Result:**  
The user receives an email: **“Your application has been rejected. Reason: [comment]”**.

**Document Reference:**  
SRS 3.2.5.3; US/UC/AC 1.1.2

---

## FE-REG-13 — Rejection without a reason

**Preconditions:**  
There is an application under review.

**Scenario type:**  
Negative

**Steps:**
1. The admin clicks **“Reject”** without filling in the **“Comment”** field.

**Expected Result:**  
The system does not allow the action to be completed and displays the message **“Reason is required”**.

**Document Reference:**  
SRS 3.2.5.3; UC 3

---

## FE-REG-14 — Login with valid credentials

**Preconditions:**  
The user is registered and has confirmed the email.

**Scenario type:**  
Positive

**Steps:**
1. Enter the email and password.
2. Click **“Log in”**.

**Expected Result:**  
The user is successfully authenticated and redirected to the profile page.

**Document Reference:**  
SRS 3.1.3; UC 6

---

## FE-REG-15 — Login with incorrect password

**Preconditions:**  
The user exists.

**Scenario type:**  
Negative

**Steps:**
1. Enter the correct email but an incorrect password.
2. Click **“Log in”**.

**Expected Result:**  
The message **“Incorrect password”** is displayed.

**Document Reference:**  
UC 6

---

## FE-REG-16 — Login attempt by a non-existing user

**Preconditions:**  
—

**Scenario type:**  
Negative

**Steps:**
1. Enter a non-existing email.
2. Click **“Log in”**.

**Expected Result:**  
The message **“User not found”** is displayed.

**Document Reference:**  
SRS 3.1.3

---

## FE-REG-17 — Verification of selecting multiple roles

**Preconditions:**  
—

**Scenario type:**  
Positive

**Steps:**
1. On the registration screen, select **“Volunteer”** and **“Driver”**.
2. Click **“Register”**.

**Expected Result:**  
Both roles are added to the profile, and the status is **“Pending confirmation”**.

**Document Reference:**  
SRS 3.1.2; AC 3.1.1

---

## FE-REG-18 — Display of the “Pending confirmation” status in the profile

**Preconditions:**  
The user is registered but has not yet been approved by the administrator.

**Scenario type:**  
Positive

**Steps:**
1. Log in to the profile.
2. Check the status block.

**Expected Result:**  
The status **“Pending confirmation”** is displayed.

**Document Reference:**  
AC 3.1.5

---

## FE-REG-19 — Re-attempt to confirm email after the confirmation link has expired

**Preconditions:**  
The user received the email more than 24 hours ago.

**Scenario type:**  
Negative

**Steps:**
1. Click the old link in the email.
2. Try to confirm the email.

**Expected Result:**  
The message **“The link is invalid, please request a new confirmation email”** is displayed.

**Document Reference:**  
SRS 3.1.6

---

## FE-REG-20 — User cannot be verified without documents

**Preconditions:**  
The admin reviews an application without attached files.

**Scenario type:**  
Negative

**Steps:**
1. Open the application without documents.
2. Click **“Approve”**.

**Expected Result:**  
The message **“Verification is not possible without documents”** is displayed.

**Document Reference:**  
SRS 3.1.4–3.1.5; UC 3
