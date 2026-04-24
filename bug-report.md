ID	
	[AC01][TC2][BR01]
Summary:	
	Next btn becomes active when Start Date selection is not made
Environment:	
	TestTask, MacOS, Chrome
Preconditons:	
	1. Start Date field contains a default value equal to the current date
	2. Start Date field is mandatory
Steps:	
	1. Enter to all mandatory fields valid data, except Start Date
Actual result:	
	1. Next btn becomes active
	2. Ability to navigate to the next page
	3. User does not make a selection in a mandatory field
Expected result:	
	1. Start Date field contains an empty value by default
	2. Next btn is inactive
	
