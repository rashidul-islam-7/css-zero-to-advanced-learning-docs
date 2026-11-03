# 📘 Phase 05 — Advanced CSS Selectors & Pseudo Classes

**Level:** Intermediate
**Duration:** Week 06
**Phase:** 05 — Advanced CSS Selectors & Pseudo Classes

## 🎯 Learning Goals (শেখার লক্ষ্য)

এই Phase-এ আমরা শিখব কীভাবে CSS Selectors ব্যবহার করে HTML Element-এর নির্দিষ্ট State, Relationship, Attribute এবং Structure অনুযায়ী Style Apply করতে হয়।

এই Phase শেষ করার পর:

- বিভিন্ন Pseudo Classes ব্যবহার করে Element-এর Interaction State অনুযায়ী Style Apply করতে পারবে।
- Structural Pseudo Classes ব্যবহার করে নির্দিষ্ট Position-এর Element Select করতে পারবে।
- Form Validation এবং Input State অনুযায়ী Design তৈরি করতে পারবে।
- `:not()`, `:is()`, `:where()` এবং `:has()` ব্যবহার করে Advanced Selection করতে পারবে।
- Pseudo Elements ব্যবহার করে HTML Content-এর নির্দিষ্ট অংশ Style করতে পারবে।
- Attribute Selectors ব্যবহার করে Attribute ও Attribute Value অনুযায়ী Element Select করতে পারবে।
- JavaScript ছাড়াই CSS দিয়ে Interactive UI-এর বিভিন্ন অংশ তৈরি করতে পারবে।
- Professional Navigation Menu, Custom Form এবং Advanced Card UI তৈরি করতে পারবে।

---

# 1. CSS Pseudo Classes (সিএসএস সিউডো ক্লাস)

CSS Pseudo Class হলো এমন একটি Selector, যা কোনো HTML Element-এর নির্দিষ্ট State, Condition অথবা Position অনুযায়ী সেই Element-কে Select করে Style Apply করতে সাহায্য করে।

সাধারণত Pseudo Class-এর আগে একটি Colon (`:`) ব্যবহার করা হয়।

**CSS Syntax:**

```css
selector:pseudo-class {
  property: value;
}
```

**Example:**

```css
button:hover {
  background-color: blue;
}
```

এখানে `button:hover` বলতে বোঝায়, যখন কোনো Button-এর ওপর Mouse Hover করা হবে, তখন Button-এর Background Color Blue হবে।

## 1.1 User Interaction Pseudo Classes

User কোনো Element-এর সঙ্গে কীভাবে Interaction করছে, তার ওপর ভিত্তি করে Style Apply করার জন্য User Interaction Pseudo Classes ব্যবহার করা হয়।

### 1.1.:hover

কোনো Element-এর ওপর Mouse Pointer নিয়ে গেলে সেই Element Select করার জন্য `:hover` ব্যবহার করা হয়।

**CSS Syntax:**

```css
button:hover {
  background-color: blue;
  color: white;
}
```

**HTML Example:**

```html
<button>Click Me</button>
```

এখানে Button-এর ওপর Mouse Pointer নিয়ে গেলে Background Blue এবং Text White হবে।

**Real-life Use Case:**

- Navigation Menu Hover Effect।
- Button Hover Effect।
- Card Hover Animation।
- Image Hover Effect।

**মনে রাখবে:** Touchscreen Device-এ Hover সবসময় Mouse-এর মতো কাজ করে না।

### 1.1.2:active

কোনো Element-এ Mouse Button চেপে ধরে রাখার সময় সেই Element-এর Style পরিবর্তন করার জন্য `:active` ব্যবহার করা হয়।

**CSS Syntax:**

```css
button:active {
  background-color: red;
  transform: scale(0.95);
}
```

এখানে Button Press করে ধরে রাখলে Background Red হবে এবং Button সামান্য ছোট হবে।

**Real-life Use Case:**

- Clickable Button।
- Navigation Link।
- Interactive Card।

**&#x20;vs&#x20;**

|                                            |                                     |
| ------------------------------------------ | ----------------------------------- |
| Mouse Pointer Element-এর ওপর থাকলে কাজ করে | Element Press করার সময় কাজ করে      |
| Hover Effect তৈরি করে                      | Press Effect তৈরি করে               |
| Pointer সরালে Hover State শেষ হয়           | Press ছেড়ে দিলে Active State শেষ হয় |

### 1.1.3:focus

কোনো Element Keyboard অথবা Mouse দিয়ে Focus অবস্থায় থাকলে সেটিকে Select করার জন্য `:focus` ব্যবহার করা হয়।

বিশেষ করে Input, Textarea এবং Button-এর ক্ষেত্রে এটি গুরুত্বপূর্ণ।

**CSS Syntax:**

```css
input:focus {
  border: 2px solid blue;
  outline: none;
  background-color: #f0f9ff;
}
```

**HTML Example:**

```html
<input type="text" placeholder="Enter your name">
```

এখানে Input-এ Click করলে অথবা Keyboard দিয়ে Focus করলে Border Blue হবে।

**Real-life Use Case:**

- Form Input Highlight।
- Search Box Design।
- Login Form।

### 1.1.4:focus-visible

কোনো Element Keyboard Navigation-এর মাধ্যমে Focus হলে সাধারণত সেই Element-এ Focus Style Apply করার জন্য `:focus-visible` ব্যবহার করা হয়।

**CSS Syntax:**

```css
button:focus-visible {
  outline: 3px solid orange;
  outline-offset: 4px;
}
```

এখানে Keyboard দিয়ে Tab Press করে Button-এ গেলে Orange Outline দেখা যাবে।

**&#x20;vs&#x20;**

|                                         |                                                              |
| --------------------------------------- | ------------------------------------------------------------ |
| Element Focus হলেই Style Apply হয়       | Browser-এর Focus Visibility Heuristic অনুযায়ী Style Apply হয় |
| Mouse ও Keyboard উভয় ক্ষেত্রেই হতে পারে | সাধারণত Keyboard Navigation-এ দেখা যায়                       |
| সব Focus State Style করে                | প্রয়োজনীয় Focus Indicator দেখাতে সাহায্য করে                 |

**মনে রাখবে:** Accessibility-এর জন্য `:focus-visible` খুবই গুরুত্বপূর্ণ।

### 1.1.5:focus-within

