# Working with Markdown

Markdown is a simple way to format text using plain characters, instead of relying on buttons or complex editors. It is commonly used in documentation, emails, chat systems, and websites because it is easy to read and write.

With Markdown, you can quickly add structure and formatting such as:

### 1. Headings

To create a heading, add number signs (`#`) in front of a word or phrase. The number of number signs you use should correspond to the heading level. For example, to create a heading level three (`<h3>`), use three number signs (e.g., `### My Header`).

| Markdown                 | HTML                       | Rendered Output                               |
| ------------------------ | -------------------------- | --------------------------------------------- |
| `# Heading level 1`      | `<h1>Heading level 1</h1>` | <h2 id="heading-level-1">Heading level 1</h2> |
| `## Heading level 2`     | `<h2>Heading level 2</h2>` | <h3 id="heading-level-2">Heading level 2</h3> |
| `### Heading level 3`    | `<h3>Heading level 3</h3>` | <h4 id="heading-level-3">Heading level 3</h4> |
| `#### Heading level 4`   | `<h4>Heading level 4</h4>` | **Heading level 4**                           |
| `##### Heading level 5`  | `<h5>Heading level 5</h5>` | **Heading level 5**                           |
| `###### Heading level 6` | `<h6>Heading level 6</h6>` | **Heading level 6**                           |

#### 2. Bold

To bold text, add two asterisks or underscores before and after a word or phrase. To bold the middle of a word for emphasis, add two asterisks without spaces around the letters.

| Markdown                     | HTML                                      | Rendered Output            |
| ---------------------------- | ----------------------------------------- | -------------------------- |
| `I just love **bold text**.` | `I just love <strong>bold text</strong>.` | I just love **bold text**. |
| `I just love __bold text__.` | `I just love <strong>bold text</strong>.` | I just love **bold text**. |
| `Love **is** bold`           | `Love<strong>is</strong>bold`             | Love **is** bold           |

#### 3. Italic

To italicize text, add one asterisk or underscore before and after a word or phrase. To italicize the middle of a word for emphasis, add one asterisk without spaces around the letters.

| Markdown                               | HTML                                          | Rendered Output                      |
| -------------------------------------- | --------------------------------------------- | ------------------------------------ |
| `Italicized text is the *cat's meow*.` | `Italicized text is the <em>cat's meow</em>.` | Italicized text is the _cat’s meow_. |
| `Italicized text is the _cat's meow_.` | `Italicized text is the <em>cat's meow</em>.` | Italicized text is the _cat’s meow_. |
| `A *cat* meow`                         | `A <em>cat</em> meow`                         | A _cat_ meow                         |

#### 4. Ordered Lists

To create an ordered list, add line items with numbers followed by periods. The numbers don’t have to be in numerical order, but the list should start with the number one.

| Markdown                                                                                                                                                                                                | HTML                                                                                                                                                                                                                                                                                                                                                                                                                                                     | Rendered Output                                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><code>1. First item</code><br><code>2. Second item</code><br><code>3. Third item</code><br><code>4. Fourth item</code></p>                                                                           | <p><code>&#x3C;ol></code><br>  <code>&#x3C;li>First item&#x3C;/li></code><br>  <code>&#x3C;li>Second item&#x3C;/li></code><br>  <code>&#x3C;li>Third item&#x3C;/li></code><br>  <code>&#x3C;li>Fourth item&#x3C;/li></code><br><code>&#x3C;/ol></code></p>                                                                                                                                                                                               | <ol><li>First item</li><li>Second item</li><li>Third item</li><li>Fourth item</li></ol>                                                             |
| <p><code>1. First item</code><br><code>2. Second item</code><br><code>3. Third item</code><br>    <code>1. Indented item</code><br>    <code>2. Indented item</code><br><code>4. Fourth item</code></p> | <p><code>&#x3C;ol></code><br>  <code>&#x3C;li>First item&#x3C;/li></code><br>  <code>&#x3C;li>Second item&#x3C;/li></code><br>  <code>&#x3C;li>Third item</code><br>    <code>&#x3C;ol></code><br>      <code>&#x3C;li>Indented item&#x3C;/li></code><br>      <code>&#x3C;li>Indented item&#x3C;/li></code><br>    <code>&#x3C;/ol></code><br>  <code>&#x3C;/li></code><br>  <code>&#x3C;li>Fourth item&#x3C;/li></code><br><code>&#x3C;/ol></code></p> | <ol><li>First item</li><li>Second item</li><li><p>Third item</p><ol><li>Indented item</li><li>Indented item</li></ol></li><li>Fourth item</li></ol> |

