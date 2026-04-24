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

---

## BUG-001 — App language is tied to App Store country instead of device language

| Field | Value |
|---|---|
| **Bug ID** | BUG-001 |
| **Title** | App language is tied to App Store country, not device language |
| **Environment** | Device: iPhone 14<br>OS: iOS 26 (beta)<br>App: Prod build 5.3.2<br>Network: Wi-Fi |
| **Severity** | Medium |
| **Priority** | Medium |
| **Status** | Open |

**Preconditions**
1. The App Store country/region is set to Poland.
2. The device interface language is set to Ukrainian.
3. The app is successfully installed on the device.

**Steps to Reproduce**
1. Open the app.

**Expected Result**
1. The app interface language matches the device interface language.
2. There is an option to change the language.

**Actual Result**
1. The app interface language matches the App Store country/region language.
2. There is no option to change the language.