কোনো Parent Element অথবা তার ভেতরের যেকোনো Child Element Focus অবস্থায় থাকলে Parent Element Select করার জন্য `:focus-within` ব্যবহার করা হয়।

**CSS Syntax:**

```css
.form-group:focus-within {
  border: 2px solid blue;
  background-color: #eff6ff;
}
```

**HTML Example:**

```html
<div class="form-group">
  <label for="email">Email</label>
  <input type="email" id="email">
</div>
```

এখানে Input Focus করলে তার Parent `.form-group`-এর Background এবং Border পরিবর্তন হবে।

**Real-life Use Case:**

- Form Group Highlight।
- Search Container Design।
- Login Form Section।

### 1.1.6:link

যেসব Link এখনো Visited হয়নি, সেগুলো Select করার জন্য `:link` ব্যবহার করা হয়।

**CSS Syntax:**

```css
a:link {
  color: blue;
  text-decoration: none;
}
```

### 1.1.7:visited

User আগে Visit করেছে এমন Link Select করার জন্য `:visited` ব্যবহার করা হয়।

**CSS Syntax:**

```css
a:visited {
  color: purple;
}
```

এখানে আগে Visit করা Link Purple Color-এ দেখা যাবে।

**মনে রাখবে:** Browser Privacy-এর কারণে `:visited` দিয়ে সীমিত কিছু CSS Property-ই পরিবর্তন করা যায়।

### 1.1.8:target

URL-এর Hash Fragment-এর সঙ্গে যে Element-এর ID Match করবে, সেটিকে Select করার জন্য `:target` ব্যবহার করা হয়।

**HTML Example:**

```html
<a href="#about">About Us</a>

<section id="about">
  <h2>About Section</h2>
  <p>Welcome to our website.</p>
</section>
```

**CSS Example:**

```css
section:target {
  background-color: lightblue;
  border: 2px solid blue;
}
```

এখানে About Link-এ Click করলে URL-এ `#about` যুক্ত হবে এবং About Section Highlight হবে।

**Real-life Use Case:**

- Table of Contents।
- Documentation Navigation।
- FAQ Section Navigation।
- Page Section Highlight।

---

## 1.2 Structural Pseudo Classes

HTML Document-এর Structure এবং Element-এর Position অনুযায়ী নির্দিষ্ট Element Select করার জন্য Structural Pseudo Classes ব্যবহার করা হয়।

### 1.2.1:first-child

কোনো Parent Element-এর প্রথম Child Element Select করার জন্য `:first-child` ব্যবহার করা হয়।

**CSS Syntax:**

```css
li:first-child {
  color: red;
}
```

**HTML Example:**

```html
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ul>
```

এখানে প্রথম `li` অর্থাৎ HTML Red হবে।

### 1.2.2:last-child

কোনো Parent Element-এর শেষ Child Element Select করার জন্য `:last-child` ব্যবহার করা হয়।

**CSS Syntax:**

```css
li:last-child {
  color: green;
}
```

এখানে শেষ `li` অর্থাৎ JavaScript Green হবে।

### 1.2.3 :nth-child()

Parent-এর Child Element-এর নির্দিষ্ট Position অনুযায়ী Element Select করার জন্য `:nth-child()` ব্যবহার করা হয়।

**CSS Syntax:**

```css
li:nth-child(2) {
  color: blue;
}
```

এখানে দ্বিতীয় Child Element Select হবে।

**Odd এবং Even Example:**

```css
li:nth-child(odd) {
  background-color: lightgray;
}

li:nth-child(even) {
  background-color: white;
}
```

এখানে:

- `odd` ব্যবহার করলে 1st, 3rd, 5th Element Select হবে।
- `even` ব্যবহার করলে 2nd, 4th, 6th Element Select হবে।

**Formula Example:**

```css
li:nth-child(3n) {
  color: red;
}
```

এখানে প্রতি তৃতীয় Child Element Select হবে।

`nth-child()`-এ আরও কিছু Formula ব্যবহার করা যায়:

| Formula  | কাজ                                   |
| -------- | ------------------------------------- |
| `2`      | দ্বিতীয় Element                       |
| `odd`    | বিজোড় Position                        |
| `even`   | জোড় Position                          |
| `3n`     | প্রতি তৃতীয় Element                   |
| `3n + 1` | 1, 4, 7, 10...                        |
| `n + 3`  | তৃতীয় Element থেকে পরবর্তী সব Element |

### 1.2.4 nth-last-child()

Parent-এর শেষ দিক থেকে গণনা করে নির্দিষ্ট Position-এর Child Select করার জন্য `:nth-last-child()` ব্যবহার করা হয়।

**CSS Syntax:**

```css
li:nth-last-child(2) {
  color: red;
}
```

এখানে শেষ থেকে দ্বিতীয় Child Element Select হবে।

### 1.2.5:first-of-type

একই Parent-এর মধ্যে নির্দিষ্ট HTML Tag-এর প্রথম Element Select করার জন্য `:first-of-type` ব্যবহার করা হয়।

**HTML Example:**

```html
<div>
  <h2>Heading One</h2>
  <p>Paragraph One</p>
  <p>Paragraph Two</p>
  <h2>Heading Two</h2>
</div>
```

**CSS Example:**

```css
p:first-of-type {
  color: red;
}
```

এখানে প্রথম `p` Element Select হবে, যদিও সেটি Parent-এর প্রথম Child নয়।

### 1.2.6:last-of-type

একই Parent-এর মধ্যে নির্দিষ্ট HTML Tag-এর শেষ Element Select করার জন্য `:last-of-type` ব্যবহার করা হয়।

**CSS Syntax:**

```css
p:last-of-type {
  color: green;
}
```

এখানে শেষ `p` Element Select হবে।

### 1.2.7 :nth-of-type()
একই Parent-এর মধ্যে নির্দিষ্ট HTML Tag-এর Position অনুযায়ী Element Select করার জন্য `:nth-of-type()` ব্যবহার করা হয়।

**CSS Syntax:**

```css
p:nth-of-type(2) {
  color: blue;
}
```

এখানে দ্বিতীয় `p` Element Select হবে।

### 1.2.8:only-child

কোনো Parent Element-এর একমাত্র Child Element Select করার জন্য `:only-child` ব্যবহার করা হয়।

**HTML Example:**

```html
<div>
  <p>Only Paragraph</p>
</div>
```

