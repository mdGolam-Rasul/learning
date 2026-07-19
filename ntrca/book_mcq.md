# ICT Lecturer MCQ - Corrected, Deduplicated and Explained Edition

## Final Correction Summary

- Source: uploaded 60-page scanned PDF.
- Broken Markdown, hidden control characters, malformed code blocks এবং raw OCR noise বাদ দেওয়া হয়েছে।
- Source page দেখে damaged question, option এবং printed answer marker সংশোধন করা হয়েছে।
- Exact/semantic duplicate সরিয়ে নতুন ধারাবাহিক serial দেওয়া হয়েছে।
- কোনো `Review Needed` block রাখা হয়নি। যে fragment নির্ভরযোগ্যভাবে উদ্ধার করা যায়নি, সেটি ভুল তথ্য বানানোর বদলে removal audit-এ রাখা হয়েছে।

```text
Original candidate MCQs       = 157
Manually removed duplicates   = 4
Unrecoverable/ambiguous removed= 3
Auto exact duplicates removed = 0
Final clean unique MCQs        = 150
Review Needed                  = 0
```

> গুরুত্বপূর্ণ: Source scan-এর বাইরে নতুন প্রশ্ন তৈরি করা হয়নি। কিছু textbook-style statement-এ standard caveat (যেমন C `int` size, `inline`, default constructor) explanation-এ যোগ করা হয়েছে।

---

# Section - Programming Fundamentals and OOP

এই অংশে language paradigm, C data type, array, pointer, function, loop এবং OOP রয়েছে।

---

## MCQ 0001

**Source:** Page 1; original no. 1  
**Original retained serial:** 0001  
**Topic:** Program  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

কম্পিউটারকে দেওয়া সুনির্দিষ্ট নির্দেশের সেটকে কী বলা হয়?

### Options

- **(ক)** সফটওয়্যার
- **(খ)** ডাটা
- **(গ)** প্রোগ্রাম
- **(ঘ)** হার্ডওয়্যার

### সঠিক উত্তর

**(গ) প্রোগ্রাম**

### কেন সঠিক

Program হলো computer-কে কোনো কাজ করানোর জন্য ধারাবাহিক ও সুনির্দিষ্ট instruction-এর সমষ্টি। Software একটি বৃহত্তর ধারণা; একটি software system-এ program, data, configuration ও documentation থাকতে পারে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) সফটওয়্যার:** Software হলো program, data ও related resource-এর বৃহত্তর সমষ্টি। কিন্তু এই প্রশ্নে চাওয়া Program-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(খ) ডাটা:** Data হলো program যে তথ্য process করে; instruction set নয়। কিন্তু এই প্রশ্নে চাওয়া Program-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(গ) প্রোগ্রাম:** এটি সঠিক উত্তর।
- ❌ **(ঘ) হার্ডওয়্যার:** Hardware হলো physical component। কিন্তু এই প্রশ্নে চাওয়া Program-এর নির্দিষ্ট শর্ত পূরণ করে না।

### সহজ Analogy

রান্নার recipe যেমন ধাপে ধাপে কী করতে হবে বলে, program computer-কে তেমন নির্দেশ দেয়।

### Memory Tip

**Instruction-এর set = Program।**

### Related Concepts

Software, Algorithm, Source Code

---

## MCQ 0002

**Source:** Page 1; original no. 2  
**Original retained serial:** 0002  
**Topic:** Programming Language Level  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

নিচের কোনটি Low-level Language?

### Options

- **(ক)** Java
- **(খ)** C++
- **(গ)** মেশিন ভাষা
- **(ঘ)** Python

### সঠিক উত্তর

**(গ) মেশিন ভাষা**

### কেন সঠিক

Machine Language processor-এর binary instruction সরাসরি প্রকাশ করে এবং hardware architecture-এর সবচেয়ে কাছাকাছি থাকে। Assembly-ও low-level, তবে mnemonic ব্যবহার করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Java:** এটি একটি programming language, তবে প্রশ্নে চাওয়া paradigm/level-এর সঙ্গে মেলে না। কিন্তু এই প্রশ্নে চাওয়া Programming Language Level-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(খ) C++:** এটি একটি programming language, তবে প্রশ্নে চাওয়া paradigm/level-এর সঙ্গে মেলে না। কিন্তু এই প্রশ্নে চাওয়া Programming Language Level-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(গ) মেশিন ভাষা:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Python:** এটি একটি programming language, তবে প্রশ্নে চাওয়া paradigm/level-এর সঙ্গে মেলে না। কিন্তু এই প্রশ্নে চাওয়া Programming Language Level-এর নির্দিষ্ট শর্ত পূরণ করে না।

### সহজ Analogy

মানুষের অনুবাদ করা ভাষার বদলে যন্ত্রের নিজস্ব সংকেতে কথা বলার মতো।

### Memory Tip

**Machine = binary; Assembly = mnemonic।**

### Related Concepts

Assembler, Compiler, Machine Code

---

## MCQ 0003

**Source:** Page 1; original no. 3  
**Original retained serial:** 0003  
**Topic:** Structured Programming  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

C কোন ধরনের প্রোগ্রামিং ভাষা?

### Options

- **(ক)** স্ক্রিপ্টিং
- **(খ)** লজিক
- **(গ)** স্ট্রাকচার্ড
- **(ঘ)** ফাংশনাল

### সঠিক উত্তর

**(গ) স্ট্রাকচার্ড**

### কেন সঠিক

Structured Programming program-কে function/module এবং sequence-selection-iteration control structure-এ ভাগ করে। Top-down design বড় problemকে ধাপে ধাপে ছোট module-এ ভাঙে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) স্ক্রিপ্টিং:** এই optionটি `স্ট্রাকচার্ড`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Structured Programming প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) লজিক:** এই optionটি `স্ট্রাকচার্ড`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Structured Programming প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) স্ট্রাকচার্ড:** এটি সঠিক উত্তর।
- ❌ **(ঘ) ফাংশনাল:** এই optionটি `স্ট্রাকচার্ড`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Structured Programming প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

বড় projectকে department ও ছোট task-এ ভাগ করার মতো।

### Memory Tip

**Structured → Function + Top-down।**

### Related Concepts

Function, Module, Control Structure

---

## MCQ 0004

**Source:** Page 1; original no. 4  
**Original retained serial:** 0004  
**Topic:** Scripting Language  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

JavaScript কোন ধরনের ভাষার উদাহরণ?

### Options

- **(ক)** স্ক্রিপ্টিং
- **(খ)** মেশিন ভাষা
- **(গ)** Assembly
- **(ঘ)** Low-level

### সঠিক উত্তর

**(ক) স্ক্রিপ্টিং**

### কেন সঠিক

JavaScript ঐতিহাসিকভাবে scripting language হিসেবে পরিচিত এবং browser-এ dynamic behavior তৈরি করে। আধুনিক JavaScript পূর্ণাঙ্গ general-purpose language হিসেবেও ব্যবহৃত হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) স্ক্রিপ্টিং:** এটি সঠিক উত্তর।
- ❌ **(খ) মেশিন ভাষা:** এই optionটি `স্ক্রিপ্টিং`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Scripting Language প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) Assembly:** এটি একটি programming language, তবে প্রশ্নে চাওয়া paradigm/level-এর সঙ্গে মেলে না। কিন্তু এই প্রশ্নে চাওয়া Scripting Language-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(ঘ) Low-level:** এই optionটি `স্ক্রিপ্টিং`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Scripting Language প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Static webpage-কে নড়াচড়া ও প্রতিক্রিয়া দেওয়ার remote control-এর মতো।

### Memory Tip

**HTML structure, CSS style, JavaScript behavior।**

### Related Concepts

ECMAScript, Browser, Node.js

---

## MCQ 0005

**Source:** Page 1; original no. 5  
**Original retained serial:** 0005  
**Topic:** Logic Programming  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Logic-এর ওপর ভিত্তি করে কাজ করে নিচের কোনটি?

### Options

- **(ক)** Pascal
- **(খ)** Prolog
- **(গ)** Haskell
- **(ঘ)** Java

### সঠিক উত্তর

**(খ) Prolog**

### কেন সঠিক

Prolog fact ও rule-এর ওপর logical inference চালায়। Programmer কী সত্য এবং কী rule তা বলে; system query-এর solution অনুসন্ধান করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Pascal:** এটি একটি programming language, তবে প্রশ্নে চাওয়া paradigm/level-এর সঙ্গে মেলে না। কিন্তু এই প্রশ্নে চাওয়া Logic Programming-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(খ) Prolog:** এটি সঠিক উত্তর।
- ❌ **(গ) Haskell:** এটি একটি programming language, তবে প্রশ্নে চাওয়া paradigm/level-এর সঙ্গে মেলে না। কিন্তু এই প্রশ্নে চাওয়া Logic Programming-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(ঘ) Java:** এটি একটি programming language, তবে প্রশ্নে চাওয়া paradigm/level-এর সঙ্গে মেলে না। কিন্তু এই প্রশ্নে চাওয়া Logic Programming-এর নির্দিষ্ট শর্ত পূরণ করে না।

### সহজ Analogy

গোয়েন্দাকে facts ও rules দিলে সে conclusion বের করে—Prologও তেমন।

### Memory Tip

**Logic Programming → Prolog।**

### Related Concepts

Fact, Rule, Inference

---

## MCQ 0006

**Source:** Page 1; original no. 6  
**Original retained serial:** 0006  
**Topic:** Functional Programming  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

নিচের কোনটি Functional Programming Language-এর উদাহরণ?

### Options

- **(ক)** C
- **(খ)** COBOL
- **(গ)** Haskell
- **(ঘ)** C++

### সঠিক উত্তর

**(গ) Haskell**

### কেন সঠিক

Functional Programming computationকে function evaluation হিসেবে দেখে। Pure function, immutability ও expression composition গুরুত্বপূর্ণ; Haskell এর একটি প্রধান উদাহরণ।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) C:** এই optionটি `Haskell`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Functional Programming প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) COBOL:** এটি একটি programming language, তবে প্রশ্নে চাওয়া paradigm/level-এর সঙ্গে মেলে না। কিন্তু এই প্রশ্নে চাওয়া Functional Programming-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(গ) Haskell:** এটি সঠিক উত্তর।
- ❌ **(ঘ) C++:** এটি একটি programming language, তবে প্রশ্নে চাওয়া paradigm/level-এর সঙ্গে মেলে না। কিন্তু এই প্রশ্নে চাওয়া Functional Programming-এর নির্দিষ্ট শর্ত পূরণ করে না।

### সহজ Analogy

একই formula-তে একই input দিলে একই output পাওয়ার মতো।

### Memory Tip

**Functional → Haskell; Logic → Prolog।**

### Related Concepts

Pure Function, Immutability, Higher-order Function

---

## MCQ 0007

**Source:** Page 1; original no. 7  
**Original retained serial:** 0007  
**Topic:** Structured Programming  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Structured Programming-এ program-কে কিসে ভাগ করা হয়?

### Options

- **(ক)** Object
- **(খ)** Function
- **(গ)** Class
- **(ঘ)** Data

### সঠিক উত্তর

**(খ) Function**

### কেন সঠিক

Structured Programming program-কে function/module এবং sequence-selection-iteration control structure-এ ভাগ করে। Top-down design বড় problemকে ধাপে ধাপে ছোট module-এ ভাঙে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Object:** এই optionটি `Function`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Structured Programming প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Function:** এটি সঠিক উত্তর।
- ❌ **(গ) Class:** এই optionটি `Function`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Structured Programming প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Data:** Data হলো program যে তথ্য process করে; instruction set নয়। কিন্তু এই প্রশ্নে চাওয়া Structured Programming-এর নির্দিষ্ট শর্ত পূরণ করে না।

### সহজ Analogy

বড় projectকে department ও ছোট task-এ ভাগ করার মতো।

### Memory Tip

**Structured → Function + Top-down।**

### Related Concepts

Function, Module, Control Structure

---

## MCQ 0008

**Source:** Page 1; original no. 8  
**Original retained serial:** 0008  
**Topic:** Encapsulation  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Data Hiding বা Encapsulation নিচের কোনটিতে থাকে?

### Options

- **(ক)** Structured Programming
- **(খ)** Object-Oriented Programming
- **(গ)** Machine Language
- **(ঘ)** Assembly Language

### সঠিক উত্তর

**(খ) Object-Oriented Programming**

### কেন সঠিক

Encapsulation data ও behaviorকে এক unit-এ রাখে এবং access modifier দিয়ে internal state-এর সরাসরি ব্যবহার সীমিত করে। এটি data protection ও controlled interface দেয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Structured Programming:** এই optionটি `Object-Oriented Programming`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Encapsulation প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Object-Oriented Programming:** এটি সঠিক উত্তর।
- ❌ **(গ) Machine Language:** এই optionটি `Object-Oriented Programming`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Encapsulation প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Assembly Language:** এটি একটি programming language, তবে প্রশ্নে চাওয়া paradigm/level-এর সঙ্গে মেলে না। কিন্তু এই প্রশ্নে চাওয়া Encapsulation-এর নির্দিষ্ট শর্ত পূরণ করে না।

### সহজ Analogy

Capsule-এর ভেতরে ওষুধ সুরক্ষিত থাকে; বাইরে শুধু capsule ব্যবহার করা হয়।

### Memory Tip

**Bundle + restrict access = Encapsulation।**

### Related Concepts

Class, Access Modifier, Data Hiding

---

## MCQ 0009

**Source:** Page 1; original no. 9  
**Original retained serial:** 0009  
**Topic:** Structured Programming  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

কোন Programming Approach 'Top-Down' পদ্ধতি অনুসরণ করে?

### Options

- **(ক)** OOP
- **(খ)** Functional
- **(গ)** Structured
- **(ঘ)** Logic

### সঠিক উত্তর

**(গ) Structured**

### কেন সঠিক

Structured Programming program-কে function/module এবং sequence-selection-iteration control structure-এ ভাগ করে। Top-down design বড় problemকে ধাপে ধাপে ছোট module-এ ভাঙে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) OOP:** এই optionটি `Structured`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Structured Programming প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) Functional:** এই optionটি `Structured`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Structured Programming প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) Structured:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Logic:** এই optionটি `Structured`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Structured Programming প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

বড় projectকে department ও ছোট task-এ ভাগ করার মতো।

### Memory Tip

**Structured → Function + Top-down।**

### Related Concepts

Function, Module, Control Structure

---

## MCQ 0010

**Source:** Page 1; original no. 10  
**Original retained serial:** 0010  
**Topic:** Variable and Identifier  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

মেমরির নামযুক্ত স্থান যেখানে মান জমা থাকে তাকে কী বলে?

### Options

- **(ক)** Constant
- **(খ)** Variable
- **(গ)** Operator
- **(ঘ)** Token

### সঠিক উত্তর

**(খ) Variable**

### কেন সঠিক

Variable হলো নামযুক্ত memory location; identifier হলো variable/function/class-এর বৈধ নাম। C identifier digit দিয়ে শুরু হতে পারে না এবং keyword যেমন `for` নাম হিসেবে ব্যবহার করা যায় না।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Constant:** এই optionটি `Variable`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Variable and Identifier প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Variable:** এটি সঠিক উত্তর।
- ❌ **(গ) Operator:** এই optionটি `Variable`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Variable and Identifier প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Token:** এই optionটি `Variable`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Variable and Identifier প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

লেবেলযুক্ত বাক্স: label হলো identifier, ভেতরের বস্তু হলো value।

### Memory Tip

**Letter/underscore দিয়ে শুরু; keyword নয়।**

### Related Concepts

Keyword, Scope, Data Type

---

## MCQ 0011

**Source:** Page 1; original no. 11  
**Original retained serial:** 0011  
**Topic:** Variable and Identifier  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Variable-এর নাম শুরু করার জন্য কোনটি বৈধ?

### Options

- **(ক)** সংখ্যা
- **(খ)** Space
- **(গ)** Underscore
- **(ঘ)** ভগ্নাংশ

### সঠিক উত্তর

**(গ) Underscore**

### কেন সঠিক

Variable হলো নামযুক্ত memory location; identifier হলো variable/function/class-এর বৈধ নাম। C identifier digit দিয়ে শুরু হতে পারে না এবং keyword যেমন `for` নাম হিসেবে ব্যবহার করা যায় না।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) সংখ্যা:** এই optionটি `Underscore`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Variable and Identifier প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) Space:** এই optionটি `Underscore`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Variable and Identifier প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) Underscore:** এটি সঠিক উত্তর।
- ❌ **(ঘ) ভগ্নাংশ:** এই optionটি `Underscore`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Variable and Identifier প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

লেবেলযুক্ত বাক্স: label হলো identifier, ভেতরের বস্তু হলো value।

### Memory Tip

**Letter/underscore দিয়ে শুরু; keyword নয়।**

### Related Concepts

Keyword, Scope, Data Type

---

## MCQ 0012

**Source:** Page 2; original no. 12  
**Original retained serial:** 0012  
**Topic:** Variable and Identifier  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

নিচের কোনটি Variable-এর নাম হিসেবে ব্যবহার করা যাবে না?

### Options

- **(ক)** _name
- **(খ)** age25
- **(গ)** for
- **(ঘ)** total_sum

### সঠিক উত্তর

**(গ) for**

### কেন সঠিক

Variable হলো নামযুক্ত memory location; identifier হলো variable/function/class-এর বৈধ নাম। C identifier digit দিয়ে শুরু হতে পারে না এবং keyword যেমন `for` নাম হিসেবে ব্যবহার করা যায় না।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) _name:** এই optionটি `for`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Variable and Identifier প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) age25:** এই optionটি `for`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Variable and Identifier প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) for:** এটি সঠিক উত্তর।
- ❌ **(ঘ) total_sum:** এই optionটি `for`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Variable and Identifier প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

লেবেলযুক্ত বাক্স: label হলো identifier, ভেতরের বস্তু হলো value।

### Memory Tip

**Letter/underscore দিয়ে শুরু; keyword নয়।**

### Related Concepts

Keyword, Scope, Data Type

---

## MCQ 0013

**Source:** Page 2; original no. 13  
**Original retained serial:** 0013  
**Topic:** C Data Types  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

C ভাষায় `int` data type সাধারণত কত memory দখল করে?

### Options

- **(ক)** 1 byte
- **(খ)** 2 bytes
- **(গ)** 4 bytes
- **(ঘ)** 8 bytes

### সঠিক উত্তর

**(গ) 4 bytes**

### কেন সঠিক

Data type value-এর representation, storage ও valid operation নির্ধারণ করে। C-তে `char`-এর size সংজ্ঞা অনুযায়ী 1 byte; `int`-এর exact byte implementation-dependent, যদিও অনেক system-এ 4 byte। `%f` floating output/input contextে ব্যবহৃত হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) 1 byte:** এই optionটি `4 bytes`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Data Types প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) 2 bytes:** এই optionটি `4 bytes`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Data Types প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) 4 bytes:** এটি সঠিক উত্তর।
- ❌ **(ঘ) 8 bytes:** এই optionটি `4 bytes`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Data Types প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

বিভিন্ন মাপের container-এ বিভিন্ন ধরনের data রাখার মতো।

### Memory Tip

**`char` = 1 byte; exact `int` size platform দেখে।**

### Related Concepts

sizeof, Format Specifier, Portability

---

## MCQ 0014

**Source:** Page 2; original no. 14  
**Original retained serial:** 0014  
**Topic:** C Data Types  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

ভগ্নাংশ বা দশমিক মান সংরক্ষণের জন্য কোন data type ব্যবহৃত হয়?

### Options

- **(ক)** int
- **(খ)** char
- **(গ)** float
- **(ঘ)** long

### সঠিক উত্তর

**(গ) float**

### কেন সঠিক

Data type value-এর representation, storage ও valid operation নির্ধারণ করে। C-তে `char`-এর size সংজ্ঞা অনুযায়ী 1 byte; `int`-এর exact byte implementation-dependent, যদিও অনেক system-এ 4 byte। `%f` floating output/input contextে ব্যবহৃত হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) int:** এই optionটি `float`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Data Types প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) char:** এই optionটি `float`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Data Types প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) float:** এটি সঠিক উত্তর।
- ❌ **(ঘ) long:** এই optionটি `float`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Data Types প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

বিভিন্ন মাপের container-এ বিভিন্ন ধরনের data রাখার মতো।

### Memory Tip

**`char` = 1 byte; exact `int` size platform দেখে।**

### Related Concepts

sizeof, Format Specifier, Portability

---

## MCQ 0015

**Source:** Page 2; original no. 15  
**Original retained serial:** 0015  
**Topic:** C Data Types  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Character (`char`) data type-এর size কত?

### Options

- **(ক)** 1 byte
- **(খ)** 2 bytes
- **(গ)** 4 bytes
- **(ঘ)** 8 bytes

### সঠিক উত্তর

**(ক) 1 byte**

### কেন সঠিক

Data type value-এর representation, storage ও valid operation নির্ধারণ করে। C-তে `char`-এর size সংজ্ঞা অনুযায়ী 1 byte; `int`-এর exact byte implementation-dependent, যদিও অনেক system-এ 4 byte। `%f` floating output/input contextে ব্যবহৃত হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) 1 byte:** এটি সঠিক উত্তর।
- ❌ **(খ) 2 bytes:** এই optionটি `1 byte`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Data Types প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) 4 bytes:** এই optionটি `1 byte`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Data Types প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) 8 bytes:** এই optionটি `1 byte`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Data Types প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

বিভিন্ন মাপের container-এ বিভিন্ন ধরনের data রাখার মতো।

### Memory Tip

**`char` = 1 byte; exact `int` size platform দেখে।**

### Related Concepts

sizeof, Format Specifier, Portability

---

## MCQ 0016

**Source:** Page 2; original no. 16  
**Original retained serial:** 0016  
**Topic:** C Data Types  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

`float` data type-এর format specifier কোনটি?

### Options

- **(ক)** `%d`
- **(খ)** `%c`
- **(গ)** `%f`
- **(ঘ)** `%s`

### সঠিক উত্তর

**(গ) `%f`**

### কেন সঠিক

Data type value-এর representation, storage ও valid operation নির্ধারণ করে। C-তে `char`-এর size সংজ্ঞা অনুযায়ী 1 byte; `int`-এর exact byte implementation-dependent, যদিও অনেক system-এ 4 byte। `%f` floating output/input contextে ব্যবহৃত হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) `%d`:** এই optionটি `%f`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Data Types প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) `%c`:** এই optionটি `%f`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Data Types প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) `%f`:** এটি সঠিক উত্তর।
- ❌ **(ঘ) `%s`:** এই optionটি `%f`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Data Types প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

বিভিন্ন মাপের container-এ বিভিন্ন ধরনের data রাখার মতো।

### Memory Tip

**`char` = 1 byte; exact `int` size platform দেখে।**

### Related Concepts

sizeof, Format Specifier, Portability

---

## MCQ 0017

**Source:** Page 2; original no. 17  
**Original retained serial:** 0017  
**Topic:** Array and String  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

একই data type-এর একাধিক মানকে ধারাবাহিকভাবে সাজানোকে কী বলে?

### Options

- **(ক)** Pointer
- **(খ)** Array
- **(গ)** Structure
- **(ঘ)** Function

### সঠিক উত্তর

**(খ) Array**

### কেন সঠিক

Array একই data type-এর element contiguous memory-তে রাখে এবং C-তে index 0 থেকে শুরু হয়। C String হলো null-terminated character array।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Pointer:** এই optionটি `Array`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array and String প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Array:** এটি সঠিক উত্তর।
- ❌ **(গ) Structure:** এই optionটি `Array`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array and String প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Function:** এই optionটি `Array`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array and String প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

এক সারিতে নম্বর দেওয়া locker—প্রথম locker-এর নম্বর 0।

### Memory Tip

**Array contiguous; C String ends with `\0`।**

### Related Concepts

Pointer, Bounds, Character Array

---

## MCQ 0018

