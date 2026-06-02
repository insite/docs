# Working with Markdown

Markdown is a simple way to format text using plain characters, instead of relying on buttons or complex editors. It is commonly used in documentation, emails, chat systems, and websites because it is easy to read and write.

With Markdown, you can quickly add structure and formatting such as:

* **Headings** using `#`
* **Bold text** using `**text**`
* _Italic text_ using `*text*`
* Lists using dashes or numbers
* Links and simple formatting without special tools

It helps make content clearer and more organized while staying lightweight and easy to edit.

Below you will find information presented in Markdown format.

## Creating Tables to content

Tables can be created within an Assessment Question, Answer Options. To add columns to the Assessment Question, use the below template/formula:&#x20;

Column 1 | Column 2 | Column 3 | Column 4

\--|--|--|--

Column 1 | Column 2 | Column 3 | Column 4\
Column 1 | Column 2 | Column 3 | Column 4\
Column 1 | Column 2 | Column 3 | Column 4\
Column 1 | Column 2 | Column 3 | Column 4\
Column 1 | Column 2 | Column 3 | Column 4

## Changing Font Color or Text <a href="#how-to-change-the-font-color-of-the-survey-question-text" id="how-to-change-the-font-color-of-the-survey-question-text"></a>

The HTML code needs to be added around the text as follows:

```
<span style="color:black">add text here</span>
```

You can change the color by typing the color name (e.g. `black`, `red`, `blue`) or adding the HTML color code (e.g. `#060606`, `#F90F0F`, `#0F0FF9`) after `color:` — for example, `color: blue` or `color: #060606`.<br>

## Changing Font Color and Size

The HTML code needs to be added around the text as follows:

```
<span style="font-size: 30px; color:green">insert text</span>
```

Instead of adding the Name of the Font (e.g. Green, Yellow, Blue, etc.) you are able to add the [HTML Color Code](https://html-color.codes/) (e.g. `#24ffff`, `#ff2424`, `#ffff24`, etc.).



## Superscript and Subscript <a href="#superscript-and-subscript" id="superscript-and-subscript"></a>

Superscripts can be written by surrounding a text by ^ characters; subscripts can be written by surrounding the subscripted text by \~ characters

* X<sup>2</sup> is created using X^2^ OR X\<sup>2\</sup>&#x20;
* 10<sup>-18</sup> is created as 10^-18^ OR 10\<sup>-18\</sup>
* H<sub>2</sub>O is created H\~2\~0 OR H\<sub>2\</sub>0
* Footnote 1<sup>†</sup> / Footnote 2<sup>‡</sup>  is created Footnote 1^†^ and Footnote 2^‡^&#x20;







