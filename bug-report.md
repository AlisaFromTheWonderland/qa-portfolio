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