#### 5. Unordered Lists

To create an unordered list, add dashes (`-`), asterisks (`*`), or plus signs (`+`) in front of line items. Indent one or more items to create a nested list.

| Markdown                                                                                                                                                                                          | HTML                                                                                                                                                                                                                                                                                                                                                                                                                                                     | Rendered Output                                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p><code>* First item</code><br><code>* Second item</code><br><code>* Third item</code><br><code>* Fourth item</code></p>                                                                         | <p><code>&#x3C;ul></code><br>  <code>&#x3C;li>First item&#x3C;/li></code><br>  <code>&#x3C;li>Second item&#x3C;/li></code><br>  <code>&#x3C;li>Third item&#x3C;/li></code><br>  <code>&#x3C;li>Fourth item&#x3C;/li></code><br><code>&#x3C;/ul></code></p>                                                                                                                                                                                               | <ul><li>First item</li><li>Second item</li><li>Third item</li><li>Fourth item</li></ul>                                                             |
| <p><code>* First item</code><br><code>* Second item</code><br><code>* Third item</code><br>    <code>* Indented item</code><br>    <code>* Indented item</code><br><code>* Fourth item</code></p> | <p><code>&#x3C;ul></code><br>  <code>&#x3C;li>First item&#x3C;/li></code><br>  <code>&#x3C;li>Second item&#x3C;/li></code><br>  <code>&#x3C;li>Third item</code><br>    <code>&#x3C;ul></code><br>      <code>&#x3C;li>Indented item&#x3C;/li></code><br>      <code>&#x3C;li>Indented item&#x3C;/li></code><br>    <code>&#x3C;/ul></code><br>  <code>&#x3C;/li></code><br>  <code>&#x3C;li>Fourth item&#x3C;/li></code><br><code>&#x3C;/ul></code></p> | <ul><li>First item</li><li>Second item</li><li><p>Third item</p><ul><li>Indented item</li><li>Indented item</li></ul></li><li>Fourth item</li></ul> |

#### 6. Table to content

Tables can be created within an Assessment Question, Answer Options. To add columns to the Assessment Question, use the below template/formula:&#x20;

Column 1 | Column 2 | Column 3 | Column 4

\--|--|--|--

Column 1 | Column 2 | Column 3 | Column 4\
Column 1 | Column 2 | Column 3 | Column 4\
Column 1 | Column 2 | Column 3 | Column 4\
Column 1 | Column 2 | Column 3 | Column 4\
Column 1 | Column 2 | Column 3 | Column 4

It will display as:

| Column 1 | Column 2 | Column 3 | Column 4 |
| -------- | -------- | -------- | -------- |
| Column 1 | Column 2 | Column 3 | Column 4 |
| Column 1 | Column 2 | Column 3 | Column 4 |
| Column 1 | Column 2 | Column 3 | Column 4 |
| Column 1 | Column 2 | Column 3 | Column 4 |
| Column 1 | Column 2 | Column 3 | Column 4 |

#### 7. Changing Font Color or Text <a href="#how-to-change-the-font-color-of-the-survey-question-text" id="how-to-change-the-font-color-of-the-survey-question-text"></a>

The HTML code needs to be added around the text as follows:

```
<span style="color:black">add text here</span>
```

