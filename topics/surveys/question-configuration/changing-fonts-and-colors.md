# Changing Fonts and Colors

Changing Survey Question Text and Response Options Font and Color\



The font and color in survey question text and response option text can be changed.&#x20;

The HTML code needs to be added around the text as follows: \
\<span style="font-size: 30px; color:green">insert text\</span>

Instead of adding the Name of the Font (e.g. Green, Yellow, Blue, etc.) you are able to add the \
[HTML Color Code ](https://html-color.codes/)(e.g. #24ffff , #ff2424  , #ffff24 , ect.)\
\
&#x20;![](../../../files/sites/global/changing-font-and-color/color-change-1.png)

\


![](../../../files/sites/global/changing-font-and-color/color-change-2.png)\


So, the above will display as follows: \


![](../../../files/sites/global/changing-font-and-color/color-change.png)\


\


Bold, Italic and Underline and Line Breaks for Survey Questions\



You are able to add Line Breaks, Bold, Underline, _Italicize_ sentences/words when adding answer options to an survey.\
HTML Code to Bold a sentence/word:Add \<b> in the beginning of the sentence/word and \</b> at the end.Example:  "\<b>This text is bold.\</b>" will display as "This text is bold."\
HTML Code for Underlining a sentence/word:\
Add \<u> in the beginning of the sentence/word and \</u> at the end.Example:  "The text is \<u>underlined\</u>." will display as "The text is underlined."\
HTML Code for _Italicizing_ a sentence/word:\
Add \<i> in the beginning of the sentence/word and \</i> at the end.\
Example:  "The text was \<i>Italicized\</i>." will display as "The text was _Italicized_."\
HTML code for adding a Line Break:Add \<br> at the end of your question option.Example:  "Adding a line break at the end of the question options.\<br> The next sentence will display in a new line." The text will display as:\
"Adding a line break at the end of the question options\
The next sentence will display in a new line."\
![](../../../files/sites/global/survey-questions-edit/bold-italic.png)\
\
![](../../../files/sites/global/survey-questions-edit/bold-italic-1.png)\
\
\


## Change font color of Question Text and Answer Options

\


## &#x20;

1\.  How to change the font color of the Answer Options in an Survey:

* Open the Survey and click on the Content tab.
* Under the Page Header tab, click the Edit button.
* Add the following code:\
  \
  \<style>.form-check-label {color: black;}\</style>\
  \

* You can change the color by typing the color name (e.g. black, red, blue) or adding the HTML color code (e.g. #060606, #F90F0F, #0F0FF9) behind color:\
  Example:   color: blue / color: #060606
* Click Save.

![](../../../files/sites/global/change-font-color/surveyfontcolor2.png)\
\
Please note:  Adding this code to the survey will change the color for all answer options in the survey.\
\


2\.  How to change the font color of the survey Question Text:

* Open the Survey and under the Questions tab, click the Pencil icon next to the question you want to change the font color for.
* Add the code \<span style="color:black">add text here\</span> in the Question Text field.
* Add your question text between "color:black"> and \</span
* You can change the color by typing the color name (e.g. black, red, blue) or adding the HTML color code (e.g. #060606, #F90F0F, #0F0FF9) behind color:\
  Example:   color: blue / color: #060606\

* Click Save.

\
![](../../../files/sites/global/change-font-color/surveyfontcolor.png)\
\
![](../../../files/sites/global/change-font-color/surveyfontcolor1.png)\
\


\


Note:  When you are adding the color coding, you need to make sure that there are no spaces in the code where there isn't supposed to be.

The code should look like this:  \<span style="color:#4f81bd">Add Content Here\</span>\
If spaces are in included in the code, where there shouldn't be spaces (e.g. < span style="color:#4f81bd">Add Content Here< /span> There is a space between the < and span in the beginning of the code and also between < and / at the end of the code), the code is not going to work correctly.

If you are copy and pasting this code, please make sure that the code copied correctly after pasting it, and fix it if it did not.
