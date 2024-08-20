# markdown tips

## vscode plugins

- Markdown Preview Enhanced
- markdownlint
  - 不应被排版的内容使用代码块包裹

    - 文件名
    - 屏幕 log

- Prettier - Code formatter

## 中文文案排版指北[<i class="fa-solid fa-link fa-2xs" style="color: #0091ff;"></i>](https://github.com/sparanoid/chinese-copywriting-guidelines/tree/master)

## Markdown 写作心得[<i class="fa-solid fa-link fa-2xs" style="color: #0091ff;"></i>](https://wu-kan.cn/2020/01/18/Markdown%E5%86%99%E4%BD%9C%E5%BF%83%E5%BE%97/)

## 图片插入

- 本地
- 图床
- Base64 编码

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

```MD
> Dorothy followed her through many of the beautiful rooms in her castle.
>
> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.
```

> Dorothy followed her through many of the beautiful rooms in her castle.
>
> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.

#### Nested Blockquotes

```MD
> Dorothy followed her through many of the beautiful rooms in her castle.
>
>> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.
```

> Dorothy followed her through many of the beautiful rooms in her castle.
>
>> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.

#### Blockquotes with Other Elements

```MD
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

```MD
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

```MD
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

```MD
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

```MD
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

```MD
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

#### Escaping Backticks

| Markdown | HTML | Rendered Output |
| --- | --- | --- |
| \`\`Use \`code\` in your Markdown file.\`\` | ```<code>Use `code` in your Markdown file.</code>``` | <code>Use `code` in your Markdown file.</code> |

#### Code Blocks

at least four spaces of one tab.

```MD
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

```MD
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

```MD
<https://www.markdownguide.org>
<fake@example.com>
```

<https://www.markdownguide.org>
<fake@example.com>

#### Formatting Links

```MD
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

```MD
[hobbit-hole][1]
or
[hobbit-hole] [1]
```

##### Formatting the Second Part of the Link

The following are quivalent.

```MD
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

```MD
In a hole in the ground there lived a hobbit. Not a nasty, dirty, wet hole, filled with the ends
of worms and an oozy smell, nor yet a dry, bare, sandy hole with nothing in it to sit down on or to
eat: it was a [hobbit-hole](https://en.wikipedia.org/wiki/Hobbit#Lifestyle "Hobbit lifestyles"), and that means comfort.
```

good one:

```MD
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

[1]: <https://en.wikipedia.org/wiki/Hobbit#Lifestyle> "Hobbit lifestyles"

| <i class="fa-solid fa-check fa-lg" style="color: #2bff00;"></i> Do this | <i class="fa-solid fa-xmark fa-lg" style="color: #ff0000;"></i> Don't do this |
| --- | --- |
| `[link](https://www.example.com/my%20great%20page)` <br><br> `<a href="https://www.example.com/my great page">link</a>` | `[link](https://www.example.com/my great page)` |
| `[a novel](https://en.wikipedia.org/wiki/The_Milagro_Beanfield_War_%28novel%29)` <br><br> `<a href="https://en.wikipedia.org/wiki/The_Milagro_Beanfield_War_(novel)">a novel</a>` | `[a novel](https://en.wikipedia.org/wiki/The_Milagro_Beanfield_War_(novel))` |

### Images

```MD
![The San Juan Mountains are beautiful!](https://mdg.imgix.net/assets/images/san-juan-mountains.jpg?auto=format&fit=clip&q=40&w=1080 "San Juan Mountains")
```

![The San Juan Mountains are beautiful!](https://mdg.imgix.net/assets/images/san-juan-mountains.jpg?auto=format&fit=clip&q=40&w=1080 "San Juan Mountains")

#### Linking Images

```MD
[![An old rock in the desert](https://mdg.imgix.net/assets/images/shiprock.jpg?auto=format&fit=clip&q=40&w=1080 "Shiprock, New Mexico by Beau Rogers")](https://www.flickr.com/)
```

[![An old rock in the desert](https://mdg.imgix.net/assets/images/shiprock.jpg?auto=format&fit=clip&q=40&w=1080 "Shiprock, New Mexico by Beau Rogers")](https://www.flickr.com/)

### Escaping Characters

```MD
\* Without the backslash, this would be a bullet in an unordered list.
```

\* Without the backslash, this would be a bullet in an unordered list.

#### Characters You Can Escape

| Character | Name |
| --- | --- |
| \\ | backslash |
| \` | backtick(see also escaping backticks in code) |
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
| \| | pipe (see also escaping pipe in tables) |

### HTML

Many Markdown applications allow you to use HTML tags in Markdown-formatted text. This is helpful if you prefer certain HTML tags to Markdown syntax.

line 493 and line 505.
