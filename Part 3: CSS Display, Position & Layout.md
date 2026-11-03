# 📘 Phase 03 — CSS Display, Position & Layout

**Level:** Intermediate  
**Duration:** Weeks 03–04  
**Phase:** 03 — CSS Display, Position & Layout

## 🎯 Learning Goals (শেখার লক্ষ্য)

এই Phase-এ আমরা শিখব কীভাবে CSS ব্যবহার করে একটি Website-এর Layout, Element Position এবং Content Arrangement নিয়ন্ত্রণ করতে হয়।

এই Phase শেষ করার পরে:

- CSS Display Properties ব্যবহার করে Element-এর Layout পরিবর্তন করতে পারবে।
- বিভিন্ন Position ব্যবহার করে Element নির্দিষ্ট স্থানে রাখতে পারবে।
- Z-index ও Stacking Context বুঝতে পারবে।
- Overflow এবং Float Properties ব্যবহার করতে পারবে।
- Flexbox দিয়ে One-dimensional Layout তৈরি করতে পারবে।
- CSS Grid দিয়ে Two-dimensional Layout তৈরি করতে পারবে।
- Responsive Navbar, Dashboard এবং Website Layout তৈরি করতে পারবে।

---

# 1. CSS Display (ডিসপ্লে প্রপার্টিজ)

CSS-এর `display` Property নির্ধারণ করে কোনো HTML Element কীভাবে Layout-এ প্রদর্শিত হবে এবং অন্য Element-এর সঙ্গে কীভাবে অবস্থান করবে।

## 1.1 Display: Block

`display: block` ব্যবহার করলে Element একটি Block Element-এর মতো আচরণ করে।

সাধারণত এটি নতুন Line থেকে শুরু হয় এবং Available Width-এর পুরোটা দখল করে।

**CSS Syntax:**

```css
.box {
  display: block;
}
```

**Common Block Elements:**
- `<div>`
- `<p>`
- `<h1>` থেকে `<h6>`
- `<section>`
- `<header>`
- `<footer>`

## 1.2 Display: Inline

`display: inline` ব্যবহার করলে Element একই Line-এর মধ্যে প্রদর্শিত হয়।

Inline Element সাধারণত Content অনুযায়ী Width নেয়। এর ওপর সরাসরি `width` ও `height` কার্যকর হয় না।

**CSS Syntax:**

```css
span {
  display: inline;
}
```

**Common Inline Elements:**
- `<span>`
- `<a>`
- `<strong>`
- `<em>`

## 1.3 Display: Inline-block

`display: inline-block` ব্যবহার করলে Element একই Line-এ পাশাপাশি থাকতে পারে এবং এর ওপর Width ও Height নির্ধারণ করা যায়।

**CSS Syntax:**

```css
.box {
  display: inline-block;
  width: 150px;
  height: 100px;
}
```

## 1.4 Display: None

কোনো Element-কে সম্পূর্ণভাবে Layout থেকে সরিয়ে লুকানোর জন্য `display: none` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.hidden {
  display: none;
}
```

এক্ষেত্রে Element দৃশ্যমান হবে না এবং Layout-এ তার জন্য কোনো জায়গাও থাকবে না।

## 1.5 Display: Flex

একটি Element-কে Flex Container হিসেবে তৈরি করার জন্য `display: flex` ব্যবহার করা হয়।

এটি দিয়ে Child Elements-কে Row অথবা Column অনুযায়ী সাজানো যায়।

**CSS Syntax:**

```css
.container {
  display: flex;
}
```

Flexbox-এর বিস্তারিত আলোচনা এই Phase-এর 5 নম্বর Section-এ রয়েছে।

## 1.6 Display: Grid

একটি Element-কে Grid Container হিসেবে তৈরি করার জন্য `display: grid` ব্যবহার করা হয়।

এটি দিয়ে Row এবং Column ব্যবহার করে Two-dimensional Layout তৈরি করা যায়।

**CSS Syntax:**

```css
.container {
  display: grid;
}
```

CSS Grid-এর বিস্তারিত আলোচনা এই Phase-এর 6 নম্বর Section-এ রয়েছে।

## 1.7 Visibility: Hidden

কোনো Element-কে দৃশ্যমানতা থেকে লুকানোর জন্য `visibility: hidden` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.hidden {
  visibility: hidden;
}
```

এক্ষেত্রে Element দেখা যাবে না, কিন্তু Layout-এ তার জায়গা থেকে যাবে।

## 1.8 Opacity: 0

