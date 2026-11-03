
# Phase 01: CSS Fundamentals (প্রথম সপ্তাহ)

## Part 1: Introduction to CSS (সিএসএস পরিচিতি)

ওয়েব ডেভেলপমেন্টে HTML হলো কোনো ওয়েবসাইটের **‘কঙ্কাল বা কাঠামো’** (Skeleton) আর CSS হলো তার **‘রং, রূপ ও ডিজাইন’** (Skin & Outfit)।

### 1. What is CSS? (CSS কী?)

CSS-এর পূর্ণরূপ হলো **Cascading Style Sheets**। এটি কোনো প্রোগ্রামিং ভাষা নয়, এটি একটি **Style Sheet Language**। HTML দিয়ে তৈরি করা সাধারণ ওয়েব পেজকে সুন্দর, আকর্ষণীয় এবং বিভিন্ন ডিভাইসে মানানসই করার জন্য CSS ব্যবহার করা হয়।

### 2. Why CSS is used? (CSS কেন ব্যবহার করা হয়?)

* **সৌন্দর্য বর্ধন:** ফন্ট, কালার, ব্যাকগ্রাউন্ড ও লেআউট সুন্দর করার জন্য।
* **কোড কমানো (DRY - Don't Repeat Yourself):** একবার CSS লিখে তা হাজারটা পেজে ব্যবহার করা যায়।
* **রেসপনসিভ ডিজাইন:** মোবাইল, ট্যাব বা ল্যাপটপ—সব স্ক্রিনে সাইট যেন সুন্দর দেখায়, তা নিশ্চিত করতে।
* **HTML থেকে স্টাইল আলাদা করা:** কাঠামো ঠিক রেখে ডিজাইন পরিবর্তন করা সহজ হয়।

### 3. How CSS works? (CSS কীভাবে কাজ করে?)

ব্রাউজার যখন কোনো HTML ফাইল লোড করে, তখন সেটি একটি **DOM (Document Object Model)** ট্রি তৈরি করে। এরপর ব্রাউজার CSS ফাইল বা স্টাইল ট্যাগ পড়ে এবং সেই অনুযায়ী HTML এলিমেন্টগুলোর ওপর রঙ, সাইজ বা লেআউট প্রয়োগ করে স্ক্রিনে প্রদর্শন করে।

---

### Anatomy of CSS (সিএসএস এর গঠন বা সিনট্যাক্স)

নিচে একটি আদর্শ CSS সিনট্যাক্স বা **Ruleset** দেখানো হলো:

```css
h1 {
  color: blue;
  font-size: 24px;
}

```

* **CSS Ruleset:** সম্পূর্ণ ব্লকটি (`h1 { color: blue; font-size: 24px; }`) হলো একটি রুলসেট। এটি ব্রাউজারকে বলে দেয় কোন এলিমেন্টে কেমন স্টাইল হবে।
* **CSS Selector:** কোডের শুরুতে থাকা `h1` হলো সিলেক্টর। এটি নির্দেশ করে কোন HTML এলিমেন্টকে ডিজাইন করা হবে।
* **CSS Declaration (ঘোষণা):** সেকেন্ড ব্র্যাকেটের ভেତরের অংশগুলো (`color: blue;`) হলো ডেক্লারেশন।
* **CSS Property (প্রপার্টি):** `color` বা `font-size` হলো প্রপার্টি—অর্থাৎ আপনি কী পরিবর্তন করতে চান (যেমন: রঙ নাকি সাইজ)।
* **CSS Value (ভ্যালু):** `blue` বা `24px` হলো ভ্যালু—অর্থাৎ প্রপার্টির মান কী হবে।

---

## Part 2: Ways to Add CSS (HTML-এর সাথে CSS যুক্ত করার ৩টি নিয়ম)

HTML ডকুমেন্টে তিনভাবে CSS যুক্ত করা যায়:

### 1. Inline CSS (ইনলাইন সিএসএস)

যখন সরাসরি কোনো নির্দিষ্ট HTML ট্যাগের ভেতরে `style` অ্যাট্রিবিউট ব্যবহার করে CSS লেখা হয়, তখন তাকে Inline CSS বলে। এটি খুব ছোট বা তাৎক্ষণিক কাজের জন্য ব্যবহার করা হয়, তবে বড় প্রজেক্টে এটি এড়িয়ে চলা ভালো।

**উদাহরণ:**

```html
<h1 style="color: red; text-align: center;">এটি ইনলাইন সিএসএস হেডিং</h1>

```

### 2. Internal CSS (ইন্টারনাল সিএসএস)

যখন HTML ফাইলের `<head>` ট্যাগের ভেতরে `<style>` ট্যাগের মাঝে CSS কোড লেখা হয়, তখন তাকে Internal CSS বলে। এটি একটি নির্দিষ্ট পেজের সব উপাদানের ডিজাইন নিয়ন্ত্রণ করতে পারে।

**উদাহরণ:**

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      background-color: #f4f4f4;
    }
    p {
      color: green;
    }
  </style>
