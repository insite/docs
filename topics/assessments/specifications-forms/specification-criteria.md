# Applying Specification Criteria

**Once the Specification has been created, you can apply filtering criteria to refine which questions are displayed on the exam Form. Filtering criteria can be applied to all questions or to each question set in the bank.**

-  Navigate to the **Specification Panel** and click on **Add Criteria**.
- Select the **Question Set** to which this criteria applies. Questions that match the criteria here will become available to include on forms.
- Select the **Filter Type**:
   - **Include All Questions:** All questions from the question set will be included in the form, up to the 
question item limit indicated (Ex. A set with 12 questions and a limit of 6 would select 6 questions 
from this set)
   - **Question Tag Filter:** Tags applied to questions in the bank can be used to refine the questions 
selected.(Ex “t1:1” means select one question with the tag “t1” from this set)
   - **Pivot Table Filter.** This feature will allow for questions to be selected across several criteria (Ex. Questions that are aligned to a particular competency AND of a certain difficulty)
- Configure **Question Set Weight**. The desired weighting for the question set to which this criterion applies, within the overall specification. The sum of all question set weights for the criteria in a specification must equal 1 (i.e. 100 percent).
- Confiqure **Question Item Limit**. The maximum number of question items allowed on an exam form from this question set.
- Click on **Save**

**Important Note:**
The **Set Weight** stores the value entered by an administrator in **GAC %** column on **Workshop** page and helps calculate the values for the **Pivot Table Filter**, and then the **Pivot Table Filter** will determine the set number of questions on the form. In other words, the **Set Weight** only makes sense when the **Filter Type** in the Specification is set to **Filter with Pivot Table**.

The **Set Weight** is not used in question filtering, even when **Filter Type** is **Filter with Pivot Table**. The **Pivot Table Filter** only applies to the questions filter while the **Set Weight** is only used to store the value that was used to calculate the **Pivot Table Filter** values.

The value in the **Question Limit** only affects the set of form questions when the **Filter Type** is set to **Include All Questions**. **Set Weight** is not applicable and has no effect on the creation, delivery, or marking of the form if the **Filter Type** is set to **Include All Questions**.

Once the **Specification** has been completed, proceed to creating a **Form**.

**Specification**: Set of rules that questions adhere to.
**Form**: How the questions are displayed.
