# 📘 Phase 02 — CSS Box Model & Typography

<text>**Level:** Beginner</text>  
**Duration:** Week 02  
**Phase:** 02 — CSS Box Model & Typography

## 🎯 Learning Goals (শেখার লক্ষ্য)

এই Phase-এ আমরা শিখব কীভাবে HTML Element-এর Size, Spacing, Border এবং Text Design নিয়ন্ত্রণ করতে হয়।

এই Phase শেষ করার পর:

- CSS Box Model ভালোভাবে বুঝতে পারবে।
- HTML Element-এর Width ও Height নিয়ন্ত্রণ করতে পারবে।
- Margin, Padding এবং Border ব্যবহার করতে পারবে।
- Element-এর Shape ও Outline তৈরি করতে পারবে।
- CSS Typography ব্যবহার করে Text সুন্দরভাবে Design করতে পারবে।
- Google Fonts এবং Custom Fonts ব্যবহার করতে পারবে।
- Box Shadow ও Text Shadow তৈরি করতে পারবে।
- বাস্তব Website-এর বিভিন্ন UI Component তৈরি করতে পারবে।

---

# 1. CSS Box Model (বক্স মডেল)

CSS Box Model হলো CSS-এর একটি গুরুত্বপূর্ণ Concept। প্রতিটি HTML Element-কে Browser একটি Rectangular Box হিসেবে বিবেচনা করে।

এই Box-এর মাধ্যমে Element-এর Content, Padding, Border এবং Margin নিয়ন্ত্রণ করা হয়।

## 1.1 What is CSS Box Model?

CSS Box Model হলো এমন একটি পদ্ধতি, যার মাধ্যমে একটি HTML Element-এর Size এবং চারপাশের Spacing নির্ধারণ করা হয়।

প্রতিটি HTML Element-এর Box Model চারটি অংশ নিয়ে গঠিত:

1. Content
2. Padding
3. Border
4. Margin

## 1.2 Content (কনটেন্ট)

Content হলো HTML Element-এর মূল অংশ, যেখানে Text, Image অথবা অন্য কোনো HTML Element থাকে।

`width` এবং `height` Property ব্যবহার করে Content-এর Size নির্ধারণ করা যায়।

**CSS Example:**

```css
.box {
  width: 300px;
  height: 150px;
}
```

এখানে Content-এর Width 300px এবং Height 150px।

## 1.3 Padding (প্যাডিং)

কোনো Element-এর Content এবং Border-এর মধ্যবর্তী ফাঁকা জায়গাকে Padding বলা হয়।

Padding ব্যবহার করে Content-এর চারপাশে ভিতরের Spacing তৈরি করা হয়।

**CSS Example:**

```css
.box {
  padding: 20px;
}
```

এখানে Content-এর চারপাশে 20px Padding যুক্ত হবে।

**মনে রাখবে:**
- Padding হলো Element-এর ভিতরের Spacing।
- Padding-এর Background Color সাধারণত Element-এর Background-এর অংশ হিসেবে প্রদর্শিত হয়।
- Padding-এর চারটি দিক আলাদাভাবে নির্ধারণ করা যায়।

## 1.4 Border (বর্ডার)

কোনো Element-এর Padding এবং Content-এর চারপাশে যে রেখা বা সীমানা তৈরি হয়, তাকে Border বলা হয়।

**CSS Example:**

```css
.box {
  border: 2px solid black;
}
```

এখানে Element-এর চারপাশে 2px পুরু কালো Solid Border তৈরি হবে।

## 1.5 Margin (মার্জিন)

কোনো Element-এর Border-এর বাইরের ফাঁকা জায়গাকে Margin বলা হয়।

Margin ব্যবহার করে একটি Element থেকে অন্য Element-এর মধ্যে দূরত্ব তৈরি করা হয়।

**CSS Example:**

```css
.box {
  margin: 20px;
}
```

এখানে Element-এর চারপাশে 20px বাইরের Spacing তৈরি হবে।

**মনে রাখবে:**
- Margin হলো Element-এর বাইরের Spacing।
- Margin দিয়ে একাধিক Element-এর মধ্যে দূরত্ব তৈরি করা যায়।
- Margin-এর Background Color থাকে না।

## 1.6 Box Model Diagram

CSS Box Model-এর চারটি অংশ নিচের Diagram-এর মাধ্যমে বোঝা যায়।

```text
+---------------------------------------+
|                MARGIN                 |
|  +---------------------------------+  |
|  |             BORDER              |  |
|  |  +---------------------------+  |  |
|  |  |          PADDING          |  |  |
|  |  |  +---------------------+  |  |  |
|  |  |  |                     |  |  |  |
|  |  |  |       CONTENT       |  |  |  |
|  |  |  |                     |  |  |  |
|  |  |  +---------------------+  |  |  |
|  |  +---------------------------+  |  |
|  +---------------------------------+  |
+---------------------------------------+
```