You can change the color by typing the color name (e.g. `black`, `red`, `blue`) or adding the HTML color code (e.g. `#060606`, `#F90F0F`, `#0F0FF9`) after `color:` — for example, `color: blue` or `color: #060606`.<br>

#### 8. Changing Font Color and Size

The HTML code needs to be added around the text as follows:

```
<span style="font-size: 30px; color:green">insert text</span>
```

Instead of adding the Name of the Font (e.g. Green, Yellow, Blue, etc.) you are able to add the [HTML Color Code](https://html-color.codes/) (e.g. `#24ffff`, `#ff2424`, `#ffff24`, etc.).



#### 9. Superscript and Subscript <a href="#superscript-and-subscript" id="superscript-and-subscript"></a>

Superscripts can be written by surrounding a text by ^ characters; subscripts can be written by surrounding the subscripted text by \~ characters

* X<sup>2</sup> is created using X^2^ OR X\<sup>2\</sup>&#x20;
* 10<sup>-18</sup> is created as 10^-18^ OR 10\<sup>-18\</sup>
* H<sub>2</sub>O is created H\~2\~0 OR H\<sub>2\</sub>0
* Footnote 1<sup>†</sup> / Footnote 2<sup>‡</sup>  is created Footnote 1^†^ and Footnote 2^‡^&#x20;

#### 10. Adding Images

You are able to drag and drop a picture from file into the body of the content. Accounts are configured with a file size limit of 1MB per image. If the file size is bigger than 1MB, please decrease the size of your file before uploading it, or contact your administrator to upgrade the settings for your account. The recommended maximum size for an upload image is 800x800 pixels. If a size of your image is bigger 800x800 pixels, the system will automatically scale the image for you. You might want to resize your own images before you upload them.&#x20;

When you added the picture to the content, it will display in a URL format:&#x20;

!\[agriculture-1.jpg]\(https://e02.insite.com/files/sites/global/images/agriculture-1.jpg)

In the content you will only see the image, but if you launch the content in the portal, it will display the image.

<img src="https://docs.shiftiq.com/~gitbook/image?url=https%3A%2F%2Fe02.insite.com%2Ffiles%2Fsites%2Fglobal%2Fadding-images-or-videos%2Fagriculture-1.jpg&#x26;width=300&#x26;dpr=3&#x26;quality=100&#x26;sign=2e533096&#x26;sv=2" alt="Agriculture 1" height="530" width="800">

File types supported: .png, .gif, .jpg, .jpeg

#### 11. Adding Links

You are able to add web links or email addresses in the text of your content.

When you select Create Link in the content editor, the system will create the outline needed for the link **\[]\(http://)**. Between the square brackets, add the text you want to be displayed. Copy and Paste or type the webpage you want the user to be directed to.&#x20;

Example of what the link will look like: \
\[Shift iQ]\(http://www.shiftiq.com).&#x20;

In your page content, the link will display as [Shift iQ](http://www.shiftiq.com/). The user can click on the text and will be directed to the webpage you added.

You are able to configure the link with an email address instead. You can either add a email address between the square brackets or text. Instead of adding a website, you remove the http:// and add [mailto:add email address.](mailto:support@insite.com.) The full link will be \[Click Here to Email]\(mailto:support@shiftiq.com) or \[support@shiftiq.com]\(mailto:support@shiftiq.com). The text will display as [Click Here to Email](mailto:support@shiftiq.com) or [support@shiftiq.com](mailto:support@shiftiq.com)

#### 12. Adding a Link that opens in a new Browser Window

If you require the link you are inserting to open on in a new browser window, you can us the following link:&#x20;

* \<a href="url or link to file" target="\_blank">text to display\</a>

An example of the full link will be:&#x20;

* \<a href="http://www.shiftiq.com" target="\_blank">Shift iQ\</a>&#x20;
* The text will display as [Shift iQ](http://www.shiftiq.com/) and when you click on the text it will open the web page in a new browser window.
