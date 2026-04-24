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
1. Create a test cases to cover each Acceptance Criteria
2. Try to show that each TC covers the AC

---

# Completed Test Assignment

## 1. Test Cases Covering Acceptance Criteria

| ID | Name | Preconditions | Steps | Expected Result | Covered AC |
|---|---|---|---|---|---|
| AC01TC1 | Valid data in Start Date field | 1. All mandatory fields contain valid data, except Start Date  2. Start Date field is mandatory | 1. Open calendar  2. Choose next day  3. Confirm the choice  4. Click **Next** button | Navigation to the next page is performed | AC01, AC10 |
| AC01TC2 | Unselected Start Date | 1. Start Date field is mandatory | 1. Enter valid data in all mandatory fields except Start Date  2. Click **Next** button | Error message is shown: **"Start Date selection is mandatory. Please make your choice."** | AC01, AC09, AC10 |
| AC02TC1 | Valid data in End Date field | 1. All mandatory fields contain valid data, except End Date  2. End Date field is mandatory | 1. Open calendar  2. Choose a day after Start Date  3. Confirm the choice  4. Click **Next** button | Navigation to the next page is performed | AC02, AC10 |
| AC02TC2 | End Date is earlier than Start Date | 1. All mandatory fields contain valid data, except End Date  2. End Date field is mandatory | 1. Open calendar  2. Choose a day before Start Date  3. Confirm the choice  4. Click **Next** button | Error message is shown: **"End Date can't be earlier than Start Date. Please make the right choice."** | AC02, AC09 |
| AC03TC1 | Valid data in Type field | 1. All mandatory fields contain valid data, except Type  2. Type field is mandatory | 1. Open dropdown menu  2. Select **Spent**  3. Confirm the choice  4. Click **Next** button | Navigation to the next page is performed | AC03, AC10 |
| AC03TC2 | Unselected Type | 1. All mandatory fields contain valid data, except Type  2. Type field is mandatory | 1. Enter valid data in all mandatory fields except Type  2. Click **Next** button | Error message is shown: **"Type selection is mandatory. Please make your choice."** | AC03, AC09 |
| AC04TC1 | Duration Hours field contains valid data | 1. All mandatory fields contain valid data  2. Duration Hours field should accept only positive numbers | 1. Hover over the Duration Hours field  2. Enter value **4**  3. Confirm the value  4. Click **Next** button | 1. Tooltip appears: **"Set to 4 to create a half day vacation."**  2. Duration Hours field accepts valid data  3. Navigation to the next page is performed | AC04, AC10 |
| AC04TC2 | Duration Hours field contains letters | 1. All mandatory fields contain valid data  2. Duration Hours field accepts only positive numbers  3. Tooltip is present | 1. Enter letters in Duration Hours  2. Click **Next** button | Error message is shown: **"Field accepts only numbers. Please make your choice."** | AC04, AC09 |
| AC05TC1 | Start Time field contains valid data | 1. All mandatory fields contain valid data  2. Duration field contains valid data  3. Start Time becomes mandatory  4. End Time contains valid data | 1. Open Start Time dropdown  2. Select valid time  3. Click **Next** button | Navigation to the next page is performed | AC05, AC10 |
| AC05TC2 | Unselected Start Time when Duration is not null | 1. All mandatory fields contain valid data  2. Duration field contains valid data  3. Start Time becomes mandatory | 1. Leave Start Time empty  2. Open End Time dropdown  3. Select valid time  4. Click **Next** button | Error message is shown: **"Start Time selection is mandatory. Please make your choice."** | AC05, AC09 |
| AC06TC1 | End Time field contains valid data | 1. All mandatory fields contain valid data  2. Duration field contains valid data  3. Start Time contains valid data  4. End Time becomes mandatory | 1. Open End Time dropdown  2. Select a valid time later than Start Time  3. Click **Next** button | Navigation to the next page is performed | AC06, AC10 |
| AC06TC2 | End Time equals Start Time | 1. All mandatory fields contain valid data  2. Duration field contains valid data  3. Start Time contains valid data  4. End Time becomes mandatory | 1. Open End Time dropdown  2. Select the same value as Start Time  3. Click **Next** button | Error message is shown: **"End Time can't be the same as Start Time. Please make your choice."** | AC06, AC09 |
| AC07TC1 | Valid default value in Sub-Type field | 1. All mandatory fields contain valid data  2. Sub-Type field contains default value | 1. Leave the default value in Sub-Type  2. Click **Next** button | Navigation to the next page is performed | AC07, AC10 |
| AC07TC2 | Empty Sub-Type field | 1. All mandatory fields contain valid data  2. Sub-Type field contains default value | 1. Focus on Sub-Type field  2. Clear the value  3. Click **Next** button | Error message is shown: **"Sub-Type selection is mandatory. Please make your choice."** | AC07, AC09 |
| AC08TC1 | Comments field contains valid data under 500 characters | 1. All mandatory fields contain valid data  2. Comments field limit is 500 characters | 1. Enter valid text in Comments  2. Click **Next** button | Navigation to the next page is performed | AC08 |
| AC08TC2 | Comments field contains more than 500 characters | 1. All mandatory fields contain valid data  2. Comments field limit is 500 characters | 1. Enter more than 500 characters in Comments  2. Click **Next** button | Error message is shown: **"Comments field has a limit of 500 characters."** | AC08, AC09 |
| AC09TC1 | End Time earlier than Start Time | 1. All mandatory fields contain valid data  2. Duration field contains valid data  3. Start Time contains valid data  4. End Time becomes mandatory | 1. Open End Time dropdown  2. Select a value earlier than Start Time  3. Click **Next** button | Error message is shown: **"End Time can't be earlier than Start Time. Please make your choice."** | AC06, AC09 |
| AC10TC1 | Next button becomes active with valid data | 1. Next button is disabled | 1. Enter valid data in all mandatory fields | Next button becomes active | AC10 |
| AC11TC1 | Entered data is retained after clicking Previous | 1. All mandatory fields contain valid data | 1. Click **Previous** button  2. Click **Next** button | Previously entered values are retained in the fields | AC11 |

## 2. Traceability Between Acceptance Criteria and Test Cases

| AC | Covered by Test Cases |
|---|---|
| AC01 | AC01TC1, AC01TC2 |
| AC02 | AC02TC1, AC02TC2 |
| AC03 | AC03TC1, AC03TC2 |
| AC04 | AC04TC1, AC04TC2 |
| AC05 | AC05TC1, AC05TC2 |
| AC06 | AC06TC1, AC06TC2, AC09TC1 |
| AC07 | AC07TC1, AC07TC2 |
| AC08 | AC08TC1, AC08TC2 |
| AC09 | AC01TC2, AC02TC2, AC03TC2, AC04TC2, AC05TC2, AC06TC2, AC08TC2, AC09TC1 |
| AC10 | AC01TC1, AC02TC1, AC03TC1, AC04TC1, AC05TC1, AC06TC1, AC07TC1, AC10TC1 |
| AC11 | AC11TC1 |