## 1.7 Box Sizing

`box-sizing` Property নির্ধারণ করে একটি Element-এর মোট Width এবং Height কীভাবে গণনা করা হবে।

CSS-এ `box-sizing`-এর দুটি গুরুত্বপূর্ণ Value রয়েছে:

- `content-box`
- `border-box`

## 1.8 box-sizing: content-box

`content-box` হলো CSS-এর Default Box Sizing Value।

এক্ষেত্রে নির্ধারিত Width এবং Height শুধু Content-এর জন্য গণনা করা হয়। Padding এবং Border অতিরিক্তভাবে যোগ হয়।

**CSS Example:**

```css
.box {
  width: 300px;
  padding: 20px;
  border: 5px solid black;
  box-sizing: content-box;
}
```

**Calculation:**

```text
Total Width =
Content Width + Left Padding + Right Padding
+ Left Border + Right Border

= 300 + 20 + 20 + 5 + 5

= 350px
```

অর্থাৎ Element-এর মোট Width হবে 350px।

## 1.9 box-sizing: border-box

`border-box` ব্যবহার করলে নির্ধারিত Width এবং Height-এর মধ্যেই Content, Padding ও Border অন্তর্ভুক্ত থাকে।

**CSS Example:**

```css
.box {
  width: 300px;
  padding: 20px;
  border: 5px solid black;
  box-sizing: border-box;
}
```

**Calculation:**

```text
Total Width = 300px
```

এখানে Padding এবং Border যোগ করার পরও Element-এর মোট Width 300px থাকবে।

**Common CSS Reset:**

```css
*,
*::before,
*::after {
  box-sizing: border-box;
}
```

**মনে রাখবে:**
- `content-box` হলো Default Value।
- `border-box` ব্যবহার করলে Width ও Height হিসাব করা সহজ হয়।
- Modern Web Development-এ সাধারণত `border-box` ব্যবহার করা হয়।

---

# 2. CSS Width & Height (প্রস্থ ও উচ্চতা)

CSS-এর মাধ্যমে কোনো HTML Element-এর Width এবং Height নিয়ন্ত্রণ করা যায়।

## 2.1 Width

কোনো Element-এর প্রস্থ নির্ধারণ করার জন্য `width` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
.box {
  width: 300px;
}
```

এখানে Element-এর Width হবে 300px।

## 2.2 Height

কোনো Element-এর উচ্চতা নির্ধারণ করার জন্য `height` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
.box {
  height: 200px;
}
```

এখানে Element-এর Height হবে 200px।

## 2.3 Min Width

কোনো Element-এর সর্বনিম্ন Width নির্ধারণ করার জন্য `min-width` Property ব্যবহার করা হয়।

Element-এর Width নির্ধারিত Min Width-এর চেয়ে ছোট হবে না।

**CSS Syntax:**

```css
.box {
  min-width: 200px;
}
```

## 2.4 Max Width

কোনো Element-এর সর্বোচ্চ Width নির্ধারণ করার জন্য `max-width` Property ব্যবহার করা হয়।

Element-এর Width নির্ধারিত Max Width-এর বেশি হবে না।

**CSS Syntax:**

```css
.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
}
```

এখানে Container-এর Width 100% পর্যন্ত বাড়তে পারবে, তবে সর্বোচ্চ 1200px হবে।

## 2.5 Min Height

কোনো Element-এর সর্বনিম্ন Height নির্ধারণ করার জন্য `min-height` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
.hero {
  min-height: 400px;
}
```

## 2.6 Max Height

কোনো Element-এর সর্বোচ্চ Height নির্ধারণ করার জন্য `max-height` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
.box {
  max-height: 300px;
  overflow: auto;
}
```

এখানে Content বেশি হলে Scrollbar প্রদর্শিত হতে পারে।

## 2.7 Aspect Ratio

কোনো Element-এর Width এবং Height-এর অনুপাত নির্ধারণ করার জন্য `aspect-ratio` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
.image-box {
  width: 100%;
  aspect-ratio: 16 / 9;
}
```

এখানে Element-এর Width এবং Height-এর অনুপাত হবে 16:9।

**Common Aspect Ratios:**

| Aspect Ratio | ব্যবহার |
|---|---|
| `1 / 1` | Square Image |
| `4 / 3` | Traditional Image |
| `16 / 9` | Video ও Banner |
| `3 / 2` | Photography |

**মনে রাখবে:**
- `width` এবং `height` দিয়ে নির্দিষ্ট Size নির্ধারণ করা যায়।
- `min-width` ও `max-width` দিয়ে Width-এর সীমা নির্ধারণ করা যায়।
- `min-height` ও `max-height` দিয়ে Height-এর সীমা নির্ধারণ করা যায়।
- Responsive Design তৈরিতে `max-width` এবং `aspect-ratio` বেশ কার্যকর।

---

# 3. CSS Border & Outline

CSS-এর মাধ্যমে কোনো Element-এর চারপাশে Border এবং Outline তৈরি করা যায়।

## 3.1 Border

কোনো HTML Element-এর চারপাশে সীমানা বা রেখা তৈরি করার জন্য `border` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
.box {
  border: 2px solid black;
}
```