**CSS Example:**

```css
p:only-child {
  color: red;
}
```

এখানে `p`-এর Parent-এর মধ্যে আর কোনো Child Element নেই। তাই এটি Select হবে।

### 1.2.9:only-of-type

কোনো Parent-এর মধ্যে নির্দিষ্ট HTML Tag-এর একটিমাত্র Element থাকলে সেটিকে Select করার জন্য `:only-of-type` ব্যবহার করা হয়।

**HTML Example:**

```html
<div>
  <h2>Heading</h2>
  <p>Paragraph One</p>
  <p>Paragraph Two</p>
</div>
```

**CSS Example:**

```css
h2:only-of-type {
  color: blue;
}
```

এখানে Parent-এর মধ্যে একটিমাত্র `h2` থাকায় সেটি Select হবে।

### 1.2.10:empty

যেসব Element-এর কোনো Child Element অথবা Text Content নেই, সেগুলো Select করার জন্য `:empty` ব্যবহার করা হয়।

**HTML Example:**

```html
<div class="box"></div>

<div class="box">
  Hello World
</div>
```

**CSS Example:**

```css
.box:empty {
  width: 100px;
  height: 100px;
  background-color: red;
}
```

এখানে প্রথম Box Select হবে।

**মনে রাখবে:** Whitespace Text Node থাকলেও Element-টি `:empty` হিসেবে Match নাও করতে পারে।

### 1.2.11:root

HTML Document-এর Root Element Select করার জন্য `:root` ব্যবহার করা হয়।

সাধারণ HTML Document-এ এটি `<html>` Element-কে Select করে।

**CSS Syntax:**

```css
:root {
  --primary-color: #2563eb;
  --text-color: #1f2937;
  --background-color: #f8fafc;
}

button {
  background-color: var(--primary-color);
}
```

এখানে `:root`-এর মধ্যে CSS Custom Properties বা Variables তৈরি করা হয়েছে।

**Real-life Use Case:**

- Global CSS Variables।
- Website Color Theme।
- Global Font Settings।
- Design System তৈরি।

---

## 1.3 Form Pseudo Classes

HTML Form-এর Input, Checkbox, Radio Button এবং অন্যান্য Form Element-এর State অনুযায়ী Style Apply করার জন্য Form Pseudo Classes ব্যবহার করা হয়।

### 1.3.1:checked

যেসব Checkbox অথবা Radio Button Selected বা Checked অবস্থায় আছে, সেগুলো Select করার জন্য `:checked` ব্যবহার করা হয়।

**HTML Example:**

```html
<input type="checkbox" id="agree">
<label for="agree">I Agree</label>
```

**CSS Example:**

```css
input:checked {
  accent-color: green;
}
```

এখানে Checkbox Check করলে Green Accent Color দেখা যাবে।

### 1.3.2:disabled

যেসব Form Element Disabled অবস্থায় আছে, সেগুলো Select করার জন্য `:disabled` ব্যবহার করা হয়।

**HTML Example:**

```html
<input type="text" disabled>
<button disabled>Submit</button>
```

**CSS Example:**

```css
:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}
```

### 1.3.3:enabled

যেসব Form Element ব্যবহার করার জন্য Enabled অবস্থায় আছে, সেগুলো Select করার জন্য `:enabled` ব্যবহার করা হয়।

**CSS Syntax:**

```css
input:enabled {
  border: 1px solid green;
}
```

### 1.3.4:required

যেসব Input Field-এ `required` Attribute দেওয়া আছে, সেগুলো Select করার জন্য `:required` ব্যবহার করা হয়।

**HTML Example:**

```html
<input type="email" required>
```

**CSS Example:**

```css
input:required {
  border-left: 4px solid red;
}
```

### 1.3.5:optional

যেসব Input Field-এ `required` Attribute নেই, সেগুলো Select করার জন্য `:optional` ব্যবহার করা হয়।

**CSS Syntax:**

```css
input:optional {
  border-left: 4px solid gray;
}
```

### 1.3.6:valid

কোনো Input Field-এর Value তার HTML Validation Rules অনুযায়ী Valid হলে `:valid` ব্যবহার করে সেটিকে Select করা যায়।

**HTML Example:**

```html
<input type="email" required>
```

**CSS Example:**

```css
input:valid {
  border: 2px solid green;
}
```

### 1.3.7:invalid

কোনো Input Field-এর Value তার HTML Validation Rules অনুযায়ী Invalid হলে `:invalid` ব্যবহার করে সেটিকে Select করা যায়।

**CSS Syntax:**

```css
input:invalid {
  border: 2px solid red;
}
```

**Example:**

```html
<form>
  <input type="email" required placeholder="Enter email">
  <button type="submit">Submit</button>
</form>
```

এখানে Email Field খালি থাকলে অথবা Invalid Email দিলে সেটি Invalid State-এ থাকবে।

**মনে রাখবে:** শুধু `:invalid` ব্যবহার করলে Empty Required Input শুরু থেকেই Invalid দেখাতে পারে। তাই User Interaction-এর পর Validation Style দেখানোর জন্য `:not(:placeholder-shown):invalid` ব্যবহার করতে পারো।

### 1.3.8:in-range

যেসব Input-এর Numeric Value নির্ধারিত Minimum এবং Maximum Range-এর মধ্যে আছে, সেগুলো Select করার জন্য `:in-range` ব্যবহার করা হয়।

**HTML Example:**

```html
<input type="number" min="1" max="100" value="50">
```

**CSS Example:**

```css
input:in-range {
  border: 2px solid green;
}
```

এখানে Value 1 থেকে 100-এর মধ্যে থাকলে Green Border হবে।

### 1.3.9:out-of-range

যেসব Input-এর Numeric Value নির্ধারিত Range-এর বাইরে আছে, সেগুলো Select করার জন্য `:out-of-range` ব্যবহার করা হয়।

**CSS Syntax:**

```css
input:out-of-range {
  border: 2px solid red;
}
```

### 1.3.10:read-only

যেসব Input Field Read-only অবস্থায় আছে, সেগুলো Select করার জন্য `:read-only` ব্যবহার করা হয়।

**HTML Example:**

```html
<input type="text" value="Bangladesh" readonly>
```

**CSS Example:**

```css
input:read-only {
  background-color: #e5e7eb;
  cursor: not-allowed;
}
```

### 1.3.11:read-write