</head>
<body>
  <p>এটি ইন্টারনাল সিএসএস দিয়ে ডিজাইন করা প্যারাগ্রাফ।</p>
</body>
</html>

```

### 3. External CSS (এক্সটার্নাল সিএসএস) — *(প্রফেশনাল পদ্ধতি)*

এটিই সবচেয়ে জনপ্রিয় ও প্রফেশনাল পদ্ধতি। এখানে আলাদা একটি `.css` এক্সটেনশনের ফাইল তৈরি করে সেখানে সমস্ত ডিজাইন লেখা হয় এবং HTML ফাইলের সাথে `<link>` ট্যাগ দিয়ে তা যুক্ত করা হয়।

* **Linking CSS File (সিএসএস ফাইল যুক্ত করা):**
`<head>` ট্যাগের ভেতরে এই কোডটি লিখে এক্সটার্নাল ফাইল যুক্ত করতে হয়:

```html
<link rel="stylesheet" href="style.css">

```

* **Multiple CSS Files (একাধিক সিএসএস ফাইল ব্যবহার করা):**
বড় প্রজেক্টে কাজের সুবিধার্থে একাধিক CSS ফাইল (যেমন: `normalize.css`, `style.css`, `dashboard.css`) আলাদাভাবে তৈরি করে সবগুলোই HTML-এ লিংক করা যায়:
```html
<link rel="stylesheet" href="normalize.css">
<link rel="stylesheet" href="style.css">
<link rel="stylesheet" href="dashboard.css">
```

---

## 3. CSS Selectors (সিএসএস সিলেক্টরসমূহ)

CSS Selector দিয়ে আমরা ব্রাউজারকে নির্দেশ করি যে HTML-এর ঠিক কোন Element বা Elements-কে Style করতে চাই।
অর্থাৎ, HTML Document-এর নির্দিষ্ট Element খুঁজে বের করে তার ওপর CSS Style Apply করার জন্য Selector ব্যবহার করা হয়।

### Example:

```html
<h1>Hello World!</h1>
<p>Welcome to CSS Learning.</p>

h1 {
  color: blue;
}

p {
  color: green;
}
```
### এখানে:
- h1 হলো একটি CSS Selector।
- color হলো CSS Property।
- blue হলো CSS Value।
- h1 Element-এর Text নীল রঙের হবে।

### 1. Element Selector (এলিমেন্ট সিলেক্টর)

Element Selector ব্যবহার করে সরাসরি HTML Tag-এর নাম উল্লেখ করে CSS Style Apply করা হয়।
অর্থাৎ, একই HTML Tag যতবারই ব্যবহার করা হোক, Element Selector দিয়ে সেই Tag-এর সব Element-কে একসঙ্গে Style করা যায়।

**Example:**

```css
p {
  color: gray;
}
```
```html
<p>This is the first paragraph.</p>
<p>This is the second paragraph.</p>
<p>This is the third paragraph.</p>
```

### ব্যাখ্যা:
- p হলো Element Selector।
- color হলো CSS Property।
- gray হলো CSS Value।
- color: gray; দ্বারা Paragraph-এর Text-এর রং ধূসর করা হয়েছে।
Output: পেজের সব <p> Tag-এর Text ধূসর রঙের হবে।

### Note: Element Selector ব্যবহার করলে নির্দিষ্ট HTML Tag-এর সব Element-এ Style Apply হয়।

### 2. Class Selector (ক্লাস সিলেক্টর)

একাধিক HTML Element-এ একই CSS Style Apply করার জন্য Class Selector ব্যবহার করা হয়।
Class Selector লেখার সময় Class-এর নামের আগে একটি ডট (`.`) দিতে হয়।

**CSS Syntax:**

```css
.btn-primary {
  background-color: blue;
  color: white;
}
```
```html
<button class="btn-primary">Click Me</button>
<button class="btn-primary">Submit</button>
<p class="btn-primary">This is a paragraph.</p>
```

### ব্যাখ্যা:
- .btn-primary হলো Class Selector।
- . (ডট) দিয়ে Class Selector শুরু হয়।
- btn-primary হলো Class-এর নাম।
- background-color: blue; দ্বারা Element-এর Background নীল করা হয়েছে।
- color: white; দ্বারা Text-এর রং সাদা করা হয়েছে।
- HTML-এর class Attribute ব্যবহার করে কোনো Element-এ Class যুক্ত করা হয়।
Output: উপরের তিনটি HTML Element-এই একই CSS Style Apply হবে।

### Note:
- একই Class একাধিক HTML Element-এ ব্যবহার করা যায়।
- একটি HTML Element-এ একাধিক Class ব্যবহার করা যায়।
- Class Name Case-sensitive, তাই বড় ও ছোট হাতের অক্ষর আলাদা হিসেবে বিবেচিত হয়।

**গুরুত্বপূর্ণ:** Class Selector বাস্তব Website Development-এ সবচেয়ে বেশি ব্যবহৃত CSS Selectors-এর মধ্যে একটি। তাই এটি ভালোভাবে অনুশীলন করবে।

### 3. ID Selector (আইডি সিলেক্টর)

কোনো নির্দিষ্ট HTML Element-কে আলাদাভাবে Style করার জন্য ID Selector ব্যবহার করা হয়।
ID Selector লেখার সময় ID-এর নামের আগে একটি হ্যাশ (`#`) চিহ্ন দিতে হয়।
একটি HTML Document-এ একই ID একাধিক Element-এ ব্যবহার করা উচিত নয়। প্রতিটি ID Unique হওয়া উচিত।