এখানে:
- `2px` হলো Border-এর Width।
- `solid` হলো Border-এর Style।
- `black` হলো Border-এর Color।

## 3.2 Border Width

Border-এর পুরুত্ব নির্ধারণ করার জন্য `border-width` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
.box {
  border-width: 3px;
}
```

## 3.3 Border Style

Border কেমন হবে তা নির্ধারণ করার জন্য `border-style` Property ব্যবহার করা হয়।

**Common Values:**

| Value | কাজ |
|---|---|
| `solid` | সাধারণ Solid Line |
| `dashed` | Dash বা ছোট ছোট রেখা |
| `dotted` | বিন্দু বিন্দু রেখা |
| `double` | দুটি সমান্তরাল রেখা |
| `none` | কোনো Border থাকবে না |
| `hidden` | Border লুকানো থাকবে |
| `groove` | খাঁজকাটা 3D Effect |
| `ridge` | উঁচু 3D Effect |
| `inset` | ভিতরের দিকে চাপা Effect |
| `outset` | বাইরের দিকে উঁচু Effect |

**CSS Example:**

```css
.box {
  border-style: dashed;
}
```

## 3.4 Border Color

Border-এর রং নির্ধারণ করার জন্য `border-color` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
.box {
  border-color: red;
}
```

## 3.5 Border Radius

কোনো Element-এর Border-এর Corner গোলাকার করার জন্য `border-radius` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
.box {
  border: 2px solid black;
  border-radius: 10px;
}
```

**Common Examples:**

```css
.box {
  border-radius: 10px;
}

.circle {
  width: 100px;
  height: 100px;
  border-radius: 50%;
}

.pill {
  border-radius: 999px;
}
```

## 3.6 Outline

কোনো Element-এর Border-এর বাইরের দিকে একটি রেখা তৈরি করার জন্য `outline` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
button {
  outline: 2px solid blue;
}
```

**Border ও Outline-এর পার্থক্য:**

| Border | Outline |
|---|---|
| Element-এর Box Model-এর অংশ | Box Model-এর অংশ নয় |
| Width ও Height-এর হিসাবকে প্রভাবিত করতে পারে | Width ও Height-এর হিসাব পরিবর্তন করে না |
| চারপাশে Border তৈরি করে | Border-এর বাইরে রেখা তৈরি করে |
| চার পাশের Border আলাদাভাবে নিয়ন্ত্রণ করা যায় | সাধারণত চার পাশের Outline একসঙ্গে নিয়ন্ত্রণ করা হয় |

## 3.7 Outline Offset

Element এবং Outline-এর মধ্যবর্তী দূরত্ব নির্ধারণ করার জন্য `outline-offset` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
button {
  outline: 2px solid blue;
  outline-offset: 5px;
}
```

এখানে Outline এবং Element-এর মধ্যে 5px দূরত্ব থাকবে।

**মনে রাখবে:**
- `border` Element-এর Box Model-এর অংশ।
- `outline` Box Model-এর অংশ নয়।
- `border-radius` দিয়ে Corner গোলাকার করা যায়।
- Form Input ও Button-এর Focus State Design করতে Outline গুরুত্বপূর্ণ।

---

# 4. CSS Spacing (মার্জিন ও প্যাডিং)

CSS-এ কোনো Element-এর ভিতরে এবং বাইরে Spacing তৈরি করার জন্য Margin ও Padding ব্যবহার করা হয়।

## 4.1 Margin

কোনো Element-এর চারপাশে বাইরের Spacing তৈরি করার জন্য `margin` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
.box {
  margin: 20px;
}
```

এখানে Element-এর চারপাশে 20px Margin থাকবে।

## 4.2 Padding