কোনো Element-কে সম্পূর্ণ Transparent বা অস্বচ্ছতাহীন করার জন্য `opacity: 0` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.transparent {
  opacity: 0;
}
```

এক্ষেত্রে Element দৃশ্যমান হবে না, কিন্তু এটি Layout-এ জায়গা ধরে রাখবে। Element-এর Interaction-ও সাধারণত চালু থাকে।

### Display, Visibility ও Opacity-এর পার্থক্য

| Property | Element দেখা যাবে? | Layout-এ জায়গা থাকবে? |
|---|---|---|
| `display: none` | না | না |
| `visibility: hidden` | না | হ্যাঁ |
| `opacity: 0` | না | হ্যাঁ |

**মনে রাখবে:**
- `block` নতুন Line থেকে শুরু হয়।
- `inline` একই Line-এ থাকে।
- `inline-block` একই Line-এ থাকে এবং Width ও Height গ্রহণ করে।
- `display: none` Element-কে Layout থেকে সরিয়ে দেয়।
- `visibility: hidden` Element লুকায়, কিন্তু তার জায়গা রেখে দেয়।
- `opacity: 0` Element-কে Transparent করে।

---

# 2. CSS Position (পজিশন প্রপার্টিজ)

CSS-এর `position` Property ব্যবহার করে কোনো HTML Element-এর অবস্থান বা Position নির্ধারণ করা যায়।

CSS-এ পাঁচটি গুরুত্বপূর্ণ Position Value রয়েছে:

1. `static`
2. `relative`
3. `absolute`
4. `fixed`
5. `sticky`

## 2.1 Position: Static

`position: static` হলো CSS-এর Default Position Value।

এক্ষেত্রে Element স্বাভাবিক Document Flow অনুযায়ী অবস্থান করে।

**CSS Syntax:**

```css
.box {
  position: static;
}
```

`top`, `right`, `bottom` এবং `left` Properties Static Element-এর অবস্থান পরিবর্তন করে না।

## 2.2 Position: Relative

`position: relative` ব্যবহার করলে Element তার স্বাভাবিক অবস্থান থেকে নির্দিষ্ট দিকে সরানো যায়।

**CSS Syntax:**

```css
.box {
  position: relative;
  top: 20px;
  left: 30px;
}
```

এখানে Element তার Original Position থেকে 20px নিচে এবং 30px ডান দিকে সরে যাবে।

**মনে রাখবে:** Relative Element-এর Original Layout Space বজায় থাকে।

## 2.3 Position: Absolute

`position: absolute` ব্যবহার করলে Element-কে Normal Document Flow থেকে সরিয়ে নির্দিষ্ট অবস্থানে রাখা যায়।

এটি সাধারণত তার নিকটতম Positioned Ancestor-এর সাপেক্ষে অবস্থান নির্ধারণ করে। কোনো Positioned Ancestor না থাকলে Initial Containing Block-এর সাপেক্ষে অবস্থান নির্ধারিত হয়।

**CSS Syntax:**

```css
.parent {
  position: relative;
  width: 300px;
  height: 200px;
}

.child {
  position: absolute;
  top: 10px;
  right: 10px;
}
```

এখানে Child Element-টি Parent Element-এর উপরের ডান দিকে অবস্থান করবে।

## 2.4 Position: Fixed

`position: fixed` ব্যবহার করলে Element-কে Viewport-এর সাপেক্ষে নির্দিষ্ট স্থানে রাখা যায়।

সাধারণত Page Scroll করলেও Element একই অবস্থানে থাকে।

**CSS Syntax:**

```css
.button {
  position: fixed;
  bottom: 20px;
  right: 20px;
}
```

এটি ব্যবহার করে Back to Top Button বা Floating Action Button তৈরি করা যায়।

## 2.5 Position: Sticky

`position: sticky` ব্যবহার করলে Element নির্দিষ্ট Scroll Position পর্যন্ত স্বাভাবিকভাবে অবস্থান করে এবং নির্দিষ্ট সীমায় পৌঁছালে Sticky হয়ে যায়।

**CSS Syntax:**

```css
.navbar {
  position: sticky;
  top: 0;
}
```

এটি সাধারণত Sticky Navbar তৈরিতে ব্যবহার করা হয়।

**মনে রাখবে:** Sticky Element-এর জন্য সাধারণত `top`, `right`, `bottom` অথবা `left`-এর অন্তত একটি Offset নির্ধারণ করতে হয়। এর কাজ Ancestor-এর Scroll Container এবং অন্যান্য Layout Condition-এর ওপরও নির্ভর করে।

## 2.6 Position Offset Properties

Element-এর অবস্থান নিয়ন্ত্রণ করার জন্য নিচের Properties ব্যবহার করা হয়:

- `top`
- `right`
- `bottom`
- `left`

**CSS Example:**

```css
.box {
  position: absolute;
  top: 20px;
  right: 30px;
  bottom: 10px;
  left: 15px;
}
```

## 2.7 Inset

`inset` হলো `top`, `right`, `bottom` এবং `left` Properties-এর Shorthand Property।

**CSS Syntax:**

```css
.box {
  position: absolute;
  inset: 10px 20px 30px 40px;
}
```

এখানে:
- প্রথম Value: Top
- দ্বিতীয় Value: Right
- তৃতীয় Value: Bottom
- চতুর্থ Value: Left

## 2.8 Z-index

একাধিক Positioned Element একে অপরের ওপর Overlap করলে কোন Element সামনে বা পেছনে থাকবে তা নিয়ন্ত্রণ করার জন্য `z-index` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
.box-one {
  position: relative;
  z-index: 2;
}

.box-two {
  position: relative;
  z-index: 1;
}
```

এখানে `.box-one` Element `.box-two`-এর সামনে প্রদর্শিত হবে।

**মনে রাখবে:** `z-index` শুধু Positioned Element-এর জন্যই নয়, Flex ও Grid Item এবং কিছু নির্দিষ্ট Stacking Context তৈরি করা Element-এর ক্ষেত্রেও কাজ করে।

## 2.9 Stacking Context

Stacking Context হলো Browser-এর তৈরি একটি Layering Environment, যার মধ্যে Element-গুলো কীভাবে একে অপরের ওপর প্রদর্শিত হবে তা নির্ধারিত হয়।

একটি Stacking Context-এর ভেতরের Element অন্য Stacking Context-এর Element-এর সঙ্গে সরাসরি `z-index` তুলনা করতে পারে না।