**CSS Syntax:**

```css
#main-heading {
  font-size: 32px;
}
```
```html
<h1 id="main-heading">স্বাগতম</h1>
<h2>আমাদের ওয়েবসাইটে আপনাকে স্বাগতম</h2>
```

### ব্যাখ্যা:
- #main-heading হলো ID Selector।
- (# হ্যাশ) দিয়ে ID Selector শুরু হয়।
- main-heading হলো ID-এর নাম।
- font-size হলো CSS Property।
- 32px হলো CSS Value।
- HTML-এর id Attribute ব্যবহার করে কোনো Element-এ ID যুক্ত করা হয়।
Output: শুধু main-heading ID যুক্ত <h1> Element-এর Font Size 32px হবে।

### Note:
- একটি ID একটি HTML Document-এ একবারই ব্যবহার করা উচিত।
- ID Selector-এর Specificity Class Selector-এর চেয়ে বেশি।
- একটি HTML Element-এর ID-তে Space ব্যবহার করা যায় না।
- CSS-এ ID Selector লেখার সময় # ব্যবহার করতে হয়।


**ID & Class এর পার্থক্য:**

| Class Selector | ID Selector |
|---|---|
| `.` দিয়ে শুরু হয় | `#` দিয়ে শুরু হয় |
| একাধিক Element-এ ব্যবহার করা যায় | একটি Document-এ Unique হওয়া উচিত |
| `class` Attribute ব্যবহার করে | `id` Attribute ব্যবহার করে |
| Specificity কম | Specificity বেশি |
 
---

### 4. Universal Selector (ইউনিভার্সাল সিলেক্টর)

Universal Selector ব্যবহার করে একটি HTML Document-এর সমস্ত HTML Element-কে একসঙ্গে Select করা যায়।
Universal Selector লেখার জন্য একটি Asterisk (`*`) চিহ্ন ব্যবহার করা হয়।
সাধারণত ওয়েব পেজের Default Margin ও Padding Reset করতে এবং সব Element-এর Box Sizing নির্ধারণ করতে এটি ব্যবহার করা হয়।

**CSS Syntax:**
```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```
### ব্যাখ্যা:
- * হলো Universal Selector।
- margin: 0; দ্বারা সব Element-এর Default Margin শূন্য করা হয়।
- padding: 0; দ্বারা সব Element-এর Default Padding শূন্য করা হয়।
- box-sizing: border-box; দ্বারা Element-এর নির্ধারিত Width ও Height-এর মধ্যে Padding এবং Border অন্তর্ভুক্ত করা হয়।
Output: পেজের সব HTML Element-এর Margin ও Padding শূন্য হবে এবং box-sizing হবে border-box।

### Note:
- Universal Selector সব HTML Element-কে Select করে।
- এটি সাধারণত CSS Reset করার জন্য ব্যবহার করা হয়।
- বড় প্রজেক্টে Universal Selector ব্যবহার করার সময় এর প্রভাব সম্পর্কে সচেতন থাকতে হবে।

---

### 5. Group Selector (গ্রুপ সিলেক্টর)

একাধিক HTML Element বা Selector-কে একই CSS Style দেওয়ার জন্য Group Selector ব্যবহার করা হয়।
Group Selector লেখার সময় প্রতিটি Selector-এর মাঝে কমা (`,`) ব্যবহার করতে হয়। এতে প্রতিটি Selector-এর জন্য আলাদাভাবে CSS লিখতে হয় না।

**CSS Syntax:**
```css
h1, h2, h3 {
  font-family: Arial, sans-serif;
  color: #333;
}
```
```html
<h1>Welcome to CSS</h1>
<h2>Learn Web Development</h2>
<h3>Start Your Journey</h3>

<p>This is a paragraph.</p>
```
### ব্যাখ্যা:
- h1, h2, h3 হলো Group Selector।
- কমা (,) দিয়ে একাধিক Selector একসঙ্গে যুক্ত করা হয়েছে।
- font-family: Arial, sans-serif; দ্বারা সব Heading-এর Font নির্ধারণ করা হয়েছে।
- color: #333; দ্বারা সব Heading-এর Text-এর রং গাঢ় ধূসর করা হয়েছে।
Output: <h1>, <h2> এবং <h3>—এই তিনটি Element-এ একই CSS Style Apply হবে। কিন্তু <p> Element-এ এই Style Apply হবে না।

### Note:
- একাধিক Selector-কে কমা দিয়ে যুক্ত করলে Group Selector তৈরি হয়।
- প্রতিটি Selector একই CSS Declaration পায়।
- কোড ছোট ও পরিষ্কার রাখতে Group Selector ব্যবহার করা হয়।

**নোট:** Group Selector-এ কমা ব্যবহার করা বাধ্যতামূলক। কমা বাদ দিলে CSS-এর অর্থ পরিবর্তিত হয়ে যায়।

---

### 6. Descendant Selector (ডিসেন্ড্যান্ট সিলেক্টর)

কোনো নির্দিষ্ট HTML Element-এর ভেতরে থাকা অন্য কোনো HTML Element-কে Select করার জন্য Descendant Selector ব্যবহার করা হয়।
Descendant Selector লেখার সময় Parent এবং Child বা Nested Element-এর Selector-এর মাঝে একটি স্পেস (` `) দিতে হয়।

**CSS Syntax:**
```css
div p {
  color: green;
}
```
---

### ৭. Child Selector (`>`)

সরাসরি ভেতরের চাইল্ড (Direct child) এলিমেন্টকে সিলেক্ট করতে গ্রেটার দেন (`>`) চিহ্ন ব্যবহার করা হয়।

```css
ul > li {
  list-style-type: none;
}
```
```html
<div>
  <p>This paragraph is inside the div.</p>

  <section>
    <p>This paragraph is also inside the div.</p>
  </section>
</div>

<p>This paragraph is outside the div.</p>
```
### ব্যাখ্যা:
- div p হলো Descendant Selector।
- div হলো Parent বা Ancestor Element।
- p হলো Target Element।
- div এবং p-এর মাঝে স্পেস ( ) ব্যবহার করা হয়েছে।
- color: green; দ্বারা নির্বাচিত Paragraph-এর Text-এর রং সবুজ করা হয়েছে।
Output: div-এর ভেতরে থাকা সব <p> Element-এর Text সবুজ হবে। এমনকি অন্য কোনো Element-এর ভেতরে Nested অবস্থায় থাকা <p> Element-ও Select হবে। কিন্তু div-এর বাইরে থাকা <p> Element-এর রং পরিবর্তন হবে না।

### Note:
- Descendant Selector-এ Parent ও Target Element-এর মাঝে স্পেস ব্যবহার করা হয়।
- এটি শুধু সরাসরি Child Element নয়, গভীরভাবে Nested অবস্থায় থাকা Descendant Element-কেও Select করে।
- নির্দিষ্ট কোনো Parent Element-এর ভেতরের একই ধরনের একাধিক Element-কে Style করতে এটি ব্যবহার করা হয়।

**নোট:** Descendant Selector এবং Child Selector এক নয়। Descendant Selector যেকোনো গভীরতার Nested Element-কে Select করতে পারে, কিন্তু Child Selector (`>`) শুধু সরাসরি Child Element-কে Select করে।

---

### 8. Adjacent Sibling Selector (অ্যাডজেসেন্ট সিবলিং সিলেক্টর)

কোনো নির্দিষ্ট HTML Element-এর ঠিক পরেই থাকা একই Parent-এর অন্য একটি Element-কে Select করার জন্য Adjacent Sibling Selector ব্যবহার করা হয়।
এটি লেখার সময় দুটি Selector-এর মাঝে প্লাস (`+`) চিহ্ন ব্যবহার করতে হয়।

**CSS Syntax:**
```css
h1 + p {
  font-weight: bold;
}
```
```html
<div>
  <h1>Welcome to CSS</h1>
  <p>This is the first paragraph.</p>
  <p>This is the second paragraph.</p>
</div>

<p>This paragraph is outside the div.</p>
```
### ব্যাখ্যা:
- h1 + p হলো Adjacent Sibling Selector।
- h1 হলো Previous Element।
- + চিহ্ন দ্বারা ঠিক পরের Sibling Element-কে Select করা হয়।
- p হলো Target Element।
- font-weight: bold; দ্বারা Paragraph-এর Text Bold করা হয়েছে।
  
Output: <h1> এর ঠিক পরেই থাকা প্রথম <p> Element-এর Text Bold হবে। দ্বিতীয় <p> এবং বাইরের Paragraph-এ এই Style Apply হবে না।

### Note:
- Adjacent Sibling Selector-এ + চিহ্ন ব্যবহার করা হয়।
- Target Element-টি অবশ্যই একই Parent-এর Sibling হতে হবে।
- Target Element-টি নির্দিষ্ট Element-এর ঠিক পরেই থাকতে হবে।
- মাঝখানে অন্য কোনো Element থাকলে সেটি Select হবে না।

---

### 9. General Sibling Selector (জেনারেল সিবলিং সিলেক্টর)

কোনো নির্দিষ্ট HTML Element-এর পরবর্তী একই Parent-এর অধীনে থাকা সব Matching Sibling Element-কে Select করার জন্য General Sibling Selector ব্যবহার করা হয়।
এটি লেখার সময় দুটি Selector-এর মাঝে টিল্ড (`~`) চিহ্ন ব্যবহার করতে হয়।

**CSS Syntax:**
```css
h1 ~ p {
  color: darkblue;
}
```
```html
<div>
  <h1>Welcome to CSS</h1>

  <p>This is the first paragraph.</p>
  <p>This is the second paragraph.</p>

  <section>
    <p>This paragraph is inside a section.</p>
  </section>

  <p>This is the third paragraph.</p>
</div>
```

### ব্যাখ্যা:
- h1 ~ p হলো General Sibling Selector।
- h1 হলো Previous Element।
- ~ (টিল্ড) চিহ্ন দিয়ে পরবর্তী Matching Sibling Element-গুলো Select করা হয়।
- p হলো Target Element।
- color: darkblue; দ্বারা নির্বাচিত Paragraph-এর Text-এর রং গাঢ় নীল করা হয়েছে।
  
Output: <h1> এর পরে একই Parent-এর অধীনে থাকা সব <p> Element-এর Text গাঢ় নীল হবে। তবে <section> এর ভেতরে থাকা <p> Select হবে না, কারণ সেটি <h1> এর সরাসরি Sibling নয়।

### Note:
- General Sibling Selector-এ ~ চিহ্ন ব্যবহার করা হয়।
- Target Element-গুলো একই Parent-এর অধীনে থাকতে হবে।
- Target Element-গুলো নির্দিষ্ট Element-এর পরে থাকতে হবে।
- মাঝখানে অন্য Element থাকলেও পরবর্তী Matching Sibling Select হতে পারে।

**নোট:** General Sibling Selector (`~`) এবং Adjacent Sibling Selector (`+`) এর মধ্যে পার্থক্য হলো `+` শুধু ঠিক পরের Sibling-কে Select করে, আর `~` পরবর্তী সব Matching Sibling কে Select করে।

---

## 4. CSS Comments (সিএসএস কমেন্টস)

CSS Code-এর মধ্যে নিজের বোঝার সুবিধার জন্য, কোডের কাজ ব্যাখ্যা করার জন্য অথবা গুরুত্বপূর্ণ নোট লিখে রাখার জন্য Comments ব্যবহার করা হয়।
CSS Comments ব্রাউজারে প্রদর্শিত হয় না এবং ব্রাউজার এগুলোকে CSS Instruction হিসেবে Execute করে না।

CSS-এ Comment লেখার জন্য `/* ... */` ব্যবহার করা হয়।

### 4.1 Single-line Comment (সিঙ্গেল লাইন কমেন্ট)

**CSS Syntax:**
```css
/* এটি একটি সিঙ্গেল লাইন কমেন্ট */
body {
  background-color: #fff;
}

* **Multi-line Comment:** একাধিক লাইনে নোট লেখার জন্য:
```css
/* 
  নিচের কোডগুলো মেইন হেডার সেকশনের জন্য 
  তৈরি করা হয়েছে। 
*/
.header { height: 80px; }

```

---

## 5. CSS Colors (সিএসএস কালার)

সিএসএসে বিভিন্ন উপায়ে রঙ দেওয়া যায়:

1. **Color Names:** সরাসরি রঙের নাম লিখে (যেমন: `red`, `blue`, `orange`, `transparent`)।
2. **HEX Code:** ৬ ডিজিটের হেক্সাডেসিমেল কোড দিয়ে (যেমন: `#ff0000` হলো লাল, `#00ff00` হলো সবুজ)।
3. **RGB:** Red, Green, Blue-এর পরিমাণ (০ থেকে ২৫৫ এর মধ্যে) নির্ধারণ করে।
```css
color: rgb(255, 0, 0); /* লাল রঙ */
```
4. **RGBA:** RGB-এর সাথে 'A' দিয়ে **Alpha** অর্থাৎ স্বচ্ছতা (Opacity) নিয়ন্ত্রণ করা হয় (মান ০ থেকে ১ এর মধ্যে)।
```css
background-color: rgba(0, 0, 0, 0.5); /* ৫০% স্বচ্ছ কালো */

```
5. **Opacity:** সম্পূর্ণ এলিমেন্ট বা তার ভেতরের সবকিছুকে কম বা বেশি দৃশ্যমান করতে (`opacity: 0.8;`) ব্যবহার করা হয়।

---

### 6. CSS Background (ব্যাকগ্রাউন্ড প্রপার্টিজ)

কোনো HTML Element-এর পেছনে Background Color বা Background Image সেট করার জন্য CSS Background Properties ব্যবহার করা হয়।
CSS-এর মাধ্যমে Background-এর রং, ছবি, ছবির অবস্থান, আকার এবং অন্যান্য বৈশিষ্ট্য নিয়ন্ত্রণ করা যায়।

### 6.1 Background Color

কোনো HTML Element-এর Background-এ রং সেট করার জন্য `background-color` Property ব্যবহার করা হয়।

**CSS Syntax:**
```css
body {
  background-color: #f4f4f4;
}
```

### ব্যাখ্যা:

- `background-color` হলো CSS Property
- `#f4f4f4` হলো Background Color-এর Value

### 6.2 Background Image

কোনো HTML Element-এর Background-এ ছবি সেট করার জন্য `background-image` Property ব্যবহার করা হয়।

**CSS Syntax:**
```
.hero {
  background-image: url('banner.jpg');
}
```

এখানে `url()` Function-এর মাধ্যমে ছবির Location বা Path উল্লেখ করা হয়েছে।

### 6.3 Background Repeat

Background Image বারবার প্রদর্শিত হবে কি না, তা নির্ধারণ করার জন্য `background-repeat` Property ব্যবহার করা হয়।

CSS Syntax:

```
.hero {
  background-image: url('pattern.png');
  background-repeat: no-repeat;
}
```

Common Values:

| Value       | কাজ                                                |
| ----------- | -------------------------------------------------- |
| `repeat`    | ছবিটি অনুভূমিক ও উল্লম্বভাবে বারবার প্রদর্শিত হবে। |
| `no-repeat` | ছবিটি একবারই প্রদর্শিত হবে।                        |
| `repeat-x`  | ছবিটি শুধু অনুভূমিকভাবে রিপিট হবে।                 |
| `repeat-y`  | ছবিটি শুধু উল্লম্বভাবে রিপিট হবে।                  |

### 6.4 Background Position

Background Image-এর অবস্থান নির্ধারণ করার জন্য `background-position` Property ব্যবহার করা হয়।

CSS Syntax:

```
.hero {
  background-image: url('banner.jpg');
  background-repeat: no-repeat;
  background-position: center;
}
```

Common Values:
- `center` — মাঝখানে অবস্থান করবে।
- `top` — উপরের দিকে অবস্থান করবে।
- `bottom` — নিচের দিকে অবস্থান করবে।
- `left` — বাম দিকে অবস্থান করবে।
- `right` — ডান দিকে অবস্থান করবে।
- `top left` — উপরের বাম দিকে অবস্থান করবে।
- `bottom right` — নিচের ডান দিকে অবস্থান করবে।

### 6.5 Background Size

Background Image-এর আকার নিয়ন্ত্রণ করার জন্য `background-size` Property ব্যবহার করা হয়।

CSS Syntax:

```
.hero {
  background-image: url('banner.jpg');
  background-size: cover;
}
```

Common Values:

| Value       | কাজ                                                            |
| ----------- | -------------------------------------------------------------- |
| `auto`      | ছবির Original Size বজায় রাখে।                                 |
| `cover`     | Element-এর পুরো Background Area ঢেকে দেয়।                     |
| `contain`   | ছবির সম্পূর্ণ অংশ দৃশ্যমান রাখে।                               |
| `100% 100%` | ছবিকে Element-এর সম্পূর্ণ Width ও Height অনুযায়ী Stretch করে। |

### Note:
- `cover` ব্যবহার করলে ছবির কিছু অংশ কেটে যেতে পারে।
- `contain` ব্যবহার করলে ছবির সম্পূর্ণ অংশ দেখা যায়, তবে কিছু জায়গা খালি থাকতে পারে।

### 6.6 Background Attachment

Page Scroll করার সময় Background Image স্থির থাকবে নাকি Scroll-এর সঙ্গে নড়বে, তা নির্ধারণ করার জন্য `background-attachment` Property ব্যবহার করা হয়।

CSS Syntax:

```
body {
  background-image: url('background.jpg');
  background-attachment: fixed;
}
```

Common Values:

| Value    | কাজ                                                                      |
| -------- | ------------------------------------------------------------------------ |
| `scroll` | Background Image Page-এর সঙ্গে Scroll করে।                               |
| `fixed`  | Background Image Viewport-এর তুলনায় স্থির থাকে।                         |
| `local`  | Element-এর নিজস্ব Content Scroll করলে Background-ও তার সঙ্গে Scroll করে। |

### 6.7 Background Shorthand

একাধিক Background Property আলাদাভাবে না লিখে একটি `background` Property-এর মাধ্যমে একসঙ্গে লেখা যায়। একে Background Shorthand বলা হয়।

CSS Syntax:

```
.hero {
  background: #000 url('bg.jpg') no-repeat center / cover fixed;
}
```

### ব্যাখ্যা:
- `#000` — Background Color।
- `url('bg.jpg')` — Background Image।
- `no-repeat` — Image Repeat হবে না।
- `center` — Image মাঝখানে থাকবে।
- `cover` — Background Area সম্পূর্ণ ঢেকে দেবে।
- `fixed` — Background Viewport-এর তুলনায় স্থির থাকবে।

### Note:
- Background Shorthand ব্যবহার করলে CSS Code ছোট ও পরিষ্কার হয়।
- সব Background Property Shorthand-এ দেওয়া বাধ্যতামূলক নয়।
- প্রয়োজন অনুযায়ী এক বা একাধিক Value ব্যবহার করা যায়।

````

## Background Properties-এর একটি গুরুত্বপূর্ণ বিষয়

একাধিক Background Image-ও ব্যবহার করা যায়। সেক্ষেত্রে কমা (`,`) দিয়ে প্রতিটি Image আলাদা করতে হয়।

```css
.hero {
  background-image: url('overlay.png'), url('banner.jpg');
  background-position: center, center;
  background-size: cover, cover;
  background-repeat: no-repeat, no-repeat;
}
````

এখানে প্রথম Image (`overlay.png`) উপরে এবং দ্বিতীয় Image (`banner.jpg`) তার নিচে প্রদর্শিত হবে। এটি Modern Web Design-এ বেশ কাজে লাগে।

---


## 7. CSS Units (সিএসএস একক বা মাপ)

CSS-এ কোনো HTML Element-এর Width, Height, Font Size, Margin, Padding এবং অন্যান্য Distance নির্ধারণ করার জন্য বিভিন্ন ধরনের Units ব্যবহার করা হয়।

CSS Units মূলত দুই ধরনের:

1. Absolute Units (নির্দিষ্ট একক)
2. Relative Units (আপেক্ষিক একক)

### 7.1 Absolute Units (অ্যাবসোলিউট ইউনিট)

Absolute Units ব্যবহার করে নির্দিষ্ট মাপ নির্ধারণ করা হয়। এগুলোর মাপ অন্য কোনো Element বা Parent-এর Font Size-এর ওপর নির্ভর করে না।

**Common Absolute Units:**

| Unit | নাম | ব্যবহার |
|---|---|---|
| `px` | Pixels | CSS-এ নির্দিষ্ট মাপ দেওয়ার জন্য |
| `cm` | Centimeters | সেন্টিমিটারে মাপ নির্ধারণ করতে |
| `mm` | Millimeters | মিলিমিটারে মাপ নির্ধারণ করতে |
| `in` | Inches | ইঞ্চিতে মাপ নির্ধারণ করতে |
| `pt` | Points | সাধারণত Print Design-এ |
| `pc` | Picas | Print Typography-তে |

**CSS Example:**

```css
.box {
  width: 300px;
  height: 200px;
  margin: 20px;
}
```

### 7.2 Relative Units (রিলেটিভ ইউনিট)

Relative Units ব্যবহার করে অন্য কোনো Element, Font Size অথবা Viewport-এর সাপেক্ষে মাপ নির্ধারণ করা হয়।

Responsive Web Design তৈরিতে Relative Units খুবই গুরুত্বপূর্ণ।

#### 1. Percentage (`%`)

কোনো Element-এর Parent Element-এর নির্দিষ্ট Dimension-এর সাপেক্ষে শতকরা মাপ নির্ধারণ করতে `%` ব্যবহার করা হয়।

**Example:**

```css
.parent {
  width: 500px;
}

.child {
  width: 50%;
}
```

**ব্যাখ্যা:** `.child` Element-এর Width হবে Parent-এর Width-এর 50%, অর্থাৎ 250px।

#### 2. EM (`em`)

`em` সাধারণত বর্তমান Element-এর Font Size-এর সাপেক্ষে মাপ নির্ধারণ করে।

**Example:**

```css
.parent {
  font-size: 16px;
}

.child {
  font-size: 2em;
}
```

**ব্যাখ্যা:** `.child`-এর Font Size হবে Parent-এর Font Size-এর দ্বিগুণ, অর্থাৎ 32px।

**মনে রাখবে:** `em`-এর আচরণ Property অনুযায়ী ভিন্ন হতে পারে। যেমন, `font-size`-এর ক্ষেত্রে এটি Parent-এর Font Size-এর ওপর নির্ভর করে, কিন্তু `padding` বা `margin`-এর ক্ষেত্রে এটি সংশ্লিষ্ট Element-এর Font Size-এর ওপর নির্ভর করে।

#### 3. REM (`rem`)

`rem` হলো Root EM। এটি HTML Document-এর Root Element (`<html>`) এর Font Size-এর সাপেক্ষে মাপ নির্ধারণ করে।

**Example:**

```css
html {
  font-size: 16px;
}

.heading {
  font-size: 2rem;
}
```

**ব্যাখ্যা:** `.heading`-এর Font Size হবে Root Font Size-এর দ্বিগুণ, অর্থাৎ 32px।

#### 4. VW (Viewport Width)

`vw` হলো Viewport Width। ব্রাউজারের Viewport-এর Width-এর 1% বোঝাতে `1vw` ব্যবহার করা হয়।

**Example:**

```css
.container {
  width: 50vw;
}
```

**ব্যাখ্যা:** Viewport-এর Width যদি 1000px হয়, তাহলে Container-এর Width হবে 500px।

#### 5. VH (Viewport Height)

`vh` হলো Viewport Height। ব্রাউজারের Viewport-এর Height-এর 1% বোঝাতে `1vh` ব্যবহার করা হয়।

**Example:**

```css
.hero {
  height: 100vh;
}
```

**ব্যাখ্যা:** `100vh` দ্বারা Element-এর Height Viewport-এর Height-এর সমান করা হয়।

#### 6. VMIN (Viewport Minimum)

`vmin` Viewport-এর Width ও Height-এর মধ্যে যেটি ছোট, তার 1% বোঝায়।

**Example:**

```css
.box {
  width: 50vmin;
}
```

#### 7. VMAX (Viewport Maximum)

`vmax` Viewport-এর Width ও Height-এর মধ্যে যেটি বড়, তার 1% বোঝায়।

**Example:**

```css
.box {
  width: 50vmax;
}
```

#### 8. CH (Character Unit)

`ch` হলো Font-এর `0` (শূন্য) Character-এর Width-এর সাপেক্ষে একটি Unit।

সাধারণত Text Content-এর Width নিয়ন্ত্রণ করতে এটি ব্যবহার করা হয়।

**Example:**

```css
p {
  max-width: 60ch;
}
```

#### 9. EX (X-height Unit)

`ex` হলো Font-এর ছোট হাতের `x` অক্ষরের উচ্চতার সাপেক্ষে একটি Unit।

**Example:**

```css
.box {
  width: 20ex;
}
```

### 7.3 CSS Units-এর তুলনা

| Unit | নির্ভরশীলতা | সাধারণ ব্যবহার |
|---|---|---|
| `px` | নির্দিষ্ট CSS মাপ | Border, Width, Height |
| `%` | Parent বা সংশ্লিষ্ট Dimension | Responsive Width |
| `em` | Font Size | Padding, Margin, Font Size |
| `rem` | Root Font Size | Typography, Spacing |
| `vw` | Viewport Width | Responsive Width |
| `vh` | Viewport Height | Full Screen Section |
| `vmin` | Viewport-এর ছোট Dimension | Responsive Sizing |
| `vmax` | Viewport-এর বড় Dimension | Responsive Sizing |
| `ch` | `0` Character-এর Width | Text Width |
| `ex` | `x` Character-এর Height | Typography |

### 7.4 Practical Example

```css
html {
  font-size: 16px;
}

.container {
  width: 80%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
}

.heading {
  font-size: 2rem;
}

.description {
  font-size: 1em;
  max-width: 60ch;
}

.hero {
  min-height: 100vh;
}
```

### Note:

- `px` নির্দিষ্ট CSS মাপের জন্য ব্যবহার করা হয়।
- `%` Parent বা সংশ্লিষ্ট Dimension-এর সাপেক্ষে কাজ করে।
- `em` ও `rem` Font Size-এর সঙ্গে সম্পর্কিত।
- `vw` ও `vh` Viewport-এর সাইজের ওপর নির্ভর করে।
- Responsive Design তৈরিতে Relative Units খুবই গুরুত্বপূর্ণ।
- আধুনিক Web Development-এ `rem`, `%`, `vw`, `vh` এবং `ch` বেশ কার্যকর।

---

## 🎯 Phase 01 Practice Projects (যে প্রজেক্টগুলো নিজে তৈরি করবেন)

এই টপিকগুলো শেখার পর এই ৩টি ছোট প্রজেক্ট কোড করে ফেলবেন:

1. **Personal Profile Card:** একটি সুন্দর কার্ড যেখানে আপনার ছবি, নাম, পেশা এবং একটি সোশ্যাল মিডিয়া বাটন থাকবে (Element, Class Selector, Box Model ও Background প্র্যাকটিসের জন্য)।
2. **Simple Profile Page:** একটি সাধারণ ওয়েব পেজ যেখানে হেডার, বায়োগ্রাফি এবং কিছু সেকশন থাকবে।
3. **Colorful Webpage:** বিভিন্ন কালার, ব্যাকগ্রাউন্ড ইমেজ এবং গ্রেডিয়েন্ট ব্যবহার করে একটি রঙিন ও আকর্ষণীয় পেজ।