যেসব Element-এর Content User পরিবর্তন করতে পারে, সেগুলো Select করার জন্য `:read-write` ব্যবহার করা হয়।

**HTML Example:**

```html
<input type="text" placeholder="Your name">

<textarea placeholder="Your message"></textarea>
```

**CSS Example:**

```css
input:read-write,
textarea:read-write {
  background-color: white;
}
```

### 1.3.12:placeholder-shown

কোনো Input Field-এ Placeholder এখনো প্রদর্শিত হচ্ছে অর্থাৎ Input Field-এ User কোনো Value দেয়নি, এমন অবস্থায় Element Select করার জন্য `:placeholder-shown` ব্যবহার করা হয়।

**HTML Example:**

```html
<input type="text" placeholder="Enter your name">
```

**CSS Example:**

```css
input:placeholder-shown {
  background-color: #f1f5f9;
}
```

এখানে Input খালি থাকলে Placeholder দেখা যাবে এবং Background Gray হবে।

**মনে রাখবে:**

- `:checked` — Selected Checkbox অথবা Radio।
- `:disabled` — ব্যবহার করা যাবে না এমন Form Element।
- `:enabled` — ব্যবহার করা যায় এমন Form Element।
- `:required` — Required Input।
- `:optional` — Optional Input।
- `:valid` — Validation অনুযায়ী সঠিক Value।
- `:invalid` — Validation অনুযায়ী ভুল Value।
- `:in-range` — নির্ধারিত Range-এর মধ্যে Value।
- `:out-of-range` — নির্ধারিত Range-এর বাইরে Value।
- `:read-only` — পরিবর্তন করা যায় না।
- `:read-write` — পরিবর্তন করা যায়।
- `:placeholder-shown` — Placeholder প্রদর্শিত হচ্ছে।

---

## 1.4 Advanced Pseudo Classes

Advanced Pseudo Classes ব্যবহার করে একাধিক Selector একসঙ্গে লেখা, নির্দিষ্ট Element বাদ দেওয়া এবং Parent Element-এর State অনুযায়ী Child বা Parent Select করা যায়।

### 1.4.1 :not()

কোনো নির্দিষ্ট Selector বাদ দিয়ে বাকি Element Select করার জন্য `:not()` ব্যবহার করা হয়।

**CSS Syntax:**

```css
li:not(.active) {
  color: gray;
}
```

**HTML Example:**

```html
<ul>
  <li>Home</li>
  <li class="active">About</li>
  <li>Services</li>
</ul>
```

এখানে `.active` Class ছাড়া বাকি সব `li` Gray হবে।

**আরেকটি Example:**

```css
input:not([type="submit"]) {
  border: 1px solid gray;
}
```

এখানে Submit Button ছাড়া বাকি Input Element Select হবে।

**Real-life Use Case:**

- Active Menu বাদ দিয়ে অন্য Menu Style করা।
- নির্দিষ্ট Element বাদ দিয়ে Design তৈরি।
- Form Element Filter করা।

### 1.4.2 :is()

একাধিক Selector-কে একসঙ্গে Group করে Style Apply করার জন্য `:is()` ব্যবহার করা হয়।

**CSS Syntax:**

```css
:is(h1, h2, h3) {
  color: blue;
}
```

এখানে `h1`, `h2` এবং `h3` একই Style পাবে।

**Without ():**

```css
h1,
h2,
h3 {
  color: blue;
}
```

**With ():**

```css
:is(h1, h2, h3) {
  color: blue;
}
```

দুইটি Code-এর ফলাফল একই।

**Advanced Example:**

```css
.card :is(h2, p, a) {
  margin-bottom: 10px;
}
```

এখানে `.card`-এর ভিতরের `h2`, `p` এবং `a` Element Select হবে।

### 1.4.3 :where()

একাধিক Selector Group করে Style Apply করার জন্য `:where()` ব্যবহার করা হয়।

এটি দেখতে `:is()`-এর মতো কাজ করে। তবে এর Specificity সবসময় Zero থাকে।

**CSS Syntax:**

```css
:where(h1, h2, h3) {
  color: blue;
}
```

এখানে `h1`, `h2` এবং `h3` Select হবে।

**() vs ()**

| ()                                         | ()                               |
| ------------------------------------------ | -------------------------------- |
| Selector Group করে                         | Selector Group করে               |
| সর্বোচ্চ Argument-এর Specificity গ্রহণ করে | Specificity সবসময় 0              |
| তুলনামূলক বেশি Specificity হতে পারে        | সহজে Override করা যায়            |
| সাধারণ Styling-এ ব্যবহার করা যায়           | Global বা Base Styling-এ কার্যকর |

**Example:**

```css
:where(h1, h2, h3) {
  color: blue;
}

h1 {
  color: red;
}
```

এখানে `h1` Red হবে, কারণ `:where()`-এর Specificity Zero।

### 1.4.4:has()

কোনো Parent Element-এর মধ্যে নির্দিষ্ট Child বা Descendant Element আছে কি না, অথবা কোনো Relationship Match করছে কি না, তার ভিত্তিতে Element Select করার জন্য `:has()` ব্যবহার করা হয়।

এটিকে অনেক সময় Parent Selector বলা হয়।

**CSS Syntax:**

```css
.card:has(img) {
  border: 2px solid blue;
}
```

এখানে যেসব `.card`-এর মধ্যে `img` আছে, সেগুলো Select হবে।

**HTML Example:**

```html
<div class="card">
  <img src="student.jpg" alt="Student">
  <h2>Student Card</h2>
</div>

<div class="card">
  <h2>Text Card</h2>
</div>
```

প্রথম Card-এ Image আছে, তাই শুধু প্রথম Card-এ Blue Border হবে।

**আরেকটি Example:**

```css
.form-group:has(input:focus) {
  background-color: #eff6ff;
}
```

এখানে কোনো `.form-group`-এর Input Focus হলে Parent-এর Background Blue হবে।

**আরেকটি Example:**

```css
.card:has(.badge) {
  border-top: 4px solid orange;
}
```

যেসব Card-এর মধ্যে `.badge` আছে, সেগুলো Select হবে।

**Real-life Use Case:**

- Parent Card Styling।
- Form Validation Design।
- Navigation Menu Styling।
- Image থাকা Card Select করা।
- Conditional UI Styling।