**Source:** Page 2; original no. 18  
**Original retained serial:** 0018  
**Topic:** Array and String  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Array-এর index কত থেকে শুরু হয়?

### Options

- **(ক)** `1`
- **(খ)** -1
- **(গ)** `0`
- **(ঘ)** ইচ্ছামতো

### সঠিক উত্তর

**(গ) `0`**

### কেন সঠিক

Array একই data type-এর element contiguous memory-তে রাখে এবং C-তে index 0 থেকে শুরু হয়। C String হলো null-terminated character array।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) `1`:** এই optionটি `0`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array and String প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) -1:** এই optionটি `0`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array and String প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) `0`:** এটি সঠিক উত্তর।
- ❌ **(ঘ) ইচ্ছামতো:** এই optionটি `0`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array and String প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

এক সারিতে নম্বর দেওয়া locker—প্রথম locker-এর নম্বর 0।

### Memory Tip

**Array contiguous; C String ends with `\0`।**

### Related Concepts

Pointer, Bounds, Character Array

---

## MCQ 0019

**Source:** Page 2; original no. 19  
**Original retained serial:** 0019  
**Topic:** Array and String  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

String আসলে কিসের Array?

### Options

- **(ক)** Integer
- **(খ)** Float
- **(গ)** Character
- **(ঘ)** Double

### সঠিক উত্তর

**(গ) Character**

### কেন সঠিক

Array একই data type-এর element contiguous memory-তে রাখে এবং C-তে index 0 থেকে শুরু হয়। C String হলো null-terminated character array।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Integer:** এই optionটি `Character`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array and String প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) Float:** এই optionটি `Character`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array and String প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) Character:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Double:** এই optionটি `Character`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array and String প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

এক সারিতে নম্বর দেওয়া locker—প্রথম locker-এর নম্বর 0।

### Memory Tip

**Array contiguous; C String ends with `\0`।**

### Related Concepts

Pointer, Bounds, Character Array

---

## MCQ 0020

**Source:** Page 2; original no. 20  
**Original retained serial:** 0020  
**Topic:** C Operators  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

নিচের কোনটি Arithmetic Operator?

### Options

- **(ক)** `&&`
- **(খ)** `<`
- **(গ)** %
- **(ঘ)** `==`

### সঠিক উত্তর

**(গ) %**

### কেন সঠিক

Operator operand-এর ওপর কাজ করে। `%` remainder দেয়, Relational operator তুলনা করে, `&&` logical AND এবং `--` এক কমায়। Bitwise AND প্রতিটি bit pair-এ AND চালায়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) `&&`:** এই optionটি `%`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Operators প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) `<`:** এই optionটি `%`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Operators প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) %:** এটি সঠিক উত্তর।
- ❌ **(ঘ) `==`:** এই optionটি `%`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Operators প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Calculator-এর বিভিন্ন button যেমন ভিন্ন operation করে।

### Memory Tip

**Logical `&&`; Bitwise `&`; Address-of `&` context দেখে।**

### Related Concepts

Precedence, Associativity, Boolean Expression

---

## MCQ 0021

**Source:** Page 2; original no. 21  
**Original retained serial:** 0021  
**Topic:** C Operators  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

দুটি মানের মধ্যে তুলনা করার জন্য কোন operator ব্যবহৃত হয়?

### Options

- **(ক)** Arithmetic
- **(খ)** Relational
- **(গ)** Logical
- **(ঘ)** Unary

### সঠিক উত্তর

**(খ) Relational**

### কেন সঠিক

Operator operand-এর ওপর কাজ করে। `%` remainder দেয়, Relational operator তুলনা করে, `&&` logical AND এবং `--` এক কমায়। Bitwise AND প্রতিটি bit pair-এ AND চালায়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Arithmetic:** এই optionটি `Relational`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Operators প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Relational:** এটি সঠিক উত্তর।
- ❌ **(গ) Logical:** এই optionটি `Relational`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Operators প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Unary:** এই optionটি `Relational`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Operators প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Calculator-এর বিভিন্ন button যেমন ভিন্ন operation করে।

### Memory Tip

**Logical `&&`; Bitwise `&`; Address-of `&` context দেখে।**

### Related Concepts

Precedence, Associativity, Boolean Expression

---

## MCQ 0022

**Source:** Page 2; original no. 22  
**Original retained serial:** 0022  
**Topic:** C Operators  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

`&&` কোন ধরনের operator?

### Options

- **(ক)** Logical AND
- **(খ)** Logical OR
- **(গ)** Bitwise AND
- **(ঘ)** Relational

### সঠিক উত্তর

**(ক) Logical AND**

### কেন সঠিক

Operator operand-এর ওপর কাজ করে। `%` remainder দেয়, Relational operator তুলনা করে, `&&` logical AND এবং `--` এক কমায়। Bitwise AND প্রতিটি bit pair-এ AND চালায়।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) Logical AND:** এটি সঠিক উত্তর।
- ❌ **(খ) Logical OR:** এই optionটি `Logical AND`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Operators প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) Bitwise AND:** এই optionটি `Logical AND`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Operators প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Relational:** এই optionটি `Logical AND`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Operators প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Calculator-এর বিভিন্ন button যেমন ভিন্ন operation করে।

### Memory Tip

**Logical `&&`; Bitwise `&`; Address-of `&` context দেখে।**

### Related Concepts

Precedence, Associativity, Boolean Expression

---

## MCQ 0023

**Source:** Page 2; original no. 23  
**Original retained serial:** 0023  
**Topic:** C Operators  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Variable-এর মান 1 কমাতে কোন Decrement operator ব্যবহৃত হয়?

### Options

- **(ক)** `++`
- **(খ)** `--`
- **(গ)** +=
- **(ঘ)** -=

### সঠিক উত্তর

**(খ) `--`**

### কেন সঠিক

Operator operand-এর ওপর কাজ করে। `%` remainder দেয়, Relational operator তুলনা করে, `&&` logical AND এবং `--` এক কমায়। Bitwise AND প্রতিটি bit pair-এ AND চালায়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) `++`:** এটি সঠিক উত্তর।
- ✅ **(খ) `--`:** এটি সঠিক উত্তর।
- ❌ **(গ) +=:** এটি সঠিক উত্তর।
- ❌ **(ঘ) -=:** এটি সঠিক উত্তর।

### সহজ Analogy

Calculator-এর বিভিন্ন button যেমন ভিন্ন operation করে।

### Memory Tip

**Logical `&&`; Bitwise `&`; Address-of `&` context দেখে।**

### Related Concepts

Precedence, Associativity, Boolean Expression

---

## MCQ 0024

**Source:** Page 2; original no. 24  
**Original retained serial:** 0024  
**Topic:** Pointer  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Pointer কী সংরক্ষণ করে?

### Options

- **(ক)** Data Value
- **(খ)** Memory Address
- **(গ)** File Name
- **(ঘ)** Function Name

### সঠিক উত্তর

**(খ) Memory Address**

### কেন সঠিক

Pointer একটি memory address ধারণ করে। `&` address নেয়, `*` dereference করে এবং `->` pointer-to-object/struct member access করে। C সব argument value হিসেবে pass করে; pointer value pass করে reference-like পরিবর্তন করা যায়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Data Value:** এই optionটি `Memory Address`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Pointer প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Memory Address:** এটি সঠিক উত্তর।
- ❌ **(গ) File Name:** এই optionটি `Memory Address`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Pointer প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Function Name:** এই optionটি `Memory Address`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Pointer প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

বাড়ি নয়, বাড়ির ঠিকানা লেখা কাগজ—Pointer সেই ঠিকানা।

### Memory Tip

**`&` address; `*` value-at-address; `->` pointer member।**

### Related Concepts

NULL, Dangling Pointer, malloc

---

## MCQ 0025

**Source:** Page 2; original no. 25  
**Original retained serial:** 0025  
**Topic:** Pointer  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

কোনো Variable-এর Memory Address পাওয়ার জন্য কোন operator ব্যবহৃত হয়?

### Options

- **(ক)** `*`
- **(খ)** `&`
- **(গ)** %
- **(ঘ)** #

### সঠিক উত্তর

**(খ) `&`**

### কেন সঠিক

Pointer একটি memory address ধারণ করে। `&` address নেয়, `*` dereference করে এবং `->` pointer-to-object/struct member access করে। C সব argument value হিসেবে pass করে; pointer value pass করে reference-like পরিবর্তন করা যায়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) `*`:** এই optionটি `&`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Pointer প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) `&`:** এটি সঠিক উত্তর।
- ❌ **(গ) %:** এই optionটি `&`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Pointer প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) #:** এই optionটি `&`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Pointer প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

বাড়ি নয়, বাড়ির ঠিকানা লেখা কাগজ—Pointer সেই ঠিকানা।

### Memory Tip

**`&` address; `*` value-at-address; `->` pointer member।**

### Related Concepts

NULL, Dangling Pointer, malloc

---

## MCQ 0026

**Source:** Page 2; original no. 26  
**Original retained serial:** 0026  
**Topic:** Pointer  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Dereference operator কোনটি?

### Options

- **(ক)** `&`
- **(খ)** `*`
- **(গ)** `->`
- **(ঘ)** .

### সঠিক উত্তর

**(খ) `*`**

### কেন সঠিক

Pointer একটি memory address ধারণ করে। `&` address নেয়, `*` dereference করে এবং `->` pointer-to-object/struct member access করে। C সব argument value হিসেবে pass করে; pointer value pass করে reference-like পরিবর্তন করা যায়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) `&`:** এই optionটি `*`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Pointer প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) `*`:** এটি সঠিক উত্তর।
- ❌ **(গ) `->`:** এটি সঠিক উত্তর।
- ❌ **(ঘ) .:** এটি সঠিক উত্তর।

### সহজ Analogy

বাড়ি নয়, বাড়ির ঠিকানা লেখা কাগজ—Pointer সেই ঠিকানা।

### Memory Tip

**`&` address; `*` value-at-address; `->` pointer member।**

### Related Concepts

NULL, Dangling Pointer, malloc

---

## MCQ 0027

**Source:** Page 2; original no. 27  
**Original retained serial:** 0027  
**Topic:** Pointer  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Pointer যখন কোনো ঠিকানাকে নির্দেশ করে না তখন তাকে কী বলে?

### Options

- **(ক)** Empty Pointer
- **(খ)** Void Pointer
- **(গ)** NULL Pointer
- **(ঘ)** Zero Pointer

### সঠিক উত্তর

**(গ) NULL Pointer**

### কেন সঠিক

Pointer একটি memory address ধারণ করে। `&` address নেয়, `*` dereference করে এবং `->` pointer-to-object/struct member access করে। C সব argument value হিসেবে pass করে; pointer value pass করে reference-like পরিবর্তন করা যায়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Empty Pointer:** এই optionটি `NULL Pointer`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Pointer প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) Void Pointer:** এই optionটি `NULL Pointer`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Pointer প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) NULL Pointer:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Zero Pointer:** এই optionটি `NULL Pointer`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Pointer প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

বাড়ি নয়, বাড়ির ঠিকানা লেখা কাগজ—Pointer সেই ঠিকানা।

### Memory Tip

**`&` address; `*` value-at-address; `->` pointer member।**

### Related Concepts

NULL, Dangling Pointer, malloc

---

## MCQ 0028

**Source:** Page 2; original no. 28  
**Original retained serial:** 0028  
**Topic:** Pointer  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Dynamic Memory Allocation কোনটির মাধ্যমে করা যায়?

### Options

- **(ক)** Array
- **(খ)** Pointer
- **(গ)** Variable
- **(ঘ)** Loop

### সঠিক উত্তর

**(খ) Pointer**

### কেন সঠিক

Pointer একটি memory address ধারণ করে। `&` address নেয়, `*` dereference করে এবং `->` pointer-to-object/struct member access করে। C সব argument value হিসেবে pass করে; pointer value pass করে reference-like পরিবর্তন করা যায়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Array:** Array contiguous indexed collection; random access দ্রুত কিন্তু size policy fixed হতে পারে। কিন্তু এই প্রশ্নে চাওয়া Pointer-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(খ) Pointer:** এটি সঠিক উত্তর।
- ❌ **(গ) Variable:** এই optionটি `Pointer`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Pointer প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Loop:** এই optionটি `Pointer`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Pointer প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

বাড়ি নয়, বাড়ির ঠিকানা লেখা কাগজ—Pointer সেই ঠিকানা।

### Memory Tip

**`&` address; `*` value-at-address; `->` pointer member।**

### Related Concepts

NULL, Dangling Pointer, malloc

---

## MCQ 0029

**Source:** Page 2; original no. 29  
**Original retained serial:** 0029  
**Topic:** Array Allocation  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Array memory বরাদ্দ সাধারণত কোন সময়ে হয়?

### Options

- **(ক)** Run Time
- **(খ)** Compile Time
- **(গ)** Debug Time
- **(ঘ)** সব সময়

### সঠিক উত্তর

**(খ) Compile Time**

### কেন সঠিক

Fixed-size static/global array-এর size compile/link time-এ জানা থাকে; automatic local array runtime stack frame-এ তৈরি হয় এবং VLA runtime size নিতে পারে। Source MCQ-এর intended distinction fixed array বনাম dynamic allocation।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Run Time:** এই optionটি `Compile Time`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array Allocation প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Compile Time:** এটি সঠিক উত্তর।
- ❌ **(গ) Debug Time:** এই optionটি `Compile Time`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array Allocation প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) সব সময়:** এই optionটি `Compile Time`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array Allocation প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

আগে থেকে নির্ধারিত আসন বনাম প্রয়োজনমতো নতুন আসন ভাড়া করার মতো।

### Memory Tip

**Fixed array ও dynamic memory এক নয়।**

### Related Concepts

VLA, Stack, Heap

---

## MCQ 0030

**Source:** Page 2; original no. 30  
**Original retained serial:** 0030  
**Topic:** Structure and Union  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

বিভিন্ন data type-এর Variable-এর সংগ্রহকে কী বলে?

### Options

- **(ক)** Array
- **(খ)** Structure
- **(গ)** Pointer
- **(ঘ)** Function

### সঠিক উত্তর

**(খ) Structure**

### কেন সঠিক

Structure-এ প্রতিটি member-এর আলাদা storage থাকে; padding যোগ হতে পারে। Union-এর সব member একই memory share করে, তাই size সাধারণত সবচেয়ে বড় member-এর size এবং alignment অনুযায়ী হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Array:** Array contiguous indexed collection; random access দ্রুত কিন্তু size policy fixed হতে পারে। কিন্তু এই প্রশ্নে চাওয়া Structure and Union-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(খ) Structure:** এটি সঠিক উত্তর।
- ❌ **(গ) Pointer:** এই optionটি `Structure`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Structure and Union প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Function:** এই optionটি `Structure`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Structure and Union প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Structure আলাদা drawer; Union একই drawer পালা করে ব্যবহার।

### Memory Tip

**Structure = separate; Union = shared।**

### Related Concepts

Padding, Alignment, typedef

---

## MCQ 0031

**Source:** Page 3; original no. 31  
**Original retained serial:** 0031  
**Topic:** Structure and Union  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Structure-এর member-গুলো memory-তে কীভাবে থাকে?

### Options

- **(ক)** একই স্থান দখল করে
- **(খ)** আলাদা আলাদা স্থান দখল করে
- **(গ)** কোনো স্থান নেয় না
- **(ঘ)** শুধু Run Time-এ তৈরি হয়

### সঠিক উত্তর

**(খ) আলাদা আলাদা স্থান দখল করে**

### কেন সঠিক

Structure-এ প্রতিটি member-এর আলাদা storage থাকে; padding যোগ হতে পারে। Union-এর সব member একই memory share করে, তাই size সাধারণত সবচেয়ে বড় member-এর size এবং alignment অনুযায়ী হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) একই স্থান দখল করে:** এই optionটি `আলাদা আলাদা স্থান দখল করে`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Structure and Union প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) আলাদা আলাদা স্থান দখল করে:** এটি সঠিক উত্তর।
- ❌ **(গ) কোনো স্থান নেয় না:** এই optionটি `আলাদা আলাদা স্থান দখল করে`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Structure and Union প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) শুধু Run Time-এ তৈরি হয়:** এই optionটি `আলাদা আলাদা স্থান দখল করে`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Structure and Union প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Structure আলাদা drawer; Union একই drawer পালা করে ব্যবহার।

### Memory Tip

**Structure = separate; Union = shared।**

### Related Concepts

Padding, Alignment, typedef

---

## MCQ 0032

**Source:** Page 3; original no. 32  
**Original retained serial:** 0032  
**Topic:** Structure and Union  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Union-এর size কতটুকু হয়?

### Options

- **(ক)** সকল member-এর size-এর যোগফল
- **(খ)** সবচেয়ে বড় member-এর size-এর সমান
- **(গ)** সবচেয়ে ছোট member-এর size-এর সমান
- **(ঘ)** 1 byte

### সঠিক উত্তর

**(খ) সবচেয়ে বড় member-এর size-এর সমান**

### কেন সঠিক

Structure-এ প্রতিটি member-এর আলাদা storage থাকে; padding যোগ হতে পারে। Union-এর সব member একই memory share করে, তাই size সাধারণত সবচেয়ে বড় member-এর size এবং alignment অনুযায়ী হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) সকল member-এর size-এর যোগফল:** এই optionটি `সবচেয়ে বড় member-এর size-এর সমান`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Structure and Union প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) সবচেয়ে বড় member-এর size-এর সমান:** এটি সঠিক উত্তর।
- ❌ **(গ) সবচেয়ে ছোট member-এর size-এর সমান:** এই optionটি `সবচেয়ে বড় member-এর size-এর সমান`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Structure and Union প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) 1 byte:** এই optionটি `সবচেয়ে বড় member-এর size-এর সমান`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Structure and Union প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Structure আলাদা drawer; Union একই drawer পালা করে ব্যবহার।

### Memory Tip

**Structure = separate; Union = shared।**

### Related Concepts

Padding, Alignment, typedef

---

## MCQ 0033

**Source:** Page 3; original no. 33  
**Original retained serial:** 0033  
**Topic:** Structure and Union  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

একই Memory Location ভাগ করে নেয় কোনটি?

### Options

- **(ক)** Structure
- **(খ)** Union
- **(গ)** Array
- **(ঘ)** Function

### সঠিক উত্তর

**(খ) Union**

### কেন সঠিক

Structure-এ প্রতিটি member-এর আলাদা storage থাকে; padding যোগ হতে পারে। Union-এর সব member একই memory share করে, তাই size সাধারণত সবচেয়ে বড় member-এর size এবং alignment অনুযায়ী হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Structure:** এই optionটি `Union`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Structure and Union প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Union:** এটি সঠিক উত্তর।
- ❌ **(গ) Array:** Array contiguous indexed collection; random access দ্রুত কিন্তু size policy fixed হতে পারে। কিন্তু এই প্রশ্নে চাওয়া Structure and Union-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(ঘ) Function:** এই optionটি `Union`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Structure and Union প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Structure আলাদা drawer; Union একই drawer পালা করে ব্যবহার।

### Memory Tip

**Structure = separate; Union = shared।**

### Related Concepts

Padding, Alignment, typedef

---

## MCQ 0034

**Source:** Page 3; original no. 34  
**Original retained serial:** 0034  
**Topic:** C Token  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

C program-এর ক্ষুদ্রতম একক unit-কে কী বলে?

### Options

- **(ক)** Keyword
- **(খ)** Token
- **(গ)** Statement
- **(ঘ)** Header File

### সঠিক উত্তর

**(খ) Token**

### কেন সঠিক

Token compiler-এর দৃষ্টিতে program-এর ক্ষুদ্রতম meaningful lexical unit—keyword, identifier, constant, operator ও punctuator।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Keyword:** এই optionটি `Token`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Token প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Token:** এটি সঠিক উত্তর।
- ❌ **(গ) Statement:** এই optionটি `Token`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Token প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Header File:** এই optionটি `Token`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Token প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

বাক্যের শব্দ ও punctuation যেমন parsing-এর unit।

### Memory Tip

**Program ভাঙলে token পাওয়া যায়।**

### Related Concepts

Lexer, Keyword, Identifier

---

## MCQ 0035

**Source:** Page 3; original no. 35  
**Original retained serial:** 0035  
**Topic:** Console I/O  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

`printf()` function কোন header file-এ থাকে?

### Options

- **(ক)** `stdio.h`
- **(খ)** `conio.h`
- **(গ)** `string.h`
- **(ঘ)** `math.h`

### সঠিক উত্তর

**(ক) `stdio.h`**

### কেন সঠিক

`printf()` formatted output দেয়, `scanf()` formatted input নেয় এবং দুটোই `stdio.h`-এ declared। `\n` newline escape sequence cursorকে পরবর্তী line-এ নেয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) `stdio.h`:** এটি সঠিক উত্তর।
- ❌ **(খ) `conio.h`:** এই optionটি `stdio.h`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Console I/O প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) `string.h`:** এই optionটি `stdio.h`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Console I/O প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) `math.h`:** এই optionটি `stdio.h`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Console I/O প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

মাইক্রোফোন input, speaker output—`scanf` ও `printf` তেমন।

### Memory Tip

**`printf` prints; `scanf` scans; `\n` new line।**

### Related Concepts

Format String, Escape Sequence, Buffer

---

## MCQ 0036

**Source:** Page 3; original no. 36  
**Original retained serial:** 0036  
**Topic:** Console I/O  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Keyboard থেকে input নেওয়ার জন্য কোন function ব্যবহৃত হয়?

### Options

- **(ক)** `printf()`
- **(খ)** `scanf()`
- **(গ)** `gets()`
- **(ঘ)** `puts()`

### সঠিক উত্তর

**(খ) `scanf()`**

### কেন সঠিক

`printf()` formatted output দেয়, `scanf()` formatted input নেয় এবং দুটোই `stdio.h`-এ declared। `\n` newline escape sequence cursorকে পরবর্তী line-এ নেয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) `printf()`:** এই optionটি `scanf()`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Console I/O প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) `scanf()`:** এটি সঠিক উত্তর।
- ❌ **(গ) `gets()`:** এই optionটি `scanf()`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Console I/O প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) `puts()`:** এই optionটি `scanf()`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Console I/O প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

মাইক্রোফোন input, speaker output—`scanf` ও `printf` তেমন।

### Memory Tip

**`printf` prints; `scanf` scans; `\n` new line।**

### Related Concepts

Format String, Escape Sequence, Buffer

---

## MCQ 0037

**Source:** Page 3; original no. 37  
**Original retained serial:** 0037  
**Topic:** Scope and Storage Duration  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Global Variable-এর default value কত?

### Options

- **(ক)** Garbage
- **(খ)** 0 (শূন্য)
- **(গ)** `1`
- **(ঘ)** Undefined

### সঠিক উত্তর

**(খ) 0 (শূন্য)**

### কেন সঠিক

Global/static object zero-initialized হয়। Local variable-এর scope তার block/function; `static` local variable function call-এর মধ্যেও value ধরে রাখে কারণ storage duration পুরো program।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Garbage:** এই optionটি `0 (শূন্য)`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Scope and Storage Duration প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) 0 (শূন্য):** এটি সঠিক উত্তর।
- ❌ **(গ) `1`:** এই optionটি `0 (শূন্য)`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Scope and Storage Duration প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Undefined:** এই optionটি `0 (শূন্য)`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Scope and Storage Duration প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Office drawer স্থানীয়, central archive global; static drawer বারবার খুললেও জিনিস থাকে।

### Memory Tip

**Scope কোথায় দেখা যায়; lifetime কতক্ষণ থাকে—দুটি আলাদা।**

### Related Concepts

Linkage, Storage Class, Initialization

---

## MCQ 0038

**Source:** Page 3; original no. 38  
**Original retained serial:** 0038  
**Topic:** Recursion  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

যে function নিজেকে নিজে call করে তাকে কী বলে?

### Options

