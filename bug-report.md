## [AC01][TC2][BR01] — Next button becomes active when Start Date is not selected

| Field | Value |
|---|---|
| **Bug ID** | [AC01][TC2][BR01] |
| **Summary** | Next button becomes active when Start Date selection is not made |
| **Environment** | TestTask, macOS, Chrome |
| **Severity** | Medium |
| **Priority** | High |
| **Status** | Open |

**Preconditions**
1. The **Start Date** field contains a default value equal to the current date.
2. The **Start Date** field is mandatory.

**Steps to Reproduce**
1. Fill in all mandatory fields with valid data except **Start Date**.

**Actual Result**
1. The **Next** button becomes active.
2. The user is able to navigate to the next page.
3. The user does not make a selection in a mandatory field.

**Expected Result**
1. The **Start Date** field should be empty by default.
2. The **Next** button should remain inactive.

<img height="100" alt="image" src="https://github.com/user-attachments/assets/970b7953-9bf1-4a2f-bbee-26ff70c2204e" />

---

## BUG-003 — Untranslated menu item in Polish locale

| Field | Value |
|---|---|
| **Bug ID** | BUG-003 |
| **Title** | Untranslated menu item (Polish locale) |
| **Environment** | Device: iPhone 14<br>OS: iOS 26 (beta)<br>App: Prod build 5.3.2<br>Network: Wi-Fi |
| **Severity** | Low |
| **Priority** | Medium |
| **Status** | Open |

**Preconditions**
1. The app is successfully installed on the device.
2. The user is registered and logged into the system.
3. The app interface language is set to Polish.

**Steps to Reproduce**
1. Open the menu in the app.

**Expected Result**
All menu items are displayed in Polish.

**Actual Result**
One menu item is displayed in English.

<img height="100" alt="image" src="https://github.com/user-attachments/assets/aacf91d2-0b3d-4525-878a-6218f481fbae" />