**মনে রাখবে:** `:has()` আধুনিক Browser-এ Supported। পুরোনো Browser Support প্রয়োজন হলে Compatibility যাচাই করবে।

---

# 2. CSS Pseudo Elements (সিএসএস সিউডো এলিমেন্ট)

Pseudo Element ব্যবহার করে HTML Element-এর নির্দিষ্ট অংশ অথবা CSS দিয়ে তৈরি Virtual Content-কে Style করা যায়।

Pseudo Element-এর আগে সাধারণত Double Colon (`::`) ব্যবহার করা হয়।

**CSS Syntax:**

```css
selector::pseudo-element {
  property: value;
}
```

## 2.1 ::before

কোনো HTML Element-এর Content-এর আগে CSS দিয়ে Generated Content যুক্ত করার জন্য `::before` ব্যবহার করা হয়।

**CSS Syntax:**

```css
h2::before {
  content: "★ ";
  color: orange;
}
```

**HTML Example:**

```html
<h2>Our Services</h2>
```

এখানে Heading-এর আগে Star Icon-এর মতো একটি Symbol দেখা যাবে।

**আরেকটি Example:**

```css
.card::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 5px;
  height: 100%;
  background-color: blue;
}
```

এখানে Card-এর বাম পাশে একটি Blue Line তৈরি হবে।

**Real-life Use Case:**

- Decorative Line।
- Custom Icon।
- Card Design।
- Heading Decoration।
- Badge Decoration।

**মনে রাখবে:** `::before` ব্যবহার করলে সাধারণত `content` Property দিতে হয়। এটি Generated Content তৈরি করে, HTML-এর প্রকৃত Element যোগ করে না।

## 2.2 ::after

কোনো HTML Element-এর Content-এর পরে CSS দিয়ে Generated Content যুক্ত করার জন্য `::after` ব্যবহার করা হয়।

**CSS Syntax:**

```css
h2::after {
  content: " ✓";
  color: green;
}
```

**HTML Example:**

```html
<h2>Completed</h2>
```

এখানে Heading-এর শেষে Green Check Symbol দেখা যাবে।

**Another Example:**

```css
.button::after {
  content: " →";
  margin-left: 8px;
}
```

এখানে Button-এর Text-এর পরে Arrow দেখা যাবে।

**::before vs ::after**

| ::before                                  | ::after                                   |
| ----------------------------------------- | ----------------------------------------- |
| Content-এর আগে Generated Content তৈরি করে | Content-এর পরে Generated Content তৈরি করে |
| Decoration ও Icon-এর জন্য ব্যবহার হয়      | Decoration ও Icon-এর জন্য ব্যবহার হয়      |
| সাধারণত প্রথম দিকে থাকে                   | সাধারণত শেষ দিকে থাকে                     |

## 2.3 ::first-letter

কোনো Text Element-এর প্রথম Letter Select করার জন্য `::first-letter` ব্যবহার করা হয়।

**CSS Syntax:**

```css
p::first-letter {
  font-size: 40px;
  color: red;
  font-weight: bold;
}
```

**HTML Example:**

```html
<p>
  Welcome to our website. We provide quality education.
</p>
```

এখানে Paragraph-এর প্রথম Letter বড় এবং Red হবে।

**Real-life Use Case:**

- Blog Design।
- Magazine Layout।
- Drop Cap Design।

## 2.4 ::first-line

কোনো Text Element-এর প্রথম Line Select করার জন্য `::first-line` ব্যবহার করা হয়।

**CSS Syntax:**

```css
p::first-line {
  color: blue;
  font-weight: bold;
}
```

এখানে Paragraph-এর প্রথম Line Blue এবং Bold হবে।

**মনে রাখবে:** Screen Size পরিবর্তন হলে Text-এর First Line-ও পরিবর্তিত হতে পারে।

## 2.5 ::placeholder

Input অথবা Textarea-এর Placeholder Text Style করার জন্য `::placeholder` ব্যবহার করা হয়।

**HTML Example:**

```html
<input type="text" placeholder="Enter your name">
```

**CSS Example:**

```css
input::placeholder {
  color: gray;
  font-size: 14px;
  font-style: italic;
}
```

এখানে Placeholder Text Gray এবং Italic হবে।

## 2.6 ::selection

User Mouse অথবা Keyboard দিয়ে কোনো Text Select করলে সেই Selected Text-এর Style পরিবর্তন করার জন্য `::selection` ব্যবহার করা হয়।

**CSS Syntax:**

```css
::selection {
  background-color: blue;
  color: white;
}
```

এখানে Website-এর Text Select করলে Blue Background এবং White Text দেখা যাবে।

**Real-life Use Case:**

- Website Branding।
- Custom Text Highlight।
- Reading Experience উন্নত করা।

## 2.7 ::marker

List Item-এর Bullet অথবা Number Style করার জন্য `::marker` ব্যবহার করা হয়।

**HTML Example:**

```html
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ul>
```

**CSS Example:**

```css
li::marker {
  color: red;
  font-size: 20px;
}
```

এখানে List-এর Bullet Red হবে।

**Numbered List Example:**

```css
ol li::marker {
  color: blue;
  font-weight: bold;
}
```

## 2.8 ::backdrop

`<dialog>` অথবা Fullscreen Element-এর পিছনে তৈরি হওয়া Backdrop Area Style করার জন্য `::backdrop` ব্যবহার করা হয়।

**HTML Example:**

```html
<dialog open>
  <h2>Hello User</h2>
  <p>Welcome to our website.</p>
</dialog>
```

**CSS Example:**

```css
dialog::backdrop {
  background-color: rgba(0, 0, 0, 0.7);
}
```

এখানে Dialog-এর পিছনের Background Dark হবে।

**Real-life Use Case:**

- Modal Dialog।
- Popup Design।
- Fullscreen Overlay।

## 2.9 ::file-selector-button

HTML File Input-এর Browse বা Choose File Button-এর Style পরিবর্তন করার জন্য `::file-selector-button` ব্যবহার করা হয়।

**HTML Example:**

```html
<input type="file">
```

**CSS Example:**

```css
input::file-selector-button {
  background-color: blue;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
}
```

এখানে File Input-এর Button Custom Design হবে।

**মনে রাখবে:**