- **(ক)** Inline Function
- **(খ)** Recursive Function
- **(গ)** Library Function
- **(ঘ)** Main Function

### সঠিক উত্তর

**(খ) Recursive Function**

### কেন সঠিক

Recursive function নিজেকে call করে এবং termination-এর জন্য base case প্রয়োজন। প্রতিটি active call সাধারণত call stack-এ frame তৈরি করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Inline Function:** এই optionটি `Recursive Function`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Recursion প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Recursive Function:** এটি সঠিক উত্তর।
- ❌ **(গ) Library Function:** এই optionটি `Recursive Function`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Recursion প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Main Function:** এই optionটি `Recursive Function`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Recursion প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

দুই আয়নার প্রতিফলন চলতে থাকে—stop condition না দিলে শেষ হয় না।

### Memory Tip

**Recursion = Base Case + Smaller Problem।**

### Related Concepts

Call Stack, Iteration, Stack Overflow

---

## MCQ 0039

**Source:** Page 3; original no. 39  
**Original retained serial:** 0039  
**Topic:** Inline Function  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Code-কে সরাসরি function call-এর জায়গায় copy করে দেয় কোন function?

### Options

- **(ক)** Recursive
- **(খ)** User-defined
- **(গ)** Inline
- **(ঘ)** External

### সঠিক উত্তর

**(গ) Inline**

### কেন সঠিক

`inline` compilerকে function-call overhead কমাতে substitution বিবেচনার ইঙ্গিত দেয়; এটি বাধ্যতামূলক copy guarantee নয়। ছোট frequently-called function-এ উপযোগী হতে পারে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Recursive:** এই optionটি `Inline`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Inline Function প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) User-defined:** এই optionটি `Inline`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Inline Function প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) Inline:** এটি সঠিক উত্তর।
- ❌ **(ঘ) External:** এই optionটি `Inline`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Inline Function প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

বারবার দূরের দোকানে না গিয়ে প্রয়োজনীয় জিনিস ডেস্কে রাখার মতো।

### Memory Tip

**`inline` একটি request/hint, guarantee নয়।**

### Related Concepts

Compiler Optimization, Macro, Function Call

---

## MCQ 0040

**Source:** Page 3; original no. 40  
**Original retained serial:** 0040  
**Topic:** Dynamic Memory Allocation  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

`malloc()`-এর পূর্ণরূপ কী?

### Options

- **(ক)** Memory Allocation
- **(খ)** Main Allocation
- **(গ)** Master Allocation
- **(ঘ)** Multi Allocation

### সঠিক উত্তর

**(ক) Memory Allocation**

### কেন সঠিক

`malloc(size)` এক argument নেয় এবং memory initialize করে না; `calloc(count,size)` দুই argument নেয় এবং allocated bytes zero-initialize করে। দুটোই failure-এ `NULL` দিতে পারে এবং `free()` করতে হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) Memory Allocation:** এটি সঠিক উত্তর।
- ❌ **(খ) Main Allocation:** এই optionটি `Memory Allocation`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Dynamic Memory Allocation প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) Master Allocation:** এই optionটি `Memory Allocation`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Dynamic Memory Allocation প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Multi Allocation:** এই optionটি `Memory Allocation`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Dynamic Memory Allocation প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

খালি ঘর ভাড়া: malloc ঘর যেমন আছে; calloc আগে পরিষ্কার/শূন্য করে দেয়।

### Memory Tip

**`malloc` 1 arg; `calloc` 2 arg + zero-init।**

### Related Concepts

free, realloc, Heap

---

## MCQ 0041

**Source:** Page 3; original no. 41  
**Original retained serial:** 0041  
**Topic:** Dynamic Memory Allocation  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

`calloc()` function memory-র মানকে শুরুতে কত দিয়ে initialize করে?

### Options

- **(ক)** `1`
- **(খ)** Garbage
- **(গ)** `0`
- **(ঘ)** `100`

### সঠিক উত্তর

**(গ) `0`**

### কেন সঠিক

`malloc(size)` এক argument নেয় এবং memory initialize করে না; `calloc(count,size)` দুই argument নেয় এবং allocated bytes zero-initialize করে। দুটোই failure-এ `NULL` দিতে পারে এবং `free()` করতে হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) `1`:** এই optionটি `0`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Dynamic Memory Allocation প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) Garbage:** এই optionটি `0`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Dynamic Memory Allocation প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) `0`:** এটি সঠিক উত্তর।
- ❌ **(ঘ) `100`:** এই optionটি `0`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Dynamic Memory Allocation প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

খালি ঘর ভাড়া: malloc ঘর যেমন আছে; calloc আগে পরিষ্কার/শূন্য করে দেয়।

### Memory Tip

**`malloc` 1 arg; `calloc` 2 arg + zero-init।**

### Related Concepts

free, realloc, Heap

---

## MCQ 0042

**Source:** Page 3; original no. 42  
**Original retained serial:** 0042  
**Topic:** Dynamic Memory Allocation  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

`malloc()` কয়টি parameter গ্রহণ করে?

### Options

- **(ক)** 1টি
- **(খ)** 2টি
- **(গ)** 3টি
- **(ঘ)** 4টি

### সঠিক উত্তর

**(ক) 1টি**

### কেন সঠিক

`malloc(size)` এক argument নেয় এবং memory initialize করে না; `calloc(count,size)` দুই argument নেয় এবং allocated bytes zero-initialize করে। দুটোই failure-এ `NULL` দিতে পারে এবং `free()` করতে হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) 1টি:** এটি সঠিক উত্তর।
- ❌ **(খ) 2টি:** এই optionটি `1টি`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Dynamic Memory Allocation প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) 3টি:** এই optionটি `1টি`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Dynamic Memory Allocation প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) 4টি:** এই optionটি `1টি`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Dynamic Memory Allocation প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

খালি ঘর ভাড়া: malloc ঘর যেমন আছে; calloc আগে পরিষ্কার/শূন্য করে দেয়।

### Memory Tip

**`malloc` 1 arg; `calloc` 2 arg + zero-init।**

### Related Concepts

free, realloc, Heap

---

## MCQ 0043

**Source:** Page 3; original no. 43  
**Original retained serial:** 0043  
**Topic:** C String Functions  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

String-এর length নির্ণয়ের function কোনটি?

### Options

- **(ক)** `strcpy()`
- **(খ)** `strcat()`
- **(গ)** `strlen()`
- **(ঘ)** `strcmp()`

### সঠিক উত্তর

**(গ) `strlen()`**

### কেন সঠিক

`strlen()` null terminator-এর আগে character count করে; `strcmp()` lexicographically দুই string তুলনা করে। `strcpy()` copy ও `strcat()` concatenate করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) `strcpy()`:** এই optionটি `strlen()`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C String Functions প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) `strcat()`:** এই optionটি `strlen()`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C String Functions প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) `strlen()`:** এটি সঠিক উত্তর।
- ❌ **(ঘ) `strcmp()`:** এই optionটি `strlen()`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C String Functions প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

ফিতা দিয়ে দৈর্ঘ্য মাপা `strlen`; অভিধানক্রমে তুলনা `strcmp`।

### Memory Tip

**len=length, cmp=compare, cpy=copy, cat=concatenate।**

### Related Concepts

string.h, Null Terminator, Buffer Safety

---

## MCQ 0044

**Source:** Page 3; original no. 44  
**Original retained serial:** 0044  
**Topic:** C String Functions  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

দুটি String তুলনা করতে কোনটি ব্যবহৃত হয়?

### Options

- **(ক)** `strcpy()`
- **(খ)** `strcmp()`
- **(গ)** `strcat()`
- **(ঘ)** `strrev()`

### সঠিক উত্তর

**(খ) `strcmp()`**

### কেন সঠিক

`strlen()` null terminator-এর আগে character count করে; `strcmp()` lexicographically দুই string তুলনা করে। `strcpy()` copy ও `strcat()` concatenate করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) `strcpy()`:** এই optionটি `strcmp()`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C String Functions প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) `strcmp()`:** এটি সঠিক উত্তর।
- ❌ **(গ) `strcat()`:** এই optionটি `strcmp()`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C String Functions প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) `strrev()`:** এই optionটি `strcmp()`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C String Functions প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

ফিতা দিয়ে দৈর্ঘ্য মাপা `strlen`; অভিধানক্রমে তুলনা `strcmp`।

### Memory Tip

**len=length, cmp=compare, cpy=copy, cat=concatenate।**

### Related Concepts

string.h, Null Terminator, Buffer Safety

---

## MCQ 0045

**Source:** Page 3; original no. 45  
**Original retained serial:** 0045  
**Topic:** Constant  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

যার মান program-এ পরিবর্তন করা যায় না তাকে কী বলে?

### Options

- **(ক)** Variable
- **(খ)** Constant
- **(গ)** Keyword
- **(ঘ)** Identifier

### সঠিক উত্তর

**(খ) Constant**

### কেন সঠিক

Constant value পরিবর্তন না করার ধারণা। C-তে `const` objectকে সেই lvalue-এর মাধ্যমে modify না করার type qualifier দেয়; macro constant আলাদা mechanism।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Variable:** এই optionটি `Constant`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Constant প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Constant:** এটি সঠিক উত্তর।
- ❌ **(গ) Keyword:** এই optionটি `Constant`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Constant প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Identifier:** এই optionটি `Constant`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Constant প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Permanent ink-এ লেখা মানের মতো।

### Memory Tip

**`const` means read-only through that name।**

### Related Concepts

Literal, Macro, Enum

---

## MCQ 0046

**Source:** Page 3; original no. 46  
**Original retained serial:** 0046  
**Topic:** Constant  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Constant declare করার জন্য কোন keyword ব্যবহৃত হয়?

### Options

- **(ক)** var
- **(খ)** static
- **(গ)** const
- **(ঘ)** final

### সঠিক উত্তর

**(গ) const**

### কেন সঠিক

Constant value পরিবর্তন না করার ধারণা। C-তে `const` objectকে সেই lvalue-এর মাধ্যমে modify না করার type qualifier দেয়; macro constant আলাদা mechanism।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) var:** এই optionটি `const`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Constant প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) static:** এই optionটি `const`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Constant প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) const:** এটি সঠিক উত্তর।
- ❌ **(ঘ) final:** এই optionটি `const`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Constant প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Permanent ink-এ লেখা মানের মতো।

### Memory Tip

**`const` means read-only through that name।**

### Related Concepts

Literal, Macro, Enum

---

## MCQ 0047

**Source:** Page 3; original no. 47  
**Original retained serial:** 0047  
**Topic:** Scope and Storage Duration  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Local Variable-এর scope কোথায়?

### Options

- **(ক)** পুরো program জুড়ে
- **(খ)** নির্দিষ্ট function বা block-এর মধ্যে
- **(গ)** শুধু main function-এ
- **(ঘ)** সারা জীবন

### সঠিক উত্তর

**(খ) নির্দিষ্ট function বা block-এর মধ্যে**

### কেন সঠিক

Global/static object zero-initialized হয়। Local variable-এর scope তার block/function; `static` local variable function call-এর মধ্যেও value ধরে রাখে কারণ storage duration পুরো program।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) পুরো program জুড়ে:** এই optionটি `নির্দিষ্ট function বা block-এর মধ্যে`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Scope and Storage Duration প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) নির্দিষ্ট function বা block-এর মধ্যে:** এটি সঠিক উত্তর।
- ❌ **(গ) শুধু main function-এ:** এই optionটি `নির্দিষ্ট function বা block-এর মধ্যে`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Scope and Storage Duration প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) সারা জীবন:** এই optionটি `নির্দিষ্ট function বা block-এর মধ্যে`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Scope and Storage Duration প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Office drawer স্থানীয়, central archive global; static drawer বারবার খুললেও জিনিস থাকে।

### Memory Tip

**Scope কোথায় দেখা যায়; lifetime কতক্ষণ থাকে—দুটি আলাদা।**

### Related Concepts

Linkage, Storage Class, Initialization

---

## MCQ 0048

**Source:** Page 3; original no. 48  
**Original retained serial:** 0048  
**Topic:** Dynamic Memory Allocation  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

`malloc()` এবং `calloc()`-এর মধ্যে কোনটি সাধারণত বেশি দ্রুত?

### Options

- **(ক)** `malloc()`
- **(খ)** `calloc()`
- **(গ)** দুটিই সমান
- **(ঘ)** কোনোটিই নয়

### সঠিক উত্তর

**(ক) `malloc()`**

### কেন সঠিক

`malloc(size)` এক argument নেয় এবং memory initialize করে না; `calloc(count,size)` দুই argument নেয় এবং allocated bytes zero-initialize করে। দুটোই failure-এ `NULL` দিতে পারে এবং `free()` করতে হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) `malloc()`:** এটি সঠিক উত্তর।
- ❌ **(খ) `calloc()`:** এই optionটি `malloc()`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Dynamic Memory Allocation প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) দুটিই সমান:** এই optionটি `malloc()`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Dynamic Memory Allocation প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) কোনোটিই নয়:** এই optionটি `malloc()`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Dynamic Memory Allocation প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

খালি ঘর ভাড়া: malloc ঘর যেমন আছে; calloc আগে পরিষ্কার/শূন্য করে দেয়।

### Memory Tip

**`malloc` 1 arg; `calloc` 2 arg + zero-init।**

### Related Concepts

free, realloc, Heap

---

## MCQ 0049

**Source:** Page 3; original no. 49  
**Original retained serial:** 0049  
**Topic:** Array and String  
**Correction basis:** Visually verified from source scan

### প্রশ্ন

Memory Allocation ধারাবাহিকভাবে (পরপর) হয় কোনটিতে?

### Options

- **(ক)** Pointer
- **(খ)** Array
- **(গ)** Union
- **(ঘ)** Recursion

### সঠিক উত্তর

**(খ) Array**

### কেন সঠিক

Array একই data type-এর element contiguous memory-তে রাখে এবং C-তে index 0 থেকে শুরু হয়। C String হলো null-terminated character array।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Pointer:** এই optionটি `Array`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array and String প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Array:** এটি সঠিক উত্তর।
- ❌ **(গ) Union:** এই optionটি `Array`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array and String প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Recursion:** এই optionটি `Array`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array and String প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

এক সারিতে নম্বর দেওয়া locker—প্রথম locker-এর নম্বর 0।

### Memory Tip

**Array contiguous; C String ends with `\0`।**

### Related Concepts

Pointer, Bounds, Character Array

---

## MCQ 0050

**Source:** Page 4; original no. 50  
**Original retained serial:** 0050  
**Topic:** Main Function  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

`main()` কী ধরনের function?

### Options

- **(ক)** Library Function
- **(খ)** User-defined Entry Function
- **(গ)** Recursive Function
- **(ঘ)** Header Function

### সঠিক উত্তর

**(খ) User-defined Entry Function**

### কেন সঠিক

`main()` hosted C/C++ program-এর entry function। Programmer definition লেখে, কিন্তু runtime environment এখান থেকে program execution শুরু করে। Standard return type `int`।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Library Function:** এই optionটি `User-defined Entry Function`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Main Function প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) User-defined Entry Function:** এটি সঠিক উত্তর।
- ❌ **(গ) Recursive Function:** এই optionটি `User-defined Entry Function`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Main Function প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Header Function:** এই optionটি `User-defined Entry Function`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Main Function প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

বাড়ির main gate দিয়ে প্রবেশের মতো program execution `main` থেকে শুরু।

### Memory Tip

**`int main(void)` বা `int main(int argc, char **argv)` standard form।**

### Related Concepts

Entry Point, Return Status, Runtime

---

## MCQ 0051

**Source:** Page 4; original no. 56  
**Original retained serial:** 0051  
**Topic:** Parameter Passing  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Call by Value পদ্ধতিতে কী pass করা হয়?

### Options

- **(ক)** Variable-এর value
- **(খ)** Memory Address
- **(গ)** Pointer-এর address
- **(ঘ)** File name

### সঠিক উত্তর

**(ক) Variable-এর value**

### কেন সঠিক

C-তে function argument-এর value copy হয়। তাই parameter পরিবর্তন করলে caller variable সরাসরি বদলায় না; pointer value pass করলে pointed object পরিবর্তন করা যায়।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) Variable-এর value:** এটি সঠিক উত্তর।
- ❌ **(খ) Memory Address:** এই optionটি `Variable-এর value`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Parameter Passing প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) Pointer-এর address:** এই optionটি `Variable-এর value`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Parameter Passing প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) File name:** এই optionটি `Variable-এর value`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Parameter Passing প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Original document নয়, photocopy পাঠানোর মতো।

### Memory Tip

**C is pass-by-value—even pointers are passed by value।**

### Related Concepts

Parameter, Pointer, Side Effect

---

## MCQ 0052

**Source:** Page 4; original no. 59  
**Original retained serial:** 0052  
**Topic:** Pointer  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Pointer ব্যবহার করে কোন calling method বাস্তবায়ন করা হয়?

### Options

- **(ক)** Call by Value
- **(খ)** Call by Reference
- **(গ)** Pass by Name
- **(ঘ)** Static Call

### সঠিক উত্তর

**(খ) Call by Reference**

### কেন সঠিক

Pointer একটি memory address ধারণ করে। `&` address নেয়, `*` dereference করে এবং `->` pointer-to-object/struct member access করে। C সব argument value হিসেবে pass করে; pointer value pass করে reference-like পরিবর্তন করা যায়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Call by Value:** এই optionটি `Call by Reference`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Pointer প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Call by Reference:** এটি সঠিক উত্তর।
- ❌ **(গ) Pass by Name:** এই optionটি `Call by Reference`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Pointer প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Static Call:** এই optionটি `Call by Reference`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Pointer প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

বাড়ি নয়, বাড়ির ঠিকানা লেখা কাগজ—Pointer সেই ঠিকানা।

### Memory Tip

**`&` address; `*` value-at-address; `->` pointer member।**

### Related Concepts

NULL, Dangling Pointer, malloc

---

## MCQ 0053

**Source:** Page 5; original no. 74  
**Original retained serial:** 0053  
**Topic:** Loop Control  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

সাধারণ condition-controlled loop কখন শেষ হয়?

### Options

- **(ক)** Condition সত্য হলে
- **(খ)** Condition মিথ্যা হলে
- **(গ)** Variable declare হলে
- **(ঘ)** প্রতি iteration-এর আগে

### সঠিক উত্তর

**(খ) Condition মিথ্যা হলে**

### কেন সঠিক

`for`, `while` ও `do-while` পুনরাবৃত্তি করে। `while` ও `for` entry-controlled; condition false হলে বন্ধ হয়। `do-while` exit-controlled, তাই body অন্তত একবার চলে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Condition সত্য হলে:** এই optionটি `Condition মিথ্যা হলে`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Loop Control প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Condition মিথ্যা হলে:** এটি সঠিক উত্তর।
- ❌ **(গ) Variable declare হলে:** এই optionটি `Condition মিথ্যা হলে`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Loop Control প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) প্রতি iteration-এর আগে:** এই optionটি `Condition মিথ্যা হলে`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Loop Control প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

দরজায় ঢোকার আগে ticket check বনাম ভেতরে ঢুকে বের হওয়ার সময় check।

### Memory Tip

**`while` আগে check; `do-while` পরে check।**

### Related Concepts

break, continue, Iteration

---

## MCQ 0054

**Source:** Page 5; original no. 75  
**Original retained serial:** 0054  
**Topic:** Loop Control  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

C ভাষায় প্রধান loop statement কয়টি?

### Options

- **(ক)** 2টি
- **(খ)** 3টি
- **(গ)** 4টি
- **(ঘ)** 5টি

### সঠিক উত্তর

**(খ) 3টি**

### কেন সঠিক

`for`, `while` ও `do-while` পুনরাবৃত্তি করে। `while` ও `for` entry-controlled; condition false হলে বন্ধ হয়। `do-while` exit-controlled, তাই body অন্তত একবার চলে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) 2টি:** এই optionটি `3টি`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Loop Control প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) 3টি:** এটি সঠিক উত্তর।
- ❌ **(গ) 4টি:** এই optionটি `3টি`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Loop Control প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) 5টি:** এই optionটি `3টি`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Loop Control প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

দরজায় ঢোকার আগে ticket check বনাম ভেতরে ঢুকে বের হওয়ার সময় check।

### Memory Tip

**`while` আগে check; `do-while` পরে check।**

### Related Concepts

break, continue, Iteration

---

## MCQ 0055

**Source:** Page 5; original no. 77  
**Original retained serial:** 0055  
**Topic:** Loop Control  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

`while` loop-এ condition কোথায় পরীক্ষা করা হয়?

### Options

- **(ক)** Loop body-এর আগে
- **(খ)** Loop body-এর পরে
- **(গ)** প্রতি iteration-এর পরে
- **(ঘ)** পরীক্ষা করা হয় না

### সঠিক উত্তর

**(ক) Loop body-এর আগে**

### কেন সঠিক

`for`, `while` ও `do-while` পুনরাবৃত্তি করে। `while` ও `for` entry-controlled; condition false হলে বন্ধ হয়। `do-while` exit-controlled, তাই body অন্তত একবার চলে।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) Loop body-এর আগে:** এটি সঠিক উত্তর।
- ❌ **(খ) Loop body-এর পরে:** এই optionটি `Loop body-এর আগে`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Loop Control প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) প্রতি iteration-এর পরে:** এই optionটি `Loop body-এর আগে`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Loop Control প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) পরীক্ষা করা হয় না:** এই optionটি `Loop body-এর আগে`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Loop Control প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

দরজায় ঢোকার আগে ticket check বনাম ভেতরে ঢুকে বের হওয়ার সময় check।

### Memory Tip

**`while` আগে check; `do-while` পরে check।**

### Related Concepts

break, continue, Iteration

---

## MCQ 0056

**Source:** Page 5; original no. 82  
**Original retained serial:** 0057  
**Topic:** Loop Control  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

`do-while` কী ধরনের loop?

### Options

- **(ক)** Entry-controlled
- **(খ)** Exit-controlled
- **(গ)** Infinite-only
- **(ঘ)** Compile-time loop

### সঠিক উত্তর

**(খ) Exit-controlled**

### কেন সঠিক

`for`, `while` ও `do-while` পুনরাবৃত্তি করে। `while` ও `for` entry-controlled; condition false হলে বন্ধ হয়। `do-while` exit-controlled, তাই body অন্তত একবার চলে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Entry-controlled:** এই optionটি `Exit-controlled`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Loop Control প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Exit-controlled:** এটি সঠিক উত্তর।
- ❌ **(গ) Infinite-only:** এই optionটি `Exit-controlled`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Loop Control প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Compile-time loop:** এই optionটি `Exit-controlled`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Loop Control প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

দরজায় ঢোকার আগে ticket check বনাম ভেতরে ঢুকে বের হওয়ার সময় check।

### Memory Tip

**`while` আগে check; `do-while` পরে check।**

### Related Concepts

break, continue, Iteration

---

## MCQ 0057

**Source:** Page 6; original no. 0  
**Original retained serial:** 0058  
**Topic:** Leap Year Logic  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Gregorian Calendar অনুযায়ী Leap Year যাচাইয়ের সঠিক condition কোনটি?

### Options

- **(ক)** `year%4==0`
- **(খ)** `year%400==0 || (year%4==0 && year%100!=0)`
- **(গ)** `year%100==0`
- **(ঘ)** `year%2==0`

### সঠিক উত্তর

**(খ) `year%400==0 || (year%4==0 && year%100!=0)`**

### কেন সঠিক

Gregorian rule অনুযায়ী 400 দিয়ে বিভাজ্য বছর leap; অন্যথায় 4 দিয়ে বিভাজ্য কিন্তু 100 দিয়ে নয়। তাই combined Boolean conditionটি century exception ঠিকভাবে সামলায়।

### Step-by-step

