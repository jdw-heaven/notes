# Markdown Tips

## VSCode Plugins

### Markdown Preview Enhanced

一个非常好的插件，支持预览以及导出各种格式，如pdf、png、html等；同时自带多种主题，也可以通过CSS自定义样式。详细功能请参照[官方文档](https://shd101wyy.github.io/markdown-preview-enhanced/#/zh-cn/)。

文章最后给出我用的[CSS样式](#css_code)，直接放在`style.less`文件中即可。

### markdownlint

一个语法检查插件，可以帮助你检查语法是否正确，并给出提示。

可以在`settings.json`文件中自定义相关规则：

```json
{
    "markdownlint.config": {
        "MD010": {
            // 不能用tab缩进，代码块除外
            "code_blocks": false
        },
        "MD024": {
            // 文档不能有重复的标题，不同标题的子标题可以
            "siblings_only": true
        },
        "MD033": false
    }
}
```

### Prettier

可以通过`Alt+Shift+F`快速格式化Markdown文件。

## 排版指导

- 中文文案排版指北[<i class="fa-solid fa-link fa-2xs" style="color: #0091ff;"></i>](https://github.com/sparanoid/chinese-copywriting-guidelines/tree/master)

- Markdown 写作心得[<i class="fa-solid fa-link fa-2xs" style="color: #0091ff;"></i>](https://wu-kan.cn/2020/01/18/Markdown%E5%86%99%E4%BD%9C%E5%BF%83%E5%BE%97/)

## 图片插入

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

## Cheat Sheet

以下内容精简于[Markdown Guide](https://www.markdownguide.org/)

### Headings

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| # Heading level 1 | `<h1>Heading level 1</h1>` | <h1>Heading level 1</h1> |
| # Heading level 2 | `<h2>Heading level 2</h2>` | <h2>Heading level 2</h2> |
| # Heading level 3 | `<h3>Heading level 3</h3>` | <h3>Heading level 3</h3> |
| # Heading level 4 | `<h4>Heading level 4</h4>` | <h4>Heading level 4</h4> |
| # Heading level 5 | `<h5>Heading level 5</h5>` | <h5>Heading level 5</h5> |
| # Heading level 6 | `<h6>Heading level 6</h6>` | <h6>Heading level 6</h6> |

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| Heading level 1<br>=== | `<h1>Heading level 1</h1>` | <h1>Heading level 1</h1> |
| Heading level 2<br>--- | `<h2>Heading level 2</h2>` | <h2>Heading level 2</h2> |

<i class="fa-solid fa-xmark fa-lg" style="color: #ff0000;"></i>

\#Here's a Heading

Without blank lines, this might not look right.
\# Heading
Don't do this!

### Paragraphs

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| I really like using Markdown. <br><br> I think I'll use it to format all of my documents from now on. | `<p>I really like using Markdown.</p>`<br><br>`<p>I think I'll use it to format all of my documents from now on.</p>` | <p>I really like using Markdown.</p><p>I think I'll use it to format all of my documents from now on.</p> |

<i class="fa-solid fa-xmark fa-lg" style="color: #ff0000;"></i>

&nbsp;&nbsp;&nbsp;&nbsp;This can result in unexpected formatting problems.

&nbsp;&nbsp;Don't add tabs or spaces in front of paragraphs.

### Line Breaks

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| This is the first line.**(there's two or more spaces, you can also use <br>)**<br>And this is the second line. | `<p>This is the first line.<br>And this is the second line.</p>` | <p>This is the first line.<br>And this is the second line.</p> |

<i class="fa-solid fa-xmark fa-lg" style="color: #ff0000;"></i>

First line with a backslash after.\
And the next line.

First line with nothing after.
And the next line.

**In vscode, line break maybe 'enter' and <br> is used to seperate paragraphs.**

### Emphasis

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| I just love \*\*blod text\*\*. | `I just love <strong>blod text</strong>` | I just love <strong>blod text</strong> |
| I just love \_\_blod text\_\_. | `I just love <strong>blod text</strong>` | I just love <strong>blod text</strong> |
| Love\*\*is\*\*bold | `Love<strong>is</strong>` | Love<strong>is</strong> |

<i class="fa-solid fa-xmark fa-lg" style="color: #ff0000;"></i> Love__is__blod

### Italic

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| Italicized text is the \*cat's meow\*. | `Italicized text is the <em>cat's meow</em>.` | Italicized text is the <em>cat's meow</em>. |
| Italicized text is the \_cat's meow\_. | `Italicized text is the <em>cat's meow</em>.` | Italicized text is the <em>cat's meow</em>. |
| A\*cat\*meow | `A<em>cat</em>` | A<em>cat</em> |

<i class="fa-solid fa-xmark fa-lg" style="color: #ff0000;"></i>
A_cat_meow

### Bold and Italic

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| This text is \*\*\*really important\*\*\*. | `This text is <em><strong>really important</strong></em>.` | This text is <em><strong>really important</strong></em>. |
| This text is \_\_\_really important\_\_\_. | `This text is <em><strong>really important</strong></em>.` | This text is <em><strong>really important</strong></em>. |
| This text is \_\_\*really important\*\_\_. | `This text is <em><strong>really important</strong></em>.` | This text is <em><strong>really important</strong></em>. |
| This text is \*\*\_really important\_\*\*. | `This text is <em><strong>really important</strong></em>.` | This text is <em><strong>really important</strong></em>. |
| This is really\*\*\*very\*\*\*important text. | `This is really<em><strong>very</strong></em>important text.` | This is really<em><strong>very</strong></em>important text. |

<i class="fa-solid fa-xmark fa-lg" style="color: #ff0000;"></i>
This is
really___very___important
text.

### Blockquotes

`> Dorothy followed her through many of the beautiful rooms in her castle.`

> Dorothy followed her through many of the beautiful rooms in her castle.

#### Blockquotes with Multiple Paragraphs

```MD {.line-numbers}
> Dorothy followed her through many of the beautiful rooms in her castle.
>
> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.
```

> Dorothy followed her through many of the beautiful rooms in her castle.
>
> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.

#### Nested Blockquotes

```MD {.line-numbers}
> Dorothy followed her through many of the beautiful rooms in her castle.
>
>> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.
```

> Dorothy followed her through many of the beautiful rooms in her castle.
>
>> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.

#### Blockquotes with Other Elements

```MD {.line-numbers}
> #### The quarterly results look great!
>
> - Revenue was off the chart.
> - Profits were higher than ever.
>
>  *Everything* is going according to **plan**.
```

> #### The quarterly results look great
>
> - Revenue was off the chart.
> - Profits were higher than ever.
>
> *Everything* is going according to **plan**.

<i class="fa-solid fa-xmark fa-lg" style="color: #ff0000;"></i>

Without blank lines, this might not look right.
\> This is a blockquote
Don't do this!

### Lists

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| 1. First item <br> 2. Second item <br> 3. Third item <br> 4. Fourth item | `<ol>` <br> &nbsp;&nbsp;`<li>First item</li>` <br> &nbsp;&nbsp;`<li>Second item</li>` <br> &nbsp;&nbsp;`<li>Third item</li>` <br> &nbsp;&nbsp;`<li>Fourth item</li>` <br> `</ol>` | <ol><li>First item</li><li>Second item</li><li>Third item</li><li>Fourth item</li></ol> |
| 1. First item <br> 1. Second item <br> 1. Third item <br> 1. Fourth item | `<ol>` <br> &nbsp;&nbsp;`<li>First item</li>` <br> &nbsp;&nbsp;`<li>Second item</li>` <br> &nbsp;&nbsp;`<li>Third item</li>` <br> &nbsp;&nbsp;`<li>Fourth item</li>` <br> `</ol>` | <ol><li>First item</li><li>Second item</li><li>Third item</li><li>Fourth item</li></ol> |
| 1. First item <br> 8. Second item <br> 3. Third item <br> 5. Fourth item | `<ol>` <br> &nbsp;&nbsp;`<li>First item</li>` <br> &nbsp;&nbsp;`<li>Second item</li>` <br> &nbsp;&nbsp;`<li>Third item</li>` <br> &nbsp;&nbsp;`<li>Fourth item</li>` <br> `</ol>` | <ol><li>First item</li><li>Second item</li><li>Third item</li><li>Fourth item</li></ol> |
| 1. First item <br> 2. Second item <br> 3. Third item <br> &nbsp;&nbsp;1. Indented item <br> &nbsp;&nbsp;2. Indented item <br> 4. Fourth item | `<ol>` <br> &nbsp;&nbsp;`<li>First item</li>` <br> &nbsp;&nbsp;`<li>Second item</li>` <br> &nbsp;&nbsp;`<li>Third item` <br> &nbsp;&nbsp;&nbsp;&nbsp;`<ol>` <br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`<li>Indented item</li>` <br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`<li>Indented item</li>` <br> &nbsp;&nbsp;&nbsp;&nbsp;`</ol>` <br> &nbsp;&nbsp;`</li>` <br> &nbsp;&nbsp;`<li>Fourth item</li>` <br> `</ol>` | <ol><li>First item</li><li>Second item</li><li>Third item</li><ol><li>Indented item</li><li>Indented item</li></ol><li>Fourth item</li></ol> |

<i class="fa-solid fa-xmark fa-lg" style="color: #ff0000;"></i>

1) First item
2) Second item

**In vscode the sntax is valid.**

#### Unordered Lists

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| -. First item <br> -. Second item <br> -. Third item <br> -. Fourth item | `<ul>` <br> &nbsp;&nbsp;`<li>First item</li>` <br> &nbsp;&nbsp;`<li>Second item</li>` <br> &nbsp;&nbsp;`<li>Third item</li>` <br> &nbsp;&nbsp;`<li>Fourth item</li>` <br> `</ul>` | <ul><li>First item</li><li>Second item</li><li>Third item</li><li>Fourth item</li></ul> |
| \*. First item <br> \*. Second item <br> \*. Third item <br> \*. Fourth item | `<ul>` <br> &nbsp;&nbsp;`<li>First item</li>` <br> &nbsp;&nbsp;`<li>Second item</li>` <br> &nbsp;&nbsp;`<li>Third item</li>` <br> &nbsp;&nbsp;`<li>Fourth item</li>` <br> `</ul>` | <ul><li>First item</li><li>Second item</li><li>Third item</li><li>Fourth item</li></ul> |
| +. First item <br> +. Second item <br> +. Third item <br> +. Fourth item | `<ul>` <br> &nbsp;&nbsp;`<li>First item</li>` <br> &nbsp;&nbsp;`<li>Second item</li>` <br> &nbsp;&nbsp;`<li>Third item</li>` <br> &nbsp;&nbsp;`<li>Fourth item</li>` <br> `</ul>` | <ul><li>First item</li><li>Second item</li><li>Third item</li><li>Fourth item</li></ul> |
| -. First item <br> -. Second item <br> -. Third item <br> &nbsp;&nbsp;-. Indented item <br> &nbsp;&nbsp;-. Indented item <br> -. Fourth item | `<ul>` <br> &nbsp;&nbsp;`<li>First item</li>` <br> &nbsp;&nbsp;`<li>Second item</li>` <br> &nbsp;&nbsp;`<li>Third item` <br> &nbsp;&nbsp;&nbsp;&nbsp;`<ul>` <br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`<li>Indented item</li>` <br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`<li>Indented item</li>` <br> &nbsp;&nbsp;&nbsp;&nbsp;`</ul>` <br> &nbsp;&nbsp;`</li>` <br> &nbsp;&nbsp;`<li>Fourth item</li>` <br> `</ul>` | <ul><li>First item</li><li>Second item</li><li>Third item</li><ul><li>Indented item</li><li>Indented item</li></ul><li>Fourth item</li></ul> |

##### Starting Unordered List Items With Numbers

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| - 1968\\. A great year! <br> - I think 1969 was second best. | `<ul>` <br> &nbsp;&nbsp;`<li>1968. A great year!</li>` <nr> &nbsp;&nbsp;`<li>I think 1969 was second best.</li>` <br> `</ul>` | <ul><li>1968. A great year!</li><li>I think 1969 was second best.</li></ul> |

<i class="fa-solid fa-xmark fa-lg" style="color: #ff0000;"></i>

\+ First item
\* Secoind item
\- Third item
\+ Fourth item

**Available in vscode, not suggested.**

#### Adding Element in Lists

##### Paragraphs

```MD {.line-numbers}
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

```MD {.line-numbers}
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

eight 'spaces' or two 'tab'.

```MD {.line-numbers}
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

```MD {.line-numbers}
1. Open the file containing the Linux mascot.
2. Marvel at its beauty.

    ![Tux, the Linux mascot](https://mdg.imgix.net/assets/images/tux.png?auto=format&fit=clip&q=40&w=100)

3. Close the file.
```

1. Open the file containing the Linux mascot.
2. Marvel at its beauty.

    ![Tux, the Linux mascot](https://mdg.imgix.net/assets/images/tux.png?auto=format&fit=clip&q=40&w=100)

3. Close the file.

##### Verse Lists

unordered lists in an ordered lists, or vice verse.

```MD {.line-numbers}
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

#### Escaping Backticks {#escaping-backticks}

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| \`\`Use \`code\` in your Markdown file.\`\` | ```<code>Use `code` in your Markdown file.</code>``` | <code>Use `code` in your Markdown file.</code> |

#### Code Blocks

at least four spaces of one tab.

```MD {.line-numbers}
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

```MD {.line-numbers}
***

---

_________________
```

***

---

_________________

<i class="fa-solid fa-xmark fa-lg" style="color: #ff0000;"></i>

Without blank lines, this would be a heading.
\-\-\-
Don't do this!

### Links

`My favorite search engine is [Duck Duck Go](https://duckduckgo.com).`

My favorite search engine is [Duck Duck Go](https://duckduckgo.com).

#### Adding Titles

`My favorite search engine is [Duck Duck Go](https://duckduckgo.com "The best search engine for privacy").`

My favorite search engine is [Duck Duck Go](https://duckduckgo.com "The best search engine for privacy").

#### URLs and Email Addresses

```MD {.line-numbers}
<https://www.markdownguide.org>
<fake@example.com>
```

<https://www.markdownguide.org>
<fake@example.com>

#### Formatting Links

```MD {.line-numbers}
I love supporting the **[EFF](https://eff.org)**.
This is the *[Markdown Guide](https://www.markdownguide.org)*.
See the section on [`code`](#code).
```

I love supporting the **[EFF](https://eff.org)**.
This is the *[Markdown Guide](https://www.markdownguide.org)*.
See the section on [`code`](#code).

**If there are more than one headings are called "code", "#code" means the first.**

#### Reference-style Links

Reference-style links are constructed in two parts: the part you keep inline with your text and the part you store somewhere else in the file to keep the text easy to read.

##### Formatting the Forst Part of the Link

```MD {.line-numbers}
[hobbit-hole][1]
or
[hobbit-hole] [1]
```

##### Formatting the Second Part of the Link

The following are quivalent.

```MD {.line-numbers}
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

```MD {.line-numbers}
In a hole in the ground there lived a hobbit. Not a nasty, dirty, wet hole, filled with the ends
of worms and an oozy smell, nor yet a dry, bare, sandy hole with nothing in it to sit down on or to
eat: it was a [hobbit-hole](https://en.wikipedia.org/wiki/Hobbit#Lifestyle "Hobbit lifestyles"), and that means comfort.
```

good one:

```MD {.line-numbers}
In a hole in the ground there lived a hobbit. Not a nasty, dirty, wet hole, filled with the ends
of worms and an oozy smell, nor yet a dry, bare, sandy hole with nothing in it to sit down on or to
eat: it was a [hobbit-hole][1], and that means comfort.

[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> "Hobbit lifestyles"
```

HTML

```HTML {.line-numbers}
<a href="https://en.wikipedia.org/wiki/Hobbit#Lifestyle" title="Hobbit lifestyles">hobbit-hole</a>
```

rendered output:
In a hole in the ground there lived a hobbit. Not a nasty, dirty, wet hole, filled with the ends
of worms and an oozy smell, nor yet a dry, bare, sandy hole with nothing in it to sit down on or to
eat: it was a [hobbit-hole][1], and that means comfort.

[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> "Hobbit lifestyles"

| <i class="fa-solid fa-check fa-lg" style="color: #2bff00;"></i> Do this | <i class="fa-solid fa-xmark fa-lg" style="color: #ff0000;"></i> Don't do this |
| --- | --- |
| `[link](https://www.example.com/my%20great%20page)` <br><br> `<a href="https://www.example.com/my great page">link</a>` | `[link](https://www.example.com/my great page)` |
| `[a novel](https://en.wikipedia.org/wiki/The_Milagro_Beanfield_War_%28novel%29)` <br><br> `<a href="https://en.wikipedia.org/wiki/The_Milagro_Beanfield_War_(novel)">a novel</a>` | `[a novel](https://en.wikipedia.org/wiki/The_Milagro_Beanfield_War_(novel))` |

### Images

```MD {.line-numbers}
![The San Juan Mountains are beautiful!](https://mdg.imgix.net/assets/images/san-juan-mountains.jpg?auto=format&fit=clip&q=40&w=1080 "San Juan Mountains")
```

![The San Juan Mountains are beautiful!](https://mdg.imgix.net/assets/images/san-juan-mountains.jpg?auto=format&fit=clip&q=40&w=1080 "San Juan Mountains")

#### Linking Images

```MD {.line-numbers}
[![An old rock in the desert](https://mdg.imgix.net/assets/images/shiprock.jpg?auto=format&fit=clip&q=40&w=1080 "Shiprock, New Mexico by Beau Rogers")](https://www.flickr.com/)
```

[![An old rock in the desert](https://mdg.imgix.net/assets/images/shiprock.jpg?auto=format&fit=clip&q=40&w=1080 "Shiprock, New Mexico by Beau Rogers")](https://www.flickr.com/)

### Escaping Characters

```MD {.line-numbers}
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

```md {.line-numbers}
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

- [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables)
- [AnyWayData Markdown Export](https://anywaydata.com/)

#### Alinment

```md {.line-numbers}
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

#### Escaping Pipe Characters in Tables {#escaping-pipe-characters-in-tables}

> You can display a pipe (|) character in a table by using its HTML character code (&#124;).

### Fenced Code Blocks

<p style="text-indent:0em;">
```<br>
{<br>
  "firstName": "John",<br>
  "lastName": "Smith",<br>
  "age": 25<br>
}<br>
```
</p>

or

<p style="text-indent:0em;">
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

<p style="text-indent:0em;">
```json<br>
{<br>
  "firstName": "John",<br>
  "lastName": "Smith",<br>
  "age": 25<br>
}<br>
```<br>
</p>

```json {.line-numbers}
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

### Footnotes

```md {.line-numbers}
Here's a simple footnote,[^1] and here's a longer one.[^bignote]

[^1]: This is the first footnote.

[^bignote]: Here's one with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.

    `{ my code }`

    Add as many paragraphs as you like.
```

Here's a simple footnote,[^1] and here's a longer one.[^bignote]

[^1]: This is the first footnote.

[^bignote]: Here's one with multiple paragraphs and code.

    Indent paragraphs to include them in the footnote.

    `{ my code }`

    Add as many paragraphs as you like.

### Heading IDs {#heading-ids}

```md {.line-numbers}
## My Great Heading {#custom-id}
```

#### Linking to Heading IDs

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| \[Heading IDs\](#heading-ids) | `<a href="#heading-1">Heading 1</a>` | [Heading IDs](#heading-ids) |

> Other websites can link to the heading by adding the custom heading ID to the full URL of the webpage (e.g, \[Heading IDs\](https://www.markdownguide.org/extended-syntax#heading-ids)).

### Definition Lists

```md {.line-numbers}
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

```md {.line-numbers}
~~The world is flat.~~ We now know that the world is round.
```

~~The world is flat.~~ We now know that the world is round.

### Task Lists

```md {.line-numbers}
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

- [Emojipedia](https://emojipedia.org/)

#### Using Shortcodes

```md {.line-numbers}
Gone camping! :tent: Be back soon.

That is so funny! :joy:
```

Gone camping! :tent: Be back soon.

That is so funny! :joy:

### Highlight

```md {.line-numbers}
I need to highlight these ==very important words==.
```

I need to highlight these ==very important words==.

### Subscript

```md {.line-numbers}
H~2~O is a chemical formula.
```

H~2~O is a chemical formula.

### Superscript

```md {.line-numbers}
X^2^ is the formula for the square of X.
```

X^2^ is the formula for the square of X.

### Automatic URL Linking

```md {.line-numbers}
https://www.example.com
```

https://www.example.com

#### Disabling Automatic URL Linking

```md {.line-numbers}
`https://www.example.com`
```

`https://www.example.com`

### Underline {#underline}

```md {.line-numbers}
Some of these words <ins>will be underlined</ins>.
```

Some of these words <ins>will be underlined</ins>.

### Indent(Tab) {#indent}

```md {.line-numbers}
&nbsp;&nbsp;&nbsp;&nbsp;This is the first sentence of my indented paragraph.
```

### Center {#center}

```md {.line-numbers}
<center>This text is centered.</center>
```

<center>This text is centered.</center>

### Color {#color}

```md {.line-numbers}
<font color="red">This text is red!</font>

or

<p style="color:blue">Make this text blue.</p>
```

<font color="red">This text is red!</font>

<p style="color:blue">Make this text blue.</p>

### Comments

> Some people need the ability to write sentences in their Markdown files that will not appear in the rendered output. These comments are essentially hidden text. 

```md {.line-numbers}
Here's a paragraph that will be visible.

[This is a comment that will be hidden.]: # 

And here's another paragraph that's visible.
```

Here's a paragraph that will be visible.

[This is a comment that will be hidden. Not work in VSCode]: #

And here's another paragraph that's visible.

Available way:

```md {.line-numbers}
<!--- This is a comment that will be hidden.--->
```

<!--- This is a comment that will be hidden.--->

### Admonitions

```md {.line-numbers}
> :warning: **Warning:** Do not push the big red button.

> :memo: **Note:** Sunrises are beautiful.

> :bulb: **Tip:** Remember to appreciate the little things in life.
```

> :warning: **Warning:** Do not push the big red button.
>
> :memo: **Note:** Sunrises are beautiful.
>
> :bulb: **Tip:** Remember to appreciate the little things in life.

or:

```md {.line-numbers}
!!! warning "Warning"
    Do not push the big red button.

!!! note "Note"
    Sunrises are beautiful.

!!! tip "Tip"
    Remember to appreciate the little things in life.
```

!!! warning "Warning"
    Do not push the big red button.

!!! note "Note"
    Sunrises are beautiful.

!!! tip "Tip"
    Remember to appreciate the little things in life.

### Image Size

```md {.line-numbers}
<img src="image.png" width="200" height="100">
```

### Image Caption

```md {.line-numbers}
<figure>
    <img src="/assets/images/albuquerque.jpg"
         alt="Albuquerque, New Mexico">
    <figcaption>A single track trail outside of Albuquerque, New Mexico.</figcaption>
</figure>
```

### Link Targets

```md {.line-numbers}
<a href="https://www.markdownguide.org" target="_blank">Learn Markdown!</a>
```

<a href="https://www.markdownguide.org" target="_blank">Learn Markdown!</a>

### Symbols

```md {.line-numbers}
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

```md {.line-numbers}
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

```md {.line-numbers}
| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title |
| List        | Here's a list! <ul><li>Item one.</li><li>Item two.</li></ul> |
```

| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title |
| List        | Here's a list! <ul><li>Item one.</li><li>Item two.</li></ul> |

### Table of Contents

```md {.line-numbers}
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

### Video

```md {.line-numbers}
[![Less Than Jake — Scott Farcas Takes It On The Chin](https://img.youtube.com/vi/PYCxct2e0zI/0.jpg)](https://www.youtube.com/watch?v=PYCxct2e0zI)
```

[![Less Than Jake — Scott Farcas Takes It On The Chin](https://img.youtube.com/vi/PYCxct2e0zI/0.jpg)](https://www.youtube.com/watch?v=PYCxct2e0zI)


## Appendix

### css_code {# css_code}

```css {.line-numbers}
    body {
        font-family: "Microsoft Yahei", Helvetica, arial, sans-serif ;
        font-size: 14px;
        line-height: 1.6;
        padding-top: 10px;
        padding-bottom: 10px;
        background-color: white;
        padding: 30px;
        color: #516272;}
    
    body > *:first-child {
        margin-top: 0 !important; }
    body > *:last-child {
        margin-bottom: 0 !important; }
    
    p {
        text-indent: 2em; }

    a {
        color: #4183C4; }
    a.absent {
        color: #cc0000; }
    a.anchor {
        display: block;
        padding-left: 30px;
        margin-left: -30px;
        cursor: pointer;
        position: absolute;
        top: 0;
        left: 0;
        bottom: 0; }
    
    h1, h2, h3, h4, h5, h6 {
        margin: 20px 0 10px;
        padding: 0;
        font-weight: bold;
        -webkit-font-smoothing: antialiased;
        cursor: text;
        position: relative; }
    
    h1:hover a.anchor, h2:hover a.anchor, h3:hover a.anchor, h4:hover a.anchor, h5:hover a.anchor, h6:hover a.anchor {
        background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAYAAAAf8/9hAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAA09pVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADw/eHBhY2tldCBiZWdpbj0i77u/IiBpZD0iVzVNME1wQ2VoaUh6cmVTek5UY3prYzlkIj8+IDx4OnhtcG1ldGEgeG1sbnM6eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IkFkb2JlIFhNUCBDb3JlIDUuMy1jMDExIDY2LjE0NTY2MSwgMjAxMi8wMi8wNi0xNDo1NjoyNyAgICAgICAgIj4gPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4gPHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9IiIgeG1sbnM6eG1wPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvIiB4bWxuczp4bXBNTT0iaHR0cDovL25zLmFkb2JlLmNvbS94YXAvMS4wL21tLyIgeG1sbnM6c3RSZWY9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC9zVHlwZS9SZXNvdXJjZVJlZiMiIHhtcDpDcmVhdG9yVG9vbD0iQWRvYmUgUGhvdG9zaG9wIENTNiAoMTMuMCAyMDEyMDMwNS5tLjQxNSAyMDEyLzAzLzA1OjIxOjAwOjAwKSAgKE1hY2ludG9zaCkiIHhtcE1NOkluc3RhbmNlSUQ9InhtcC5paWQ6OUM2NjlDQjI4ODBGMTFFMTg1ODlEODNERDJBRjUwQTQiIHhtcE1NOkRvY3VtZW50SUQ9InhtcC5kaWQ6OUM2NjlDQjM4ODBGMTFFMTg1ODlEODNERDJBRjUwQTQiPiA8eG1wTU06RGVyaXZlZEZyb20gc3RSZWY6aW5zdGFuY2VJRD0ieG1wLmlpZDo5QzY2OUNCMDg4MEYxMUUxODU4OUQ4M0REMkFGNTBBNCIgc3RSZWY6ZG9jdW1lbnRJRD0ieG1wLmRpZDo5QzY2OUNCMTg4MEYxMUUxODU4OUQ4M0REMkFGNTBBNCIvPiA8L3JkZjpEZXNjcmlwdGlvbj4gPC9yZGY6UkRGPiA8L3g6eG1wbWV0YT4gPD94cGFja2V0IGVuZD0iciI/PsQhXeAAAABfSURBVHjaYvz//z8DJYCRUgMYQAbAMBQIAvEqkBQWXI6sHqwHiwG70TTBxGaiWwjCTGgOUgJiF1J8wMRAIUA34B4Q76HUBelAfJYSA0CuMIEaRP8wGIkGMA54bgQIMACAmkXJi0hKJQAAAABJRU5ErkJggg==) no-repeat 10px center;
        text-decoration: none; }
    
    h1 tt, h1 code {
        font-size: inherit; }
    
    h2 tt, h2 code {
        font-size: inherit; }
    
    h3 tt, h3 code {
        font-size: inherit; }
    
    h4 tt, h4 code {
        font-size: inherit; }
    
    h5 tt, h5 code {
        font-size: inherit; }
    
    h6 tt, h6 code {
        font-size: inherit; }
    
    h1 {
        font-size: 28px;
        color: #2B3F52; }
    
    h2 {
        font-size: 24px;
        border-bottom: 1px solid #DDE4E9;
        color: #2B3F52; }
    
    h3 {
        font-size: 18px;
        color: #2B3F52;  }
    
    h4 {
        font-size: 16px;
        color: #2B3F52;  }
    
    h5 {
        font-size: 14px;
        color: #2B3F52;  }
    
    h6 {
        color: #2B3F52;
        font-size: 14px;
    }
    strong {
        color: #2B3F52;
    }
    
    p, blockquote, ul, ol, dl, li, table, pre {
        margin: 15px 0;
        color: #516272;  }
    
    hr {
        background: transparent url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAYAAAAECAYAAACtBE5DAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAyJpVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADw/eHBhY2tldCBiZWdpbj0i77u/IiBpZD0iVzVNME1wQ2VoaUh6cmVTek5UY3prYzlkIj8+IDx4OnhtcG1ldGEgeG1sbnM6eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IkFkb2JlIFhNUCBDb3JlIDUuMC1jMDYwIDYxLjEzNDc3NywgMjAxMC8wMi8xMi0xNzozMjowMCAgICAgICAgIj4gPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4gPHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9IiIgeG1sbnM6eG1wPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvIiB4bWxuczp4bXBNTT0iaHR0cDovL25zLmFkb2JlLmNvbS94YXAvMS4wL21tLyIgeG1sbnM6c3RSZWY9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC9zVHlwZS9SZXNvdXJjZVJlZiMiIHhtcDpDcmVhdG9yVG9vbD0iQWRvYmUgUGhvdG9zaG9wIENTNSBNYWNpbnRvc2giIHhtcE1NOkluc3RhbmNlSUQ9InhtcC5paWQ6OENDRjNBN0E2NTZBMTFFMEI3QjRBODM4NzJDMjlGNDgiIHhtcE1NOkRvY3VtZW50SUQ9InhtcC5kaWQ6OENDRjNBN0I2NTZBMTFFMEI3QjRBODM4NzJDMjlGNDgiPiA8eG1wTU06RGVyaXZlZEZyb20gc3RSZWY6aW5zdGFuY2VJRD0ieG1wLmlpZDo4Q0NGM0E3ODY1NkExMUUwQjdCNEE4Mzg3MkMyOUY0OCIgc3RSZWY6ZG9jdW1lbnRJRD0ieG1wLmRpZDo4Q0NGM0E3OTY1NkExMUUwQjdCNEE4Mzg3MkMyOUY0OCIvPiA8L3JkZjpEZXNjcmlwdGlvbj4gPC9yZGY6UkRGPiA8L3g6eG1wbWV0YT4gPD94cGFja2V0IGVuZD0iciI/PqqezsUAAAAfSURBVHjaYmRABcYwBiM2QSA4y4hNEKYDQxAEAAIMAHNGAzhkPOlYAAAAAElFTkSuQmCC) repeat-x 0 0;
        border: 0 none;
        color: #cccccc;
        height: 4px;
        padding: 0;
    
    }
    
    body > h2:first-child {
        margin-top: 0;
        padding-top: 0; }
    body > h1:first-child {
        margin-top: 0;
        padding-top: 0; }
    body > h1:first-child + h2 {
        margin-top: 0;
        padding-top: 0; }
    body > h3:first-child, body > h4:first-child, body > h5:first-child, body > h6:first-child {
        margin-top: 0;
        padding-top: 0; }
    
    a:first-child h1, a:first-child h2, a:first-child h3, a:first-child h4, a:first-child h5, a:first-child h6 {
        margin-top: 0;
        padding-top: 0; }
    
    h1 p, h2 p, h3 p, h4 p, h5 p, h6 p {
        margin-top: 0; }
    
    li p.first {
        display: inline-block; }
    li {
        margin: 0; }
    ul, ol {
        padding-left: 30px; }
    
    ul :first-child, ol :first-child {
        margin-top: 0; }
    
    dl {
        padding: 0; }
    dl dt {
        font-size: 14px;
        font-weight: bold;
        font-style: italic;
        padding: 0;
        margin: 15px 0 5px; }
    dl dt:first-child {
        padding: 0; }
    dl dt > :first-child {
        margin-top: 0; }
    dl dt > :last-child {
        margin-bottom: 0; }
    dl dd {
        margin: 0 0 15px;
        padding: 0 15px; }
    dl dd > :first-child {
        margin-top: 0; }
    dl dd > :last-child {
        margin-bottom: 0; }
    
    blockquote {
        border-left: 4px solid #ECF0F3;
        /*padding: 0 15px;*/
        padding: 15px;
        background-color:#F7F9FA;
        color: #2B3F52; }
    blockquote > :first-child {
        margin-top: 0; }
    blockquote > :last-child {
        margin-bottom: 0; }
    
    table {
        padding: 0;border-collapse: collapse; }
    table tr {
        border-top: 1px solid #cccccc;
        background-color: white;
        margin: 0;
        padding: 0; }
    table tr:nth-child(2n) {
        background-color: #f8f8f8; }
    table tr th {
        font-weight: bold;
        border: 1px solid #cccccc;
        margin: 0;
        padding: 6px 13px; }
    table tr td {
        border: 1px solid #cccccc;
        margin: 0;
        padding: 6px 13px; }
    table tr th :first-child, table tr td :first-child {
        margin-top: 0; }
    table tr th :last-child, table tr td :last-child {
        margin-bottom: 0; }
    
    img {
        max-width: 100%; }
    
    span.frame {
        display: block;
        overflow: hidden; }
    span.frame > span {
        border: 1px solid #dddddd;
        display: block;
        float: left;
        overflow: hidden;
        margin: 13px 0 0;
        padding: 7px;
        width: auto; }
    span.frame span img {
        display: block;
        float: left; }
    span.frame span span {
        clear: both;
        color: #333333;
        display: block;
        padding: 5px 0 0; }
    span.align-center {
        display: block;
        overflow: hidden;
        clear: both; }
    span.align-center > span {
        display: block;
        overflow: hidden;
        margin: 13px auto 0;
        text-align: center; }
    span.align-center span img {
        margin: 0 auto;
        text-align: center; }
    span.align-right {
        display: block;
        overflow: hidden;
        clear: both; }
    span.align-right > span {
        display: block;
        overflow: hidden;
        margin: 13px 0 0;
        text-align: right; }
    span.align-right span img {
        margin: 0;
        text-align: right; }
    span.float-left {
        display: block;
        margin-right: 13px;
        overflow: hidden;
        float: left; }
    span.float-left span {
        margin: 13px 0 0; }
    span.float-right {
        display: block;
        margin-left: 13px;
        overflow: hidden;
        float: right; }
    span.float-right > span {
        display: block;
        overflow: hidden;
        margin: 13px auto 0;
        text-align: right; }
    
    code, tt {
        margin: 0 2px;
        padding: 0 5px;
        white-space: nowrap;
        border: 1px solid #eaeaea;
        background-color: #f8f8f8;
        border-radius: 3px; }
    
    pre code {
        margin: 0;
        padding: 0;
        white-space: pre;
        border: none;
        background: transparent; }
    
    .highlight pre {
        background-color: #f8f8f8;
        border: 1px solid #cccccc;
        font-size: 13px;
        line-height: 19px;
        overflow: auto;
        padding: 6px 10px;
        border-radius: 3px; }
    
    pre {
        background-color: #f8f8f8;
        border: 1px solid #cccccc;
        font-size: 13px;
        line-height: 19px;
        overflow: auto;
        border-radius: 3px; }
    pre code, pre tt {
        background-color: transparent;
        border: none; }
    
    sup {
        font-size: 0.83em;
        vertical-align: super;
        line-height: 0;
    }
    
    code {
        white-space: pre-wrap;
        word-break: break-all;
    }
    * {
        print-color-adjust: exact;
    }
    @media screen and (min-width: 914px) {
        body {
            width: 960px;
            margin:0 auto;
        }
    }
    @media print {
        table, pre {
            page-break-inside: avoid;
        }
        pre {
            word-wrap: break-word;
        }
    }
```