- `::before` — Content-এর আগে Generated Content।
- `::after` — Content-এর পরে Generated Content।
- `::first-letter` — প্রথম Letter।
- `::first-line` — প্রথম Line।
- `::placeholder` — Placeholder Text।
- `::selection` — Selected Text।
- `::marker` — List Bullet অথবা Number।
- `::backdrop` — Dialog বা Fullscreen-এর পিছনের Layer।
- `::file-selector-button` — File Input-এর Button।

---

# 3. CSS Attribute Selectors (অ্যাট্রিবিউট সিলেক্টর)

HTML Element-এর নির্দিষ্ট Attribute অথবা Attribute-এর Value অনুযায়ী Element Select করার জন্য Attribute Selectors ব্যবহার করা হয়।

Attribute Selector-এর ক্ষেত্রে Square Brackets (`[]`) ব্যবহার করা হয়।

**Basic Syntax:**

```css
[attribute] {
  property: value;
}
```

**HTML Example:**

```html
<input type="text">
<input type="email">
<input type="password">
```

## 3.1 [attribute]

যেসব HTML Element-এর মধ্যে নির্দিষ্ট Attribute রয়েছে, সেগুলো Select করার জন্য `[attribute]` ব্যবহার করা হয়।

**CSS Syntax:**

```css
[disabled] {
  opacity: 0.5;
}
```

**HTML Example:**

```html
<button disabled>Submit</button>
<input type="text" disabled>
```

এখানে যেসব Element-এর মধ্যে `disabled` Attribute আছে, সেগুলো Select হবে।

## 3.2 [attribute="value"]

নির্দিষ্ট Attribute-এর Value-এর সঙ্গে সম্পূর্ণ Match করলে Element Select করার জন্য `[attribute="value"]` ব্যবহার করা হয়।

**CSS Syntax:**

```css
input[type="email"] {
  border: 2px solid blue;
}
```

এখানে শুধু Email Type-এর Input Select হবে।

**HTML Example:**

```html
<input type="text">
<input type="email">
<input type="password">
```

## 3.3 [attribute\~="value"]

কোনো Attribute-এর Space-separated Value List-এর মধ্যে নির্দিষ্ট একটি সম্পূর্ণ Word থাকলে Element Select করার জন্য `[attribute~="value"]` ব্যবহার করা হয়।

**CSS Syntax:**

```css
[class~="active"] {
  color: green;
}
```

**HTML Example:**

```html
<div class="card active">Card One</div>
<div class="card featured">Card Two</div>
```

এখানে প্রথম Element Select হবে।

**মনে রাখবে:** এটি সম্পূর্ণ Word Match করে, Partial Word নয়।

## 3.4 [attribute|="value"]

কোনো Attribute-এর Value ঠিক নির্দিষ্ট Value হলে অথবা Value-এর পরে Hyphen (`-`) থাকলে Element Select করার জন্য `[attribute|="value"]` ব্যবহার করা হয়।

**CSS Syntax:**

```css
[lang|="en"] {
  color: blue;
}
```

**HTML Example:**

```html
<p lang="en">English Content</p>
<p lang="en-US">American English</p>
<p lang="bn">Bangla Content</p>
```

এখানে প্রথম দুটি Paragraph Select হবে।

## 3.5 [attribute^="value"]

কোনো Attribute-এর Value নির্দিষ্ট Text দিয়ে শুরু হলে Element Select করার জন্য `[attribute^="value"]` ব্যবহার করা হয়।

**CSS Syntax:**

```css
a[href^="https"] {
  color: green;
}
```

এখানে যেসব Link-এর `href` Value `https` দিয়ে শুরু হয়েছে, সেগুলো Select হবে।

**HTML Example:**

```html
<a href="https://google.com">Google</a>
<a href="http://example.com">Example</a>
```

এখানে প্রথম Link Select হবে।

## 3.6 [attribute$="value"]

কোনো Attribute-এর Value নির্দিষ্ট Text দিয়ে শেষ হলে Element Select করার জন্য `[attribute$="value"]` ব্যবহার করা হয়।

**CSS Syntax:**

```css
a[href$=".pdf"] {
  color: red;
}
```

এখানে যেসব Link-এর URL `.pdf` দিয়ে শেষ হয়েছে, সেগুলো Select হবে।

**HTML Example:**

```html
<a href="document.pdf">PDF File</a>
<a href="image.jpg">Image</a>
```

এখানে প্রথম Link Select হবে।

## 3.7 [attribute\*="value"]

কোনো Attribute-এর Value-এর মধ্যে নির্দিষ্ট Text যেকোনো জায়গায় থাকলে Element Select করার জন্য `[attribute*="value"]` ব্যবহার করা হয়।

**CSS Syntax:**

```css
a[href*="youtube"] {
  color: red;
}
```

**HTML Example:**

```html
<a href="https://youtube.com">YouTube</a>
<a href="https://youtube.com/channel">Channel</a>
<a href="https://google.com">Google</a>
```

এখানে প্রথম দুটি Link Select হবে।

### Attribute Selectors-এর পার্থক্য

| Selector          | কাজ                                 | Example                              |         |          |
| ----------------- | ----------------------------------- | ------------------------------------ | ------- | -------- |
| `[attr]`          | Attribute থাকলেই Select             | `[disabled]`                         |         |          |
| `[attr="value"]`  | সম্পূর্ণ Value Match                | `[type="email"]`                     |         |          |
| `[attr~="value"]` | Space-separated সম্পূর্ণ Word Match | `[class~="active"]`                  |         |          |
| \`[attr           | ="value"]\`                         | Exact Value অথবা Value-এর পরে Hyphen | \`[lang | ="en"]\` |
| `[attr^="value"]` | নির্দিষ্ট Value দিয়ে শুরু           | `[href^="https"]`                    |         |          |
| `[attr$="value"]` | নির্দিষ্ট Value দিয়ে শেষ            | `[href$=".pdf"]`                     |         |          |
| `[attr*="value"]` | Value-এর মধ্যে নির্দিষ্ট Text আছে   | `[href*="youtube"]`                  |         |          |

**মনে রাখবে:**

- `^=` মানে Starts With।
- `$=` মানে Ends With।
- `*=` মানে Contains।
- `~=` মানে Space-separated Word Match।
- `|=` মানে Exact অথবা Hyphen-separated Prefix Match।

---

# 4. CSS Specificity & Selector Priority

Advanced CSS Selectors শেখার সময় Specificity বোঝা অত্যন্ত গুরুত্বপূর্ণ।

একাধিক CSS Rule একই HTML Element-এ Apply হলে কোন Rule কার্যকর হবে, তা নির্ধারণ করতে CSS Cascade এবং Specificity গুরুত্বপূর্ণ ভূমিকা রাখে।

## 4.1 Specificity কী?

CSS Specificity হলো একটি Calculation System, যার মাধ্যমে Browser নির্ধারণ করে কোন CSS Selector-এর Priority বেশি।

**Specificity-এর সাধারণ Priority:**

1. ID Selector
2. Class, Attribute এবং Pseudo Class Selector
3. Element এবং Pseudo Element Selector

**Example:**

```css
p {
  color: blue;
}