```text
Rule:
A year is leap if it is divisible by 400,
or divisible by 4 but not by 100.

Boolean form:
year % 400 == 0 || (year % 4 == 0 && year % 100 != 0)
```

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) `year%4==0`:** এই optionটি `year%400==0 || (year%4==0 && year%100!=0)`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Leap Year Logic প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) `year%400==0 || (year%4==0 && year%100!=0)`:** এটি সঠিক উত্তর।
- ❌ **(গ) `year%100==0`:** এই optionটি `year%400==0 || (year%4==0 && year%100!=0)`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Leap Year Logic প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) `year%2==0`:** এই optionটি `year%400==0 || (year%4==0 && year%100!=0)`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Leap Year Logic প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

চার বছর পরপর bonus day, কিন্তু শতাব্দীতে 400-এর gatekeeper আছে।

### Memory Tip

**`%400==0 || (%4==0 && %100!=0)`।**

### Related Concepts

Modulo, Boolean Operator, Precedence

---

## MCQ 0058

**Source:** Page 8; original no. 0  
**Original retained serial:** 0060  
**Topic:** Pointer  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

C++-এ `shape->getArea()` expression-এ `->` operator কী নির্দেশ করে?

### Options

- **(ক)** Object-এর সরাসরি member access
- **(খ)** Pointer-এর মাধ্যমে member access
- **(গ)** শুধু memory address নেওয়া
- **(ঘ)** Value copy করা

### সঠিক উত্তর

**(খ) Pointer-এর মাধ্যমে member access**

### কেন সঠিক

Pointer একটি memory address ধারণ করে। `&` address নেয়, `*` dereference করে এবং `->` pointer-to-object/struct member access করে। C সব argument value হিসেবে pass করে; pointer value pass করে reference-like পরিবর্তন করা যায়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Object-এর সরাসরি member access:** এই optionটি `Pointer-এর মাধ্যমে member access`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Pointer প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Pointer-এর মাধ্যমে member access:** এটি সঠিক উত্তর।
- ❌ **(গ) শুধু memory address নেওয়া:** এই optionটি `Pointer-এর মাধ্যমে member access`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Pointer প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Value copy করা:** এই optionটি `Pointer-এর মাধ্যমে member access`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Pointer প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

বাড়ি নয়, বাড়ির ঠিকানা লেখা কাগজ—Pointer সেই ঠিকানা।

### Memory Tip

**`&` address; `*` value-at-address; `->` pointer member।**

### Related Concepts

NULL, Dangling Pointer, malloc

---

## MCQ 0059

**Source:** Page 8; original no. 2  
**Original retained serial:** 0061  
**Topic:** Console I/O  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

`printf("\n");` statement-এর কাজ কী?

### Options

- **(ক)** নতুন line তৈরি করা
- **(খ)** Data মুছে ফেলা
- **(গ)** Program শেষ করা
- **(ঘ)** Input নেওয়া

### সঠিক উত্তর

**(ক) নতুন line তৈরি করা**

### কেন সঠিক

`printf()` formatted output দেয়, `scanf()` formatted input নেয় এবং দুটোই `stdio.h`-এ declared। `\n` newline escape sequence cursorকে পরবর্তী line-এ নেয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) নতুন line তৈরি করা:** এটি সঠিক উত্তর।
- ❌ **(খ) Data মুছে ফেলা:** এই optionটি `নতুন line তৈরি করা`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Console I/O প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) Program শেষ করা:** এই optionটি `নতুন line তৈরি করা`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Console I/O প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Input নেওয়া:** এই optionটি `নতুন line তৈরি করা`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Console I/O প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

মাইক্রোফোন input, speaker output—`scanf` ও `printf` তেমন।

### Memory Tip

**`printf` prints; `scanf` scans; `\n` new line।**

### Related Concepts

Format String, Escape Sequence, Buffer

---

## MCQ 0060

**Source:** Page 8; original no. 8  
**Original retained serial:** 0062  
**Topic:** C Operators  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Bitwise AND-এ `5 & 3`-এর মান কত?

### Options

- **(ক)** `1`
- **(খ)** `2`
- **(গ)** `3`
- **(ঘ)** `8`

### সঠিক উত্তর

**(ক) `1`**

### কেন সঠিক

Operator operand-এর ওপর কাজ করে। `%` remainder দেয়, Relational operator তুলনা করে, `&&` logical AND এবং `--` এক কমায়। Bitwise AND প্রতিটি bit pair-এ AND চালায়।

### Step-by-step

```text
5 = 0101
3 = 0011
--------- AND
    0001 = 1
```

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) `1`:** এটি সঠিক উত্তর।
- ❌ **(খ) `2`:** এই optionটি `1`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Operators প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) `3`:** এই optionটি `1`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Operators প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) `8`:** এই optionটি `1`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই C Operators প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Calculator-এর বিভিন্ন button যেমন ভিন্ন operation করে।

### Memory Tip

**Logical `&&`; Bitwise `&`; Address-of `&` context দেখে।**

### Related Concepts

Precedence, Associativity, Boolean Expression

---

## MCQ 0061

**Source:** Page 9; original no. 141  
**Original retained serial:** 0064  
**Topic:** Class and Object  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Object তৈরির blueprint বা template কোনটি?

### Options

- **(ক)** Object
- **(খ)** Class
- **(গ)** Method
- **(ঘ)** Variable

### সঠিক উত্তর

**(খ) Class**

### কেন সঠিক

Class attribute ও method-এর blueprint; Object সেই class-এর concrete instance। Object create হলে তার instance state-এর জন্য memory বরাদ্দ হয়, যদিও method code সাধারণত shared থাকে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Object:** এই optionটি `Class`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Class and Object প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Class:** এটি সঠিক উত্তর।
- ❌ **(গ) Method:** এই optionটি `Class`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Class and Object প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Variable:** এই optionটি `Class`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Class and Object প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Class হলো বাড়ির নকশা, Object সেই নকশায় তৈরি বাস্তব বাড়ি।

### Memory Tip

**Class = blueprint; Object = instance।**

### Related Concepts

Constructor, Attribute, Method

---

## MCQ 0062

**Source:** Page 9; original no. 142  
**Original retained serial:** 0065  
**Topic:** Class and Object  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Object তৈরি হলে সাধারণত কী ঘটে?

### Options

- **(ক)** Class delete হয়
- **(খ)** Object-এর জন্য memory বরাদ্দ হয়
- **(গ)** Compiler বন্ধ হয়
- **(ঘ)** কোনো memory লাগে না

### সঠিক উত্তর

**(খ) Object-এর জন্য memory বরাদ্দ হয়**

### কেন সঠিক

Class attribute ও method-এর blueprint; Object সেই class-এর concrete instance। Object create হলে তার instance state-এর জন্য memory বরাদ্দ হয়, যদিও method code সাধারণত shared থাকে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Class delete হয়:** এই optionটি `Object-এর জন্য memory বরাদ্দ হয়`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Class and Object প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Object-এর জন্য memory বরাদ্দ হয়:** এটি সঠিক উত্তর।
- ❌ **(গ) Compiler বন্ধ হয়:** এই optionটি `Object-এর জন্য memory বরাদ্দ হয়`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Class and Object প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) কোনো memory লাগে না:** এই optionটি `Object-এর জন্য memory বরাদ্দ হয়`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Class and Object প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Class হলো বাড়ির নকশা, Object সেই নকশায় তৈরি বাস্তব বাড়ি।

### Memory Tip

**Class = blueprint; Object = instance।**

### Related Concepts

Constructor, Attribute, Method

---

## MCQ 0063

**Source:** Page 9; original no. 143  
**Original retained serial:** 0066  
**Topic:** Class and Object  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

একটি Class-এর instance-কে কী বলা হয়?

### Options

- **(ক)** Polymorphism
- **(খ)** Inheritance
- **(গ)** Object
- **(ঘ)** Interface

### সঠিক উত্তর

**(গ) Object**

### কেন সঠিক

Class attribute ও method-এর blueprint; Object সেই class-এর concrete instance। Object create হলে তার instance state-এর জন্য memory বরাদ্দ হয়, যদিও method code সাধারণত shared থাকে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Polymorphism:** এই optionটি `Object`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Class and Object প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) Inheritance:** এই optionটি `Object`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Class and Object প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) Object:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Interface:** এই optionটি `Object`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Class and Object প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Class হলো বাড়ির নকশা, Object সেই নকশায় তৈরি বাস্তব বাড়ি।

### Memory Tip

**Class = blueprint; Object = instance।**

### Related Concepts

Constructor, Attribute, Method

---

## MCQ 0064

**Source:** Page 9; original no. 144  
**Original retained serial:** 0067  
**Topic:** Encapsulation  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

Data এবং method-কে একটি unit বা package-এ একত্রে রাখার প্রক্রিয়াকে কী বলে?

### Options

- **(ক)** Abstraction
- **(খ)** Encapsulation
- **(গ)** Inheritance
- **(ঘ)** Overloading

### সঠিক উত্তর

**(খ) Encapsulation**

### কেন সঠিক

Encapsulation data ও behaviorকে এক unit-এ রাখে এবং access modifier দিয়ে internal state-এর সরাসরি ব্যবহার সীমিত করে। এটি data protection ও controlled interface দেয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Abstraction:** এই optionটি `Encapsulation`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Encapsulation প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Encapsulation:** এটি সঠিক উত্তর।
- ❌ **(গ) Inheritance:** এই optionটি `Encapsulation`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Encapsulation প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Overloading:** এই optionটি `Encapsulation`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Encapsulation প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Capsule-এর ভেতরে ওষুধ সুরক্ষিত থাকে; বাইরে শুধু capsule ব্যবহার করা হয়।

### Memory Tip

**Bundle + restrict access = Encapsulation।**

### Related Concepts

Class, Access Modifier, Data Hiding

---

## MCQ 0065

**Source:** Page 9; original no. 145  
**Original retained serial:** 0068  
**Topic:** Abstraction  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Implementation detail লুকিয়ে সহজ interface দেওয়াকে কী বলে?

### Options

- **(ক)** Inheritance
- **(খ)** Abstraction
- **(গ)** Overriding
- **(ঘ)** Compilation

### সঠিক উত্তর

**(খ) Abstraction**

### কেন সঠিক

Abstraction প্রয়োজনীয় behavior/interface দেখায় এবং অপ্রয়োজনীয় implementation detail লুকায়। Interface ও abstract class contract প্রকাশের common mechanism।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Inheritance:** এই optionটি `Abstraction`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Abstraction প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Abstraction:** এটি সঠিক উত্তর।
- ❌ **(গ) Overriding:** এই optionটি `Abstraction`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Abstraction প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Compilation:** এই optionটি `Abstraction`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Abstraction প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

গাড়ি চালাতে engine-এর ভিতরের combustion জানা লাগে না; steering ও pedal interface যথেষ্ট।

### Memory Tip

**What দেখায়, How লুকায়।**

### Related Concepts

Interface, Abstract Class, Encapsulation

---

## MCQ 0066

**Source:** Page 9; original no. 146  
**Original retained serial:** 0069  
**Topic:** Inheritance  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

একটি Class অন্য একটি Class-এর বৈশিষ্ট্য গ্রহণ করলে তাকে কী বলে?

### Options

- **(ক)** Encapsulation
- **(খ)** Polymorphism
- **(গ)** Inheritance
- **(ঘ)** Binding

### সঠিক উত্তর

**(গ) Inheritance**

### কেন সঠিক

Inheritance existing class-এর accessible feature নতুন class-এ reuse/extend করতে দেয় এবং is-a relationship প্রকাশ করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Encapsulation:** এই optionটি `Inheritance`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Inheritance প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) Polymorphism:** এই optionটি `Inheritance`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Inheritance প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) Inheritance:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Binding:** এই optionটি `Inheritance`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Inheritance প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

সন্তান পারিবারিক বৈশিষ্ট্য পায়, তবে নিজস্ব বৈশিষ্ট্যও যোগ করতে পারে।

### Memory Tip

**Inheritance → is-a + reuse।**

### Related Concepts

Base Class, Derived Class, Overriding

---

## MCQ 0067

**Source:** Page 9; original no. 147  
**Original retained serial:** 0070  
**Topic:** Polymorphism  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Polymorphism শব্দের অর্থ কী?

### Options

- **(ক)** একটি রূপ
- **(খ)** বহু রূপ
- **(গ)** কোনো রূপ নয়
- **(ঘ)** শুধু inheritance

### সঠিক উত্তর

**(খ) বহু রূপ**

### কেন সঠিক

Polymorphism একই interface/name-এ ভিন্ন behavior দেয়। Overloading compile-time selection; overriding ও virtual dispatch runtime behavior দিতে পারে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) একটি রূপ:** এই optionটি `বহু রূপ`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Polymorphism প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) বহু রূপ:** এটি সঠিক উত্তর।
- ❌ **(গ) কোনো রূপ নয়:** এই optionটি `বহু রূপ`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Polymorphism প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) শুধু inheritance:** এই optionটি `বহু রূপ`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Polymorphism প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

একই “play” button গান ও video-তে ভিন্ন কাজ করে।

### Memory Tip

**Overload = compile-time; Override/virtual = runtime।**

### Related Concepts

Dynamic Binding, Virtual Function, Inheritance

---

## MCQ 0068

**Source:** Page 11; original no. 168  
**Original retained serial:** 0072  
**Topic:** Encapsulation  
**Correction basis:** Source answer marker

### প্রশ্ন

ডেটাকে বাইরের হস্তক্ষেপ থেকে রক্ষা করতে কোনটি ব্যবহৃত হয়?

### Options

- **(ক)** ত্যাবসট্রাকশন
- **(খ)** Encapsulation
- **(গ)** নেটওয়ার্ক ঝুঁকি
- **(ঘ)** Inheritance

### সঠিক উত্তর

**(খ) Encapsulation**

### কেন সঠিক

Encapsulation data ও behaviorকে এক unit-এ রাখে এবং access modifier দিয়ে internal state-এর সরাসরি ব্যবহার সীমিত করে। এটি data protection ও controlled interface দেয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) ত্যাবসট্রাকশন:** এই optionটি `Encapsulation`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Encapsulation প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Encapsulation:** এটি সঠিক উত্তর।
- ❌ **(গ) নেটওয়ার্ক ঝুঁকি:** এই optionটি `Encapsulation`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Encapsulation প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Inheritance:** এই optionটি `Encapsulation`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Encapsulation প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Capsule-এর ভেতরে ওষুধ সুরক্ষিত থাকে; বাইরে শুধু capsule ব্যবহার করা হয়।

### Memory Tip

**Bundle + restrict access = Encapsulation।**

### Related Concepts

Class, Access Modifier, Data Hiding

---

## MCQ 0069

**Source:** Page 11; original no. 169  
**Original retained serial:** 0073  
**Topic:** Abstraction  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

Abstraction বাস্তবায়নে নিচের কোনটি সবচেয়ে সরাসরি ব্যবহৃত হয়?

### Options

- **(ক)** Getter ও Setter
- **(খ)** Interface এবং Abstract Class
- **(গ)** শুধু Private Variable
- **(ঘ)** Loop

### সঠিক উত্তর

**(খ) Interface এবং Abstract Class**

### কেন সঠিক

Abstraction প্রয়োজনীয় behavior/interface দেখায় এবং অপ্রয়োজনীয় implementation detail লুকায়। Interface ও abstract class contract প্রকাশের common mechanism।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Getter ও Setter:** এই optionটি `Interface এবং Abstract Class`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Abstraction প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Interface এবং Abstract Class:** এটি সঠিক উত্তর।
- ❌ **(গ) শুধু Private Variable:** এই optionটি `Interface এবং Abstract Class`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Abstraction প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Loop:** এই optionটি `Interface এবং Abstract Class`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Abstraction প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

গাড়ি চালাতে engine-এর ভিতরের combustion জানা লাগে না; steering ও pedal interface যথেষ্ট।

### Memory Tip

**What দেখায়, How লুকায়।**

### Related Concepts

Interface, Abstract Class, Encapsulation

---

## MCQ 0070

**Source:** Page 11; original no. 170  
**Original retained serial:** 0074  
**Topic:** Encapsulation  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Encapsulation বাস্তবায়নে কোনটি গুরুত্বপূর্ণ?

### Options

- **(ক)** Access Modifier
- **(খ)** Loop Counter
- **(গ)** Header Guard only
- **(ঘ)** File Extension

### সঠিক উত্তর

**(ক) Access Modifier**

### কেন সঠিক

Encapsulation data ও behaviorকে এক unit-এ রাখে এবং access modifier দিয়ে internal state-এর সরাসরি ব্যবহার সীমিত করে। এটি data protection ও controlled interface দেয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) Access Modifier:** এটি সঠিক উত্তর।
- ❌ **(খ) Loop Counter:** এই optionটি `Access Modifier`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Encapsulation প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) Header Guard only:** এই optionটি `Access Modifier`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Encapsulation প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) File Extension:** এই optionটি `Access Modifier`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Encapsulation প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Capsule-এর ভেতরে ওষুধ সুরক্ষিত থাকে; বাইরে শুধু capsule ব্যবহার করা হয়।

### Memory Tip

**Bundle + restrict access = Encapsulation।**

### Related Concepts

Class, Access Modifier, Data Hiding

---

## MCQ 0071

**Source:** Page 13; original no. 101  
**Original retained serial:** 0076  
**Topic:** Conditional Control  
**Correction basis:** Source answer marker

### প্রশ্ন

প্রোগ্রামের ফ্রো নিয়ন্ত্রণে নিচের কোনটি Conditional কন্ট্রোল স্টেটমেন্ট?

### Options

- **(ক)** For
- **(খ)** While
- **(গ)** if-else
- **(ঘ)** do-while

### সঠিক উত্তর

**(গ) if-else**

### কেন সঠিক

`if-else` Boolean condition অনুযায়ী alternative execution path বেছে নেয়। Loop repeat করে; condition statement branch নির্বাচন করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) For:** এই optionটি `if-else`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Conditional Control প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) While:** এই optionটি `if-else`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Conditional Control প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) if-else:** এটি সঠিক উত্তর।
- ❌ **(ঘ) do-while:** এই optionটি `if-else`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Conditional Control প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

রাস্তার মোড়ে signal অনুযায়ী ডান বা বাম পথ নেওয়া।

### Memory Tip

**if = decision; loop = repetition।**

### Related Concepts

switch, Boolean Expression, Branch

---

## MCQ 0072

**Source:** Page 13; original no. 102  
**Original retained serial:** 0077  
**Topic:** Loop Control  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Iteration সংখ্যা আগে থেকে জানা থাকলে কোন loop সবচেয়ে সুবিধাজনক?

### Options

- **(ক)** while
- **(খ)** for
- **(গ)** do-while
- **(ঘ)** goto

### সঠিক উত্তর

**(খ) for**

### কেন সঠিক

`for`, `while` ও `do-while` পুনরাবৃত্তি করে। `while` ও `for` entry-controlled; condition false হলে বন্ধ হয়। `do-while` exit-controlled, তাই body অন্তত একবার চলে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) while:** এই optionটি `for`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Loop Control প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) for:** এটি সঠিক উত্তর।
- ❌ **(গ) do-while:** এই optionটি `for`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Loop Control প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) goto:** এই optionটি `for`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Loop Control প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

দরজায় ঢোকার আগে ticket check বনাম ভেতরে ঢুকে বের হওয়ার সময় check।

### Memory Tip

**`while` আগে check; `do-while` পরে check।**

### Related Concepts

break, continue, Iteration

---

## MCQ 0073

**Source:** Page 13; original no. 103  
**Original retained serial:** 0078  
**Topic:** Loop Control  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

কোন loop-এর body কমপক্ষে একবার execute হয়?

### Options

- **(ক)** for
- **(খ)** while
- **(গ)** do-while
- **(ঘ)** nested for

### সঠিক উত্তর

**(গ) do-while**

### কেন সঠিক

`for`, `while` ও `do-while` পুনরাবৃত্তি করে। `while` ও `for` entry-controlled; condition false হলে বন্ধ হয়। `do-while` exit-controlled, তাই body অন্তত একবার চলে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) for:** এই optionটি `do-while`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Loop Control প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) while:** এই optionটি `do-while`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Loop Control প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) do-while:** এটি সঠিক উত্তর।
- ❌ **(ঘ) nested for:** এই optionটি `do-while`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Loop Control প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

দরজায় ঢোকার আগে ticket check বনাম ভেতরে ঢুকে বের হওয়ার সময় check।

### Memory Tip

**`while` আগে check; `do-while` পরে check।**

### Related Concepts

break, continue, Iteration

---

## MCQ 0074

**Source:** Page 13; original no. 198  
**Original retained serial:** 0080  
**Topic:** Array Tracing  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

নিচের code-এর output কত? ```c int matrix[2][3] = {{1,4,2},{3,6,8}}; printf("%d", matrix[0][0]); ```

### Options

- **(ক)** `1`
- **(খ)** `3`
- **(গ)** `0`
- **(ঘ)** Null

### সঠিক উত্তর

**(ক) `1`**

### কেন সঠিক

C array row-major order-এ index 0 থেকে শুরু হয়। `matrix[0][0]` প্রথম row-এর প্রথম element। পাঁচটি 4-byte `int` হলে raw array size 20 byte।

### Step-by-step

```text
matrix[0][0] means first row, first column.
First row = {1, 4, 2}
Therefore matrix[0][0] = 1.
```

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) `1`:** এটি সঠিক উত্তর।
- ❌ **(খ) `3`:** এই optionটি `1`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array Tracing প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) `0`:** এই optionটি `1`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array Tracing প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Null:** এই optionটি `1`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array Tracing প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Spreadsheet-এর প্রথম cell row 0, column 0 হিসেবে ধরার মতো।

### Memory Tip

**Index trace করুন; size = element count × sizeof(element)।**

### Related Concepts

2D Array, Row-major, sizeof

---

## MCQ 0075

**Source:** Page 13; original no. 199  
**Original retained serial:** 0081  
**Topic:** Array Tracing  
**Correction basis:** Source answer marker

### প্রশ্ন

int ictWizardStd[] = {10, 25, 50, 75, 100}; মেমোরিতে এই array size হবে?

### Options

- **(ক)** `20`
- **(খ)** `5`
- **(গ)** `4`
- **(ঘ)** Undefined

### সঠিক উত্তর

**(ক) `20`**

### কেন সঠিক

C array row-major order-এ index 0 থেকে শুরু হয়। `matrix[0][0]` প্রথম row-এর প্রথম element। পাঁচটি 4-byte `int` হলে raw array size 20 byte।

### Step-by-step

```text
Element count = 5
Assumed sizeof(int) = 4 bytes
Array size = 5 x 4 = 20 bytes.
```

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) `20`:** এটি সঠিক উত্তর।
- ❌ **(খ) `5`:** এই optionটি `20`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array Tracing প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) `4`:** এই optionটি `20`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array Tracing প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Undefined:** এই optionটি `20`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Array Tracing প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Spreadsheet-এর প্রথম cell row 0, column 0 হিসেবে ধরার মতো।

### Memory Tip

**Index trace করুন; size = element count × sizeof(element)।**

### Related Concepts

2D Array, Row-major, sizeof

---

## MCQ 0076

**Source:** Page 15; original no. 228  
**Original retained serial:** 0082  
**Topic:** Polymorphism  
**Correction basis:** Source answer marker

### প্রশ্ন

মেথড ওভারলোডিং Polymorphismের কোন প্রকারের উদাহরণ?

### Options

- **(ক)** রানটাইম Polymorphism
- **(খ)** কম্পাইল-টাইম Polymorphism
- **(গ)** ডায়নামিক IAP
- **(ঘ)** ইনহেরিট্যাস oe

### সঠিক উত্তর

**(খ) কম্পাইল-টাইম Polymorphism**

### কেন সঠিক

Polymorphism একই interface/name-এ ভিন্ন behavior দেয়। Overloading compile-time selection; overriding ও virtual dispatch runtime behavior দিতে পারে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) রানটাইম Polymorphism:** এই optionটি `কম্পাইল-টাইম Polymorphism`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Polymorphism প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) কম্পাইল-টাইম Polymorphism:** এটি সঠিক উত্তর।
- ❌ **(গ) ডায়নামিক IAP:** এই optionটি `কম্পাইল-টাইম Polymorphism`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Polymorphism প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) ইনহেরিট্যাস oe:** এই optionটি `কম্পাইল-টাইম Polymorphism`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Polymorphism প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

