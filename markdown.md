---
title: Markdown Tips
tags:
  - Test
---

Markdown 是一个非常方便的轻量级标记语言，非常适合平时用来写写笔记、小论文以及个人主页。  

本文将介绍我在使用 Markdown 时的一些经验以及近乎所有的 Markdown 语法列表及注意事项。  

⚠️ **本文部分内容具有一定的平台(VSCode and My Jekyll Blog Theme)依赖，不同的平台在 Markdown 语法的支持上存在差异，因此部分内容仅供参考。下面说的 Jekyll 指的是我的Jekyll Blog主题，可以通过我的 [GitHub][github] 仓库查看具体的代码。**  


## VS Code Plugins  


### Markdown Preview Enhanced  

一个非常好的插件，支持预览以及导出各种格式，如pdf、png、html等；同时自带多种主题，还可以通过CSS自定义样式。缺点就是对于 CSS 语法的兼容性不怎么好，对新手以及非前端工作者比较不友好。  

详细功能请参照[官方文档][markdown-preview-enhanced]。  

另外，给一个比较好的 CSS [主题] [css-theme]。在导出长代码的时侯，主题会出问题，可以通过添加下面的语句解决：

```css
  @media print {
      table, pre {
          page-break-inside: avoid;
      }
      pre code {
          word-wrap: break-word;
          white-space: pre-wrap;
          overflow-wrap: break-word;
      }
  }
```

✏️ **VS Code 插件 Markdown Preview Enhanced 渲染的围栏式（前后三个反引号包围的）代码块 HTML 代码为 `<pre><code> ... </code></pre>`（整个 Markdown 文档只有一个 `<div>` 标签），而 Jekyll 渲染的则是 `<div><pre><code> ... </code></pre></div>`。**  

对于我而言，这一个插件就够用了。我Blog主题的作者还推荐了两款用来规范格式的插件，有利于优化写作的习惯，但是很难处理上面说的平台对 Markdown 语法的支持问题，因此格式这方面我认为自己把控比较好。想了解的可以参考其文章，同时我下面提到的排版技巧也出自这篇文章：  

[Markdown 写作心得][markdown-writing]


## 排版技巧

首先，给个专业的建议：

[中文文案排版指北][chinese-copywriting-guidelines]


### 图片插入

- 本地
  - 不建议，兼容性较差，除非你导出pdf
- 图床
  - 推荐GitHub仓库+jsdelivr
  - 优点：免费、稳定、支持图片压缩、支持图片缓存、支持图片防盗链
  - 缺点：图片管理麻烦、图片上传后可能需要一段时间才能访问到
  - 步骤：
    1. 注册GitHub账号，新建仓库
    2. 上传图片到仓库
    3. 获取图片链接，如`https://cdn.jsdelivr.net/gh/username/repo@latest/image.png`
    4. 在Markdown中插入图片链接
- Base64 编码
  - 直接将图片编码，可能会比较长

一般来说，对于大一点的图片，用图床比较好；小一点的文件直接用压缩然后用Base64编码插入就好。下面是一个图片压缩工具以及 Base64 编码工具的链接：  

- [图片压缩工具][image-compress]  
- [Base64 编码工具][base64-encoder]  


## Markdown Syntax Cheatsheet


### Headings

Markdown 中使用井号 `#` 加空格的方式表示表题，`#` 的数量表示标题级别。对应于 HTML 中的 `<h1>` 到 `<h6>` 标签。例如，下面的语句分别表示一级标题、二级标题、三级标题：

```md
# Heading level 1
## Heading level 2
### Heading level 3
```

另外，一级标题和二级标题也可以表示为：

```md  
Heading level 1  
===  
  
Heading level 2  
---  
```  

⚠️ **不要像下面那样将标题夹在正文中间，否则可能会出问题。**

```md
Without blank lines, this might not look right.
# Heading
Don't do this!
```


### Paragraphs

Markdown 使用空行将两个段落隔开，对应于 HTML 中的 `<p>` 标签。

⚠️ **段落前面不要使用回车键，否则可能导致意料之外的格式错误；因为回车键也可以作为代码块的以一种表示。**  