**Stacking Context তৈরি হওয়ার কিছু কারণ:**
- Root HTML Element।
- Positioned Element-এর `z-index` নির্দিষ্ট করা।
- `opacity`-এর Value 1-এর কম হওয়া।
- `transform` Property-এর Value `none` না হওয়া।
- `position: fixed` বা `position: sticky` ব্যবহার করা।
- Flex বা Grid Item-এর `z-index` নির্ধারণ করা।

**Example:**

```css
.parent {
  position: relative;
  z-index: 1;
  opacity: 0.99;
}

.child {
  position: absolute;
  z-index: 999;
}
```

এখানে Child-এর `z-index: 999` হলেও Parent-এর Stacking Context-এর বাইরে গিয়ে অন্য Element-এর ওপর প্রদর্শিত হওয়ার নিশ্চয়তা নেই।

---

# 3. CSS Overflow (ওভারফ্লো প্রপার্টিজ)

কোনো HTML Element-এর Content তার নির্ধারিত Width বা Height-এর বাইরে চলে গেলে কীভাবে প্রদর্শিত হবে তা নিয়ন্ত্রণ করার জন্য `overflow` Property ব্যবহার করা হয়।

## 3.1 Overflow

`overflow` Property দিয়ে Element-এর Content Container-এর বাইরে চলে গেলে কী হবে তা নির্ধারণ করা যায়।

**CSS Syntax:**

```css
.box {
  width: 200px;
  height: 100px;
  overflow: hidden;
}
```

## 3.2 Overflow-x

Horizontal বা অনুভূমিক দিকে Content Overflow নিয়ন্ত্রণ করার জন্য `overflow-x` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.box {
  overflow-x: auto;
}
```

## 3.3 Overflow-y

Vertical বা উল্লম্ব দিকে Content Overflow নিয়ন্ত্রণ করার জন্য `overflow-y` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.box {
  overflow-y: scroll;
}
```

## 3.4 Overflow: Hidden

Container-এর বাইরে চলে যাওয়া Content লুকানোর জন্য `overflow: hidden` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.box {
  overflow: hidden;
}
```

## 3.5 Overflow: Auto

Content প্রয়োজন অনুযায়ী Overflow করলে Scrollbar প্রদর্শন করার জন্য `overflow: auto` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.box {
  width: 250px;
  height: 150px;
  overflow: auto;
}
```

## 3.6 Overflow: Scroll