একই “play” button গান ও video-তে ভিন্ন কাজ করে।

### Memory Tip

**Overload = compile-time; Override/virtual = runtime।**

### Related Concepts

Dynamic Binding, Virtual Function, Inheritance

---

## MCQ 0077

**Source:** Page 16; original no. 3  
**Original retained serial:** 0083  
**Topic:** Default Constructor  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

একটি Class-এ কোনো Constructor লেখা না থাকলে সাধারণত কী ঘটে?

### Options

- **(ক)** সেই Class-এর Object তৈরি করা যায় না
- **(খ)** Compiler স্বয়ংক্রিয়ভাবে Default Constructor সরবরাহ করতে পারে
- **(গ)** Classটি Abstract Class হয়ে যায়
- **(ঘ)** অবশ্যই Runtime Error হয়

### সঠিক উত্তর

**(খ) Compiler স্বয়ংক্রিয়ভাবে Default Constructor সরবরাহ করতে পারে**

### কেন সঠিক

যদি কোনো user-declared constructor না থাকে, C++ compiler একটি implicit default constructor declare/define করতে পারে, শর্তসাপেক্ষে। অন্য constructor declare করলে zero-argument implicit constructor স্বয়ংক্রিয়ভাবে নাও থাকে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) সেই Class-এর Object তৈরি করা যায় না:** এই optionটি `Compiler স্বয়ংক্রিয়ভাবে Default Constructor সরবরাহ করতে পারে`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Default Constructor প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Compiler স্বয়ংক্রিয়ভাবে Default Constructor সরবরাহ করতে পারে:** এটি সঠিক উত্তর।
- ❌ **(গ) Classটি Abstract Class হয়ে যায়:** এই optionটি `Compiler স্বয়ংক্রিয়ভাবে Default Constructor সরবরাহ করতে পারে`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Default Constructor প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) অবশ্যই Runtime Error হয়:** এই optionটি `Compiler স্বয়ংক্রিয়ভাবে Default Constructor সরবরাহ করতে পারে`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Default Constructor প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

ফর্মে custom setup না দিলে system default setup ব্যবহার করে।

### Memory Tip

**No user constructor → implicit default may be generated।**

### Related Concepts

Constructor, Object Initialization, Compiler-generated Function

---

## MCQ 0078

**Source:** Page 16; original no. 41  
**Original retained serial:** 0084  
**Topic:** Scope and Storage Duration  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

C-তে Function call-এর মধ্যে Variable-এর value ধরে রাখতে কোন storage class ব্যবহার করা হয়?

### Options

- **(ক)** auto
- **(খ)** extern
- **(গ)** static
- **(ঘ)** register

### সঠিক উত্তর

**(গ) static**

### কেন সঠিক

Global/static object zero-initialized হয়। Local variable-এর scope তার block/function; `static` local variable function call-এর মধ্যেও value ধরে রাখে কারণ storage duration পুরো program।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) auto:** এই optionটি `static`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Scope and Storage Duration প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) extern:** এই optionটি `static`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Scope and Storage Duration প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) static:** এটি সঠিক উত্তর।
- ❌ **(ঘ) register:** এই optionটি `static`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Scope and Storage Duration প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Office drawer স্থানীয়, central archive global; static drawer বারবার খুললেও জিনিস থাকে।

### Memory Tip

**Scope কোথায় দেখা যায়; lifetime কতক্ষণ থাকে—দুটি আলাদা।**

### Related Concepts

Linkage, Storage Class, Initialization

---

## MCQ 0079

**Source:** Page 16; original no. 239  
**Original retained serial:** 0085  
**Topic:** Polymorphism  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

C++-এ Run-time Method Overriding সক্রিয় করতে কোন keyword ব্যবহৃত হতে পারে?

### Options

- **(ক)** static
- **(খ)** virtual
- **(গ)** const
- **(ঘ)** friend

### সঠিক উত্তর

**(খ) virtual**

### কেন সঠিক

Polymorphism একই interface/name-এ ভিন্ন behavior দেয়। Overloading compile-time selection; overriding ও virtual dispatch runtime behavior দিতে পারে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) static:** এই optionটি `virtual`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Polymorphism প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) virtual:** এটি সঠিক উত্তর।
- ❌ **(গ) const:** এই optionটি `virtual`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Polymorphism প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) friend:** এই optionটি `virtual`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Polymorphism প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

একই “play” button গান ও video-তে ভিন্ন কাজ করে।

### Memory Tip

**Overload = compile-time; Override/virtual = runtime।**

### Related Concepts

Dynamic Binding, Virtual Function, Inheritance

---

## MCQ 0080

**Source:** Page 17; original no. 246  
**Original retained serial:** 0086  
**Topic:** Object-Oriented Language  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

নিচের কোন Programming Languageটি Object-Oriented feature-এর জন্য সুপরিচিত?

### Options

- **(ক)** C
- **(খ)** C++
- **(গ)** Assembly
- **(ঘ)** BASIC

### সঠিক উত্তর

**(খ) C++**

### কেন সঠিক

C++ class, inheritance, polymorphism ও encapsulation সমর্থন করে এবং C-এর procedural featureও রাখে। Assembly low-level এবং C মূলত structured/procedural।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) C:** এটি সঠিক উত্তর।
- ✅ **(খ) C++:** এটি সঠিক উত্তর।
- ❌ **(গ) Assembly:** এটি একটি programming language, তবে প্রশ্নে চাওয়া paradigm/level-এর সঙ্গে মেলে না। কিন্তু এই প্রশ্নে চাওয়া Object-Oriented Language-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(ঘ) BASIC:** এই optionটি `C++`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Object-Oriented Language প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

এক toolbox-এ procedural ও object-oriented দুই ধরনের যন্ত্র থাকা।

### Memory Tip

**C++ extends C with strong OOP facilities।**

### Related Concepts

Class, C, Java

---

# Section - Software Engineering

এই অংশে process model ও software testing রয়েছে।

---

## MCQ 0081

**Source:** Page 20; original no. 3  
**Original retained serial:** 0088  
**Topic:** Software Testing  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Internal code না দেখে input-output ভিত্তিক testing কোনটি?

### Options

- **(ক)** Black-box Testing
- **(খ)** White-box Testing
- **(গ)** Path Testing
- **(ঘ)** Loop Testing

### সঠিক উত্তর

**(ক) Black-box Testing**

### কেন সঠিক

Black-box testing internal code না দেখে input-output behavior যাচাই করে। Unit testing ক্ষুদ্র component পরীক্ষা করে; Regression পরিবর্তনের পর পুরোনো behavior ভাঙেনি কি না দেখে; Performance testing non-functional quality যাচাই করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) Black-box Testing:** এটি সঠিক উত্তর।
- ❌ **(খ) White-box Testing:** White-box internal code/control path দেখে। কিন্তু এই প্রশ্নে চাওয়া Software Testing-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(গ) Path Testing:** এই optionটি `Black-box Testing`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Software Testing প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Loop Testing:** এই optionটি `Black-box Testing`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Software Testing প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

গাড়ির engine না খুলে চালিয়ে ফল দেখা Black-box; প্রতিটি part আলাদা পরীক্ষা Unit test।

### Memory Tip

**Unit ছোট অংশ; Regression পুরোনো feature; Performance quality।**

### Related Concepts

White-box, Integration, System Testing

---

## MCQ 0082

**Source:** Page 20; original no. 4  
**Original retained serial:** 0089  
**Topic:** Software Testing  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

নিচের কোনটি Non-functional Testing-এর উদাহরণ?

### Options

- **(ক)** Unit Testing
- **(খ)** Integration Testing
- **(গ)** Performance Testing
- **(ঘ)** Regression Testing

### সঠিক উত্তর

**(গ) Performance Testing**

### কেন সঠিক

Black-box testing internal code না দেখে input-output behavior যাচাই করে। Unit testing ক্ষুদ্র component পরীক্ষা করে; Regression পরিবর্তনের পর পুরোনো behavior ভাঙেনি কি না দেখে; Performance testing non-functional quality যাচাই করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Unit Testing:** Unit testing ছোট component পরীক্ষা করে। কিন্তু এই প্রশ্নে চাওয়া Software Testing-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(খ) Integration Testing:** Integration testing component interaction পরীক্ষা করে। কিন্তু এই প্রশ্নে চাওয়া Software Testing-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(গ) Performance Testing:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Regression Testing:** এই optionটি `Performance Testing`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Software Testing প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

গাড়ির engine না খুলে চালিয়ে ফল দেখা Black-box; প্রতিটি part আলাদা পরীক্ষা Unit test।

### Memory Tip

**Unit ছোট অংশ; Regression পুরোনো feature; Performance quality।**

### Related Concepts

White-box, Integration, System Testing

---

## MCQ 0083

**Source:** Page 20; original no. 5  
**Original retained serial:** 0090  
**Topic:** Software Testing  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Software-এর ক্ষুদ্রতম testable unit পরীক্ষা করাকে কী বলে?

### Options

- **(ক)** Integration Testing
- **(খ)** Unit Testing
- **(গ)** System Testing
- **(ঘ)** Acceptance Testing

### সঠিক উত্তর

**(খ) Unit Testing**

### কেন সঠিক

Black-box testing internal code না দেখে input-output behavior যাচাই করে। Unit testing ক্ষুদ্র component পরীক্ষা করে; Regression পরিবর্তনের পর পুরোনো behavior ভাঙেনি কি না দেখে; Performance testing non-functional quality যাচাই করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Integration Testing:** Integration testing component interaction পরীক্ষা করে। কিন্তু এই প্রশ্নে চাওয়া Software Testing-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(খ) Unit Testing:** এটি সঠিক উত্তর।
- ❌ **(গ) System Testing:** এই optionটি `Unit Testing`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Software Testing প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Acceptance Testing:** এই optionটি `Unit Testing`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Software Testing প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

গাড়ির engine না খুলে চালিয়ে ফল দেখা Black-box; প্রতিটি part আলাদা পরীক্ষা Unit test।

### Memory Tip

**Unit ছোট অংশ; Regression পুরোনো feature; Performance quality।**

### Related Concepts

White-box, Integration, System Testing

---

## MCQ 0084

**Source:** Page 20; original no. 6  
**Original retained serial:** 0091  
**Topic:** Software Testing  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

পরিবর্তনের পর পুরোনো feature ঠিক আছে কি না কোন testing যাচাই করে?

### Options

- **(ক)** System Testing
- **(খ)** Regression Testing
- **(গ)** Smoke Testing
- **(ঘ)** Load Testing

### সঠিক উত্তর

**(খ) Regression Testing**

### কেন সঠিক

Black-box testing internal code না দেখে input-output behavior যাচাই করে। Unit testing ক্ষুদ্র component পরীক্ষা করে; Regression পরিবর্তনের পর পুরোনো behavior ভাঙেনি কি না দেখে; Performance testing non-functional quality যাচাই করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) System Testing:** এই optionটি `Regression Testing`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Software Testing প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Regression Testing:** এটি সঠিক উত্তর।
- ❌ **(গ) Smoke Testing:** এই optionটি `Regression Testing`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Software Testing প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Load Testing:** এই optionটি `Regression Testing`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Software Testing প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

গাড়ির engine না খুলে চালিয়ে ফল দেখা Black-box; প্রতিটি part আলাদা পরীক্ষা Unit test।

### Memory Tip

**Unit ছোট অংশ; Regression পুরোনো feature; Performance quality।**

### Related Concepts

White-box, Integration, System Testing

---

## MCQ 0085

**Source:** Page 21; original no. 8  
**Original retained serial:** 0092  
**Topic:** Waterfall Model  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Linear Sequential Model নামে কোনটি পরিচিত?

### Options

- **(ক)** Waterfall Model
- **(খ)** Spiral Model
- **(গ)** Prototype Model
- **(ঘ)** Agile Model

### সঠিক উত্তর

**(ক) Waterfall Model**

### কেন সঠিক

Waterfall একটি linear sequential process model—Requirement, Design, Implementation, Testing, Deployment/Maintenance ধাপ ক্রমানুসারে চলে। Stable requirement-এ সহজ, change সামলানো কঠিন।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) Waterfall Model:** এটি সঠিক উত্তর।
- ❌ **(খ) Spiral Model:** এই optionটি `Waterfall Model`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Waterfall Model প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) Prototype Model:** এই optionটি `Waterfall Model`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Waterfall Model প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Agile Model:** Agile iterative ও change-responsive development approach। কিন্তু এই প্রশ্নে চাওয়া Waterfall Model-এর নির্দিষ্ট শর্ত পূরণ করে না।

### সহজ Analogy

জলপ্রপাতের পানি এক ধাপ থেকে নিচের ধাপে যায়, সহজে উল্টো ফেরে না।

### Memory Tip

**Waterfall = linear sequential।**

### Related Concepts

SDLC, Spiral, Agile

---

# Section - Data Structure and Algorithm

এই অংশে tree, graph, search, priority queue ও indexing structure রয়েছে।

---

## MCQ 0086

**Source:** Page 23; original no. 3  
**Original retained serial:** 0093  
**Topic:** Tree  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

নিচের কোনটি Non-linear Data Structure?

### Options

- **(ক)** Array
- **(খ)** Queue
- **(গ)** Tree
- **(ঘ)** Stack

### সঠিক উত্তর

**(গ) Tree**

### কেন সঠিক

Tree একটি non-linear hierarchical structure। Graph theory-তে connected acyclic undirected graph একটি tree এবং n vertex-এর tree-তে n-1 edge থাকে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Array:** Array contiguous indexed collection; random access দ্রুত কিন্তু size policy fixed হতে পারে। কিন্তু এই প্রশ্নে চাওয়া Tree-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(খ) Queue:** Queue FIFO structure। কিন্তু এই প্রশ্নে চাওয়া Tree-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(গ) Tree:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Stack:** Stack LIFO structure। কিন্তু এই প্রশ্নে চাওয়া Tree-এর নির্দিষ্ট শর্ত পূরণ করে না।

### সহজ Analogy

পরিবারের বংশলতিকার parent-child কাঠামো।

### Memory Tip

**Tree = connected + acyclic।**

### Related Concepts

Root, Leaf, BST, Graph

---

## MCQ 0087

**Source:** Page 23; original no. 5  
**Original retained serial:** 0094  
**Topic:** Queue  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

ডাক্তারের জন্য রোগীর serial পরিচালনায় কোন Data Structure উপযুক্ত?

### Options

- **(ক)** Stack
- **(খ)** Queue
- **(গ)** Tree
- **(ঘ)** Graph

### সঠিক উত্তর

**(খ) Queue**

### কেন সঠিক

Queue FIFO principle অনুসরণ করে—আগে আসা item আগে service পায়। Patient serial, printer job ও BFS-এ তাই Queue উপযোগী।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Stack:** Stack LIFO structure। কিন্তু এই প্রশ্নে চাওয়া Queue-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(খ) Queue:** এটি সঠিক উত্তর।
- ❌ **(গ) Tree:** এই optionটি `Queue`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Queue প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Graph:** এই optionটি `Queue`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Queue প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

টিকিট কাউন্টারের লাইনের মতো।

### Memory Tip

**FIFO = First In, First Out।**

### Related Concepts

Enqueue, Dequeue, Circular Queue

---

## MCQ 0088

**Source:** Page 23; original no. 8  
**Original retained serial:** 0095  
**Topic:** Linked List  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

Array-এর তুলনায় Linked List-এর প্রধান সুবিধা কোনটি?

### Options

- **(ক)** Faster random access
- **(খ)** Static size
- **(গ)** Dynamic size
- **(ঘ)** Better cache performance

### সঠিক উত্তর

**(গ) Dynamic size**

### কেন সঠিক

Linked List node-গুলো pointer/link দিয়ে যুক্ত করে এবং contiguous memory প্রয়োজন হয় না। Dynamic insertion/deletion সহজ, কিন্তু index-based random access O(n) এবং cache locality সাধারণত Array-এর চেয়ে কম।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Faster random access:** এই optionটি `Dynamic size`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Linked List প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) Static size:** এই optionটি `Dynamic size`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Linked List প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) Dynamic size:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Better cache performance:** Performance testing speed, load ও resource quality যাচাই করে। কিন্তু এই প্রশ্নে চাওয়া Linked List-এর নির্দিষ্ট শর্ত পূরণ করে না।

### সহজ Analogy

ট্রেনের কামরা আলাদা জায়গায় থাকলেও coupling দিয়ে যুক্ত—Linked List তেমন।

### Memory Tip

**Linked List dynamic; Array random access দ্রুত।**

### Related Concepts

Node, Pointer, Array

---

## MCQ 0089

**Source:** Page 24; original no. 0  
**Original retained serial:** 0096  
**Topic:** Dijkstra Algorithm  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Dijkstra Algorithm কী বের করতে ব্যবহৃত হয়?

### Options

- **(ক)** Minimum Spanning Tree
- **(খ)** All-pairs path
- **(গ)** Single-source Shortest Path with non-negative weights
- **(ঘ)** Topological order

### সঠিক উত্তর

**(গ) Single-source Shortest Path with non-negative weights**

### কেন সঠিক

Dijkstra non-negative edge weight-যুক্ত graph-এ single-source shortest path বের করে। Negative edge থাকলে standard Dijkstra ব্যবহার নিরাপদ নয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Minimum Spanning Tree:** এই optionটি `Single-source Shortest Path with non-negative weights`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Dijkstra Algorithm প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) All-pairs path:** এই optionটি `Single-source Shortest Path with non-negative weights`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Dijkstra Algorithm প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) Single-source Shortest Path with non-negative weights:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Topological order:** এই optionটি `Single-source Shortest Path with non-negative weights`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Dijkstra Algorithm প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

প্রতিবার বর্তমানে সবচেয়ে কম দূরত্বের শহরটি নিশ্চিত করার মতো।

### Memory Tip

**Dijkstra → non-negative weights।**

### Related Concepts

Relaxation, Priority Queue, Bellman-Ford

---

## MCQ 0090

**Source:** Page 24; original no. 15  
**Original retained serial:** 0097  
**Topic:** Breadth-First Search  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

কোন Graph Traversal Algorithm level-by-level কাজ করে?

### Options

- **(ক)** DFS
- **(খ)** BFS
- **(গ)** Dijkstra
- **(ঘ)** Kruskal

### সঠিক উত্তর

**(খ) BFS**

### কেন সঠিক

BFS Queue ব্যবহার করে source থেকে level-by-level vertex visit করে এবং unweighted graph-এ minimum edge-count path দেয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) DFS:** DFS depth-first traversal। কিন্তু এই প্রশ্নে চাওয়া Breadth-First Search-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(খ) BFS:** এটি সঠিক উত্তর।
- ❌ **(গ) Dijkstra:** Dijkstra non-negative weighted graph-এর shortest path algorithm। কিন্তু এই প্রশ্নে চাওয়া Breadth-First Search-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(ঘ) Kruskal:** Kruskal minimum spanning tree algorithm। কিন্তু এই প্রশ্নে চাওয়া Breadth-First Search-এর নির্দিষ্ট শর্ত পূরণ করে না।

### সহজ Analogy

পুকুরে ঢিল ফেললে ঢেউ স্তর ধরে ছড়ায়।

### Memory Tip

**BFS = Queue + Levels।**

### Related Concepts

DFS, Graph Traversal, Shortest Path

---

## MCQ 0091

**Source:** Page 24; original no. 16  
**Original retained serial:** 0098  
**Topic:** Graph Degree  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

একটি Vertex-এর সঙ্গে যুক্ত Edge-এর সংখ্যাকে কী বলে?

### Options

- **(ক)** Path
- **(খ)** Degree
- **(গ)** Weight
- **(ঘ)** Component

### সঠিক উত্তর

**(খ) Degree**

### কেন সঠিক

Undirected graph-এ একটি vertex-এর সঙ্গে incident edge-এর সংখ্যা তার degree। সব degree-এর sum = 2E।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Path:** এই optionটি `Degree`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Graph Degree প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Degree:** এটি সঠিক উত্তর।
- ❌ **(গ) Weight:** এই optionটি `Degree`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Graph Degree প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Component:** এই optionটি `Degree`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Graph Degree প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

রাস্তার মোড়ে যত রাস্তা যুক্ত, সেটিই degree।

### Memory Tip

**Undirected degree sum = 2 × edges।**

### Related Concepts

In-degree, Out-degree, Handshaking Lemma

---

## MCQ 0092

**Source:** Page 24; original no. 21  
**Original retained serial:** 0099  
**Topic:** Tree  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Connected Acyclic Undirected Graph-কে কী বলে?

### Options

- **(ক)** Tree
- **(খ)** DAG
- **(গ)** Complete Graph
- **(ঘ)** Multigraph

### সঠিক উত্তর

**(ক) Tree**

### কেন সঠিক

Tree একটি non-linear hierarchical structure। Graph theory-তে connected acyclic undirected graph একটি tree এবং n vertex-এর tree-তে n-1 edge থাকে।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) Tree:** এটি সঠিক উত্তর।
- ❌ **(খ) DAG:** এই optionটি `Tree`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Tree প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) Complete Graph:** এই optionটি `Tree`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Tree প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Multigraph:** এই optionটি `Tree`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Tree প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

পরিবারের বংশলতিকার parent-child কাঠামো।

### Memory Tip

**Tree = connected + acyclic।**

### Related Concepts

Root, Leaf, BST, Graph

---

## MCQ 0093

**Source:** Page 24; original no. 23  
**Original retained serial:** 0100  
**Topic:** Minimum Spanning Tree  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Minimum Spanning Tree বের করতে কোন Algorithm ব্যবহৃত হয়?

### Options

- **(ক)** Dijkstra
- **(খ)** Floyd-Warshall
- **(গ)** Kruskal
- **(ঘ)** Binary Search

### সঠিক উত্তর

**(গ) Kruskal**

### কেন সঠিক

MST সব vertexকে cycle ছাড়া V-1 edge-এ connect করে এবং total weight minimum করে। Kruskal edge weight ascending নিয়ে cycle না হলে select করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Dijkstra:** Dijkstra non-negative weighted graph-এর shortest path algorithm। কিন্তু এই প্রশ্নে চাওয়া Minimum Spanning Tree-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(খ) Floyd-Warshall:** Floyd-Warshall all-pairs shortest path algorithm। কিন্তু এই প্রশ্নে চাওয়া Minimum Spanning Tree-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(গ) Kruskal:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Binary Search:** এই optionটি `Kruskal`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Minimum Spanning Tree প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

সব গ্রামকে সবচেয়ে কম মোট cable দিয়ে যুক্ত করার মতো।

### Memory Tip

**Kruskal = sort edges + avoid cycle।**

### Related Concepts

Prim, DSU, Cut Property

---

## MCQ 0094

**Source:** Page 25; original no. 2  
**Original retained serial:** 0101  
**Topic:** Quick Sort  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Quick Sort কোন Design Approach ব্যবহার করে?

### Options

- **(ক)** Greedy
- **(খ)** Dynamic Programming
- **(গ)** Divide and Conquer
- **(ঘ)** Backtracking

### সঠিক উত্তর

**(গ) Divide and Conquer**

### কেন সঠিক

Quick Sort pivot দিয়ে partition করে এবং দুই অংশ recursively sort করে। Average O(n log n), কিন্তু highly unbalanced partitionে worst O(n²)।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Greedy:** এই optionটি `Divide and Conquer`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Quick Sort প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) Dynamic Programming:** এই optionটি `Divide and Conquer`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Quick Sort প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) Divide and Conquer:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Backtracking:** এই optionটি `Divide and Conquer`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Quick Sort প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

বইকে pivot-এর চেয়ে ছোট ও বড় দুই স্তূপে ভাগ করা।