.text {
  color: green;
}

#title {
  color: red;
}
```

**HTML:**

```html
<p class="text" id="title">Hello World</p>
```

এখানে Text Red হবে, কারণ ID Selector-এর Specificity বেশি।

## 4.2 Specificity Calculation

Specificity সাধারণত চারটি অংশে বোঝানো হয়:

`Inline - ID - Class - Element`

| Selector        | Specificity |
| --------------- | ----------- |
| `p`             | 0-0-0-1     |
| `.card`         | 0-0-1-0     |
| `#header`       | 0-1-0-0     |
| `div.card`      | 0-0-1-1     |
| `#header .card` | 0-1-1-0     |
| `p:hover`       | 0-0-1-1     |

**মনে রাখবে:**

- `:is()` তার সবচেয়ে বেশি Specificity-যুক্ত Argument-এর Specificity গ্রহণ করে।
- `:where()`-এর Specificity সবসময় Zero।
- `:not()` নিজে Specificity যোগ করে না; তার Argument-এর Specificity গণনা হয়।
- `:has()` নিজে Specificity যোগ করে না; তার Argument-এর সর্বোচ্চ Specificity গণনা হয়।
- `::before` এবং `::after` Pseudo Elements হিসেবে গণনা হয়।
- `!important` সাধারণ Specificity Calculation-এর অংশ নয়; এটি Cascade Priority পরিবর্তন করে।

---

# 5. Practical Projects (প্র্যাকটিক্যাল প্রজেক্ট)

এই Phase-এ শেখা Advanced CSS Selectors এবং Pseudo Classes ব্যবহার করে নিচের পাঁচটি Project তৈরি করবে।

## Project 01 — Interactive Navigation Menu

**Project Goal:** CSS Pseudo Classes ব্যবহার করে একটি Interactive Navigation Menu তৈরি করা।

**Requirements:**

- Website Logo যুক্ত করতে হবে।
- Home, About, Services, Contact Navigation Link তৈরি করতে হবে।
- Hover করলে Link-এর Color পরিবর্তন করতে হবে।
- Active Link Highlight করতে হবে।
- Visited Link-এর Style নির্ধারণ করতে হবে।
- Keyboard Navigation-এর জন্য Focus Indicator যুক্ত করতে হবে।
- `::before` এবং `::after` দিয়ে Underline Animation তৈরি করতে হবে।
- `:not()` ব্যবহার করে Active Link বাদে অন্য Link Style করতে হবে।

**Practice Topics:**

- `:hover`
- `:active`
- `:focus-visible`
- `:link`
- `:visited`
- `:target`
- `:not()`
- `::before`
- `::after`

## Project 02 — Custom Form Design

**Project Goal:** Advanced CSS Selectors ব্যবহার করে একটি Professional Registration Form তৈরি করা।

**Requirements:**

- Full Name Input।
- Email Input।
- Password Input।
- Phone Number Input।
- Gender Radio Button।
- Skills Checkbox।
- Terms & Conditions Checkbox।
- Submit Button।
- Required Field Highlight করতে হবে।
- Valid এবং Invalid Input-এর জন্য আলাদা Design করতে হবে।
- Disabled Input-এর Style তৈরি করতে হবে।
- Focus করলে Input-এর Border পরিবর্তন করতে হবে।
- Placeholder-এর Custom Style তৈরি করতে হবে।

**Practice Topics:**

- `:focus`
- `:focus-visible`
- `:focus-within`
- `:required`
- `:optional`
- `:valid`
- `:invalid`
- `:disabled`
- `:enabled`
- `:placeholder-shown`
- `::placeholder`

## Project 03 — Custom Checkbox & Radio Button

**Project Goal:** CSS ব্যবহার করে Custom Checkbox এবং Radio Button তৈরি করা।

**Requirements:**

- Default Checkbox Design পরিবর্তন করতে হবে।
- Custom Checkbox তৈরি করতে হবে।
- Custom Radio Button তৈরি করতে হবে।
- Checked অবস্থায় Background Color পরিবর্তন করতে হবে।
- Hover Effect যুক্ত করতে হবে।
- Disabled State তৈরি করতে হবে।
- Selected Option-এর Label Highlight করতে হবে।
- `:checked` ব্যবহার করে Design তৈরি করতে হবে।

**Practice Topics:**

- `:checked`
- `:disabled`
- `:enabled`
- `:hover`
- `:focus-visible`
- `:has()`
- `::before`
- `::after`

## Project 04 — Stylish Table Design

**Project Goal:** Structural Pseudo Classes ব্যবহার করে একটি Professional Table তৈরি করা।

**Requirements:**

- Student Information Table তৈরি করতে হবে।
- Table Header যুক্ত করতে হবে।
- Odd Row-এর Background পরিবর্তন করতে হবে।
- Even Row-এর Background পরিবর্তন করতে হবে।
- First Row Highlight করতে হবে।
- Last Row Highlight করতে হবে।
- Hover করলে Row Highlight করতে হবে।
- নির্দিষ্ট Column-এর Style পরিবর্তন করতে হবে।

**Practice Topics:**

- `:first-child`
- `:last-child`
- `:nth-child()`
- `:nth-last-child()`
- `:first-of-type`
- `:last-of-type`
- `:nth-of-type()`
- `:hover`

## Project 05 — Advanced Card UI

**Project Goal:** Advanced Pseudo Classes এবং Pseudo Elements ব্যবহার করে Professional Card Design তৈরি করা।

**Requirements:**

