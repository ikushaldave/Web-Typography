# Web Typography

### Web Typography

While surfing on the internet the type of content you come through are texts, images, video, audio, etc. The key point is that 95% of information on the web is in textual form. Knowing representing texts in the best way on a page is also a great challenge. In this lesson, we are going to take a look at the basic principles of typography and how to apply it using HTML & CSS.

There are two basic terms in the typography world that you will often come through: `Typeface` and `Font`.

#### Typeface Vs Font

The "typeface" and "font" are often interchanged causing confusion. But the two are traditionally different.

**Typography:** It's the design of a collection of glyphs(e.g. letters, numbers, symbols). A typeface is what we see, how the text looks, feels, and reads.

**Font:** On the other hand font is the file that contains typeface. A specific size, weight, or style of a typeface is defined inside font (e.g. regular, bold, italic).

For better understanding, a _typeface_ is like a song and the _font_ is like an MP3 file.

In the past, we were limited to a small number of typeface that we could use for a website. The font installed on the computer was only available on the website. But now we can embed fonts based on our choices.

[Medium Article on Typeface & font difference](https://medium.com/black-white-studios/whats-the-difference-between-a-font-and-a-typeface-introduction-to-typography-2-5a5d9e25136e)


#### Embeding Web Fonts

Now we have the ability to upload the fonts on the server and then include on a website using CSS `@font-face` at-rule.

The CSS `@font-face` at-rule includes `font-family` and `src` property. The `font-family` property identifies the font's name and the `src` determines the source file of the `font-family`. Thereafter we can use the `font-family` property on elements.

The `@font-face` rule should be added to the stylesheet before any styles.

```css
@font-face {
    font-family: 'Lobster';
    src: url('lobster.woff2') format('woff2'),
         url('lobster.woff') format('woff'),
         url('lobster.ttf') format('truetype');
}

body {
    font-family: "Lobster", "Comic Sans", cursive;
}
```

We can also embed a font using its online soucrce, that can be added inside the `head` using `<link>` tag in the HTML document. For example:

```html
  <!-- HTML -->
<head>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">

    <style>
        body {
            font-family: 'Roboto', sans-serif;
        }
    </style>
</head>
```

Or else we can also directly embed in our existing stylesheet using `@import` rule.

```css
/* CSS */
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap');

body {
    font-family: 'Roboto', sans-serif;
}
```

While embedding fonts on your page, keep in mind not all fonts are freely available. There are paid fonts also. To use paid fonts you must take the authority to do so.

The companies like [Typekit](https://fonts.adobe.com/) and [fotdeck](http://fontdeck.com/) that license the fonts on a paid basis, while [Google](https://fonts.google.com/) license the fonts for free.

### Font Based Properties

To edit the look and feel of texts on a page CSS offers a lot of different properties. These properties are mainly categorized into two categories: "font based properties" and "text-based properties".

##### Font Family

The `font-family` property determines which font will be used to display text on a page.

```css
  body {
    font-family: 'Roboto', 'Lato' sans-serif;
  }
```

Multiple values for the font names can be defined under `font-family` property comma separated. As you can see in the above code. Here we have two values `Roboto` and `Lato` and the third value is fallback.

The first value will be primarily choice. In case the first font won't available the next value will be the alternative choice and so on.

The last value in the expression is the system's default font, which is a fallback value. If any the font declared not available then this fallback value will be applied, most commonly either `sans-serif` or `serif`.

##### Font Size

The `font-size` property sets the size of the text used on a page. It accepts all the length values, pixel(px)s, em, percentage, points, or keywords.

```
  body {
    font-size: 16px;
  }
```

##### Font Style

The `font-style` property used to italicize the texts or prevent the texts from being italicized.

```css
  span {
    font-style: italic;
  }
```

Apart from `italic`, it accepts three other values also, `normal`, `oblique`, and `inherit`.

##### Font Variant

The `font-variant` property is rarely used. It accepts three values: `small-caps`, `normal`, and `inherit`. The `small-caps` value is occasionally used to make the text in small capitals.

```css
  .small-caps {
    font-variant: small-caps;
  }
```

##### Font Weight

The `font-weight` property is used to make text light or bold. The property accepts either keyword values or numeric values.

The keyword values are `normal`, `bold`, `lighter`, `bolder` and `inherit`.

```css
  .span {
    font-weight: bold;
  }
```

The numeric values are `100`, `200`, `300`, `400`, `500`, `600`, `700`, `800`, `900`, where `100` is thinnest and `900` is the boldest. The `400` is equivalent to `normal` and `700` is equivalent to `bold` weight. You can choose any of these weights.

If a font embedded in our page doesn't include any of these weights, you cannot apply that value. However, if you applied then the nearest value of that particular weight will be applied. For example, if you chose `900` weight and `900` is not available then the nearest value may be `800` or `700` will be applied.

##### Line Height

The `line-height` property determines the distance between two lines (often referred to as leading). It accepts all the general length values.

```css
  body {
    line-height: 1.5;
  }
```

The `1.5` or `150%` value is the standard value that can be applied for the `line-height` property, which is one and a half times of the `font-size` of the typeface. However, values in pixels are also preferable.

```css
  .btn {
    line-height: 24px;
  }
```

##### Shorthand Font Properties

All these font-based properties can also be applied using just `font` shorthand property.

```css
  body {
    font: italic small-caps bold 16px/24px "Roboto", "Lato", sans-serif;
  }
```

The order of the prperty values should be from left right: `font-style`, `font-variant`, `font-weight`, `font-size`, `line-height`, and `font-family`.

The values of all these properties are optional while using shorthand `font` property except the `font-size` and `font-family`.

### Text Based Properties

##### Text Align

The `text-align` property is used to align the content inside an element.

```css
  p {
    text-align: center;
  }
```

The values for the text-align properties are `left`, `right`, `center`, `justify`, and `inherit`. The `left` is the default value that aligns texts to the left side of the element. Similarly, the rest of the values are also straight forward, `right` will align to the right side of the element. The `center` will keep the content center of the element. To justify text in an element the `justify` value can be used which will keep aligning the texts in such a way that the first word of the line will align and the last word will align to the right side of the element.

The `text-align` property can also be used to align the `inline` and `inline-block` element inside a container.

##### Text Decoration

The `text-decoration` property adds underline overline or line-through or combination of all to the selected text.

```css
  .heading {
    text-decoration: underline.
  }
```

The values it can accept are `none`, `underline`, `overline`, `line-through` and `inherit`.

The `none` value will remove any decoration line already available to text.

The `underline` will draw `1px` solid line at the baseline of the text, `overline` will draw `1px` solid line directly above its top point.

The `line-through` value will draw `1px` solid line through its middle point.

By default, the `color` and `style` of the decoration line will be font color and solid respectively. However, you can change the line's color using `text-decoration-color` property.

```css
  .heading {
    text-decoration-color: blue;
  }
```

Similarly using `text-decoration-style` the `solid` style of the line can be chagned. The other values for `text-decoration-style` are `wavy`, `dotted`, `dashed`, `double`.

```css
  .heading {
    text-decoration-style: dotted;
  }
```

##### Text Indent

The text-indent property specifies how much horizontal space should be left before the starting of the first line within an element. All common length values are accepted by the `text-indent` property.

```css
  p {
    text-indent: 32px;
  }
```

##### Text Shadow

The text-shadow property is very similar to the box-shadow property that we have learned in the [box-model](https://github.com/AltCampus/AC-STYLE-box-model) chapter. The only difference is that the text-shadow property doesn't accept fourth(spread) value, which optional in the `box-shadow` property.

```css
.heading {
    text-shadow: 3px 6px 2px rgba(0, 0, 0, .3);
}
```

##### Text Transform

The `text-transform` property controls the case and capitalization of the text. The property accepts five different values: `none`, `capitalize`, `uppercase`, `lowercase`, and `inherit`.

The `capitalize` value will make the first letter each word capital, the uppercase value will capitalize every letter, and the lowercase value will make every letter lowercase. The `none` will leave the text as it was entered in the document.

```css
  h1 {
    text-transform: uppercase;
  }
```

##### Letter Spacing

The `letter-spacing` property controls the amount of space between each character in an element. Space can be increased or decreased. It accepts all the common length values, `none`, and `inherit` value.

```css
  p {
    letter-spacing: 2px;
  }
```

The positive value increases the space and the negative value will decrease the space between each character. The `none` value will bring back to the normal space size.

##### Word Spacing

The `word-spacing` property is similar to the `letter-spacing` property, but it controls the space between each word within an element. The word-spacing property also accepts all the common length values, `none`, and inherit as the `letter-spacing` accepts.

```css
  p {
    letter-spacing: 32px;
  }
```

While going through all these "font-based" and "text-based" properties, the `inherit` value was almost common for each property. The `inherit` keyword value specifies that a property will inherit its value from its parent element. The `inherit` value can be used for any CSS property and on any HTML element.

#### direction

The direction property in CSS sets the direction of of content flow within a block-level element. This applies to text, inline, and inline-block elements. It also sets the default alignment of text and the direction that table cells flow within a table row.

The text on this page is set in the default ltr direction. The most common use case to set rtl is for web pages with Hebrew or Arabic text. Here is an example of Arabic set in rtl:

There is an HTML attribute for setting the direction as well:

`<body dir="rtl">`

Both the CSS property and the HTML attribute will cascade the direction to descendent elements. It is recommended you use the HTML attribute, as that will work even if CSS fails or doesn’t affect the page for any reason.

```css
html {
    /* Keyword values */
    direction: ltr;
    direction: rtl;
}
```

#### text-align-left

The text-align-last CSS property sets how the last line of a block or a line, right before a forced line break, is aligned.

```
/* Keyword values */
text-align-last: auto;
text-align-last: start;
text-align-last: end;
text-align-last: left;
text-align-last: right;
text-align-last: center;
text-align-last: justify;
```

[Read Here More](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align-last)

#### white-space

The white-space CSS property sets how white space inside an element should handled.

```
/* Keyword values */
white-space: normal;
white-space: nowrap;
white-space: pre;
white-space: pre-wrap;
white-space: pre-line;
white-space: break-spaces;
```

#### word-break

The word-break CSS property sets whether line breaks appear wherever the text would otherwise overflow its content box.

```
/* Keyword values */
word-break: normal; 
word-break: break-all; 
word-break: keep-all;
```

[Read Here](https://developer.mozilla.org/en-US/docs/Web/CSS/word-break)

#### word-wrap

The word-wrap property allows long words to be able to be broken and wrap onto the next line.

```
word-wrap: nowrap;
```

### Quotion and Citation in HTML

It is common to find that incorrect tags are used to markup quotes in an HTML document. Usually, beginners treat regular text and quotes in the same way. But actually, they are different. To cover all types of quotation HTML provides different semantic tags: `<cite>`, `<q>` and `<blockquote>`.

It is a great challenge when to use which tags, requires a bit of practice. Let's discuss them in detail.

##### Quoting with `<q>`

The `q` tag is an inline-level element often used to markup inline quotes within other text.
The `<q>` tag is used to semantically represent the dialogue and prose in the HTML document.

By default, the browser will insert proper quotation marks for the content wrapped inside the `q` element.

```html
  <p><q>Programming isn't about what you know; it's about what you can figure out.</q> said by Chris Pine</p>
```

#### Blockquote

To markup, a large block of text as quote, the `<blockquote>` tag is used. The `<blockquote>` is a block-level element that may have another block-level element nested inside it.

For example:

```html
  <blockquote>
    <p>&#8220;In most people&#8217;s vocabularies, design is a veneer. It&#8217;s interior decorating. It&#8217;s the fabric of the curtains, of the sofa. But to me, nothing could be further from the meaning of design. Design is the fundamental soul of a human-made creation that ends up expressing itself in successive outer layers of the product.&#8221;</p>
  </blockquote>
```

You can nest other elements too like heading or list.

```html
  <blockquote>
    <h2>...</h2>
    <p>...</p>
    <ul>
      <li>...</li>
      <li>...</li>
      <li>...</li>
    </ul>
  </blockquote>
```

##### The Citation Attribute

Both `<q>` and `<blockquote>` can have an optional `cite` attribute. The `cite` attribute holds a URL that acts as a reference to the quote. This attribute does not alter the appearance of the element, just add value for screen readers and other devices.

```html
  <p>The officer left a note saying <q cite="https://johnrhea.com/summons">You have been summoned to appear on the 4th day of January on charges of attempted reader bribery.</q></p>
```

##### The `<cite>` Element

The `<cite>` tag is used for citing or referencing any creative work by a person. The tag should not be used for citing or referencing a person who said or wrote the quote.

For Example:

```html
  <p>My favorite book is <cite>The Reality Dysfunction</cite> by
  Peter F. Hamilton. My favorite comic is <cite>Pearls Before
  Swine</cite> by Stephan Pastis. My favorite track is <cite>Jive
  Samba</cite> by the Cannonball Adderley Sextet.</p>
```

By default, browsers italicize cite tags.