### Memory Tip

**Quick Sort = Pivot + Partition।**

### Related Concepts

Merge Sort, Recursion, Partition

---

## MCQ 0095

**Source:** Page 26; original no. 49  
**Original retained serial:** 0102  
**Topic:** Heap and Priority Queue  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Priority Queue implement করতে সবচেয়ে কার্যকর structure কোনটি?

### Options

- **(ক)** Heap
- **(খ)** Stack
- **(গ)** Linear Array only
- **(ঘ)** Linked List only

### সঠিক উত্তর

**(ক) Heap**

### কেন সঠিক

Binary Heap root-এ highest/lowest priority element রাখে এবং insert/remove সাধারণত O(log n), peek O(1)। তাই Priority Queue-এর efficient implementation।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) Heap:** এটি সঠিক উত্তর।
- ❌ **(খ) Stack:** Stack LIFO structure। কিন্তু এই প্রশ্নে চাওয়া Heap and Priority Queue-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(গ) Linear Array only:** Array contiguous indexed collection; random access দ্রুত কিন্তু size policy fixed হতে পারে। কিন্তু এই প্রশ্নে চাওয়া Heap and Priority Queue-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(ঘ) Linked List only:** Linked List node ও pointer দিয়ে dynamic sequence তৈরি করে। কিন্তু এই প্রশ্নে চাওয়া Heap and Priority Queue-এর নির্দিষ্ট শর্ত পূরণ করে না।

### সহজ Analogy

জরুরি রোগীকে queue-এর সামনে রাখার স্বয়ংক্রিয় ব্যবস্থা।

### Memory Tip

**Priority Queue → Heap।**

### Related Concepts

Min-Heap, Max-Heap, Complete Binary Tree

---

## MCQ 0096

**Source:** Page 29; original no. 67  
**Original retained serial:** 0103  
**Topic:** Binary Search  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Binary Search-এর পূর্বশর্ত কী?

### Options

- **(ক)** Data sorted হতে হবে
- **(খ)** Data encrypted হতে হবে
- **(গ)** Graph connected হতে হবে
- **(ঘ)** Hash table full হতে হবে

### সঠিক উত্তর

**(ক) Data sorted হতে হবে**

### কেন সঠিক

Binary Search sorted data-এর middle element তুলনা করে search interval অর্ধেক করে; time O(log n)। Unsorted data-তে এই elimination valid নয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) Data sorted হতে হবে:** এটি সঠিক উত্তর।
- ❌ **(খ) Data encrypted হতে হবে:** এই optionটি `Data sorted হতে হবে`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Binary Search প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) Graph connected হতে হবে:** এই optionটি `Data sorted হতে হবে`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Binary Search প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Hash table full হতে হবে:** এই optionটি `Data sorted হতে হবে`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Binary Search প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

অভিধানে মাঝখান খুলে শব্দের দিক নির্ধারণ করার মতো।

### Memory Tip

**Binary Search requires sorted order।**

### Related Concepts

Divide and Conquer, O(log n), Array

---

## MCQ 0097

**Source:** Page 30; original no. 0  
**Original retained serial:** 0104  
**Topic:** AVL Tree  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

AVL Tree-এর একটি balanced node-এর Balance Factor কোন set-এর মধ্যে থাকে?

### Options

- **(ক)** -1, 0, +1
- **(খ)** -2, 0, +2
- **(গ)** 1, 2, 3
- **(ঘ)** যেকোনো সংখ্যা

### সঠিক উত্তর

**(ক) -1, 0, +1**

### কেন সঠিক

AVL একটি self-balancing BST। Balance Factor = height(left)-height(right), এবং balanced node-এর valid value -1, 0 বা +1।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) -1, 0, +1:** এটি সঠিক উত্তর।
- ❌ **(খ) -2, 0, +2:** এই optionটি `-1, 0, +1`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই AVL Tree প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) 1, 2, 3:** এই optionটি `-1, 0, +1`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই AVL Tree প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) যেকোনো সংখ্যা:** এই optionটি `-1, 0, +1`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই AVL Tree প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

দাঁড়িপাল্লার দুই পাশে উচ্চতার পার্থক্য একের বেশি হতে দেওয়া হয় না।

### Memory Tip

**|BF| ≤ 1।**

### Related Concepts

Rotation, BST, Height

---

## MCQ 0098

**Source:** Page 30; original no. 00  
**Original retained serial:** 0105  
**Topic:** B-Tree Index  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

Database indexing-এর জন্য সাধারণত কোন Data Structure ব্যবহৃত হয়?

### Options

- **(ক)** Binary Tree
- **(খ)** B-Tree / B+ Tree
- **(গ)** Stack
- **(ঘ)** Queue

### সঠিক উত্তর

**(খ) B-Tree / B+ Tree**

### কেন সঠিক

B-Tree/B+ Tree high fan-out balanced search tree হওয়ায় disk page access কমায়। B+ Tree leaf linkage range queryকে বিশেষভাবে efficient করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Binary Tree:** এই optionটি `B-Tree / B+ Tree`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই B-Tree Index প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) B-Tree / B+ Tree:** এটি সঠিক উত্তর।
- ❌ **(গ) Stack:** Stack LIFO structure। কিন্তু এই প্রশ্নে চাওয়া B-Tree Index-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(ঘ) Queue:** Queue FIFO structure। কিন্তু এই প্রশ্নে চাওয়া B-Tree Index-এর নির্দিষ্ট শর্ত পূরণ করে না।

### সহজ Analogy

একটি directory page-এ বহু section-এর পথ দেখিয়ে দ্রুত সঠিক shelf-এ যাওয়া।

### Memory Tip

**Disk index → B+ Tree; exact hash lookup → Hash।**

### Related Concepts

Index, Fan-out, Range Query

---

# Section - Web Technology

এই অংশে HTML element ও document structure রয়েছে।

---

## MCQ 0099

**Source:** Page 33; original no. 4  
**Original retained serial:** 0106  
**Topic:** HTML  
**Correction basis:** Source answer marker

### প্রশ্ন

নিচের কোন ট্যাগের closing ট্যাগ থাকে?

### Options

- **(ক)** খুদে
- **(খ)** `<img>`
- **(গ)** `<tr>`
- **(ঘ)** `<br`

### সঠিক উত্তর

**(গ) `<tr>`**

### কেন সঠিক

HTML element document-এর semantic structure তৈরি করে। Paired tag-এর opening ও closing form থাকে; void element যেমন `<br>` closing tag নেয় না। `<title>` tab title, `<p>` paragraph, `<tr>` table row এবং `<div>` block container।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) খুদে:** এই optionটি `<tr>`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই HTML প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) `<img>`:** এই optionটি `<tr>`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই HTML প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) `<tr>`:** এটি সঠিক উত্তর।
- ❌ **(ঘ) `<br`:** এই optionটি `<tr>`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই HTML প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

HTML হলো বাড়ির দেয়াল-কক্ষের কাঠামো; CSS পরে সাজায়।

### Memory Tip

**title=tab, p=paragraph, tr=row, div=container, br=break।**

### Related Concepts

Element, Attribute, Semantic HTML

---

## MCQ 0100

**Source:** Page 33; original no. 5  
**Original retained serial:** 0107  
**Topic:** HTML  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

নিচের কোন HTML tag-এর closing tag থাকে না?

### Options

- **(ক)** `<h1>`
- **(খ)** `<i>`
- **(গ)** `<tr>`
- **(ঘ)** `<br>`

### সঠিক উত্তর

**(ঘ) `<br>`**

### কেন সঠিক

HTML element document-এর semantic structure তৈরি করে। Paired tag-এর opening ও closing form থাকে; void element যেমন `<br>` closing tag নেয় না। `<title>` tab title, `<p>` paragraph, `<tr>` table row এবং `<div>` block container।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) `<h1>`:** এই optionটি `<br>`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই HTML প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) `<i>`:** এই optionটি `<br>`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই HTML প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) `<tr>`:** এই optionটি `<br>`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই HTML প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(ঘ) `<br>`:** এটি সঠিক উত্তর।

### সহজ Analogy

HTML হলো বাড়ির দেয়াল-কক্ষের কাঠামো; CSS পরে সাজায়।

### Memory Tip

**title=tab, p=paragraph, tr=row, div=container, br=break।**

### Related Concepts

Element, Attribute, Semantic HTML

---

## MCQ 0101

**Source:** Page 33; original no. 6  
**Original retained serial:** 0108  
**Topic:** HTML  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

Browser-এর tab-এ webpage-এর শিরোনাম দেখাতে কোন HTML element ব্যবহৃত হয়?

### Options

- **(ক)** `<h2>`
- **(খ)** `<head>`
- **(গ)** `<caption>`
- **(ঘ)** `<title>`

### সঠিক উত্তর

**(ঘ) `<title>`**

### কেন সঠিক

HTML element document-এর semantic structure তৈরি করে। Paired tag-এর opening ও closing form থাকে; void element যেমন `<br>` closing tag নেয় না। `<title>` tab title, `<p>` paragraph, `<tr>` table row এবং `<div>` block container।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) `<h2>`:** এই optionটি `<title>`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই HTML প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) `<head>`:** এই optionটি `<title>`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই HTML প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) `<caption>`:** এই optionটি `<title>`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই HTML প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(ঘ) `<title>`:** এটি সঠিক উত্তর।

### সহজ Analogy

HTML হলো বাড়ির দেয়াল-কক্ষের কাঠামো; CSS পরে সাজায়।

### Memory Tip

**title=tab, p=paragraph, tr=row, div=container, br=break।**

### Related Concepts

Element, Attribute, Semantic HTML

---

## MCQ 0102

**Source:** Page 33; original no. 9  
**Original retained serial:** 0109  
**Topic:** HTML  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

HTML-এ Paragraph-এর tag কোনটি?

### Options

- **(ক)** `<p>`
- **(খ)** `<h1>`
- **(গ)** `<br>`
- **(ঘ)** `<span>`

### সঠিক উত্তর

**(ক) `<p>`**

### কেন সঠিক

HTML element document-এর semantic structure তৈরি করে। Paired tag-এর opening ও closing form থাকে; void element যেমন `<br>` closing tag নেয় না। `<title>` tab title, `<p>` paragraph, `<tr>` table row এবং `<div>` block container।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) `<p>`:** এটি সঠিক উত্তর।
- ❌ **(খ) `<h1>`:** এই optionটি `<p>`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই HTML প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) `<br>`:** এই optionটি `<p>`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই HTML প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) `<span>`:** এই optionটি `<p>`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই HTML প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

HTML হলো বাড়ির দেয়াল-কক্ষের কাঠামো; CSS পরে সাজায়।

### Memory Tip

**title=tab, p=paragraph, tr=row, div=container, br=break।**

### Related Concepts

Element, Attribute, Semantic HTML

---

## MCQ 0103

**Source:** Page 35; original no. 5  
**Original retained serial:** 0110  
**Topic:** HTML  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

HTML Table-এর Row তৈরির tag কোনটি?

### Options

- **(ক)** `<td>`
- **(খ)** `<tr>`
- **(গ)** `<th>`
- **(ঘ)** `<table-row>`

### সঠিক উত্তর

**(খ) `<tr>`**

### কেন সঠিক

HTML element document-এর semantic structure তৈরি করে। Paired tag-এর opening ও closing form থাকে; void element যেমন `<br>` closing tag নেয় না। `<title>` tab title, `<p>` paragraph, `<tr>` table row এবং `<div>` block container।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) `<td>`:** এই optionটি `<tr>`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই HTML প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) `<tr>`:** এটি সঠিক উত্তর।
- ❌ **(গ) `<th>`:** এই optionটি `<tr>`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই HTML প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) `<table-row>`:** এই optionটি `<tr>`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই HTML প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

HTML হলো বাড়ির দেয়াল-কক্ষের কাঠামো; CSS পরে সাজায়।

### Memory Tip

**title=tab, p=paragraph, tr=row, div=container, br=break।**

### Related Concepts

Element, Attribute, Semantic HTML

---

## MCQ 0104

**Source:** Page 35; original no. 84  
**Original retained serial:** 0111  
**Topic:** HTML  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

একটি HTML document-এর বিভিন্ন অংশ আলাদা container হিসেবে রাখতে কোন tag ব্যবহার করা হয়?

### Options

- **(ক)** `<div>`
- **(খ)** `<span>`
- **(গ)** `<select>`
- **(ঘ)** `<option>`

### সঠিক উত্তর

**(ক) `<div>`**

### কেন সঠিক

HTML element document-এর semantic structure তৈরি করে। Paired tag-এর opening ও closing form থাকে; void element যেমন `<br>` closing tag নেয় না। `<title>` tab title, `<p>` paragraph, `<tr>` table row এবং `<div>` block container।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) `<div>`:** এটি সঠিক উত্তর।
- ❌ **(খ) `<span>`:** এই optionটি `<div>`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই HTML প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) `<select>`:** এই optionটি `<div>`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই HTML প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) `<option>`:** এই optionটি `<div>`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই HTML প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

HTML হলো বাড়ির দেয়াল-কক্ষের কাঠামো; CSS পরে সাজায়।

### Memory Tip

**title=tab, p=paragraph, tr=row, div=container, br=break।**

### Related Concepts

Element, Attribute, Semantic HTML

---

## MCQ 0105

**Source:** Page 37; original no. 9  
**Original retained serial:** 0112  
**Topic:** Arithmetic Series  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

1 থেকে `n` পর্যন্ত পূর্ণসংখ্যার যোগফলের সূত্র কোনটি?

### Options

- **(ক)** n(n+1)/2
- **(খ)** n²
- **(গ)** n(n−1)/2
- **(ঘ)** `2n`

### সঠিক উত্তর

**(ক) n(n+1)/2**

### কেন সঠিক

1 থেকে n পর্যন্ত natural number-এর sum n(n+1)/2। Pairing methodে প্রথম+শেষ প্রতিটি pair n+1 হয়।

### Step-by-step

```text
Pair terms:
1 + n = n + 1
2 + (n-1) = n + 1
There are n/2 equivalent pairs.
Sum = n(n+1)/2.
```

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) n(n+1)/2:** এটি সঠিক উত্তর।
- ❌ **(খ) n²:** এই optionটি `n(n+1)/2`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Arithmetic Series প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) n(n−1)/2:** এই optionটি `n(n+1)/2`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Arithmetic Series প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) `2n`:** এই optionটি `n(n+1)/2`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Arithmetic Series প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

1 ও n, 2 ও n-1—জোড়া বানিয়ে একই sum পাওয়া।

### Memory Tip

**Sum 1..n = n(n+1)/2।**

### Related Concepts

Series, Loop Complexity, Gauss

---

# Section - Operating System

এই অংশে DOS command, OS history ও operating-system type রয়েছে।

---

## MCQ 0106

**Source:** Page 38; original no. 4  
**Original retained serial:** 0113  
**Topic:** DOS  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

MS-DOS প্রথম কোন সালে প্রকাশিত হয়?

### Options

- **(ক)** `1975`
- **(খ)** `1985`
- **(গ)** `1981`
- **(ঘ)** `1990`

### সঠিক উত্তর

**(গ) `1981`**

### কেন সঠিক

MS-DOS একটি command-line disk operating system। `DATE` command date দেখায়/পরিবর্তন করে এবং Microsoft DOS 1981 সালে প্রকাশিত হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) `1975`:** এই optionটি `1981`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই DOS প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) `1985`:** এই optionটি `1981`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই DOS প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) `1981`:** এটি সঠিক উত্তর।
- ❌ **(ঘ) `1990`:** এই optionটি `1981`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই DOS প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Graphical icon নয়, text command দিয়ে computer চালানোর পুরোনো console।

### Memory Tip

**DOS = Disk Operating System; date command = DATE।**

### Related Concepts

CLI, Command Prompt, File System

---

## MCQ 0107

**Source:** Page 38; original no. 09  
**Original retained serial:** 0114  
**Topic:** DOS  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

DOS-এ বর্তমান তারিখ দেখা বা পরিবর্তনের জন্য কোন command ব্যবহৃত হয়?

### Options

- **(ক)** SHOWDATE
- **(খ)** DATE
- **(গ)** TARIQ
- **(ঘ)** VIEW/D

### সঠিক উত্তর

**(খ) DATE**

### কেন সঠিক

MS-DOS একটি command-line disk operating system। `DATE` command date দেখায়/পরিবর্তন করে এবং Microsoft DOS 1981 সালে প্রকাশিত হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) SHOWDATE:** এই optionটি `DATE`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই DOS প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) DATE:** এটি সঠিক উত্তর।
- ❌ **(গ) TARIQ:** এই optionটি `DATE`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই DOS প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) VIEW/D:** এই optionটি `DATE`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই DOS প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Graphical icon নয়, text command দিয়ে computer চালানোর পুরোনো console।

### Memory Tip

**DOS = Disk Operating System; date command = DATE।**

### Related Concepts

CLI, Command Prompt, File System

---

## MCQ 0108

**Source:** Page 39; original no. 9  
**Original retained serial:** 0115  
**Topic:** Operating System Types  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

বইটির প্রেক্ষিতে Microsoft-এর সবচেয়ে ব্যবহৃত ও জনপ্রিয় Operating System কোনটি?

### Options

- **(ক)** Windows Vista
- **(খ)** Windows 8
- **(গ)** Windows 10/11
- **(ঘ)** Windows XP

### সঠিক উত্তর

**(গ) Windows 10/11**

### কেন সঠিক

Time-sharing OS ছোট time slice দিয়ে বহু user/processকে responsive service দেয়। Real-Time OS deadline-bound control system যেমন robot/machine control-এ ব্যবহৃত হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Windows Vista:** এই optionটি `Windows 10/11`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Operating System Types প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) Windows 8:** এই optionটি `Windows 10/11`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Operating System Types প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) Windows 10/11:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Windows XP:** এই optionটি `Windows 10/11`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Operating System Types প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

এক শিক্ষক পালা করে অনেক studentকে সময় দেন; RTOS ambulance signal-এর মতো deadline মানে।

### Memory Tip

**Time-sharing = slices; RTOS = deadlines।**

### Related Concepts

Batch OS, Multiprogramming, Scheduler

---

## MCQ 0109

**Source:** Page 40; original no. 1  
**Original retained serial:** 0116  
**Topic:** Operating System Types  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

CPU time ভাগ করে একাধিক user/process-কে service দেয় কোন OS?

### Options

- **(ক)** Batch OS
- **(খ)** Time-sharing OS
- **(গ)** Single-task OS
- **(ঘ)** No OS

### সঠিক উত্তর

**(খ) Time-sharing OS**

### কেন সঠিক

Time-sharing OS ছোট time slice দিয়ে বহু user/processকে responsive service দেয়। Real-Time OS deadline-bound control system যেমন robot/machine control-এ ব্যবহৃত হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Batch OS:** এই optionটি `Time-sharing OS`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Operating System Types প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Time-sharing OS:** এটি সঠিক উত্তর।
- ❌ **(গ) Single-task OS:** এই optionটি `Time-sharing OS`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Operating System Types প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) No OS:** এই optionটি `Time-sharing OS`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Operating System Types প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

এক শিক্ষক পালা করে অনেক studentকে সময় দেন; RTOS ambulance signal-এর মতো deadline মানে।

### Memory Tip

**Time-sharing = slices; RTOS = deadlines।**

### Related Concepts

Batch OS, Multiprogramming, Scheduler

---

## MCQ 0110

**Source:** Page 40; original no. 1  
**Original retained serial:** 0117  
**Topic:** DOS  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

DOS-এর পূর্ণরূপ কী?

### Options

- **(ক)** Data Operating System
- **(খ)** Disk Order Software
- **(গ)** Disk Operating System
- **(ঘ)** Digital Output Service

### সঠিক উত্তর

**(গ) Disk Operating System**

### কেন সঠিক

MS-DOS একটি command-line disk operating system। `DATE` command date দেখায়/পরিবর্তন করে এবং Microsoft DOS 1981 সালে প্রকাশিত হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Data Operating System:** এই optionটি `Disk Operating System`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই DOS প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) Disk Order Software:** এই optionটি `Disk Operating System`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই DOS প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) Disk Operating System:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Digital Output Service:** এটি একটি guided cable medium; প্রতিটির cost, bandwidth ও interference property ভিন্ন। কিন্তু এই প্রশ্নে চাওয়া DOS-এর নির্দিষ্ট শর্ত পূরণ করে না।

### সহজ Analogy

Graphical icon নয়, text command দিয়ে computer চালানোর পুরোনো console।

### Memory Tip

**DOS = Disk Operating System; date command = DATE।**

### Related Concepts

CLI, Command Prompt, File System

---

## MCQ 0111

**Source:** Page 40; original no. 9  
**Original retained serial:** 0118  
**Topic:** Operating System Types  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Robot বা Machine Control-এ কোন OS ব্যবহৃত হয়?

### Options

- **(ক)** Real-Time OS
- **(খ)** Time-sharing OS
- **(গ)** Batch OS
- **(ঘ)** Single-user OS

### সঠিক উত্তর

**(ক) Real-Time OS**

### কেন সঠিক

Time-sharing OS ছোট time slice দিয়ে বহু user/processকে responsive service দেয়। Real-Time OS deadline-bound control system যেমন robot/machine control-এ ব্যবহৃত হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) Real-Time OS:** এটি সঠিক উত্তর।
- ❌ **(খ) Time-sharing OS:** SHA/hash one-way digest; reversible encryption নয়। কিন্তু এই প্রশ্নে চাওয়া Operating System Types-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(গ) Batch OS:** এই optionটি `Real-Time OS`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Operating System Types প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Single-user OS:** এই optionটি `Real-Time OS`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Operating System Types প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

এক শিক্ষক পালা করে অনেক studentকে সময় দেন; RTOS ambulance signal-এর মতো deadline মানে।

### Memory Tip

**Time-sharing = slices; RTOS = deadlines।**

### Related Concepts

Batch OS, Multiprogramming, Scheduler

---

# Section - Database and Security

এই অংশে ER model, key, normalization, transaction, SQL ও cryptography রয়েছে।

---

## MCQ 0112

**Source:** Page 42; original no. 2  
**Original retained serial:** 0119  
**Topic:** Database Keys and Relationships  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

একাধিক Student একাধিক Course-এ ভর্তি হলে Relationship কোনটি?

### Options

- **(ক)** One-to-One
- **(খ)** One-to-Many
- **(গ)** Many-to-One
- **(ঘ)** Many-to-Many

### সঠিক উত্তর

**(ঘ) Many-to-Many**

### কেন সঠিক

Many-to-many relationshipে উভয় entity-এর একাধিক association থাকে এবং junction table লাগে। Foreign Key referenced table-এর keyকে নির্দেশ করে; নির্বাচিত নয় এমন Candidate Key হলো Alternate Key।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) One-to-One:** এই optionটি `Many-to-Many`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Database Keys and Relationships প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) One-to-Many:** এই optionটি `Many-to-Many`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Database Keys and Relationships প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) Many-to-One:** এই optionটি `Many-to-Many`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Database Keys and Relationships প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(ঘ) Many-to-Many:** এটি সঠিক উত্তর।

### সহজ Analogy

Student-Course enrollment list এবং পরিচয়পত্র নম্বরের মতো।

### Memory Tip

**Candidate-এর chosenটি Primary; অন্যটি Alternate; referenceটি Foreign।**

### Related Concepts

Composite Key, Junction Table, Referential Integrity

---

## MCQ 0113

**Source:** Page 42; original no. 2  
**Original retained serial:** 0120  
**Topic:** Database Keys and Relationships  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

এক Table-এর Primary Key অন্য Table-এ ব্যবহৃত হলে সেটিকে কী বলে?

### Options

- **(ক)** Alternate Key
- **(খ)** Foreign Key
- **(গ)** Super Key
- **(ঘ)** Composite Key

### সঠিক উত্তর

