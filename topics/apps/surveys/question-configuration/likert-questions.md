**Likert question: column Category**
Click the Columns tab and enter values, text and scores for your answer fields. 

- Name column headers
- Define associated scores: By entering scores, the system will automatically calculate Mean and Standard Deviation on these answer fields.

The Disable Column Heading Wrap option will force your column header to print in one horizontal row.

**Likert question: row Category**
Use Categories on likert rows to group scores for meaningful output. 

Decide if your likert analysis applies to the current question only, or multiple previous questions
- Current Question Only: Allows user to define likert feedback for the current question.
- Preceding Question(s)
   - All Scales: Allows user to define likert feedback for the preceding questions. This will make the current question hidden; it will only show up for the purpose of feedback on the Survey Review report. Feedback will display for every category defined.
   - Preceding Questions, Highest-Point Scale Only: Allows user to define likert feedback for the preceding questions. This will make the current question hidden; it will only show up for the purpose of feedback on the Survey Review report. Feedback will only display for the category that had the highest score.

For example, suppose you have a likert question with 4 rows:

What career is good for you?
1. I enjoy working alone at my own pace [category=Housekeeping]
2. I have experience cleaning outside my own home [category=Housekeeping]
3. I love interacting with people [category=Front Desk]
4. I like telling people about local attractions [category=Front Desk]

Scores for answers on the above questions will be grouped into 2 categories. The system will structure your likert feedback to allow you to enter scores and feedback for both Front Desk and Housekeeping.  

You can set this up on a single likert question or use the same categories over multiple questions to group data over multiple questions.  If you do this option, you will need to insert a likert summary question to configure the feedback.

Example 1
Question 1 text
	Answer option 1 [Category A]
	Answer option 2 [Category A]
	Answer option 3 [Category A]
Question 2 text
	Answer option 1 [Category B]
	Answer option 2 [Category B]
	Answer option 3 [Category B]
Question 3 (select Preceding Questions, All scales)
- Define feedback for Category A and Category B
- This will be hidden to the user, and display it’s feedback on the Survey Review report

Example 2
Question 1 text
	Answer option 1 [Category A]
	Answer option 2 [Category A]
	Answer option 3 [Category B]
	Answer option 4 [Category B]
	Answer option 5 [Category C]
	Answer option 6 [Category C]
- Define feedback for Categories A, B, & C.
- Feedback on the Survey Review report will summarize A, B, & C right on the current question.

**Enable Branches:** Check the Enable Branches box to set up skip patterns. When skip patterns are in play, the respondents answer to a question will skip them forward to a predetermined place in the survey. Note that branches will not work from inside a nested question, or to a nested question.

**Example: Skip to termination**
If you want to skip to a terminate survey scenario you have to have:
1. Question with branches enabled (Edit question, Options panel)
2. Add Page break 
3. Add Break question with termination text (This is important. Text on a Termination Question will not display)
4. Add termination question 
5. Add page break

**Please note:  Once a Likert Table is created, it is advised not to change the order of the questions or categories within that Likert Table. You would have to delete that Likert Table and recreate the Likert Table with the questions or categories in the order you would like it to be displayed.**