Content Overflow করুক বা না করুক, Scroll Container তৈরি করার জন্য `overflow: scroll` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.box {
  height: 150px;
  overflow: scroll;
}
```

## 3.7 Text Overflow

Container-এর মধ্যে Text জায়গা না পেলে কীভাবে প্রদর্শিত হবে তা নিয়ন্ত্রণ করার জন্য `text-overflow` Property ব্যবহার করা হয়।

**Common Values:**
- `clip`
- `ellipsis`

**CSS Syntax:**

```css
.title {
  width: 200px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
```

এখানে Text-এর জন্য জায়গা কম হলে শেষ অংশে তিনটি Dot (`...`) প্রদর্শিত হবে।

**মনে রাখবে:**
- `overflow: hidden` অতিরিক্ত Content লুকিয়ে রাখে।
- `overflow: auto` প্রয়োজন অনুযায়ী Scrollbar দেখায়।
- `overflow: scroll` Scrollbar ব্যবহারের সুযোগ দেয়।
- `text-overflow: ellipsis` দিয়ে Long Text সংক্ষেপে দেখানো যায়।

---

# 4. CSS Float & Clear

CSS-এর `float` Property ব্যবহার করে কোনো Element-কে বাম বা ডান দিকে সরিয়ে অন্য Content-কে তার পাশে Wrap করানো যায়।

এটি আগে Website Layout তৈরিতে বেশি ব্যবহৃত হতো। বর্তমানে মূলত Image ও Text Wrapping-এর ক্ষেত্রে ব্যবহার করা হয়।

## 4.1 Float: Left

কোনো Element-কে বাম দিকে Float করার জন্য `float: left` ব্যবহার করা হয়।

**CSS Syntax:**

```css
img {
  float: left;
  margin-right: 15px;
}
```

## 4.2 Float: Right

কোনো Element-কে ডান দিকে Float করার জন্য `float: right` ব্যবহার করা হয়।

**CSS Syntax:**

```css
img {
  float: right;
  margin-left: 15px;
}
```

## 4.3 Clear

Float করা Element-এর পাশে পরবর্তী Element যেন না আসে, তা নিশ্চিত করার জন্য `clear` Property ব্যবহার করা হয়।

**Common Values:**
- `left`
- `right`
- `both`
- `none`

**CSS Syntax:**

```css
.footer {
  clear: both;
}
```

## 4.4 Clearfix

Float করা Child Element-এর কারণে Parent Container-এর Height ঠিকভাবে বজায় রাখতে Clearfix Technique ব্যবহার করা হয়।

**CSS Syntax:**

```css
.clearfix::after {
  content: "";
  display: table;
  clear: both;
}
```

**HTML Example:**

```html
<div class="container clearfix">
  <img src="image.jpg" alt="Example">
  <p>Some content goes here.</p>
</div>
```

## 4.5 Modern Layout vs Float Layout

আগে Float ব্যবহার করে Website Layout তৈরি করা হতো। বর্তমানে Flexbox এবং CSS Grid ব্যবহার করে Layout তৈরি করা অনেক সহজ ও কার্যকর।

| Float Layout | Modern Layout |
|---|---|
| `float` ব্যবহার করে | Flexbox ও Grid ব্যবহার করে |
| মূলত Content Wrapping-এর জন্য তৈরি | Layout তৈরির জন্য বিশেষভাবে তৈরি |
| Complex Layout তৈরি কঠিন হতে পারে | Complex Layout সহজে তৈরি করা যায় |
| Clearfix প্রয়োজন হতে পারে | সাধারণত Clearfix প্রয়োজন হয় না |

**মনে রাখবে:** Float এখনো গুরুত্বপূর্ণ, তবে নতুন Website Layout তৈরির জন্য Flexbox ও Grid শেখা বেশি জরুরি।

---

# 5. CSS Flexbox (ফ্লেক্সবক্স)

CSS Flexbox হলো একটি One-dimensional Layout System। এটি দিয়ে Row অথবা Column বরাবর HTML Element সাজানো যায়।

Flexbox মূলত দুইটি অংশ নিয়ে কাজ করে:

1. Flex Container
2. Flex Items

## 5.1 Flex Container

যে Parent Element-এর মধ্যে `display: flex` ব্যবহার করা হয়, তাকে Flex Container বলা হয়।

**CSS Syntax:**

```css
.container {
  display: flex;
}
```

এর ভেতরের Direct Child Element-গুলো Flex Items হিসেবে কাজ করে।

## 5.2 Display: Flex

কোনো Parent Element-কে Flex Container হিসেবে তৈরি করতে `display: flex` ব্যবহার করা হয়।

**Example:**

```css
.container {
  display: flex;
}
```

## 5.3 Flex Direction

Flex Items কোন Direction-এ সাজানো হবে তা নির্ধারণ করার জন্য `flex-direction` Property ব্যবহার করা হয়।

**Common Values:**

| Value | কাজ |
|---|---|
| `row` | বাম থেকে ডানে সাজায় |
| `row-reverse` | ডান থেকে বামে সাজায় |
| `column` | উপর থেকে নিচে সাজায় |
| `column-reverse` | নিচ থেকে উপরে সাজায় |

**CSS Syntax:**

```css
.container {
  display: flex;
  flex-direction: row;
}
```

## 5.4 Flex Wrap

Flex Container-এর মধ্যে পর্যাপ্ত জায়গা না থাকলে Flex Items পরবর্তী Line-এ যাবে কি না তা নির্ধারণ করার জন্য `flex-wrap` ব্যবহার করা হয়।

**Common Values:**
- `nowrap`
- `wrap`
- `wrap-reverse`

**CSS Syntax:**

```css
.container {
  display: flex;
  flex-wrap: wrap;
}
```

## 5.5 Flex Flow

`flex-flow` হলো `flex-direction` এবং `flex-wrap` Properties-এর Shorthand Property।

**CSS Syntax:**

```css
.container {
  display: flex;
  flex-flow: row wrap;
}
```

## 5.6 Justify Content

Flex Container-এর Main Axis বরাবর Flex Items কীভাবে সাজানো হবে তা নিয়ন্ত্রণ করার জন্য `justify-content` ব্যবহার করা হয়।

**Common Values:**
- `flex-start`
- `flex-end`
- `center`
- `space-between`
- `space-around`
- `space-evenly`

**CSS Syntax:**

```css
.container {
  display: flex;
  justify-content: space-between;
}
```

## 5.7 Align Items

Flex Container-এর Cross Axis বরাবর Flex Items-এর Alignment নিয়ন্ত্রণ করার জন্য `align-items` ব্যবহার করা হয়।

**Common Values:**
- `stretch`
- `flex-start`
- `flex-end`
- `center`
- `baseline`

**CSS Syntax:**

```css
.container {
  display: flex;
  align-items: center;
}
```

## 5.8 Align Content

একাধিক Flex Line থাকলে Cross Axis বরাবর Line-গুলোর মধ্যবর্তী Spacing ও Alignment নিয়ন্ত্রণ করার জন্য `align-content` ব্যবহার করা হয়।

**Common Values:**
- `stretch`
- `flex-start`
- `flex-end`
- `center`
- `space-between`
- `space-around`
- `space-evenly`

**CSS Syntax:**

```css
.container {
  display: flex;
  flex-wrap: wrap;
  align-content: center;
}
```

**মনে রাখবে:** `align-content` কার্যকর হওয়ার জন্য সাধারণত একাধিক Flex Line থাকা প্রয়োজন।

## 5.9 Gap

Flex Items-এর মধ্যে দূরত্ব তৈরি করার জন্য `gap` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
.container {
  display: flex;
  gap: 20px;
}
```

## 5.10 Row Gap

Flex Items-এর Row-গুলোর মধ্যে Vertical Gap তৈরি করার জন্য `row-gap` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.container {
  display: flex;
  flex-wrap: wrap;
  row-gap: 20px;
}
```

## 5.11 Column Gap

Flex Items-এর Column-গুলোর মধ্যে Horizontal Gap তৈরি করার জন্য `column-gap` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.container {
  display: flex;
  column-gap: 20px;
}
```

---

## 5.12 Flex Items

Flex Container-এর Direct Child Element-গুলোকে Flex Items বলা হয়।

Flex Items-এর Size, Alignment এবং Order নিয়ন্ত্রণ করার জন্য নিচের Properties ব্যবহার করা হয়।

### Flex Grow

কোনো Flex Item অতিরিক্ত Available Space-এর কতটুকু গ্রহণ করবে তা নির্ধারণ করার জন্য `flex-grow` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.item {
  flex-grow: 1;
}
```

### Flex Shrink

Container-এর জায়গা কম হলে কোনো Flex Item কতটুকু Shrink করবে তা নির্ধারণ করার জন্য `flex-shrink` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.item {
  flex-shrink: 1;
}
```

### Flex Basis

Flex Item-এর Initial Main Size নির্ধারণ করার জন্য `flex-basis` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.item {
  flex-basis: 200px;
}
```

### Flex

`flex` হলো `flex-grow`, `flex-shrink` এবং `flex-basis` Properties-এর Shorthand Property।

**CSS Syntax:**

```css
.item {
  flex: 1 1 200px;
}
```

### Align Self

কোনো নির্দিষ্ট Flex Item-এর Cross Axis Alignment আলাদাভাবে নিয়ন্ত্রণ করার জন্য `align-self` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.item {
  align-self: center;
}
```

### Order

Flex Items-এর Visual Display Order পরিবর্তন করার জন্য `order` Property ব্যবহার করা হয়।

**CSS Syntax:**

```css
.item-one {
  order: 2;
}

.item-two {
  order: 1;
}
```

**মনে রাখবে:**
- `flex-grow` Item-কে Available Space নিতে সাহায্য করে।
- `flex-shrink` Item-এর Size কমাতে সাহায্য করে।
- `flex-basis` Initial Size নির্ধারণ করে।
- `align-self` নির্দিষ্ট Item-এর Alignment পরিবর্তন করে।
- `order` Visual Order পরিবর্তন করে, HTML-এর Source Order নয়।

---

# 6. CSS Grid (সিএসএস গ্রিড)

CSS Grid হলো একটি Two-dimensional Layout System। এটি দিয়ে একই সঙ্গে Row এবং Column ব্যবহার করে Complex Website Layout তৈরি করা যায়।

CSS Grid-এর দুটি প্রধান অংশ:

1. Grid Container
2. Grid Items

## 6.1 Grid Container

যে Parent Element-এর মধ্যে `display: grid` ব্যবহার করা হয়, তাকে Grid Container বলা হয়।

**CSS Syntax:**

```css
.container {
  display: grid;
}
```

এর ভেতরের Direct Child Element-গুলো Grid Items হিসেবে কাজ করে।

## 6.2 Display: Grid

কোনো Parent Element-কে Grid Container হিসেবে তৈরি করার জন্য `display: grid` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.container {
  display: grid;
}
```

## 6.3 Grid Template Columns

Grid Container-এর Column-এর সংখ্যা এবং Size নির্ধারণ করার জন্য `grid-template-columns` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.container {
  display: grid;
  grid-template-columns: 200px 200px 200px;
}
```

এখানে তিনটি Column তৈরি হবে এবং প্রতিটির Width হবে 200px।

## 6.4 Grid Template Rows

Grid Container-এর Row-এর সংখ্যা এবং Size নির্ধারণ করার জন্য `grid-template-rows` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.container {
  display: grid;
  grid-template-rows: 100px 200px;
}
```

## 6.5 Grid Template Areas

Grid Layout-কে বিভিন্ন Named Area-তে ভাগ করার জন্য `grid-template-areas` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.container {
  display: grid;
  grid-template-columns: 200px 1fr;
  grid-template-rows: 80px 1fr 60px;

  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
}

.header {
  grid-area: header;
}

.sidebar {
  grid-area: sidebar;
}

.main {
  grid-area: main;
}

.footer {
  grid-area: footer;
}
```

এখানে একটি সাধারণ Website Layout তৈরি করা হয়েছে।

## 6.6 Grid Auto Columns

Implicit Grid-এ স্বয়ংক্রিয়ভাবে তৈরি হওয়া Column-এর Size নির্ধারণ করার জন্য `grid-auto-columns` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.container {
  display: grid;
  grid-auto-columns: 150px;
}
```

## 6.7 Grid Auto Rows

Implicit Grid-এ স্বয়ংক্রিয়ভাবে তৈরি হওয়া Row-এর Size নির্ধারণ করার জন্য `grid-auto-rows` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.container {
  display: grid;
  grid-auto-rows: 100px;
}
```

## 6.8 Grid Auto Flow

Grid Items কোন Direction-এ স্বয়ংক্রিয়ভাবে বসবে তা নির্ধারণ করার জন্য `grid-auto-flow` ব্যবহার করা হয়।

**Common Values:**
- `row`
- `column`
- `dense`
- `row dense`
- `column dense`

**CSS Syntax:**

```css
.container {
  display: grid;
  grid-auto-flow: row;
}
```

## 6.9 Grid Gap

Grid Rows এবং Columns-এর মধ্যে Spacing তৈরি করার জন্য `gap` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.container {
  display: grid;
  gap: 20px;
}
```

---

## 6.10 Grid Items

Grid Container-এর Direct Child Element-গুলোকে Grid Items বলা হয়।

Grid Items-এর অবস্থান এবং Size নিয়ন্ত্রণ করার জন্য নিচের Properties ব্যবহার করা হয়।

### Grid Column

কোনো Grid Item কোন Column থেকে শুরু হবে এবং কোথায় শেষ হবে তা নির্ধারণ করার জন্য `grid-column` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.item {
  grid-column: 1 / 3;
}
```

এখানে Item-টি প্রথম Column Line থেকে তৃতীয় Column Line পর্যন্ত বিস্তৃত হবে।

### Grid Row

কোনো Grid Item কোন Row থেকে শুরু হবে এবং কোথায় শেষ হবে তা নির্ধারণ করার জন্য `grid-row` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.item {
  grid-row: 1 / 3;
}
```

### Grid Area

Grid Item-কে নির্দিষ্ট Grid Area-তে অবস্থান করানোর জন্য `grid-area` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.header {
  grid-area: header;
}
```

### Justify Items

Grid Container-এর প্রতিটি Grid Item-কে Horizontal বা Inline Axis বরাবর কীভাবে Align করা হবে তা নির্ধারণ করার জন্য `justify-items` ব্যবহার করা হয়।

**Common Values:**
- `start`
- `end`
- `center`
- `stretch`

**CSS Syntax:**

```css
.container {
  display: grid;
  justify-items: center;
}
```

### Align Items

Grid Container-এর প্রতিটি Grid Item-কে Vertical বা Block Axis বরাবর কীভাবে Align করা হবে তা নির্ধারণ করার জন্য `align-items` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.container {
  display: grid;
  align-items: center;
}
```

### Place Items

`place-items` হলো `align-items` এবং `justify-items` Properties-এর Shorthand Property।

**CSS Syntax:**

```css
.container {
  display: grid;
  place-items: center;
}
```

### Justify Content

Grid-এর সম্পূর্ণ Content-কে Inline Axis বরাবর কীভাবে Align করা হবে তা নিয়ন্ত্রণ করার জন্য `justify-content` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.container {
  display: grid;
  justify-content: center;
}
```

### Align Content

Grid-এর সম্পূর্ণ Content-কে Block Axis বরাবর কীভাবে Align করা হবে তা নিয়ন্ত্রণ করার জন্য `align-content` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.container {
  display: grid;
  align-content: center;
}
```

**মনে রাখবে:**
- `justify-items` ও `align-items` প্রতিটি Grid Item-এর Alignment নিয়ন্ত্রণ করে।
- `justify-content` ও `align-content` পুরো Grid Content-এর Alignment নিয়ন্ত্রণ করে।
- `place-items` হলো `align-items` এবং `justify-items`-এর Shorthand।

---

## 6.11 Advanced CSS Grid

CSS Grid-এর কিছু Advanced Features ব্যবহার করে Responsive এবং Complex Layout আরও সহজে তৈরি করা যায়।

### Repeat()

একই ধরনের Column বা Row বারবার তৈরি করার জন্য `repeat()` Function ব্যবহার করা হয়।

**CSS Syntax:**

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}
```

এখানে সমান Width-এর তিনটি Column তৈরি হবে।

### Minmax()

কোনো Grid Track-এর সর্বনিম্ন এবং সর্বোচ্চ Size নির্ধারণ করার জন্য `minmax()` Function ব্যবহার করা হয়।

**CSS Syntax:**

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, minmax(200px, 1fr));
}
```

### FR Unit

`fr` হলো Fractional Unit। এটি Grid Container-এর Available Space-কে নির্দিষ্ট অনুপাতে ভাগ করে।

**CSS Syntax:**

```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
}
```

এখানে Column-গুলোর অনুপাত হবে 1:2:1।

### Auto-fit

`auto-fit` ব্যবহার করে Available Space অনুযায়ী যতগুলো Column সম্ভব তৈরি করা যায়। প্রয়োজন অনুযায়ী Grid Track-গুলো প্রসারিতও হতে পারে।

**CSS Syntax:**

```css
.container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
}
```

### Auto-fill

`auto-fill` ব্যবহার করে Available Space অনুযায়ী যতগুলো Column সম্ভব তৈরি করা হয়। খালি Track-এর জায়গাও সংরক্ষিত থাকতে পারে।

**CSS Syntax:**

```css
.container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 20px;
}
```

**Auto-fit ও Auto-fill-এর পার্থক্য:**

| Auto-fit | Auto-fill |
|---|---|
| খালি Track-গুলো Collapse করতে পারে | খালি Track-এর জায়গা ধরে রাখতে পারে |
| বিদ্যমান Item-গুলো Available Space ব্যবহার করে বড় হতে পারে | খালি Track থাকলে Item-এর জন্য জায়গা সংরক্ষিত থাকে |

### Implicit Grid

Grid Container-এ নির্ধারিত Row বা Column-এর বাইরে অতিরিক্ত Grid Item তৈরি হলে Browser স্বয়ংক্রিয়ভাবে যে নতুন Track তৈরি করে, তাকে Implicit Grid বলা হয়।

**CSS Syntax:**

```css
.container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-auto-rows: 100px;
}
```

### Explicit Grid

`grid-template-columns`, `grid-template-rows` অথবা `grid-template-areas` ব্যবহার করে আগে থেকে নির্ধারণ করা Grid Track-গুলোকে Explicit Grid বলা হয়।

**CSS Syntax:**

```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 100px 200px;
}
```

### Nested Grid

একটি Grid Item-এর ভেতরে আবার `display: grid` ব্যবহার করে আরেকটি Grid Layout তৈরি করাকে Nested Grid বলা হয়।

**CSS Syntax:**

```css
.parent {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}