**(খ) Foreign Key**

### কেন সঠিক

Many-to-many relationshipে উভয় entity-এর একাধিক association থাকে এবং junction table লাগে। Foreign Key referenced table-এর keyকে নির্দেশ করে; নির্বাচিত নয় এমন Candidate Key হলো Alternate Key।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Alternate Key:** Alternate Key primary হিসেবে না-নির্বাচিত candidate key। কিন্তু এই প্রশ্নে চাওয়া Database Keys and Relationships-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(খ) Foreign Key:** এটি সঠিক উত্তর।
- ❌ **(গ) Super Key:** এই optionটি `Foreign Key`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Database Keys and Relationships প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Composite Key:** এই optionটি `Foreign Key`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Database Keys and Relationships প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Student-Course enrollment list এবং পরিচয়পত্র নম্বরের মতো।

### Memory Tip

**Candidate-এর chosenটি Primary; অন্যটি Alternate; referenceটি Foreign।**

### Related Concepts

Composite Key, Junction Table, Referential Integrity

---

## MCQ 0114

**Source:** Page 42; original no. 4  
**Original retained serial:** 0121  
**Topic:** Database Keys and Relationships  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Primary Key হিসেবে নির্বাচিত হয়নি এমন Candidate Key-কে কী বলে?

### Options

- **(ক)** Super Key
- **(খ)** Alternate Key
- **(গ)** Composite Key
- **(ঘ)** Artificial Key

### সঠিক উত্তর

**(খ) Alternate Key**

### কেন সঠিক

Many-to-many relationshipে উভয় entity-এর একাধিক association থাকে এবং junction table লাগে। Foreign Key referenced table-এর keyকে নির্দেশ করে; নির্বাচিত নয় এমন Candidate Key হলো Alternate Key।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Super Key:** এই optionটি `Alternate Key`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Database Keys and Relationships প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Alternate Key:** এটি সঠিক উত্তর।
- ❌ **(গ) Composite Key:** এই optionটি `Alternate Key`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Database Keys and Relationships প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Artificial Key:** এই optionটি `Alternate Key`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Database Keys and Relationships প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Student-Course enrollment list এবং পরিচয়পত্র নম্বরের মতো।

### Memory Tip

**Candidate-এর chosenটি Primary; অন্যটি Alternate; referenceটি Foreign।**

### Related Concepts

Composite Key, Junction Table, Referential Integrity

---

## MCQ 0115

**Source:** Page 42; original no. 5  
**Original retained serial:** 0122  
**Topic:** Hierarchical Database  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Hierarchical DBMS data কোন কাঠামোতে সংরক্ষণ করে?

### Options

- **(ক)** Network
- **(খ)** Tree
- **(গ)** Star
- **(ঘ)** Relational Table

### সঠিক উত্তর

**(খ) Tree**

### কেন সঠিক

Hierarchical DBMS dataকে parent-child tree structure-এ রাখে। একটি child সাধারণত এক parent-এর অধীন থাকে, তাই one-to-many relation স্বাভাবিক।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Network:** Network/Internet layer logical addressing ও routing করে। কিন্তু এই প্রশ্নে চাওয়া Hierarchical Database-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(খ) Tree:** এটি সঠিক উত্তর।
- ❌ **(গ) Star:** এই optionটি `Tree`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Hierarchical Database প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Relational Table:** এই optionটি `Tree`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Hierarchical Database প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Folder-এর ভিতর subfolder-এর মতো।

### Memory Tip

**Hierarchical = Tree।**

### Related Concepts

Network Model, Relational Model, Parent-Child

---

## MCQ 0116

**Source:** Page 42; original no. 7  
**Original retained serial:** 0123  
**Topic:** ER Model  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Entity-এর বৈশিষ্ট্যকে কী বলা হয়?

### Options

- **(ক)** Relationship
- **(খ)** Attribute
- **(গ)** Record
- **(ঘ)** Key only

### সঠিক উত্তর

**(খ) Attribute**

### কেন সঠিক

ER model-এ Entity rectangle, Attribute ellipse এবং Relationship diamond। Multi-valued attribute এক entity-এর একাধিক value ধারণ করে এবং double ellipse দিয়ে দেখানো হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Relationship:** এই optionটি `Attribute`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই ER Model প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Attribute:** এটি সঠিক উত্তর।
- ❌ **(গ) Record:** এই optionটি `Attribute`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই ER Model প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Key only:** এই optionটি `Attribute`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই ER Model প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

মানচিত্রে city, property ও road-এর জন্য আলাদা symbol ব্যবহারের মতো।

### Memory Tip

**Entity=rectangle; Attribute=ellipse; Relationship=diamond।**

### Related Concepts

Cardinality, Weak Entity, Key Attribute

---

## MCQ 0117

**Source:** Page 42; original no. 7  
**Original retained serial:** 0124  
**Topic:** Normalization  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Normalization-এর প্রধান উদ্দেশ্য কী?

### Options

- **(ক)** Access speed সবসময় বাড়ানো
- **(খ)** Data Redundancy ও anomaly কমানো
- **(গ)** Table সংখ্যা ইচ্ছামতো বাড়ানো
- **(ঘ)** Data type মুছে ফেলা

### সঠিক উত্তর

**(খ) Data Redundancy ও anomaly কমানো**

### কেন সঠিক

Normalization dependency অনুযায়ী relation ভেঙে redundancy ও insertion/update/deletion anomaly কমায়। 2NF composite key-এর partial dependency দূর করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Access speed সবসময় বাড়ানো:** এই optionটি `Data Redundancy ও anomaly কমানো`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Normalization প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Data Redundancy ও anomaly কমানো:** এটি সঠিক উত্তর।
- ❌ **(গ) Table সংখ্যা ইচ্ছামতো বাড়ানো:** এই optionটি `Data Redundancy ও anomaly কমানো`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Normalization প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Data type মুছে ফেলা:** এই optionটি `Data Redundancy ও anomaly কমানো`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Normalization প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

একই তথ্য বহু খাতায় না লিখে master record আলাদা রাখার মতো।

### Memory Tip

**1NF atomic; 2NF no partial; 3NF no transitive non-key dependency।**

### Related Concepts

Functional Dependency, 3NF, BCNF

---

## MCQ 0118

**Source:** Page 42; original no. 9  
**Original retained serial:** 0125  
**Topic:** ER Model  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

একটি Attribute-এর একাধিক মান থাকতে পারে—এটি কোন ধরনের Attribute?

### Options

- **(ক)** Simple
- **(খ)** Composite
- **(গ)** Multi-valued
- **(ঘ)** Derived

### সঠিক উত্তর

**(গ) Multi-valued**

### কেন সঠিক

ER model-এ Entity rectangle, Attribute ellipse এবং Relationship diamond। Multi-valued attribute এক entity-এর একাধিক value ধারণ করে এবং double ellipse দিয়ে দেখানো হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Simple:** এই optionটি `Multi-valued`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই ER Model প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) Composite:** এই optionটি `Multi-valued`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই ER Model প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) Multi-valued:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Derived:** এই optionটি `Multi-valued`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই ER Model প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

মানচিত্রে city, property ও road-এর জন্য আলাদা symbol ব্যবহারের মতো।

### Memory Tip

**Entity=rectangle; Attribute=ellipse; Relationship=diamond।**

### Related Concepts

Cardinality, Weak Entity, Key Attribute

---

## MCQ 0119

**Source:** Page 42; original no. 9  
**Original retained serial:** 0126  
**Topic:** ER Model  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

ER Diagram-এ Entity কোন প্রতীক দিয়ে দেখানো হয়?

### Options

- **(ক)** Diamond
- **(খ)** Ellipse
- **(গ)** Rectangle
- **(ঘ)** Double Ellipse

### সঠিক উত্তর

**(গ) Rectangle**

### কেন সঠিক

ER model-এ Entity rectangle, Attribute ellipse এবং Relationship diamond। Multi-valued attribute এক entity-এর একাধিক value ধারণ করে এবং double ellipse দিয়ে দেখানো হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Diamond:** এই optionটি `Rectangle`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই ER Model প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) Ellipse:** এই optionটি `Rectangle`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই ER Model প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) Rectangle:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Double Ellipse:** এই optionটি `Rectangle`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই ER Model প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

মানচিত্রে city, property ও road-এর জন্য আলাদা symbol ব্যবহারের মতো।

### Memory Tip

**Entity=rectangle; Attribute=ellipse; Relationship=diamond।**

### Related Concepts

Cardinality, Weak Entity, Key Attribute

---

## MCQ 0120

**Source:** Page 43; original no. 8  
**Original retained serial:** 0127  
**Topic:** Transaction Rollback  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Transaction-এর uncommitted change বাতিল করতে কোন command ব্যবহৃত হয়?

### Options

- **(ক)** COMMIT
- **(খ)** ROLLBACK
- **(গ)** GRANT
- **(ঘ)** SELECT

### সঠিক উত্তর

**(খ) ROLLBACK**

### কেন সঠিক

`ROLLBACK` current transaction-এর uncommitted change বাতিল করে। `COMMIT` change স্থায়ী করে; savepoint আংশিক rollback point হতে পারে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) COMMIT:** এই optionটি `ROLLBACK`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Transaction Rollback প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) ROLLBACK:** এটি সঠিক উত্তর।
- ❌ **(গ) GRANT:** এই optionটি `ROLLBACK`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Transaction Rollback প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) SELECT:** এই optionটি `ROLLBACK`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Transaction Rollback প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

খসড়া edit save না করে “undo all” করার মতো।

### Memory Tip

**COMMIT রাখে; ROLLBACK ফিরিয়ে নেয়।**

### Related Concepts

Transaction, Savepoint, Atomicity

---

## MCQ 0121

**Source:** Page 44; original no. 9  
**Original retained serial:** 0128  
**Topic:** ACID Atomicity  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

ACID-এর `A` কী বোঝায়?

### Options

- **(ক)** Atomicity
- **(খ)** Availability
- **(গ)** Authentication
- **(ঘ)** Association

### সঠিক উত্তর

**(ক) Atomicity**

### কেন সঠিক

Atomicity transaction-এর সব operation সম্পূর্ণ হবে অথবা কোনোটি স্থায়ী হবে না—এই all-or-nothing guarantee।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) Atomicity:** এটি সঠিক উত্তর।
- ❌ **(খ) Availability:** এই optionটি `Atomicity`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই ACID Atomicity প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) Authentication:** এই optionটি `Atomicity`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই ACID Atomicity প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Association:** এই optionটি `Atomicity`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই ACID Atomicity প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Bank transfer-এ debit ও credit দুটোই হবে, অর্ধেক নয়।

### Memory Tip

**A = Atomicity = All or nothing।**

### Related Concepts

Consistency, Isolation, Durability

---

## MCQ 0122

**Source:** Page 44; original no. 87  
**Original retained serial:** 0129  
**Topic:** Hashing  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Password নিরাপদে one-way রূপান্তরের প্রক্রিয়াকে কী বলে?

### Options

- **(ক)** Encryption only
- **(খ)** Hashing
- **(গ)** Compression
- **(ঘ)** Indexing

### সঠিক উত্তর

**(খ) Hashing**

### কেন সঠিক

Cryptographic hashing variable-length inputকে fixed-length one-way digest-এ রূপান্তর করে। Password storage-এ salt ও slow password hash প্রয়োজন; plain fast hash যথেষ্ট নয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Encryption only:** এই optionটি `Hashing`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Hashing প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Hashing:** এটি সঠিক উত্তর।
- ❌ **(গ) Compression:** এই optionটি `Hashing`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Hashing প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Indexing:** Indexing search access path তৈরি করে; normalization-এর বিকল্প নয়। কিন্তু এই প্রশ্নে চাওয়া Hashing-এর নির্দিষ্ট শর্ত পূরণ করে না।

### সহজ Analogy

আঙুলের ছাপ থেকে মানুষ চেনা যায়, কিন্তু ছাপ থেকে মানুষ পুনর্গঠন করা যায় না।

### Memory Tip

**Password → salted slow hash, not reversible encryption।**

### Related Concepts

Salt, bcrypt, Argon2, Digest

---

## MCQ 0123

**Source:** Page 45; original no. 4  
**Original retained serial:** 0130  
**Topic:** Normalization  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

কোন Database design process redundancy কমায় এবং integrity উন্নত করে?

### Options

- **(ক)** Indexing
- **(খ)** Normalization
- **(গ)** Denormalization
- **(ঘ)** Partitioning

### সঠিক উত্তর

**(খ) Normalization**

### কেন সঠিক

Normalization dependency অনুযায়ী relation ভেঙে redundancy ও insertion/update/deletion anomaly কমায়। 2NF composite key-এর partial dependency দূর করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Indexing:** Indexing search access path তৈরি করে; normalization-এর বিকল্প নয়। কিন্তু এই প্রশ্নে চাওয়া Normalization-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(খ) Normalization:** এটি সঠিক উত্তর।
- ❌ **(গ) Denormalization:** Normalization dependency অনুযায়ী redundancy/anomaly কমায়। কিন্তু এই প্রশ্নে চাওয়া Normalization-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(ঘ) Partitioning:** এই optionটি `Normalization`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Normalization প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

একই তথ্য বহু খাতায় না লিখে master record আলাদা রাখার মতো।

### Memory Tip

**1NF atomic; 2NF no partial; 3NF no transitive non-key dependency।**

### Related Concepts

Functional Dependency, 3NF, BCNF

---

## MCQ 0124

**Source:** Page 45; original no. 9  
**Original retained serial:** 0131  
**Topic:** SQL DDL  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

নিচের কোনটি DDL Command?

### Options

- **(ক)** SELECT
- **(খ)** INSERT
- **(গ)** ALTER
- **(ঘ)** COMMIT

### সঠিক উত্তর

**(গ) ALTER**

### কেন সঠিক

DDL schema structure define বা পরিবর্তন করে—`CREATE`, `ALTER`, `DROP`। `ALTER` existing table/object-এর definition বদলায়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) SELECT:** এই optionটি `ALTER`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই SQL DDL প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) INSERT:** এই optionটি `ALTER`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই SQL DDL প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) ALTER:** এটি সঠিক উত্তর।
- ❌ **(ঘ) COMMIT:** এই optionটি `ALTER`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই SQL DDL প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

বাড়ির blueprint বদলানো DDL; ঘরের জিনিস বদলানো DML।

### Memory Tip

**DDL = structure; DML = data।**

### Related Concepts

CREATE, DROP, DML

---

## MCQ 0125

**Source:** Page 46; original no. 8  
**Original retained serial:** 0132  
**Topic:** Normalization  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Partial Dependency দূর করতে কোন Normal Form প্রয়োজন?

### Options

- **(ক)** `1NF`
- **(খ)** `2NF`
- **(গ)** `3NF`
- **(ঘ)** BCNF

### সঠিক উত্তর

**(খ) `2NF`**

### কেন সঠিক

Normalization dependency অনুযায়ী relation ভেঙে redundancy ও insertion/update/deletion anomaly কমায়। 2NF composite key-এর partial dependency দূর করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) `1NF`:** এই optionটি `2NF`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Normalization প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) `2NF`:** এটি সঠিক উত্তর।
- ❌ **(গ) `3NF`:** এই optionটি `2NF`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Normalization প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) BCNF:** এই optionটি `2NF`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Normalization প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

একই তথ্য বহু খাতায় না লিখে master record আলাদা রাখার মতো।

### Memory Tip

**1NF atomic; 2NF no partial; 3NF no transitive non-key dependency।**

### Related Concepts

Functional Dependency, 3NF, BCNF

---

## MCQ 0126

**Source:** Page 46; original no. 9  
**Original retained serial:** 0133  
**Topic:** Symmetric Encryption  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

নিচের কোনটি বহুল ব্যবহৃত Symmetric Encryption Algorithm?

### Options

- **(ক)** AES
- **(খ)** RSA
- **(গ)** SHA
- **(ঘ)** DES

### সঠিক উত্তর

**(ক) AES**

### কেন সঠিক

AES একই secret key দিয়ে encryption ও decryption করে এবং আধুনিক বহুল ব্যবহৃত symmetric block cipher। RSA asymmetric; SHA hash function।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) AES:** এটি সঠিক উত্তর।
- ❌ **(খ) RSA:** RSA asymmetric public-key algorithm। কিন্তু এই প্রশ্নে চাওয়া Symmetric Encryption-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(গ) SHA:** SHA/hash one-way digest; reversible encryption নয়। কিন্তু এই প্রশ্নে চাওয়া Symmetric Encryption-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(ঘ) DES:** এই optionটি `AES`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Symmetric Encryption প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

একই তালা-চাবি দিয়ে lock ও unlock করার মতো।

### Memory Tip

**AES symmetric; RSA asymmetric; SHA hash।**

### Related Concepts

Block Cipher, Key, DES

---

## MCQ 0127

**Source:** Page 46; original no. 49  
**Original retained serial:** 0134  
**Topic:** Asymmetric Encryption  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

নিচের কোনটি Asymmetric Encryption Algorithm?

### Options

- **(ক)** AES
- **(খ)** RSA
- **(গ)** DES
- **(ঘ)** Blowfish

### সঠিক উত্তর

**(খ) RSA**

### কেন সঠিক

RSA public/private key pair ব্যবহার করা asymmetric algorithm। Public key দিয়ে encrypt/verify এবং private key দিয়ে decrypt/sign—use case অনুযায়ী।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) AES:** AES symmetric block cipher। কিন্তু এই প্রশ্নে চাওয়া Asymmetric Encryption-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(খ) RSA:** এটি সঠিক উত্তর।
- ❌ **(গ) DES:** এই optionটি `RSA`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Asymmetric Encryption প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Blowfish:** এই optionটি `RSA`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Asymmetric Encryption প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

খোলা ডাকবাক্সে সবাই চিঠি ফেলতে পারে, কিন্তু private keyধারী খুলতে পারে।

### Memory Tip

**RSA = public + private key।**

### Related Concepts

Digital Signature, PKI, AES

---

# Section - Data Communication and Networking

এই অংশে network scope, OSI/TCP-IP, protocol, media, duplex, cloud ও security রয়েছে।

---

## MCQ 0128

**Source:** Page 48; original no. 3  
**Original retained serial:** 0135  
**Topic:** Network Scope  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

সবচেয়ে ছোট ব্যক্তিগত ভৌগোলিক এলাকার Network কোনটি?

### Options

- **(ক)** WAN
- **(খ)** MAN
- **(গ)** PAN
- **(ঘ)** LAN

### সঠিক উত্তর

**(গ) PAN**

### কেন সঠিক

PAN ব্যক্তির খুব কাছাকাছি device network; LAN building/campus, MAN city এবং WAN বড় ভৌগোলিক এলাকা cover করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) WAN:** এই optionটি `PAN`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Network Scope প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) MAN:** এই optionটি `PAN`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Network Scope প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) PAN:** এটি সঠিক উত্তর।
- ❌ **(ঘ) LAN:** এই optionটি `PAN`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Network Scope প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

নিজের pocket devices PAN, office LAN, city MAN, country/world WAN।

### Memory Tip

**PAN < LAN < MAN < WAN।**

### Related Concepts

Bluetooth, LAN, WAN

---

## MCQ 0129

**Source:** Page 49; original no. 580  
**Original retained serial:** 0136  
**Topic:** WiMAX  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

প্রায় 10 থেকে 50 কিলোমিটার পর্যন্ত বড় এলাকায় উচ্চগতির wireless Internet দিতে কোন technology ব্যবহৃত হয়?

### Options

- **(ক)** Wi-Fi
- **(খ)** Bluetooth
- **(গ)** WiMAX
- **(ঘ)** Infrared

### সঠিক উত্তর

**(গ) WiMAX**

### কেন সঠিক

WiMAX IEEE 802.16 family-এর metropolitan broadband wireless technology, বহু কিলোমিটার coverage দিতে design করা।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Wi-Fi:** Wi-Fi wireless LAN technology। কিন্তু এই প্রশ্নে চাওয়া WiMAX-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(খ) Bluetooth:** Bluetooth short-range low-power PAN technology। কিন্তু এই প্রশ্নে চাওয়া WiMAX-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(গ) WiMAX:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Infrared:** এই optionটি `WiMAX`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই WiMAX প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

বাড়ির Wi-Fi-এর চেয়ে বড় শহর-পর্যায়ের wireless umbrella।

### Memory Tip

**WiMAX → Metropolitan broadband।**

### Related Concepts

Wi-Fi, IEEE 802.16, MAN

---

## MCQ 0130

**Source:** Page 52; original no. 3  
**Original retained serial:** 0137  
**Topic:** OSI Presentation Layer  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

Data Encryption এবং Compression OSI Model-এর কোন Layer-এর প্রধান কাজ?

### Options

- **(ক)** Application Layer
- **(খ)** Presentation Layer
- **(গ)** Transport Layer
- **(ঘ)** Network Layer

### সঠিক উত্তর

**(খ) Presentation Layer**

### কেন সঠিক

Presentation Layer data representation, translation, compression এবং encryption/decryption-এর সঙ্গে সম্পর্কিত। Application service দেয়; Transport end-to-end delivery।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Application Layer:** Application layer user-facing network protocol service দেয়। কিন্তু এই প্রশ্নে চাওয়া OSI Presentation Layer-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(খ) Presentation Layer:** এটি সঠিক উত্তর।
- ❌ **(গ) Transport Layer:** Transport layer process-to-process delivery ও ports পরিচালনা করে। কিন্তু এই প্রশ্নে চাওয়া OSI Presentation Layer-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(ঘ) Network Layer:** Network/Internet layer logical addressing ও routing করে। কিন্তু এই প্রশ্নে চাওয়া OSI Presentation Layer-এর নির্দিষ্ট শর্ত পূরণ করে না।

### সহজ Analogy

এক ভাষার message অনুবাদ, zip ও lock করে পাঠানোর clerk।

### Memory Tip

**Presentation = Translate + Compress + Encrypt।**

### Related Concepts

OSI, Session, Application

---

## MCQ 0131

**Source:** Page 52; original no. 4  
**Original retained serial:** 0138  
**Topic:** Application Layer Protocols  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

DNS ও HTTP কোন Layer-এর Protocol?

### Options

- **(ক)** Transport
- **(খ)** Internet
- **(গ)** Application
- **(ঘ)** Network Access

### সঠিক উত্তর

**(গ) Application**

### কেন সঠিক

DNS name resolution এবং HTTP web resource transfer—দুটিই Application Layer protocol। তারা transport হিসেবে UDP/TCP ব্যবহার করতে পারে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Transport:** Transport layer process-to-process delivery ও ports পরিচালনা করে। কিন্তু এই প্রশ্নে চাওয়া Application Layer Protocols-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(খ) Internet:** এই optionটি `Application`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Application Layer Protocols প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) Application:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Network Access:** Network/Internet layer logical addressing ও routing করে। কিন্তু এই প্রশ্নে চাওয়া Application Layer Protocols-এর নির্দিষ্ট শর্ত পূরণ করে না।

### সহজ Analogy

User যে service সরাসরি ব্যবহার করে, সেটি stack-এর application floor।

### Memory Tip

**HTTP/DNS/SMTP/FTP → Application Layer।**

### Related Concepts

TCP, UDP, Port

---

## MCQ 0132

**Source:** Page 52; original no. 6  
**Original retained serial:** 0139  
**Topic:** TCP/IP Internet Layer  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

TCP/IP Model-এ IP Address কোন Layer-এর?

### Options

- **(ক)** Network Access
- **(খ)** Internet
- **(গ)** Transport
- **(ঘ)** Application

### সঠিক উত্তর

**(খ) Internet**

### কেন সঠিক