কোনো Element-এর Content এবং Border-এর মধ্যে ভিতরের Spacing তৈরি করার জন্য `padding` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
.box {
  padding: 20px;
}
```

## 4.3 Individual Sides

Margin এবং Padding-এর চারটি দিক আলাদাভাবে নিয়ন্ত্রণ করা যায়।

চারটি দিক হলো:

- Top
- Right
- Bottom
- Left

**Margin Individual Properties:**

```css
.box {
  margin-top: 10px;
  margin-right: 20px;
  margin-bottom: 30px;
  margin-left: 40px;
}
```

**Padding Individual Properties:**

```css
.box {
  padding-top: 10px;
  padding-right: 20px;
  padding-bottom: 30px;
  padding-left: 40px;
}
```

## 4.4 Shorthand Properties

একাধিক Margin বা Padding Property আলাদাভাবে না লিখে Shorthand ব্যবহার করে সংক্ষেপে লেখা যায়।

**One Value:**

```css
.box {
  margin: 20px;
  padding: 20px;
}
```

চারটি দিকেই 20px প্রযোজ্য হবে।

**Two Values:**

```css
.box {
  margin: 10px 20px;
}
```

- প্রথম Value: Top ও Bottom।
- দ্বিতীয় Value: Right ও Left।

**Three Values:**

```css
.box {
  margin: 10px 20px 30px;
}
```

- প্রথম Value: Top।
- দ্বিতীয় Value: Right ও Left।
- তৃতীয় Value: Bottom।

**Four Values:**

```css
.box {
  margin: 10px 20px 30px 40px;
}
```

- প্রথম Value: Top।
- দ্বিতীয় Value: Right।
- তৃতীয় Value: Bottom।
- চতুর্থ Value: Left।

**মনে রাখবে:** Shorthand-এর চারটি Value সবসময় Clockwise Direction অনুযায়ী কাজ করে।

## 4.5 Margin Auto

কোনো নির্দিষ্ট Width-এর Block Element-কে Horizontal বা অনুভূমিকভাবে Center করার জন্য `margin: auto` ব্যবহার করা যায়।

**CSS Syntax:**

```css
.container {
  width: 80%;
  max-width: 1200px;
  margin: 0 auto;
}
```

এখানে Element-এর Left এবং Right Margin স্বয়ংক্রিয়ভাবে সমান হবে।

## 4.6 Margin Collapse

দুটি Block Element-এর Vertical Margin একে অপরের সঙ্গে মিলিত হয়ে একটি Margin হিসেবে গণনা হওয়ার প্রক্রিয়াকে Margin Collapse বলা হয়।

**CSS Example:**

```css
.box-one {
  margin-bottom: 30px;
}

.box-two {
  margin-top: 20px;
}
```

সাধারণ Block Layout-এ দুটি Element-এর মধ্যে মোট Vertical Gap 50px না হয়ে 30px হবে।

কারণ বড় Margin Value-টি কার্যকর হবে।

**মনে রাখবে:**
- Margin Element-এর বাইরের Spacing তৈরি করে।
- Padding Element-এর ভিতরের Spacing তৈরি করে।
- Margin Collapse সাধারণত Block Element-এর Vertical Margin-এর ক্ষেত্রে দেখা যায়।
- Flexbox ও Grid Layout-এ সাধারণত এই ধরনের Margin Collapse হয় না।

---

# 5. CSS Typography (টাইপোগ্রাফি)

CSS Typography হলো Text-এর Font, Size, Weight, Color, Alignment, Spacing এবং অন্যান্য বৈশিষ্ট্য নিয়ন্ত্রণ করার পদ্ধতি।

একটি Website-এর Text সুন্দর, পরিষ্কার এবং সহজে পড়ার উপযোগী করতে Typography গুরুত্বপূর্ণ ভূমিকা রাখে।

## 5.1 Font Family

কোনো Text কোন ধরনের Font ব্যবহার করবে তা নির্ধারণ করার জন্য `font-family` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
body {
  font-family: Arial, sans-serif;
}
```

এখানে Browser প্রথমে Arial Font ব্যবহার করার চেষ্টা করবে। সেটি না থাকলে `sans-serif` Generic Font ব্যবহার করবে।

## 5.2 Font Size

Text-এর আকার নির্ধারণ করার জন্য `font-size` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
h1 {
  font-size: 32px;
}

p {
  font-size: 16px;
}
```

## 5.3 Font Weight

Text কতটা মোটা বা পাতলা হবে তা নির্ধারণ করার জন্য `font-weight` Property ব্যবহার করা হয়।

**Common Values:**

| Value | কাজ |
|---|---|
| `100` | Thin |
| `200` | Extra Light |
| `300` | Light |
| `400` | Normal |
| `500` | Medium |
| `600` | Semi Bold |
| `700` | Bold |
| `800` | Extra Bold |
| `900` | Black |

**CSS Syntax:**

```css
h1 {
  font-weight: 700;
}

p {
  font-weight: 400;
}
```

## 5.4 Font Style

Text-এর Font Style নির্ধারণ করার জন্য `font-style` Property ব্যবহার করা হয়।

**Common Values:**
- `normal`
- `italic`
- `oblique`

**CSS Syntax:**

```css
p {
  font-style: italic;
}
```

## 5.5 Font Variant

Text-এর ছোট হাতের অক্ষরগুলোকে Small Capital Letter হিসেবে প্রদর্শন করার জন্য `font-variant` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
h2 {
  font-variant: small-caps;
}
```

**Common Values:**
- `normal`
- `small-caps`

## 5.6 Line Height

