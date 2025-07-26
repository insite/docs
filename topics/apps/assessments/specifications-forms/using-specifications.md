Every Bank will contain at least ONE Specification. Specifications provide the rules that determinewhich questions will be contained on an exam Form. The same Specification may be used for multiple Forms, or there may be a different specification for each Form.

![specification.png](https://e02.insite.com/files/sites/global/using-specifications/specification.png)

![specification-2.png](https://e02.insite.com/files/sites/global/9844/specification-2.png)


**Important Note when using Filter Type in Specifications:**
The **Set Weight** stores the value entered by an administrator in **GAC %** column on **Workshop** page and helps calculate the values for the **Pivot Table Filter**, and then the **Pivot Table Filter** will determine the set number of questions on the form. In other words, the **Set Weight** only makes sense when the **Filter Type** in the Specification is set to **Filter with Pivot Table**.

The **Set Weight** is not used in question filtering, even when **Filter Type** is **Filter with Pivot Table**. The **Pivot Table Filter** only applies to the questions filter while the **Set Weight** is only used to store the value that was used to calculate the **Pivot Table Filter** values.

The value in the **Question Limit** only affects the set of form questions when the **Filter Type** is set to **Include All Questions**. **Set Weight** is not applicable and has no effect on the creation, delivery, or marking of the form if the **Filter Type** is set to **Include All Questions**.