.child {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
}
```

**মনে রাখবে:**
- `repeat()` দিয়ে একই ধরনের Track বারবার তৈরি করা যায়।
- `minmax()` দিয়ে Track-এর Minimum ও Maximum Size নির্ধারণ করা যায়।
- `fr` Available Space ভাগ করে।
- `auto-fit` ও `auto-fill` Responsive Grid তৈরিতে কার্যকর।
- Explicit Grid আগে থেকে নির্ধারিত থাকে।
- Implicit Grid প্রয়োজন অনুযায়ী স্বয়ংক্রিয়ভাবে তৈরি হয়।

---

# 7. Flexbox vs CSS Grid

Flexbox এবং CSS Grid উভয়ই Modern CSS Layout System। তবে এদের ব্যবহারের ক্ষেত্রে কিছু পার্থক্য রয়েছে।

| Flexbox | CSS Grid |
|---|---|
| One-dimensional Layout System | Two-dimensional Layout System |
| Row অথবা Column বরাবর কাজ করে | Row ও Column একসঙ্গে নিয়ন্ত্রণ করে |
| Navbar ও Button Group-এর জন্য কার্যকর | Dashboard ও Complex Layout-এর জন্য কার্যকর |
| Content-এর ভিত্তিতে Layout সাজাতে সুবিধাজনক | নির্দিষ্ট Grid Structure তৈরিতে সুবিধাজনক |
| `display: flex` ব্যবহার করা হয় | `display: grid` ব্যবহার করা হয় |

**কখন কোনটি ব্যবহার করবে?**

- Navbar, Button Group, Card-এর ভিতরের Content Alignment-এর জন্য Flexbox ব্যবহার করতে পারো।
- Dashboard, Image Gallery, Page Structure এবং Complex Layout-এর জন্য Grid ব্যবহার করতে পারো।
- প্রয়োজনে একই Website-এ Flexbox এবং Grid একসঙ্গে ব্যবহার করা যায়।

---

# 8. Practical Projects (প্র্যাকটিক্যাল প্রজেক্ট)

এই Phase-এ শেখা CSS Properties ব্যবহার করে নিচের ছয়টি Project তৈরি করবে।

## Project 01 — Responsive Navbar

**Project Goal:** Flexbox ব্যবহার করে একটি Responsive Navigation Bar তৈরি করা।

**Requirements:**
- Website Logo যুক্ত করতে হবে।
- Navigation Links তৈরি করতে হবে।
- Login অথবা CTA Button যুক্ত করতে হবে।
- Flexbox দিয়ে Items Align করতে হবে।
- Sticky Navbar তৈরি করতে হবে।
- Mobile Screen-এর জন্য Navigation Responsive করতে হবে।

**Practice Topics:**
- Display
- Flexbox
- Position
- Gap
- Z-index

## Project 02 — Image Gallery

**Project Goal:** CSS Grid ব্যবহার করে একটি Responsive Image Gallery তৈরি করা।

**Requirements:**
- একাধিক Image যুক্ত করতে হবে।
- Grid Layout তৈরি করতে হবে।
- Image-এর Size ও Gap নিয়ন্ত্রণ করতে হবে।
- বিভিন্ন Screen Size অনুযায়ী Column পরিবর্তন করতে হবে।
- কিছু Image-কে একাধিক Grid Cell জুড়ে প্রদর্শন করতে হবে।

**Practice Topics:**
- CSS Grid
- Grid Template Columns
- Grid Column
- Grid Row
- Repeat()
- Minmax()
- Auto-fit

## Project 03 — Dashboard Layout

**Project Goal:** একটি Professional Dashboard Layout তৈরি করা।

**Requirements:**
- Sidebar তৈরি করতে হবে।
- Top Navigation Bar তৈরি করতে হবে।
- Main Content Section তৈরি করতে হবে।
- Statistics Cards যুক্ত করতে হবে।
- Content Area-তে Grid ব্যবহার করতে হবে।
- Sidebar-এর Position নিয়ন্ত্রণ করতে হবে।
- Mobile Screen-এর জন্য Layout Responsive করতে হবে।

**Practice Topics:**
- CSS Grid
- Flexbox
- Position
- Z-index
- Overflow
- Gap

## Project 04 — Blog Layout

**Project Goal:** একটি Professional Blog Website Layout তৈরি করা।

**Requirements:**
- Header ও Navigation তৈরি করতে হবে।
- Main Blog Content Section তৈরি করতে হবে।
- Sidebar যুক্ত করতে হবে।
- Blog Cards তৈরি করতে হবে।
- Footer তৈরি করতে হবে।
- Grid অথবা Flexbox ব্যবহার করতে হবে।
- Long Text ও Content Overflow নিয়ন্ত্রণ করতে হবে।

**Practice Topics:**
- CSS Grid
- Flexbox
- Display
- Position
- Overflow
- Gap

## Project 05 — Product Grid

**Project Goal:** একটি Responsive E-commerce Product Grid তৈরি করা।

**Requirements:**
- একাধিক Product Card তৈরি করতে হবে।
- Product Image যুক্ত করতে হবে।
- Product Name ও Price দেখাতে হবে।
- Add to Cart Button যুক্ত করতে হবে।
- Responsive Grid ব্যবহার করতে হবে।
- বিভিন্ন Screen Size অনুযায়ী Column পরিবর্তন করতে হবে।

**Practice Topics:**
- CSS Grid
- Repeat()
- Minmax()
- Auto-fit
- Auto-fill
- Flexbox
- Gap

## Project 06 — Two-column Website Layout

**Project Goal:** একটি Two-column Website Layout তৈরি করা।

**Requirements:**
- একটি Header তৈরি করতে হবে।
- Main Content এবং Sidebar তৈরি করতে হবে।
- দুইটি Column-এর Width নিয়ন্ত্রণ করতে হবে।
- Content-এর মধ্যে Gap রাখতে হবে।
- Footer যুক্ত করতে হবে।
- Mobile Screen-এ Column-গুলো Stack করতে হবে।

**Practice Topics:**
- CSS Grid
- Flexbox
- Grid Template Columns
- Responsive Layout
- Gap
- Position

---

# 9. Weekly Practice Routine (সাপ্তাহিক অনুশীলন)

| Day | Topics | Practice |
|---|---|---|
| Day 01 | CSS Display | Block, Inline, Inline-block, None |
| Day 02 | CSS Position | Static, Relative, Absolute, Fixed, Sticky |
| Day 03 | CSS Overflow | Overflow, Text Overflow, Float & Clear |
| Day 04 | Flexbox Basics | Direction, Wrap, Justify, Align |
| Day 05 | Flexbox Advanced | Grow, Shrink, Basis, Order |
| Day 06 | CSS Grid | Grid Container, Items, Grid Properties |
| Day 07 | Advanced Grid & Revision | Responsive Grid ও Project Practice |

**Week 04:** এই সপ্তাহে ছয়টি Practical Project সম্পন্ন করবে। প্রতিটি Project Responsive করার চেষ্টা করবে।

---

# 10. Learning Checklist (শেখার অগ্রগতি)

### CSS Display
- [ ] `display: block`
- [ ] `display: inline`
- [ ] `display: inline-block`
- [ ] `display: none`
- [ ] `display: flex`
- [ ] `display: grid`
- [ ] `visibility: hidden`
- [ ] `opacity: 0`

### CSS Position
- [ ] `position: static`
- [ ] `position: relative`
- [ ] `position: absolute`
- [ ] `position: fixed`
- [ ] `position: sticky`
- [ ] `top`, `right`, `bottom`, `left`
- [ ] `inset`
- [ ] `z-index`
- [ ] Stacking Context

### CSS Overflow
- [ ] `overflow`
- [ ] `overflow-x`
- [ ] `overflow-y`
- [ ] `overflow: hidden`
- [ ] `overflow: auto`
- [ ] `overflow: scroll`
- [ ] `text-overflow`

### CSS Float & Clear
- [ ] `float: left`
- [ ] `float: right`
- [ ] `clear`
- [ ] Clearfix
- [ ] Modern Layout vs Float Layout

### CSS Flexbox
- [ ] `display: flex`
- [ ] `flex-direction`
- [ ] `flex-wrap`
- [ ] `flex-flow`
- [ ] `justify-content`
- [ ] `align-items`
- [ ] `align-content`
- [ ] `gap`
- [ ] `row-gap`
- [ ] `column-gap`
- [ ] `flex-grow`
- [ ] `flex-shrink`
- [ ] `flex-basis`
- [ ] `flex`
- [ ] `align-self`
- [ ] `order`

### CSS Grid
- [ ] `display: grid`
- [ ] `grid-template-columns`
- [ ] `grid-template-rows`
- [ ] `grid-template-areas`
- [ ] `grid-auto-columns`
- [ ] `grid-auto-rows`
- [ ] `grid-auto-flow`
- [ ] `gap`
- [ ] `grid-column`
- [ ] `grid-row`
- [ ] `grid-area`
- [ ] `justify-items`
- [ ] `align-items`
- [ ] `place-items`
- [ ] `justify-content`
- [ ] `align-content`

### Advanced CSS Grid
- [ ] `repeat()`
- [ ] `minmax()`
- [ ] `fr` Unit
- [ ] `auto-fit`
- [ ] `auto-fill`
- [ ] Implicit Grid
- [ ] Explicit Grid
- [ ] Nested Grid

### Practical Projects
- [ ] Responsive Navbar
- [ ] Image Gallery
- [ ] Dashboard Layout
- [ ] Blog Layout
- [ ] Product Grid
- [ ] Two-column Website Layout

---

# 11. Learning Resources (শেখার রিসোর্স)

| Resource | Link |
|---|---|
| MDN CSS Display | https://developer.mozilla.org/en-US/docs/Web/CSS/display |
| MDN CSS Position | https://developer.mozilla.org/en-US/docs/Web/CSS/position |
| MDN CSS Overflow | https://developer.mozilla.org/en-US/docs/Web/CSS/overflow |
| MDN CSS Flexbox | https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout |
| MDN CSS Grid | https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout |
| Flexbox Froggy | https://flexboxfroggy.com/ |
| Grid Garden | https://cssgridgarden.com/ |
| CSS Tricks — A Complete Guide to Flexbox | https://css-tricks.com/snippets/css/a-guide-to-flexbox/ |
| CSS Tricks — A Complete Guide to Grid | https://css-tricks.com/snippets/css/complete-guide-grid/ |

---

# 12. Final Tips (গুরুত্বপূর্ণ পরামর্শ)

1. Display Properties-এর মধ্যে পার্থক্য ভালোভাবে বুঝবে।
2. Relative এবং Absolute Positioning নিজে Code করে Practice করবে।
3. Z-index ও Stacking Context ভালোভাবে বুঝবে।
4. Float-এর তুলনায় Flexbox ও Grid-কে বেশি গুরুত্ব দেবে।
5. Flexbox-এর Main Axis এবং Cross Axis সম্পর্কে পরিষ্কার ধারণা তৈরি করবে।
6. Grid-এর Row, Column এবং Grid Line ভালোভাবে বুঝবে।
7. শুধু Code দেখে শেখার পরিবর্তে প্রতিটি Layout নিজে তৈরি করবে।
8. প্রতিটি Project Desktop, Tablet এবং Mobile Screen-এ পরীক্ষা করবে।

---

## 🎓 Phase 03 Completion Goal

এই Phase সম্পন্ন করার পর তুমি CSS Display, Position, Flexbox এবং Grid ব্যবহার করে Professional Website Layout তৈরি করতে পারবে।

**Learning Strategy:**

- 30% — Learn & Understand
- 70% — Coding & Practical Projects

**Remember:**

> Don't just memorize CSS properties. Learn how to control elements, arrange content, and build professional website layouts.

**Happy Coding! 🚀**