একটি Text Line থেকে পরবর্তী Text Line-এর মধ্যবর্তী Vertical Spacing নিয়ন্ত্রণ করার জন্য `line-height` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
p {
  font-size: 16px;
  line-height: 1.6;
}
```

এখানে Font Size-এর 1.6 গুণ Line Height নির্ধারণ করা হয়েছে।

**মনে রাখবে:** Paragraph পড়ার সুবিধার জন্য সাধারণত 1.5 থেকে 1.8 Line Height ব্যবহার করা হয়।

## 5.7 Letter Spacing

প্রতিটি Character বা Letter-এর মধ্যবর্তী দূরত্ব নিয়ন্ত্রণ করার জন্য `letter-spacing` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
h1 {
  letter-spacing: 2px;
}
```

## 5.8 Word Spacing

একটি Word থেকে অন্য Word-এর মধ্যবর্তী দূরত্ব নিয়ন্ত্রণ করার জন্য `word-spacing` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
p {
  word-spacing: 5px;
}
```

## 5.9 Text Align

Text কোন দিকে Align হবে তা নির্ধারণ করার জন্য `text-align` Property ব্যবহার করা হয়।

**Common Values:**

| Value | কাজ |
|---|---|
| `left` | বাম দিকে Align |
| `right` | ডান দিকে Align |
| `center` | মাঝখানে Align |
| `justify` | দুই পাশ সমানভাবে Align |
| `start` | Text Direction অনুযায়ী শুরুতে Align |
| `end` | Text Direction অনুযায়ী শেষে Align |

**CSS Syntax:**

```css
h1 {
  text-align: center;
}

p {
  text-align: justify;
}
```

## 5.10 Text Decoration

Text-এর নিচে, উপরে অথবা মাঝখানে রেখা তৈরি করার জন্য `text-decoration` Property ব্যবহার করা হয়।

**Common Values:**

- `none`
- `underline`
- `overline`
- `line-through`

**CSS Syntax:**

```css
a {
  text-decoration: none;
}

h2 {
  text-decoration: underline;
}
```

## 5.11 Text Transform

Text-এর Letter বড় হাতের বা ছোট হাতের করার জন্য `text-transform` Property ব্যবহার করা হয়।

**Common Values:**

| Value | কাজ |
|---|---|
| `uppercase` | সব Letter বড় হাতের করে |
| `lowercase` | সব Letter ছোট হাতের করে |
| `capitalize` | প্রতিটি Word-এর প্রথম Letter বড় হাতের করে |
| `none` | কোনো পরিবর্তন করে না |

**CSS Syntax:**

```css
h1 {
  text-transform: uppercase;
}

p {
  text-transform: capitalize;
}
```

## 5.12 Text Indent

Paragraph-এর প্রথম Line-এর শুরুতে অতিরিক্ত Space তৈরি করার জন্য `text-indent` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
p {
  text-indent: 40px;
}
```

## 5.13 Text Shadow

