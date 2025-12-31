# Adding and Editing Site and Block Content

Add your site page or block content here using the Markdown or HTML editors. Markdown is a simple way to format text that looks great on any device. We recommend caution when using HTML, as there can be hidden formatting code that may not translate as expected on different computer platforms, screen sizes, or software versions.

Here are some formatting tips for using Markdown:

## Links

You are able to add web links or email addresses in the text of your content.

When you select Create Link, the system will create the outline needed for the link \[]\(http://). Between the square brackets, add the text you want to be displayed. Copy and Paste or type the webpage you want the user to be directed to.  Example of what the link will look like:  \[Shift iQ]\(https://www.shiftiq.com). In your page content, the link will display as [Shift iQ](https://www.shiftiq.com/). The user can click on the text and will be directed to the webpage you added.

You are able to configure the link with an email address instead. You can either add a email address between the square brackets or text. Instead of adding a website, you remove the http:// and add [mailto:add email address.](mailto:support@shiftiq.com.) The full link will be \[Click Here to Email]\(mailto:support@shiftiq.com) or \[support@shiftiq.com]\(mailto:support@shiftiq.com). The text will display as [Click Here to Email](mailto:support@shiftiq.com) or [support@shiftiq.com](mailto:support@shiftiq.com)

#### Open Link in New Browser Window:

If you require the link you are inserting to open on in a new browser window, you can us the following link:\
\<a href="url or link to file" target="\_blank">text to display\</a>

An example of the full link will be:\
\<a href="http://www.insite.com" target="\_blank">InSite Information Systems\</a>\
The text will display as [InSite Information Systems](http://www.insite.com/) and when you click on the text it will open the web page in a new browser window.

## Special Characters

You can force Markdown to print special characters using HTML. Please visit the site below for a more comprehensive list of HTML character codes:

* [https://www.rapidtables.com/web/html/html-codes.html](https://www.rapidtables.com/web/html/html-codes.html)

Text copied out of Microsoft word is renowned for having special characters that look nice, but are not universal.&#x20;

&#x20; If you’re copying text out of Word, we recommend replacing all special characters.\
Common replacements:\
<br>

| Special Character  | Markdown Equivalent  |
| ------------------ | -------------------- |
| <p>“ or ”<br></p>  | <p>“<br></p>         |
| <p>’<br></p>       | <p>’<br></p>         |
| <p>·<br></p>       | <p>-<br></p>         |
| <p>\<br></p>       | <p>\\<br></p>        |
| <p>*<br></p>       | <p>\*<br></p>        |
| <p>_<br></p>       | <p>\_ <br></p>       |
| <p>–<br></p>       | <p>-<br></p>         |
| <p>[ or ] <br></p> | <p>\[ or \] <br></p> |
| <p>{ or }<br></p>  | \\{ or \\}           |

| <p>Special Character<br></p> | <p>Markdown Equivalent<br></p> |
| ---------------------------- | ------------------------------ |
| <p>(or)<br></p>              | <p>\( or \) <br></p>           |
| <p>#<br></p>                 | <p>\#<br></p>                  |
| <p>+<br></p>                 | <p>\+<br></p>                  |
| <p>-<br></p>                 | <p>\-<br></p>                  |
| <p>.<br></p>                 | <p>\.<br></p>                  |
| <p>!<br></p>                 | <p>!<br></p>                   |

<br>

| <p>Special Character<br></p> | <p>Markdown Equivalent<br></p> |
| ---------------------------- | ------------------------------ |
| <p>®<br></p>                 | <p>&#x26;#174;<br></p>         |
| <p>TM <br></p>               | <p>&#x26;#8482;<br></p>        |
| <p>© <br></p>                | <p>&#x26;#xA9<br></p>          |
| <p>Ø<br></p>                 | <p>&#x26;#981;<br></p>         |
| <p>Ω<br></p>                 | <p>&#x26;#8486;<br></p>        |
| <p>∆<br></p>                 | <p>&#x26;Delta;<br></p>        |

### Superscript and Subscript

Superscripts can be written by surrounding a text by ^ characters; subscripts can be written by surrounding the subscripted text by \~ characters

H~~2~~O is a liquid. 2^10^ is 1024 .

H<sub>2</sub>O is a liquid. 2<sup>10</sup> is 1024

![markdown-1.png](https://e02.insite.com/files/sites/global/superscript-and-subscript/markdown-1.png)

Certain punctuation characters are exempted from the rule forbidding them within inline delimiters

One quintillionth can be expressed as 10^-18^

Daggers^†^ and double-daggers^‡^ can be used to denote notes. .

One quintillionth can be expressed as 10<sup>-18</sup>

Daggers<sup>†</sup> and double-daggers<sup>‡</sup> can be used to denote notes.

![markdown-2.png](https://e02.insite.com/files/sites/global/superscript-and-subscript/markdown-2.png)

[See **Markdown Extensions**](https://github.com/xoofx/markdig/blob/master/src/Markdig.Tests/Specs/EmphasisExtraSpecs.md)