- Profile Card তৈরি করতে হবে।
- Product Card তৈরি করতে হবে।
- Image এবং Text যুক্ত করতে হবে।
- Hover Effect তৈরি করতে হবে।
- Card-এর মধ্যে Image থাকলে আলাদা Style Apply করতে হবে।
- Badge থাকলে Card Highlight করতে হবে।
- Card-এর Before এবং After Decoration তৈরি করতে হবে।
- `:is()` ব্যবহার করে একাধিক Element Group করতে হবে।
- `:where()` ব্যবহার করে Base Style তৈরি করতে হবে।
- `:has()` ব্যবহার করে Parent Card Select করতে হবে।

**Practice Topics:**

- `:hover`
- `:focus-within`
- `:not()`
- `:is()`
- `:where()`
- `:has()`
- `::before`
- `::after`
- `::first-letter`

---

# 6. Weekly Practice Routine (সাপ্তাহিক অনুশীলন)

| Day    | Topics                          | Practice                              |
| ------ | ------------------------------- | ------------------------------------- |
| Day 01 | User Interaction Pseudo Classes | Hover, Active, Focus, Focus-visible   |
| Day 02 | Structural Pseudo Classes       | First-child, Last-child, Nth-child    |
| Day 03 | Form Pseudo Classes             | Checked, Valid, Invalid, Required     |
| Day 04 | Advanced Pseudo Classes         | Not, Is, Where, Has                   |
| Day 05 | Pseudo Elements                 | Before, After, Placeholder, Selection |
| Day 06 | Attribute Selectors             | All Attribute Selector Practice       |
| Day 07 | Revision & Practice             | Specificity এবং ছোট ছোট UI তৈরি       |

**Week 06:** এই সপ্তাহে পাঁচটি Practical Project সম্পন্ন করার চেষ্টা করবে।

---

# 7. Learning Checklist (শেখার অগ্রগতি)

### User Interaction Pseudo Classes

- [ ] `:hover`
- [ ] `:active`
- [ ] `:focus`
- [ ] `:focus-visible`
- [ ] `:focus-within`
- [ ] `:visited`
- [ ] `:link`
- [ ] `:target`

### Structural Pseudo Classes

- [ ] `:first-child`
- [ ] `:last-child`
- [ ] `:nth-child()`
- [ ] `:nth-last-child()`
- [ ] `:first-of-type`
- [ ] `:last-of-type`
- [ ] `:nth-of-type()`
- [ ] `:only-child`
- [ ] `:only-of-type`
- [ ] `:empty`
- [ ] `:root`

### Form Pseudo Classes

- [ ] `:checked`
- [ ] `:disabled`
- [ ] `:enabled`
- [ ] `:required`
- [ ] `:optional`
- [ ] `:valid`
- [ ] `:invalid`
- [ ] `:in-range`
- [ ] `:out-of-range`
- [ ] `:read-only`
- [ ] `:read-write`
- [ ] `:placeholder-shown`

### Advanced Pseudo Classes

- [ ] `:not()`
- [ ] `:is()`
- [ ] `:where()`
- [ ] `:has()`

### Pseudo Elements

- [ ] `::before`
- [ ] `::after`
- [ ] `::first-letter`
- [ ] `::first-line`
- [ ] `::placeholder`
- [ ] `::selection`
- [ ] `::marker`
- [ ] `::backdrop`
- [ ] `::file-selector-button`

### Attribute Selectors

- [ ] `[attribute]`
- [ ] `[attribute="value"]`
- [ ] `[attribute~="value"]`
- [ ] `[attribute|="value"]`
- [ ] `[attribute^="value"]`
- [ ] `[attribute$="value"]`
- [ ] `[attribute*="value"]`

### Additional CSS Concepts

- [ ] CSS Specificity
- [ ] Selector Priority
- [ ] Selector Grouping
- [ ] Parent Selection using `:has()`

### Practical Projects

- [ ] Interactive Navigation Menu
- [ ] Custom Form Design
- [ ] Custom Checkbox & Radio Button
- [ ] Stylish Table Design
- [ ] Advanced Card UI

---

# 8. Learning Resources (শেখার রিসোর্স)

| Resource                | Link                                                                                                                                         |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| MDN CSS Selectors       | [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors)             |
| MDN Pseudo Classes      | [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)           |
| MDN Pseudo Elements     | [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)         |
| MDN Attribute Selectors | [https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors) |
| MDN Specificity         | [https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)                 |
| CSS Selectors Level 4   | [https://www.w3.org/TR/selectors-4/](https://www.w3.org/TR/selectors-4/)                                                                     |
| CSS Diner               | [https://flukeout.github.io/](https://flukeout.github.io/)                                                                                   |

---

# 9. Final Tips (গুরুত্বপূর্ণ পরামর্শ)

1. Pseudo Class এবং Pseudo Element-এর পার্থক্য ভালোভাবে বুঝবে।
2. `:hover`, `:active` এবং `:focus` নিজে Code করে Practice করবে।
3. `:nth-child()` এবং `:nth-of-type()`-এর পার্থক্য বুঝবে।
4. Form Validation-এর জন্য `:valid` এবং `:invalid` ব্যবহার করবে।
5. `:is()` এবং `:where()`-এর Specificity ভালোভাবে বুঝবে।
6. `:has()` ব্যবহার করে Parent Element Select করার Practice করবে।
7. `::before` এবং `::after` দিয়ে বিভিন্ন Decoration তৈরি করবে।
8. Attribute Selectors ব্যবহার করে HTML Attribute অনুযায়ী Element Select করবে।
9. CSS Specificity এবং Cascade সম্পর্কে পরিষ্কার ধারণা তৈরি করবে।
10. Accessibility-এর জন্য Keyboard Focus Style বজায় রাখবে।
11. শুধু Code দেখে শেখার পরিবর্তে প্রতিটি Selector নিজে ব্যবহার করবে।
12. প্রতিটি Project Desktop এবং Mobile Screen-এ পরীক্ষা করবে।

---

## 🎓 Phase 05 Completion Goal

এই Phase সম্পন্ন করার পর তুমি Advanced CSS Selectors, Pseudo Classes, Pseudo Elements এবং Attribute Selectors ব্যবহার করে Professional এবং Interactive Website UI তৈরি করতে পারবে।

**Learning Strategy:**

- 30% — Learn & Understand
- 70% — Coding & Practical Projects

**Remember:**

> Don't just memorize CSS selectors. Understand how to select elements based on their state, structure, relationship, and attributes.

**Happy Coding! 🚀**