Text-এর পেছনে Shadow বা ছায়া তৈরি করার জন্য `text-shadow` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
h1 {
  text-shadow: 2px 2px 4px gray;
}
```

এখানে:
- প্রথম `2px` হলো Horizontal Shadow Offset।
- দ্বিতীয় `2px` হলো Vertical Shadow Offset।
- `4px` হলো Blur Radius।
- `gray` হলো Shadow Color।

## 5.14 White Space

HTML Element-এর ভেতরে থাকা Space, Tab এবং Line Break কীভাবে প্রদর্শিত হবে তা নিয়ন্ত্রণ করার জন্য `white-space` Property ব্যবহার করা হয়।

**Common Values:**

| Value | কাজ |
|---|---|
| `normal` | অতিরিক্ত Space ও Line Break স্বাভাবিক নিয়মে পরিচালনা করে |
| `nowrap` | Text-কে এক লাইনে রাখে |
| `pre` | HTML-এর Whitespace ও Line Break সংরক্ষণ করে |
| `pre-wrap` | Whitespace সংরক্ষণ করে এবং প্রয়োজন হলে Text Wrap করে |
| `pre-line` | Line Break সংরক্ষণ করে, অতিরিক্ত Space একত্রিত করে |
| `break-spaces` | Whitespace সংরক্ষণ করে এবং প্রয়োজন অনুযায়ী Wrap করে |

**CSS Syntax:**

```css
p {
  white-space: nowrap;
}
```

## 5.15 Word Break

কোনো Word বা Text-এর মধ্যে কোথায় Line Break হবে তা নিয়ন্ত্রণ করার জন্য `word-break` Property ব্যবহার করা হয়।

**Common Values:**

- `normal`
- `break-all`
- `keep-all`
- `break-word` (পুরোনো ও Deprecated Value; এর পরিবর্তে `overflow-wrap` ব্যবহার করা ভালো।)

**CSS Syntax:**

```css
.box {
  word-break: break-all;
}
```

## 5.16 Overflow Wrap

কোনো দীর্ঘ Word বা URL Container-এর বাইরে চলে যাওয়া থেকে রক্ষা করতে `overflow-wrap` Property ব্যবহার করা হয়।

**Common Values:**

- `normal`
- `break-word`
- `anywhere`

**CSS Syntax:**

```css
p {
  overflow-wrap: break-word;
}
```

**মনে রাখবে:**
- Typography Website-এর Readability বাড়ায়।
- `font-family` Font নির্ধারণ করে।
- `font-size` Text-এর Size নির্ধারণ করে।
- `font-weight` Text-এর পুরুত্ব নিয়ন্ত্রণ করে।
- `line-height` Line-এর মধ্যবর্তী Vertical Spacing নিয়ন্ত্রণ করে।
- `letter-spacing` ও `word-spacing` Text-এর Spacing নিয়ন্ত্রণ করে।
- `overflow-wrap` দীর্ঘ Word বা URL-এর Layout সমস্যা কমাতে সাহায্য করে।

---

# 6. CSS Fonts (ফন্ট)

CSS Fonts ব্যবহার করে Website-এর Text-এর জন্য বিভিন্ন Font Style এবং Custom Font ব্যবহার করা যায়।

## 6.1 Web Safe Fonts

Web Safe Fonts হলো এমন কিছু Font, যেগুলো অধিকাংশ Operating System ও Browser-এ সাধারণত পাওয়া যায়।

**Common Web Safe Fonts:**

| Font | Type |
|---|---|
| Arial | Sans-serif |
| Verdana | Sans-serif |
| Tahoma | Sans-serif |
| Trebuchet MS | Sans-serif |
| Times New Roman | Serif |
| Georgia | Serif |
| Courier New | Monospace |

**CSS Example:**

```css
body {
  font-family: Arial, sans-serif;
}
```

## 6.2 Google Fonts

Google Fonts হলো একটি জনপ্রিয় Free Font Library, যেখান থেকে বিভিন্ন Font সংগ্রহ করে Website-এ ব্যবহার করা যায়।

**Google Fonts Website:**  
https://fonts.google.com/

**Google Fonts ব্যবহার করার নিয়ম:**

1. Google Fonts Website-এ প্রবেশ করো।
2. পছন্দের Font Search করো।
3. প্রয়োজনীয় Font Weight নির্বাচন করো।
4. Google Fonts থেকে Embed Code সংগ্রহ করো।
5. HTML-এর `<head>` Section-এ Link যুক্ত করো।
6. CSS-এ `font-family` ব্যবহার করো।

**HTML Example:**

```html
<head>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

  <link
    href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&display=swap"
    rel="stylesheet"
  >
</head>
```

**CSS Example:**

```css
body {
  font-family: "Poppins", sans-serif;
}
```

## 6.3 @font-face

নিজের Download করা Font File Website-এ ব্যবহার করার জন্য `@font-face` Rule ব্যবহার করা হয়।

**CSS Syntax:**

```css
@font-face {
  font-family: "MyCustomFont";
  src: url("./fonts/my-font.woff2") format("woff2");
  font-weight: 400;
  font-style: normal;
}

body {
  font-family: "MyCustomFont", sans-serif;
}
```

এখানে `@font-face` দিয়ে Custom Font Register করা হয়েছে।

## 6.4 Font Formats

Website-এ বিভিন্ন ধরনের Font File Format ব্যবহার করা যায়।

| Format | Description |
|---|---|
| `.woff2` | Modern Web Font Format; সাধারণত বেশি Recommended |
| `.woff` | Web Font Format |
| `.ttf` | TrueType Font |
| `.otf` | OpenType Font |
| `.eot` | পুরোনো Internet Explorer-এর জন্য ব্যবহৃত Font Format |
| `.svg` | পুরোনো কিছু Web Font ব্যবহারের Format |

**মনে রাখবে:** Modern Website-এর জন্য সাধারণত `.woff2` Font Format ব্যবহার করা ভালো।

## 6.5 Font Fallback

প্রথম পছন্দের Font কোনো কারণে Load না হলে Browser যেন অন্য Font ব্যবহার করতে পারে, সেজন্য একাধিক Font-এর নাম CSS-এ দেওয়া হয়। একে Font Fallback বলা হয়।

**CSS Syntax:**

```css
body {
  font-family: Arial, Helvetica, sans-serif;
}
```

এখানে Browser প্রথমে Arial ব্যবহার করার চেষ্টা করবে। সেটি না পেলে Helvetica এবং সেটিও না থাকলে Generic `sans-serif` Font ব্যবহার করবে।

**মনে রাখবে:**
- Website-এর Typography সুন্দর করতে উপযুক্ত Font নির্বাচন গুরুত্বপূর্ণ।
- Google Fonts ব্যবহার করে সহজে Custom Font যুক্ত করা যায়।
- `@font-face` দিয়ে নিজের Font File ব্যবহার করা যায়।
- Font Fallback ব্যবহার করলে Font Load না হলেও Text প্রদর্শিত হবে।

---

# 7. CSS Shadows (শ্যাডো)

CSS Shadow ব্যবহার করে কোনো Element অথবা Text-এর পেছনে ছায়া তৈরি করা যায়।

CSS-এ Shadow-এর দুটি গুরুত্বপূর্ণ Property রয়েছে:

1. `box-shadow`
2. `text-shadow`

## 7.1 Box Shadow

কোনো HTML Element-এর চারপাশে Shadow বা ছায়া তৈরি করার জন্য `box-shadow` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
.card {
  box-shadow: 2px 4px 10px gray;
}
```