### Line Breaks

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| This is the first line.**(there's two or more spaces, you can also use `<br>`)**<br>And this is the second line. | `<p>This is the first line.<br>And this is the second line.</p>` | This is the first line.<br>And this is the second line. |

⚠️ **不要使用在一行后加反斜杠 \\ 或者什么都不加来代表换行；但是在VS Code中，换行也可以用回车键表示。**


### Emphasis

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| I just love \*\*blod text\*\*. | `I just love <strong>blod text</strong>` | I just love **blod text** |
| I just love \_\_blod text\_\_. | `I just love <strong>blod text</strong>` | I just love __blod text__ |
| Love\*\*is\*\*bold | `Love<strong>is</strong>bold` | Love**is**bold |

⚠️ **不要这样用`Love__is__bold`。**


### Italic

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| Italicized text is the \*cat's meow\*. | `Italicized text is the <em>cat's meow</em>.` | Italicized text is the *cat's meow*. |
| Italicized text is the \_cat's meow\_. | `Italicized text is the <em>cat's meow</em>.` | Italicized text is the _cat's meow_. |
| A\*cat\*meow | `A<em>cat</em>meow` | A*cat*meow |

⚠️ **不要用`A_cat_meow`。**  


### Bold and Italic

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| This text is \*\*\*really important\*\*\*. | `This text is <em><strong>really important</strong></em>.` | This text is ***really important***. |
| This text is \_\_\_really important\_\_\_. | `This text is <em><strong>really important</strong></em>.` | This text is ___really important___. |
| This text is \_\_\*really important\*\_\_. | `This text is <em><strong>really important</strong></em>.` | This text is __*really important*__. |
| This text is \*\*\_really important\_\*\*. | `This text is <em><strong>really important</strong></em>.` | This text is **_really important_**. |
| This is really\*\*\*very\*\*\*important text. | `This is really<em><strong>very</strong></em>important text.` | This is really***very***important text. |

⚠️ **不要这样写`This is really__very__important text.`。**  


### Blockquotes

`> Dorothy followed her through many of the beautiful rooms in her castle.`

> Dorothy followed her through many of the beautiful rooms in her castle.

#### Blockquotes with Multiple Paragraphs

```md
> Dorothy followed her through many of the beautiful rooms in her castle.
>
> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.
```

> Dorothy followed her through many of the beautiful rooms in her castle.
>
> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.

#### Nested Blockquotes

```md
> Dorothy followed her through many of the beautiful rooms in her castle.
>
>> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.
```

> Dorothy followed her through many of the beautiful rooms in her castle.
>
>> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.

#### Blockquotes with Other Elements

```md 
> ##### The quarterly results look great!
>
> - Revenue was off the chart.
> - Profits were higher than ever.
>
>  *Everything* is going according to **plan**.
```

> ##### The quarterly results look great!
>
> - Revenue was off the chart.
> - Profits were higher than ever.
>
> *Everything* is going according to **plan**.

⚠️

```md
Without blank lines, this might not look right.
> This is a blockquote
Don't do this!
```


### Lists

Markdown 使用数字加点 `.` 加空格表示有序列表，减号 `-` 、星号 `*` 、加号 `+` 加空格的方式表示无序列表。对应于 HTML 中的 `<ul>` 和 `<ol>` 标签。
并使用 `tab` 键缩进表示子列表。对应于 HTML 中的 `<li>` 标签。  
对于有序列表，数字可以是乱序的，不影响正常渲染。

⚠️ **对某些平台可用，但不建议使用。**

```md
+ First item
* Secoind item
- Third item
+ Fourth item

1) First item
2) Second item
3) Third item
```

#### Adding Element in Lists

##### Paragraphs

```md
- This is the first list item.
- Here's the second list item.

    I need to add another paragraph below the second list item.

- And here's the third list item.
```

- This is the first list item.  
- Here's the second list item.  

    I need to add another paragraph below the second list item.

- And here's the third list item.  

##### Blockquotes

```md
- This is the first list item.
- Here's the second list item.

    > A blockquote would look great below the second list item.

- And here's the third list item.
```

- This is the first list item.
- Here's the second list item.

    > A blockquote would look great below the second list item.

- And here's the third list item.

##### Code Blocks

八个空格或两个制表符

```md
1. Open the file.
2. Find the following code block on line 21:

        <html>
          <head>
            <title>Test</title>
          </head>

3. Update the title to match the name of your website.
```

1. Open the file.
2. Find the following code block on line 21:

        <html>
            <head>
            <title>Test</title>
            </head>

3. Update the title to match the name of your website.

##### Images

```md
1. Open the file containing the Linux mascot.
2. Marvel at its beauty.

    ![Tux, the Linux mascot](https://mdg.imgix.net/assets/images/tux.png?auto=format&fit=clip&q=40&w=100)

3. Close the file.
```

1. Open the file containing the Linux mascot.
2. Marvel at its beauty.

    ![Tux, the Linux mascot][linux-mascot]

3. Close the file.

##### Verse Lists

unordered lists in an ordered lists, or vice verse.

```md
1. First item
2. Second item
3. Third item
    - Indented item
    - Indented item
4. Fourth item
```

1. First item
2. Second item
3. Third item
    - Indented item
    - Indented item
4. Fourth item


### Code

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| At the command prompt, type \`nano\`. | `At the command prompt, type <code>nano</code>.` | At the command prompt, type <code>nano</code>. |

✏️ **这里有个奇怪的Bug，第三个单元格的内容如果是 `` At the command prompt, type `nano` ``，那么渲染出来的结果会与第二个单元格合在一起；但第一个单元格如果是 `` At the command prompt, type `nano` ``，渲染出来的结果是正常的。因此最后只能用 HTML 标签 `<code> ... </code>` 来解决这个问题。**

#### Escaping Backticks

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| \`\`Use \`code\` in your Markdown file.\`\` | ```<code>Use `code` in your Markdown file.</code>``` | ``Use `code` in your Markdown file.`` |

#### Code Blocks

at least four spaces of one tab.

```md
    <html>
      <head>
      </head>
    </html>
```

    <html>
      <head>
      </head>
    </html>

To create code blocks without indenting lines, use *fenced code blocks*.


### horizontal Rules

```md
***

---

_________________
```

***

---

_________________

⚠️ **不要将 `---` 放在两段落之间，否则会被识别为二级标题。**


### Links

`My favorite search engine is [Duck Duck Go](https://duckduckgo.com).`

My favorite search engine is [Duck Duck Go] [duckduckgo].

#### Adding Titles

`My favorite search engine is [Duck Duck Go](https://duckduckgo.com "The best search engine for privacy").`

My favorite search engine is [Duck Duck Go] [duckduckgo].

#### URLs and Email Addresses

```md
<https://www.markdownguide.org>
<fake@example.com>
```

<https://www.markdownguide.org>

<fake@example.com>

#### Formatting Links

```md
I love supporting the **[EFF](https://eff.org)**.
This is the *[Markdown Guide](https://www.markdownguide.org)*.
See the section on [`code`](#code).
```

I love supporting the **[EFF] [eff]**.  
This is the *[Markdown Guide] [markdown-guide]*.  
See the section on [`code`](#code).  

**If there are more than one headings are called `code`, `#code` means the first. So it's a good habit to use unique headings for each section or other content with labels.**

#### Reference-style Links

Reference-style links are constructed in two parts: the part you keep inline with your text and the part you store somewhere else in the file to keep the text easy to read.

##### Formatting the Forst Part of the Link

```md
[hobbit-hole][1]
or
[hobbit-hole] [1]
```

##### Formatting the Second Part of the Link

The following are quivalent.

```md
[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle
[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle "Hobbit lifestyles"
[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle 'Hobbit lifestyles'
[1]: https://en.wikipedia.org/wiki/Hobbit#Lifestyle (Hobbit lifestyles)
[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> "Hobbit lifestyles"
[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> 'Hobbit lifestyles'
[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> (Hobbit lifestyles)
```

##### An Example Putting the Parts Together

harder to read:

```md
In a hole in the ground there lived a hobbit. Not a nasty, dirty, wet hole, filled with the ends
of worms and an oozy smell, nor yet a dry, bare, sandy hole with nothing in it to sit down on or to
eat: it was a [hobbit-hole](https://en.wikipedia.org/wiki/Hobbit#Lifestyle "Hobbit lifestyles"), and that means comfort.
```

good one:

```md
In a hole in the ground there lived a hobbit. Not a nasty, dirty, wet hole, filled with the ends
of worms and an oozy smell, nor yet a dry, bare, sandy hole with nothing in it to sit down on or to
eat: it was a [hobbit-hole][1], and that means comfort.

[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> "Hobbit lifestyles"
```

HTML

```HTML 
<a href="https://en.wikipedia.org/wiki/Hobbit#Lifestyle" title="Hobbit lifestyles">hobbit-hole</a>
```

rendered output:  
In a hole in the ground there lived a hobbit. Not a nasty, dirty, wet hole, filled with the ends
of worms and an oozy smell, nor yet a dry, bare, sandy hole with nothing in it to sit down on or to
eat: it was a [hobbit-hole][1], and that means comfort.  

⚠️ **链接中如出现字符，请用URL编码，否则可能导致格式错误。另外，对于部分编译器允许我们重复使用同一个标签。也就是我们将标签 `1` 指向一个地址，在文本中我们可以多粗调用它而不用重新定义指向其地址的标签。**  


### Images

```md
![The San Juan Mountains are beautiful!](https://mdg.imgix.net/assets/images/san-juan-mountains.jpg?auto=format&fit=clip&q=40&w=1080 "San Juan Mountains")
```

![The San Juan Mountains are beautiful!][san-juan-mountains]

#### Linking Images

```md
[![An old rock in the desert](https://mdg.imgix.net/assets/images/shiprock.jpg?auto=format&fit=clip&q=40&w=1080 "Shiprock, New Mexico by Beau Rogers")](https://www.flickr.com/)
```

[![An old rock in the desert][san-juan-mountains]][flickr]


### Escaping Characters

```md
\* Without the backslash, this would be a bullet in an unordered list.
```

\* Without the backslash, this would be a bullet in an unordered list.

#### Characters You Can Escape

| Character | Name |
| --- | --- |
| \\ | backslash |
| \` | backtick(see also [escaping backticks in code](#escaping-backticks)) |
| \* | asterisk |
| \_ | underscore |
| \{ \} | curly braces |
| \[ \] | brackets |
| \< \> | angle brackets |
| \( \) | parentheses |
| \# | pound sign |
| \+ | plus sign |
| \- | minus sign (hyphen) |
| \. | dot |
| \! | exclamation mark |
| \| | pipe (see also [escaping pipe in tables](#escaping-pipe-characters-in-tables)) |


### HTML

Many Markdown applications allow you to use HTML tags in Markdown-formatted text. This is helpful if you prefer certain HTML tags to Markdown syntax.


### Tables

```md
| Syntax | Description |
| --- | --- |
| Header | Title |
| Paragraph | Text |
```

| Syntax | Description |
| --- | --- |
| Header | Title |
| Paragraph | Text |

Some web tools to generated Markdown tables:

- [Markdown Tables Generator][markdown-tables-generator]
- [AnyWayData Markdown Export][anywaydata-markdown-export]

#### Alinment

```md
| Syntax      | Description | Test Text     |
| :---        |    :----:   |          ---: |
| Header      | Title       | Here's this   |
| Paragraph   | Text        | And more      |
```

| Syntax      | Description | Test Text     |
| :---        |    :----:   |          ---: |
| Header      | Title       | Here's this   |
| Paragraph   | Text        | And more      |

#### Formatting Text in Tables

> You can format the text within tables. For example, you can add links, code (words or phrases in backticks (`) only, not code blocks), and emphasis.
>
> You can’t use headings, blockquotes, lists, horizontal rules, images, or most HTML tags.

#### Escaping Pipe Characters in Tables

> You can display a pipe (\|) character in a table by using its HTML character code (`&#124;`).


### Fenced Code Blocks

<p>
```<br>
{<br>
  "firstName": "John",<br>
  "lastName": "Smith",<br>
  "age": 25<br>
}<br>
```
</p>

or

<p>
~~~<br>
{<br>
  "firstName": "John",<br>
  "lastName": "Smith",<br>
  "age": 25<br>
}<br>
~~~<br>
</p>

#### Syntax Highlighting

> To add syntax highlighting, specify a language next to the backticks before the fenced code block.

<p>
```json<br>
{<br>
  "firstName": "John",<br>
  "lastName": "Smith",<br>
  "age": 25<br>
}<br>
```<br>
</p>

```json 
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```


### Footnotes

```md
Here's a simple footnote,[^1] and here's a longer one.[^bignote]

[^1]: This is the first footnote.

[^bignote]: Here's one with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.

    `{ my code }`

    Add as many paragraphs as you like.
```

Here's a simple footnote,[^1] and here's a longer one.[^bignote]


### Heading IDs  

```md
## My Great Heading {#custom-id}
```

#### Linking to Heading IDs

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| \[Heading IDs\](#heading-ids) | `<a href="#heading-ids">Heading 1</a>` | [Heading IDs](#heading-ids) |

> Other websites can link to the heading by adding the custom heading ID to the full URL of the webpage (e.g, \[Heading IDs\](https://www.markdownguide.org/extended-syntax#heading-ids)).

⚠️ **对于 VS Code 以及 Jekyll Markdown 编辑器，在渲染成 HTML 时，每个标题都有一个自动生成的 ID，如 `<h4 id="formatting-text-in-tables">Formatting Text in Tables</h4>`。**


### Definition Lists

```md
First Term
: This is the definition of the first term.

Second Term
: This is one definition of the second term.
: This is another definition of the second term.
```

First Term
: This is the definition of the first term.

Second Term
: This is one definition of the second term.
: This is another definition of the second term.


### Strikethrough

```md
~~The world is flat.~~ We now know that the world is round.
```

~~The world is flat.~~ We now know that the world is round.


### Task Lists

```md
- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media
```

- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media


### Emoji

> There are two ways to add emoji to Markdown files: copy and paste the emoji into your Markdown-formatted text, or type emoji shortcodes.

#### Copying and Pasting Emoji

- [Emojipedia][emojipedia]

#### Using Shortcodes

```md
Gone camping! :tent: Be back soon.

That is so funny! :joy:
```

✏️ **Jekyll 不支持这种格式。**


### Some Special Syntax

| Name | Markdown | HTML | Rendered Output |
| --- | --- | --- | --- |
| Highlight | I need to highlight these ==very important words==. | `I need to highlight these <mark>very important words</mark>.` | I need to highlight these <mark>very important words</mark>. |
| Subscript | H~2~O is a chemical formula. | `H<sub>2</sub>O is a chemical formula.` | H<sub>2</sub>O is a chemical formula. |
| Superscript | X^2^ is a mathematical formula. | `X<sup>2</sup> is a mathematical formula.` | X<sup>2</sup> is a mathematical formula. |
| Automatic Links| https://www.example.com | `<a href="https://www.example.com">https://www.example.com</a>` | <a href="https://www.example.com">https://www.example.com</a> |
| Disable Automatic Links | `https://www.example.com` | `<code>https://www.example.com</code>` | <code>https://www.example.com</code> |

✏️ **Jekyll 不支持上面的语法。下面的特征通过 HTML 标签实现。**

| Name | Markdown  | Rendered Output |
| --- | --- | --- |
| Underline | `Some of these words <ins>will be underlined</ins>.` | Some of these words <ins>will be underlined</ins>. |
| Indent(tab) | `&nbsp;&nbsp;&nbsp;&nbsp;This is the first sentence of my indented paragraph.` | &nbsp;&nbsp;&nbsp;&nbsp;This is the first sentence of my indented paragraph. |
| Center | `<center>This text is centered.</center>` | <center>This text is centered.</center> |
| Color | `<font color="red">This text is red!</font>` <br><br> `<p style="color:blue">Make this text blue.</p>` | <font color="red">This text is red!</font> <br><br> Tag <p> cannot insert in table cell. |


### Comments

> Some people need the ability to write sentences in their Markdown files that will not appear in the rendered output. These comments are essentially hidden text. 

```md
Here's a paragraph that will be visible.

[This is a comment that will be hidden.]: # 

And here's another paragraph that's visible.
```

Here's a paragraph that will be visible.

[This is a comment that will be hidden. Not work in VSCode]: #

And here's another paragraph that's visible.

✏️ **就像你看到的那样，Jekyll 不支持这种语法。**

Available way:

```md
<!--- This is a comment that will be hidden.--->
```

<!--- This is a comment that will be hidden.--->


### Admonitions

```md
> :warning: **Warning:** Do not push the big red button.

> :memo: **Note:** Sunrises are beautiful.

> :bulb: **Tip:** Remember to appreciate the little things in life.
```

or:

```md
!!! warning "Warning"
    Do not push the big red button.

!!! note "Note"
    Sunrises are beautiful.

!!! tip "Tip"
    Remember to appreciate the little things in life.
```

✏️ **很好，Jekyll 也不支持这个；不过主要原因可能是因为我的主题并没有配置这个。在 VS Code 中，效果图如下：**

![Admonition_emoji][admonition_emoji]
![Admonition_css][admonition_css]


### Image Size

```md
<img src="image.png" width="200" height="100">
```


### Image Caption

```md
<figure>
    <img src="/assets/images/albuquerque.jpg"
         alt="Albuquerque, New Mexico">
    <figcaption>A single track trail outside of Albuquerque, New Mexico.</figcaption>
</figure>
```


### Link Targets

```md
<a href="https://www.markdownguide.org" target="_blank">Learn Markdown!</a>
```

<a href="https://www.markdownguide.org" target="_blank">Learn Markdown!</a>


### Symbols

```md
- Copyright (©) — &copy;
- Registered trademark (®) — &reg;
- Trademark (™) — &trade;
- Euro (€) — &euro;
- Left arrow (←) — &larr;
- Up arrow (↑) — &uarr;
- Right arrow (→) — &rarr;
- Down arrow (↓) — &darr;
- Degree (°) — &#176;
- Pi (π) — &#960;
```

> For a complete list of available HTML entities, refer to Wikipedia’s page on [HTML entities](https://en.wikipedia.org/wiki/List_of_XML_and_HTML_character_entity_references).


### Table Formatting

#### Line Breaks Within Table Cells

```md
| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title |
| Paragraph   | First paragraph. <br><br> Second paragraph. |
```

| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title |
| Paragraph   | First paragraph. <br><br> Second paragraph. |

#### Lists Within Table Cells

```md
| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title |
| List        | Here's a list! <ul><li>Item one.</li><li>Item two.</li></ul> |
```

✏️ **Jekyll 不支持这种格式。**

### Table of Contents

```md
#### Table of Contents

- [Underline](#underline)
- [Indent](#indent)
- [Center](#center)
- [Color](#color)
```

- [Underline](#underline)
- [Indent](#indent)
- [Center](#center)
- [Color](#color)

✏️ **一般不用这种方法，通常会使用插件或者 也可以通过 `[TOC]` 来生成目录。**


### Video

```md
[![Less Than Jake — Scott Farcas Takes It On The Chin](https://img.youtube.com/vi/PYCxct2e0zI/0.jpg)](https://www.youtube.com/watch?v=PYCxct2e0zI)
```

[![Less Than Jake — Scott Farcas Takes It On The Chin][less-than-jake]][youtube-less-than-jake]


[github]: https://github.com/jdw-heaven  "My GitHub Homepage"
[markdown-preview-enhanced]: https://shd101wyy.github.io/markdown-preview-enhanced/#/zh-cn/  "Markdown Preview Enhanced"  
[css-theme]: https://learnku.com/users/57474  "CSS Theme"  
[markdown-writing]: https://wu-kan.cn/2020/01/18/Markdown%E5%86%99%E4%BD%9C%E5%BF%83%E5%BE%97/  "Markdown 写作心得"  
[chinese-copywriting-guidelines]: https://github.com/sparanoid/chinese-copywriting-guidelines/tree/master   "中文文案排版指北"  
[image-compress]: https://squoosh.app/  "图片压缩工具"  
[base64-encoder]: https://base64.us/  "Base64 编码工具"  
[linux-mascot]: https://mdg.imgix.net/assets/images/tux.png?auto=format&fit=clip&q=40&w=100  "Tux, the Linux mascot"  
[duckduckgo]: https://duckduckgo.com "The best search engine for privacy"  
[eff]: https://eff.org  "Electronic Frontier Foundation"  
[markdown-guide]: https://www.markdownguide.org  "Markdown Guide"  
[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> "Hobbit lifestyles"  
[san-juan-mountains]: https://mdg.imgix.net/assets/images/san-juan-mountains.jpg?auto=format&fit=clip&q=40&w=1080 "San Juan Mountains"  
[flickr]: https://www.flickr.com/  "Flickr"  
[markdown-tables-generator]: https://www.tablesgenerator.com/markdown_tables  "Markdown Tables Generator"  
[anywaydata-markdown-export]: https://anywaydata.com/  "AnywayData Markdown Export"  
[emojipedia]: https://emojipedia.org/  "Emojipedia"  
[admonition_emoji]: https://cdn.jsdelivr.net/gh/jdw-heaven/images01@main/Admonitions_emoji.png  "Admonition_emoji"  
[admonition_css]: https://cdn.jsdelivr.net/gh/jdw-heaven/images01@main/Admonition_css.png  "Admonition_css"  
[less-than-jake]: https://lh3.googleusercontent.com/Bi3G-B-E-xb3Axoi2ph_txwc8qAiOk_hlkMMMGXMCCPh22zfGWuX4x6fOj1CtMacaeyx7jch-mUlAGM  "Less Than Jake — Scott Farcas Takes It On The Chin"  
[youtube-less-than-jake]: https://www.youtube.com/watch?v=PYCxct2e0zI  "Less Than Jake — Scott Farcas Takes It On The Chin"  



[^1]: This is the first footnote.

[^bignote]: Here's one with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.

    `{ my code }`

    Add as many paragraphs as you like.