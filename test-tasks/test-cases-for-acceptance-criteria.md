## Test Task
Company “Dummy_Name” has implemented new functionality for employees to create vacation requests.
With this feature, employees can create a vacation for 1 full day or even half a day (4 hours). After approval by the PM and TL, the vacation becomes valid

### Acceptance Criteria

**AC01**
The user must be able to select a Start Date using a date picker. This field is mandatory and must not be left blank.

**AC02**
The user must be able to select an End Date using a date picker. The End Date must be the same as or later than the Start Date. This field is mandatory.

**AC03**
The user must select a Type from the dropdown menu. This is a required field. Available values: Spent, Business Trip

**AC04**
The user must be able to enter a numeric value in the Duration Hours field, including decimal numbers. The field must accept only positive numbers. A tooltip should be displayed for this field: “Set to 4 to create a half day vacation.”

**AC05**
The user may optionally select a Start Time from a dropdown or time picker. This field becomes mandatory only if Duration is not null.

**AC06**
The user may optionally select an End Time from a dropdown or time picker. If Start Time is selected, End Time becomes required and must be later than Start Time. This field is mandatory only if Duration is not null.

**AC07**
The Sub-Type value should be “Paid” by default. This field is required.

**AC08**
The user may enter optional text in the Comments field. This field should allow free text input and support multiline entries with a reasonable character limit (f.e., 500 characters)

**AC09**
If any required fields are left empty or invalid values are entered (for example, End Date earlier than Start Date), a validation message must be displayed.

**AC10**
The Next button must remain disabled until all mandatory fields are completed correctly. Once valid input is detected, the button becomes clickable.

**AC11**
The Previous button must take the user to the prior step in the flow without clearing the current form data.

---

## Task
Create a test cases to cover each Acceptance Criteria. Try to show that each TC covers the AC

---