**Box Shadow Syntax:**

```css
box-shadow: horizontal-offset vertical-offset blur-radius spread-radius color;
```

**ব্যাখ্যা:**

- `horizontal-offset` — Shadow ডানে বা বামে কতটুকু যাবে।
- `vertical-offset` — Shadow উপরে বা নিচে কতটুকু যাবে।
- `blur-radius` — Shadow কতটুকু Blurry হবে।
- `spread-radius` — Shadow কতটুকু বড় বা ছোট হবে।
- `color` — Shadow-এর রং।

**Example:**

```css
.card {
  width: 300px;
  padding: 20px;
  background-color: white;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}
```

## 7.2 Text Shadow

কোনো Text-এর পেছনে Shadow বা ছায়া তৈরি করার জন্য `text-shadow` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
h1 {
  text-shadow: 2px 2px 4px gray;
}
```

**Text Shadow Syntax:**

```css
text-shadow: horizontal-offset vertical-offset blur-radius color;
```

**Example:**

```css
h1 {
  color: #071b36;
  text-shadow: 2px 3px 5px rgba(0, 0, 0, 0.3);
}
```

**Box Shadow ও Text Shadow-এর পার্থক্য:**

| Box Shadow | Text Shadow |
|---|---|
| Element-এর চারপাশে Shadow তৈরি করে | Text-এর পেছনে Shadow তৈরি করে |
| `box-shadow` ব্যবহার করা হয় | `text-shadow` ব্যবহার করা হয় |
| Spread Radius ব্যবহার করা যায় | Spread Radius নেই |

**মনে রাখবে:**
- Card Design-এ `box-shadow` বেশি ব্যবহার করা হয়।
- Heading ও Special Text Design-এ `text-shadow` ব্যবহার করা যায়।
- Shadow-এর অতিরিক্ত ব্যবহার Website-এর UI অগোছালো করতে পারে।

---

# 8. Practical Projects (প্র্যাকটিক্যাল প্রজেক্ট)

এই Phase-এ শেখা CSS Properties ব্যবহার করে নিচের চারটি Project তৈরি করবে।

## Project 01 — Login Form

**Project Goal:** একটি সুন্দর ও Responsive Login Form তৈরি করা।

**Requirements:**

- Form-এর জন্য একটি Card Design তৈরি করতে হবে।
- Input Field-এ Padding ও Border ব্যবহার করতে হবে।
- Border Radius যুক্ত করতে হবে।
- Login Button Design করতে হবে।
- Input ও Button-এ Focus State তৈরি করতে হবে।
- Card-এ Box Shadow ব্যবহার করতে হবে।
- Typography সুন্দরভাবে সাজাতে হবে।

**Practice Topics:**
- Box Model
- Width & Height
- Padding & Margin
- Border & Outline
- Typography
- Box Shadow

## Project 02 — Product Card

**Project Goal:** একটি Product Card Design তৈরি করা।

**Requirements:**

- Product Image যুক্ত করতে হবে।
- Product Name ও Description দেখাতে হবে।
- Product Price ও Discount যুক্ত করতে হবে।
- Add to Cart Button তৈরি করতে হবে।
- Border Radius ও Box Shadow ব্যবহার করতে হবে।
- Image-এর Aspect Ratio ঠিক রাখতে হবে।

**Practice Topics:**
- Width & Height
- Aspect Ratio
- Border Radius
- Padding & Margin
- Typography
- Box Shadow

## Project 03 — Blog Post Card

**Project Goal:** একটি সুন্দর Blog Post Card তৈরি করা।

**Requirements:**

- Blog Thumbnail Image যুক্ত করতে হবে।
- Blog Title ও Description দেখাতে হবে।
- Author Name ও Publish Date যুক্ত করতে হবে।
- Text Spacing সুন্দরভাবে সাজাতে হবে।
- Card-এর Width ও Height নিয়ন্ত্রণ করতে হবে।
- Long Text-এর Overflow ঠিক করতে হবে।

**Practice Topics:**
- Box Model
- Width & Height
- Typography
- Text Alignment
- Line Height
- Overflow Wrap
- Border & Shadow

## Project 04 — Pricing Card

**Project Goal:** একটি Professional Pricing Card Design তৈরি করা।

**Requirements:**

- Pricing Plan-এর Name যুক্ত করতে হবে।
- Monthly অথবা Yearly Price দেখাতে হবে।
- Features List যুক্ত করতে হবে।
- Subscribe Button তৈরি করতে হবে।
- Border Radius ও Shadow ব্যবহার করতে হবে।
- Important Plan Highlight করতে হবে।
- Typography ও Spacing সুন্দরভাবে সাজাতে হবে।

**Practice Topics:**
- Box Model
- Width & Height
- Margin & Padding
- Border & Outline
- Typography
- Box Shadow

---

# 9. Weekly Practice Routine (সাপ্তাহিক অনুশীলন)

| Day | Topics | Practice |
|---|---|---|
| Day 01 | CSS Box Model | Content, Padding, Border, Margin |
| Day 02 | Width & Height | Min, Max ও Aspect Ratio |
| Day 03 | Border & Outline | Border Style, Radius ও Outline |
| Day 04 | Spacing | Margin, Padding ও Shorthand |
| Day 05 | Typography | Font ও Text Properties |
| Day 06 | CSS Fonts & Shadows | Google Fonts, @font-face, Shadow |
| Day 07 | Revision & Projects | চারটি Project-এর কাজ |

---

# 10. Learning Checklist (শেখার অগ্রগতি)

নিচের Checklist ব্যবহার করে নিজের Learning Progress Track করতে পারবে।

### CSS Box Model
- [ ] CSS Box Model কী বুঝতে পেরেছি।
- [ ] Content, Padding, Border ও Margin বুঝেছি।
- [ ] Box Model Diagram বুঝেছি।
- [ ] `box-sizing: content-box` বুঝেছি।
- [ ] `box-sizing: border-box` বুঝেছি।

### Width & Height
- [ ] `width` ও `height`
- [ ] `min-width` ও `max-width`
- [ ] `min-height` ও `max-height`
- [ ] `aspect-ratio`

### Border & Outline
- [ ] `border`
- [ ] `border-width`
- [ ] `border-style`
- [ ] `border-color`
- [ ] `border-radius`
- [ ] `outline`
- [ ] `outline-offset`

### Spacing
- [ ] `margin`
- [ ] `padding`
- [ ] Individual Sides
- [ ] Shorthand Properties
- [ ] Margin Collapse

### Typography
- [ ] `font-family`
- [ ] `font-size`
- [ ] `font-weight`
- [ ] `font-style`
- [ ] `font-variant`
- [ ] `line-height`
- [ ] `letter-spacing`
- [ ] `word-spacing`
- [ ] `text-align`
- [ ] `text-decoration`
- [ ] `text-transform`
- [ ] `text-indent`
- [ ] `text-shadow`
- [ ] `white-space`
- [ ] `word-break`
- [ ] `overflow-wrap`

### CSS Fonts
- [ ] Web Safe Fonts
- [ ] Google Fonts
- [ ] `@font-face`
- [ ] Font Formats
- [ ] Font Fallback

### CSS Shadows
- [ ] `box-shadow`
- [ ] `text-shadow`

### Practical Projects
- [ ] Login Form
- [ ] Product Card
- [ ] Blog Post Card
- [ ] Pricing Card

---

# 11. Learning Resources (শেখার রিসোর্স)

CSS শেখার জন্য নিচের Resources ব্যবহার করতে পারো।

| Resource | Link |
|---|---|
| MDN CSS Box Model | https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model |
| MDN CSS Sizing | https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_sizing |
| MDN CSS Borders | https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders |
| MDN CSS Text | https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_text |
| MDN CSS Fonts | https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts |
| Google Fonts | https://fonts.google.com/ |
| W3Schools CSS | https://www.w3schools.com/css/ |

---

# 12. Final Tips (গুরুত্বপূর্ণ পরামর্শ)

1. শুধু CSS Properties মুখস্থ না করে প্রতিটি Property নিজে Code করে Practice করবে।
2. Margin ও Padding-এর পার্থক্য ভালোভাবে বুঝবে।
3. `box-sizing: border-box` ব্যবহার করার অভ্যাস তৈরি করবে।
4. Typography Design করার সময় Readability-কে গুরুত্ব দেবে।
5. Google Fonts ব্যবহার করে বিভিন্ন Font Combination Practice করবে।
6. Box Shadow ও Border Radius ব্যবহার করে Professional UI তৈরি করার চেষ্টা করবে।
7. প্রতিটি Project Responsive করার চেষ্টা করবে।
8. প্রতিদিন শেখা বিষয়গুলো Revision করবে।

---

## 🎓 Phase 02 Completion Goal

এই Phase সম্পন্ন করার পর তুমি CSS Box Model, Spacing, Sizing, Border, Typography, Fonts এবং Shadows ব্যবহার করে বিভিন্ন ধরনের Professional UI Component তৈরি করতে পারবে।

**Learning Strategy:**

- 30% — Learn & Understand
- 70% — Coding & Practical Projects

**Remember:**

> Don't just learn CSS properties. Understand how every property changes the layout and design of your website.

**Happy Coding! 🚀**