TCP/IP Internet Layer logical addressing ও routing করে; IPv4/IPv6 এখানে। OSI model-এর Network Layer-এর সমতুল্য।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Network Access:** Network/Internet layer logical addressing ও routing করে। কিন্তু এই প্রশ্নে চাওয়া TCP/IP Internet Layer-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(খ) Internet:** এটি সঠিক উত্তর।
- ❌ **(গ) Transport:** Transport layer process-to-process delivery ও ports পরিচালনা করে। কিন্তু এই প্রশ্নে চাওয়া TCP/IP Internet Layer-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(ঘ) Application:** Application layer user-facing network protocol service দেয়। কিন্তু এই প্রশ্নে চাওয়া TCP/IP Internet Layer-এর নির্দিষ্ট শর্ত পূরণ করে না।

### সহজ Analogy

চিঠির গন্তব্য শহরের address দেখে route ঠিক করার মতো।

### Memory Tip

**IP = Internet/Network Layer।**

### Related Concepts

Router, ICMP, Routing

---

## MCQ 0133

**Source:** Page 54; original no. 2  
**Original retained serial:** 0140  
**Topic:** ARP  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Local Network-এ IPv4 Address থেকে MAC Address জানার Protocol কোনটি?

### Options

- **(ক)** DNS
- **(খ)** ARP
- **(গ)** DHCP
- **(ঘ)** FTP

### সঠিক উত্তর

**(খ) ARP**

### কেন সঠিক

ARP local network-এ next-hop IPv4 address-এর MAC address resolve করে। Remote destination হলে host gateway-এর MAC resolve করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) DNS:** এই optionটি `ARP`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই ARP প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) ARP:** এটি সঠিক উত্তর।
- ❌ **(গ) DHCP:** DHCP network configuration lease দেয়। কিন্তু এই প্রশ্নে চাওয়া ARP-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(ঘ) FTP:** এই optionটি `ARP`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই ARP প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

নাম জানা আছে, স্থানীয় ফোনবুকে নম্বর খোঁজার মতো।

### Memory Tip

**ARP = IPv4 to MAC on local link।**

### Related Concepts

MAC, Broadcast, Neighbor Discovery

---

## MCQ 0134

**Source:** Page 54; original no. 4  
**Original retained serial:** 0141  
**Topic:** DHCP  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

DHCP DISCOVER message সাধারণত কোন ধরনের delivery ব্যবহার করে?

### Options

- **(ক)** Unicast
- **(খ)** Anycast
- **(গ)** Multicast
- **(ঘ)** Broadcast

### সঠিক উত্তর

**(ঘ) Broadcast**

### কেন সঠিক

DHCP clientকে IP, mask, gateway ও DNS configuration দেয়। Initial DISCOVER সাধারণত broadcast, কারণ client তখন server ও নিজ network configuration জানে না।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Unicast:** এই optionটি `Broadcast`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই DHCP প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) Anycast:** এই optionটি `Broadcast`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই DHCP প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) Multicast:** এই optionটি `Broadcast`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই DHCP প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(ঘ) Broadcast:** এটি সঠিক উত্তর।

### সহজ Analogy

নতুন অফিসে এসে receptionকে সবাইকে শোনানো প্রশ্ন—“আমার desk কোথায়?”

### Memory Tip

**DORA: Discover, Offer, Request, Ack।**

### Related Concepts

UDP 67/68, Lease, Broadcast

---

## MCQ 0135

**Source:** Page 55; original no. 0  
**Original retained serial:** 0142  
**Topic:** DNS Transport  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

Simple DNS query-এর জন্য প্রধানত কোন Transport Protocol ব্যবহৃত হয়?

### Options

- **(ক)** TCP
- **(খ)** UDP
- **(গ)** HTTP
- **(ঘ)** SMTP

### সঠিক উত্তর

**(খ) UDP**

### কেন সঠিক

Simple DNS query সাধারণত UDP port 53 ব্যবহার করে কারণ overhead কম। Truncated response, zone transfer বা কিছু modern use case-এ TCP ব্যবহৃত হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) TCP:** TCP reliable connection-oriented transport। কিন্তু এই প্রশ্নে চাওয়া DNS Transport-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(খ) UDP:** এটি সঠিক উত্তর।
- ❌ **(গ) HTTP:** HTTP web application protocol। কিন্তু এই প্রশ্নে চাওয়া DNS Transport-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(ঘ) SMTP:** এই optionটি `UDP`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই DNS Transport প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

ছোট প্রশ্ন postcard-এ; বড় answer হলে registered parcel।

### Memory Tip

**DNS usually UDP; TCP when needed।**

### Related Concepts

Port 53, Resolver, TCP

---

## MCQ 0136

**Source:** Page 55; original no. 1  
**Original retained serial:** 0143  
**Topic:** Phishing  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

বিশ্বস্ত উৎস সেজে sensitive তথ্য নেওয়ার Cyber Attack কোনটি?

### Options

- **(ক)** Phishing
- **(খ)** DDoS
- **(গ)** Ransomware
- **(ঘ)** Brute-force only

### সঠিক উত্তর

**(ক) Phishing**

### কেন সঠিক

Phishing trusted ব্যক্তি/প্রতিষ্ঠান সেজে password, OTP বা sensitive তথ্য আদায় করার social-engineering attack।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) Phishing:** এটি সঠিক উত্তর।
- ❌ **(খ) DDoS:** এই optionটি `Phishing`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Phishing প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) Ransomware:** এই optionটি `Phishing`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Phishing প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Brute-force only:** এই optionটি `Phishing`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Phishing প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

নকল ব্যাংক কর্মকর্তা ফোন করে PIN চাওয়ার মতো।

### Memory Tip

**Verify sender/domain; never share OTP।**

### Related Concepts

Social Engineering, Spoofing, MFA

---

## MCQ 0137

**Source:** Page 55; original no. 1  
**Original retained serial:** 0144  
**Topic:** DHCP  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Client-কে স্বয়ংক্রিয়ভাবে IP configuration দেয় কোন Protocol?

### Options

- **(ক)** DHCP
- **(খ)** ARP
- **(গ)** DNS
- **(ঘ)** ICMP

### সঠিক উত্তর

**(ক) DHCP**

### কেন সঠিক

DHCP clientকে IP, mask, gateway ও DNS configuration দেয়। Initial DISCOVER সাধারণত broadcast, কারণ client তখন server ও নিজ network configuration জানে না।

### প্রতিটি Option-এর বিশ্লেষণ

- ✅ **(ক) DHCP:** এটি সঠিক উত্তর।
- ❌ **(খ) ARP:** ARP local IPv4-to-MAC resolution করে। কিন্তু এই প্রশ্নে চাওয়া DHCP-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(গ) DNS:** এই optionটি `DHCP`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই DHCP প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) ICMP:** এই optionটি `DHCP`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই DHCP প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

নতুন অফিসে এসে receptionকে সবাইকে শোনানো প্রশ্ন—“আমার desk কোথায়?”

### Memory Tip

**DORA: Discover, Offer, Request, Ack।**

### Related Concepts

UDP 67/68, Lease, Broadcast

---

## MCQ 0138

**Source:** Page 55; original no. 2  
**Original retained serial:** 0145  
**Topic:** SSH  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

SSH-এর default Port Number কত?

### Options

- **(ক)** `20`
- **(খ)** `22`
- **(গ)** `25`
- **(ঘ)** `53`

### সঠিক উত্তর

**(খ) `22`**

### কেন সঠিক

SSH encrypted remote login ও command execution protocol; default TCP port 22।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) `20`:** এই optionটি `22`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই SSH প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) `22`:** এটি সঠিক উত্তর।
- ❌ **(গ) `25`:** এই optionটি `22`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই SSH প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) `53`:** এই optionটি `22`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই SSH প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

দূরের computer-এ নিরাপদ তালাবদ্ধ terminal খুলে কাজ করা।

### Memory Tip

**SSH = TCP 22।**

### Related Concepts

SFTP, Telnet, Public Key

---

## MCQ 0139

**Source:** Page 55; original no. 6  
**Original retained serial:** 0146  
**Topic:** Bluetooth  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

তারবিহীন সংযোগগুলোর মধ্যে কোনটি সাধারণত স্বল্প দূরত্বে এবং কম শক্তিতে ব্যবহৃত হয়?

### Options

- **(ক)** Wi-Fi
- **(খ)** Bluetooth
- **(গ)** Satellite
- **(ঘ)** Cellular (5G)

### সঠিক উত্তর

**(খ) Bluetooth**

### কেন সঠিক

Bluetooth short-range, low-power personal-area communication-এর জন্য design করা। Wi-Fi সাধারণত বেশি range/throughput; satellite long-distance।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Wi-Fi:** Wi-Fi wireless LAN technology। কিন্তু এই প্রশ্নে চাওয়া Bluetooth-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(খ) Bluetooth:** এটি সঠিক উত্তর।
- ❌ **(গ) Satellite:** এই optionটি `Bluetooth`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Bluetooth প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Cellular (5G):** এই optionটি `Bluetooth`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Bluetooth প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Wireless earphone ও phone-এর ছোট ব্যক্তিগত link।

### Memory Tip

**Bluetooth = short range + low power + PAN।**

### Related Concepts

IEEE 802.15, BLE, PAN

---

## MCQ 0140

**Source:** Page 55; original no. 9  
**Original retained serial:** 0147  
**Topic:** TCP vs UDP  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

TCP যে সুবিধা দেয় কিন্তু UDP সাধারণত দেয় না—সেটি কোনটি?

### Options

- **(ক)** Port Number
- **(খ)** Reliable ordered delivery
- **(গ)** Checksum
- **(ঘ)** Datagram boundary

### সঠিক উত্তর

**(খ) Reliable ordered delivery**

### কেন সঠিক

TCP connection-oriented reliable ordered byte stream দেয়—sequence, ACK, retransmission ও flow controlসহ। UDP lower overhead datagram service, reliability/order applicationকে সামলাতে হয়।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Port Number:** এই optionটি `Reliable ordered delivery`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই TCP vs UDP প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Reliable ordered delivery:** এটি সঠিক উত্তর।
- ❌ **(গ) Checksum:** এই optionটি `Reliable ordered delivery`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই TCP vs UDP প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Datagram boundary:** এই optionটি `Reliable ordered delivery`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই TCP vs UDP প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

TCP registered courier; UDP দ্রুত postcard।

### Memory Tip

**TCP reliable/order; UDP lightweight/message।**

### Related Concepts

Port, Flow Control, Checksum

---

## MCQ 0141

**Source:** Page 56; original no. 2  
**Original retained serial:** 0148  
**Topic:** Encryption  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

Data communication-এ তথ্যকে দুর্বোধ্য রূপে পরিবর্তন করার প্রক্রিয়াকে কী বলে?

### Options

- **(ক)** Decryption
- **(খ)** Authentication
- **(গ)** Encryption
- **(ঘ)** Broadcast

### সঠিক উত্তর

**(গ) Encryption**

### কেন সঠিক

Encryption plaintextকে key ব্যবহার করে ciphertext-এ রূপান্তর করে যাতে অনুমোদনহীন ব্যক্তি অর্থ বুঝতে না পারে। Decryption বৈধ key দিয়ে original data উদ্ধার করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Decryption:** এই optionটি `Encryption`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Encryption প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) Authentication:** এই optionটি `Encryption`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Encryption প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) Encryption:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Broadcast:** এই optionটি `Encryption`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Encryption প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

চিঠি secret code-এ লেখা; keyধারীই পড়তে পারে।

### Memory Tip

**Plaintext → Encrypt + key → Ciphertext।**

### Related Concepts

Decryption, Cipher, Key

---

## MCQ 0142

**Source:** Page 56; original no. 5  
**Original retained serial:** 0149  
**Topic:** Half-duplex  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Walkie-Talkie কোন communication mode-এ কাজ করে?

### Options

- **(ক)** Simplex
- **(খ)** Half-duplex
- **(গ)** Full-duplex
- **(ঘ)** Broadcast-only

### সঠিক উত্তর

**(খ) Half-duplex**

### কেন সঠিক

Half-duplex-এ দুই দিকেই communication সম্ভব, কিন্তু একই সময়ে নয়। Walkie-talkie-তে এক পক্ষ কথা বললে অন্য পক্ষ শোনে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Simplex:** Simplex শুধু এক direction। কিন্তু এই প্রশ্নে চাওয়া Half-duplex-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(খ) Half-duplex:** এটি সঠিক উত্তর।
- ❌ **(গ) Full-duplex:** Full-duplex দুই direction একই সময়ে। কিন্তু এই প্রশ্নে চাওয়া Half-duplex-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(ঘ) Broadcast-only:** এই optionটি `Half-duplex`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Half-duplex প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

এক lane bridge-এ গাড়ি দুই দিক থেকে যায়, কিন্তু পালা করে।

### Memory Tip

**Half-duplex = both directions, not simultaneous।**

### Related Concepts

Simplex, Full-duplex, Push-to-talk

---

## MCQ 0143

**Source:** Page 56; original no. 6  
**Original retained serial:** 0150  
**Topic:** Full-duplex  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Telephone conversation কোন mode-এর উদাহরণ?

### Options

- **(ক)** Simplex
- **(খ)** Half-duplex
- **(গ)** Full-duplex
- **(ঘ)** Multicast

### সঠিক উত্তর

**(গ) Full-duplex**

### কেন সঠিক

Full-duplex-এ দুই endpoint একই সময়ে send ও receive করতে পারে। Telephone conversation এর পরিচিত উদাহরণ।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Simplex:** Simplex শুধু এক direction। কিন্তু এই প্রশ্নে চাওয়া Full-duplex-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(খ) Half-duplex:** Half-duplex দুই direction, কিন্তু একই সময়ে নয়। কিন্তু এই প্রশ্নে চাওয়া Full-duplex-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(গ) Full-duplex:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Multicast:** এই optionটি `Full-duplex`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Full-duplex প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

দুই ব্যক্তি একই সময়ে কথা বলতে ও শুনতে পারে।

### Memory Tip

**Full-duplex = simultaneous both ways।**

### Related Concepts

Simplex, Half-duplex, Duplexing

---

## MCQ 0144

**Source:** Page 57; original no. 0  
**Original retained serial:** 0151  
**Topic:** Transport Layer Ports  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

TCP/IP Model-এর কোন Layer port binding-এর জন্য দায়ী?

### Options

- **(ক)** Application Layer
- **(খ)** Internet Layer
- **(গ)** Transport Layer
- **(ঘ)** Network Access Layer

### সঠিক উত্তর

**(গ) Transport Layer**

### কেন সঠিক

TCP/IP Transport Layer port number ব্যবহার করে data সঠিক application process/socket-এ demultiplex করে। IP address host চিহ্নিত করে, port application endpoint।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Application Layer:** Application layer user-facing network protocol service দেয়। কিন্তু এই প্রশ্নে চাওয়া Transport Layer Ports-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(খ) Internet Layer:** Network/Internet layer logical addressing ও routing করে। কিন্তু এই প্রশ্নে চাওয়া Transport Layer Ports-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(গ) Transport Layer:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Network Access Layer:** Network/Internet layer logical addressing ও routing করে। কিন্তু এই প্রশ্নে চাওয়া Transport Layer Ports-এর নির্দিষ্ট শর্ত পূরণ করে না।

### সহজ Analogy

Apartment building-এর address IP, flat number port।

### Memory Tip

**IP finds host; Port finds process।**

### Related Concepts

TCP, UDP, Socket

---

## MCQ 0145

**Source:** Page 57; original no. 0  
**Original retained serial:** 0152  
**Topic:** Asynchronous Serial Framing  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

Asynchronous Serial Transmission-এ একটি data byte বা character-এর সমাপ্তি নির্দেশ করতে কোন bit ব্যবহৃত হয়?

### Options

- **(ক)** Start Bit
- **(খ)** Stop Bit
- **(গ)** Clock Signal
- **(ঘ)** Parity Bit

### সঠিক উত্তর

**(খ) Stop Bit**

### কেন সঠিক

Asynchronous serial transmission-এ start bit character শুরু এবং stop bit character শেষ নির্দেশ করে; shared clock line থাকে না।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Start Bit:** এই optionটি `Stop Bit`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Asynchronous Serial Framing প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Stop Bit:** এটি সঠিক উত্তর।
- ❌ **(গ) Clock Signal:** এই optionটি `Stop Bit`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Asynchronous Serial Framing প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Parity Bit:** এই optionটি `Stop Bit`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Asynchronous Serial Framing প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

প্রতিটি parcel-এর শুরু ও শেষ marker লাগানোর মতো।

### Memory Tip

**Start begins; Stop ends।**

### Related Concepts

Parity, Baud Rate, UART

---

## MCQ 0146

**Source:** Page 57; original no. 4  
**Original retained serial:** 0153  
**Topic:** Transmission Media  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

নিচের কোনটি Guided Transmission Medium?

### Options

- **(ক)** Radio Wave
- **(খ)** Microwave
- **(গ)** Coaxial Cable
- **(ঘ)** Infrared

### সঠিক উত্তর

**(গ) Coaxial Cable**

### কেন সঠিক

Guided medium physical cable-এর ভিতর signal পরিচালনা করে—twisted pair, coaxial ও fiber। Radio, microwave ও infrared unguided।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Radio Wave:** এই optionটি `Coaxial Cable`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Transmission Media প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) Microwave:** এই optionটি `Coaxial Cable`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Transmission Media প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) Coaxial Cable:** এটি সঠিক উত্তর।
- ❌ **(ঘ) Infrared:** এই optionটি `Coaxial Cable`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Transmission Media প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

ট্রেন rail ধরে guided; aircraft খোলা আকাশে unguided।

### Memory Tip

**Cable = guided; wireless wave = unguided।**

### Related Concepts

Fiber, Twisted Pair, Radio

---

## MCQ 0147

**Source:** Page 58; original no. 1  
**Original retained serial:** 0154  
**Topic:** Data Center Cooling  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

Data Center-এর temperature ও humidity নিয়ন্ত্রণে কোন system ব্যবহৃত হয়?

### Options

- **(ক)** UPS
- **(খ)** IDS
- **(গ)** CRAC
- **(ঘ)** DNS

### সঠিক উত্তর

**(গ) CRAC**

### কেন সঠিক

CRAC (Computer Room Air Conditioner) data center-এর temperature ও humidity control করে যাতে server নির্ভরযোগ্যভাবে চলে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) UPS:** এই optionটি `CRAC`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Data Center Cooling প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) IDS:** এই optionটি `CRAC`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Data Center Cooling প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(গ) CRAC:** এটি সঠিক উত্তর।
- ❌ **(ঘ) DNS:** এই optionটি `CRAC`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Data Center Cooling প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Server room-এর বিশেষ climate-control system।

### Memory Tip

**CRAC controls cooling/humidity।**

### Related Concepts

HVAC, Hot Aisle, DCIM

---

## MCQ 0148

**Source:** Page 58; original no. 4  
**Original retained serial:** 0155  
**Topic:** UTP Cable  
**Correction basis:** Visually corrected from source scan

### প্রশ্ন

Internet/Ethernet cabling-এ নিচের কোন cableটি সবচেয়ে বেশি ব্যবহৃত হয়?

### Options

- **(ক)** STP
- **(খ)** UTP
- **(গ)** Coaxial Cable
- **(ঘ)** Optical Fiber

### সঠিক উত্তর

**(খ) UTP**

### কেন সঠিক

UTP twisted-pair cable Ethernet LAN-এ ব্যাপক ব্যবহৃত, সস্তা ও সহজ installation-এর জন্য। Twist electromagnetic interference কমাতে সাহায্য করে।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) STP:** এটি একটি guided cable medium; প্রতিটির cost, bandwidth ও interference property ভিন্ন। কিন্তু এই প্রশ্নে চাওয়া UTP Cable-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ✅ **(খ) UTP:** এটি সঠিক উত্তর।
- ❌ **(গ) Coaxial Cable:** এটি একটি guided cable medium; প্রতিটির cost, bandwidth ও interference property ভিন্ন। কিন্তু এই প্রশ্নে চাওয়া UTP Cable-এর নির্দিষ্ট শর্ত পূরণ করে না।
- ❌ **(ঘ) Optical Fiber:** এটি একটি guided cable medium; প্রতিটির cost, bandwidth ও interference property ভিন্ন। কিন্তু এই প্রশ্নে চাওয়া UTP Cable-এর নির্দিষ্ট শর্ত পূরণ করে না।

### সহজ Analogy

দুটি তার জড়িয়ে বাইরের noise-এর প্রভাব একে অন্যকে cancel করার মতো।

### Memory Tip

**UTP common Ethernet copper cable।**

### Related Concepts

STP, RJ-45, Cat6

---

## MCQ 0149

**Source:** Page 58; original no. 8  
**Original retained serial:** 0156  
**Topic:** Community Cloud  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

একাধিক সমমনা প্রতিষ্ঠান যৌথভাবে Cloud share করলে তাকে কী বলে?

### Options

- **(ক)** Public Cloud
- **(খ)** Private Cloud
- **(গ)** Hybrid Cloud
- **(ঘ)** Community Cloud

### সঠিক উত্তর

**(ঘ) Community Cloud**

### কেন সঠিক

Community Cloud একই ধরনের mission, policy বা compliance প্রয়োজন থাকা একাধিক প্রতিষ্ঠানের যৌথ cloud infrastructure।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Public Cloud:** এই optionটি `Community Cloud`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Community Cloud প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(খ) Private Cloud:** এই optionটি `Community Cloud`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Community Cloud প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(গ) Hybrid Cloud:** এই optionটি `Community Cloud`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Community Cloud প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(ঘ) Community Cloud:** এটি সঠিক উত্তর।

### সহজ Analogy

কয়েকটি বিশ্ববিদ্যালয় মিলে shared research cloud চালানোর মতো।

### Memory Tip

**Community = shared by related organizations।**

### Related Concepts

Public, Private, Hybrid Cloud

---

## MCQ 0150

**Source:** Page 59; original no. 5  
**Original retained serial:** 0157  
**Topic:** Early Search Engine  
**Correction basis:** AI reconstruction from recognizable source concept

### প্রশ্ন

প্রথম দিকের Search Engine হিসেবে পরিচিত কোনটি?

### Options

- **(ক)** Google
- **(খ)** Archie
- **(গ)** AltaVista
- **(ঘ)** Bing

### সঠিক উত্তর

**(খ) Archie**

### কেন সঠিক

Archie 1990-এর শুরুতে anonymous FTP archive-এর file list index করত এবং প্রথমদিকের Internet search tool হিসেবে পরিচিত।

### প্রতিটি Option-এর বিশ্লেষণ

- ❌ **(ক) Google:** এই optionটি `Archie`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Early Search Engine প্রসঙ্গে এটি সঠিক নয়।
- ✅ **(খ) Archie:** এটি সঠিক উত্তর।
- ❌ **(গ) AltaVista:** এই optionটি `Archie`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Early Search Engine প্রসঙ্গে এটি সঠিক নয়।
- ❌ **(ঘ) Bing:** এই optionটি `Archie`-এর প্রয়োজনীয় সংজ্ঞা বা property প্রকাশ করে না; তাই Early Search Engine প্রসঙ্গে এটি সঠিক নয়।

### সহজ Analogy

Web page নয়, FTP file catalog-এর digital index।

### Memory Tip

**Archie searched FTP archives।**

### Related Concepts

WAIS, Gopher, Web Search

---

# Removal Audit Summary

নিচের original serial-গুলো primary study file থেকে বাদ দেওয়া হয়েছে:

- **0056:** Duplicate of MCQ 0055 (while condition checked before loop body)
- **0059:** Duplicate of MCQ 0044 (strcmp compares two strings)
- **0063:** Unrecoverable OCR fragment; no reliable question/options in source block
- **0071:** Ambiguous source wording; retaining it would risk teaching a wrong definition
- **0075:** Near-duplicate of Encapsulation questions 0067/0072
- **0079:** Duplicate of MCQ 0044 (strcmp)
- **0087:** Duplicate of MCQ 0085 (virtual keyword for runtime overriding)

সম্পূর্ণ audit আলাদা Markdown file-এ দেওয়া হয়েছে।
