# ICT Lecturer MCQ — Clean Study Edition

## MCQ 0151–0300

এই সংস্করণে Markdown structure, contradictory option analysis, OCR-garbled text, hidden characters এবং malformed inline code ঠিক করা হয়েছে।

---

# Section — Programming Fundamentals & OOP

---

## MCQ 0151

**Master-bank reference:** Question 0001
**Metadata:** Topic: Structured Programming > C Program Entry Point | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Hosted C environment-এ program execution কোন function থেকে শুরু হয়?

A) `start()`
B) `init()`
C) `main()`
D) `execute()`

**সঠিক উত্তর: C) `main()`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `main()` hosted C program-এর standard entry function। Environment program চালু করলে control `main()`-এ দেয়।
- **A option কেন ভুল:** `start()` standard C entry function নয়।
- **B option কেন ভুল:** `init()` user-defined helper হতে পারে, entry point নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `execute()` নামে standard entry function নেই।
- **Related Concept:** `main()` সাধারণত `int main(void)` বা `int main(int argc, char *argv[])` form-এ লেখা হয়।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** C program শুরু হয় `main()` থেকে।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0152

**Master-bank reference:** Question 0002
**Metadata:** Topic: Structured Programming > Tokens | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. C program-এর ক্ষুদ্রতম অর্থপূর্ণ lexical unit কোনটি?

A) Token
B) Module
C) Package
D) Procedure

**সঠিক উত্তর: A) Token**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Keyword, identifier, literal, operator ও punctuator—সবই token।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Module একটি বড় organizational unit।
- **C option কেন ভুল:** Package standard C lexical unit নয়।
- **D option কেন ভুল:** Procedure function/routine বোঝায়, lexical unit নয়।
- **Related Concept:** `int x = 5;`-এ `int`, `x`, `=`, `5`, `;` পৃথক token।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Whitespace separator; semicolon-ও token।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0153

**Master-bank reference:** Question 0003
**Metadata:** Topic: Structured Programming > Identifier | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. নিচের কোনটি valid C identifier?

A) `2ndValue`
B) `total_marks2`
C) `total-marks`
D) `float`

**সঠিক উত্তর: B) `total_marks2`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `total_marks2` letter দিয়ে শুরু হয়েছে এবং শুধু valid character ব্যবহার করেছে।
- **A option কেন ভুল:** Identifier digit দিয়ে শুরু করা যায় না।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Hyphen `-` subtraction operator হিসেবে ধরা হয়।
- **D option কেন ভুল:** `float` reserved keyword।
- **Related Concept:** C identifier case-sensitive।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** প্রথম character letter/underscore; পরে letter/digit/underscore।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0154

**Master-bank reference:** Question 0004
**Metadata:** Topic: Structured Programming > Operator Precedence | Difficulty: Medium | Type: Code
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. নিচের code-টির output কী হবে?

```c
#include <stdio.h>
int main(void){ int x=5; printf("%d", x+3*2); return 0; }
```

A) 16
B) 13
C) 10
D) 11

**সঠিক উত্তর: D) 11**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Trace

```text
x = 5
3 × 2 = 6
5 + 6 = 11
Output = 11
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `*`-এর precedence `+`-এর চেয়ে বেশি; তাই আগে `3*2`, পরে `5+6`।
- **A option কেন ভুল:** সব value ভুলভাবে multiply করা হয়েছে।
- **B option কেন ভুল:** সঠিক operation order অনুসরণ করা হয়নি।
- **C option কেন ভুল:** শুধু `x*2` ধরনের ভুল করা হয়েছে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Parentheses precedence override করতে পারে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Multiplication আগে, addition পরে।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0155

**Master-bank reference:** Question 0005
**Metadata:** Topic: Structured Programming > Program Errors | Difficulty: Medium | Type: Scenario
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Program compile ও run করে, কিন্তু addition-এর বদলে subtraction ব্যবহারের কারণে ভুল result দেয়। এটি কোন error?

A) Syntax Error
B) Linker Error
C) Logical Error
D) Preprocessing Error

**সঠিক উত্তর: C) Logical Error**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Program validভাবে চলে, কিন্তু algorithmic logic ভুল হওয়ায় output ভুল—এটাই Logical Error।
- **A option কেন ভুল:** Syntax Error হলে source grammar invalid হয়।
- **B option কেন ভুল:** Linker Error external symbol resolution-এর সমস্যা।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Preprocessing Error directive processing-এর সমস্যা।
- **Related Concept:** Testing Logical Error প্রকাশ করে; debugging root cause খুঁজে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Runs but wrong output = Logical Error।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0156

**Master-bank reference:** Question 0011
**Metadata:** Topic: Structured Programming > Preprocessor | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `#include` ও `#define` কোন translation stage-এ process হয়?

A) Linking
B) Preprocessing
C) Loading
D) Execution

**সঠিক উত্তর: B) Preprocessing**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Compiler-এর আগে Preprocessor directive expand ও process করে।
- **A option কেন ভুল:** Linker object/library combine করে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Loader executable memory-তে আনে।
- **D option কেন ভুল:** Execution program চালায়।
- **Related Concept:** Macro expansion ও conditional compilation-ও preprocessing।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** `#` দেখলে Preprocessor।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0157

**Master-bank reference:** Question 0012
**Metadata:** Topic: Structured Programming > Linker | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `printf()`-এর externally defined implementation-এর reference প্রধানত কে resolve করে?

A) Editor
B) Preprocessor
C) Debugger
D) Linker

**সঠিক উত্তর: D) Linker**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Linker library/object file থেকে external symbol-এর definition খুঁজে reference resolve করে।
- **A option কেন ভুল:** Editor code লেখার tool।
- **B option কেন ভুল:** Preprocessor declaration include করে, link নয়।
- **C option কেন ভুল:** Debugger runtime behavior পরীক্ষা করে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Header declaration দেয়; library implementation দেয়।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** External symbol resolve = Linker।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0158

**Master-bank reference:** Question 0013
**Metadata:** Topic: Structured Programming > Object File | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Object file সম্পর্কে কোন statement সঠিক?

A) Machine code-এর সঙ্গে symbol ও relocation information থাকতে পারে
B) শুধু source code থাকে
C) সবসময় সরাসরি executable
D) শুধু preprocessor directive থাকে

**সঠিক উত্তর: A) Machine code-এর সঙ্গে symbol ও relocation information থাকতে পারে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Object file final linking-এর জন্য machine instructions, symbol table ও relocation data ধারণ করতে পারে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Source file আলাদা থাকে।
- **C option কেন ভুল:** Unresolved external reference থাকতে পারে।
- **D option কেন ভুল:** Directive preprocessing-এ process হয়ে যায়।
- **Related Concept:** একাধিক object file link করে executable হয়।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Object file প্রায় machine code, final executable নয়।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0159

**Master-bank reference:** Question 0015
**Metadata:** Topic: Structured Programming > Include Guard | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Header file-এ include guard-এর প্রধান উদ্দেশ্য কী?

A) Header encrypt করা
B) Repeated inclusion-এর সমস্যা প্রতিরোধ
C) Runtime speed বাড়ানো
D) `main()` declare করা

**সঠিক উত্তর: B) Repeated inclusion-এর সমস্যা প্রতিরোধ**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একই declaration/definition বারবার process হওয়া ঠেকাতে `#ifndef/#define/#endif` ব্যবহার হয়।
- **A option কেন ভুল:** Encryption নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** মূল উদ্দেশ্য runtime optimization নয়।
- **D option কেন ভুল:** `main()`-এর সঙ্গে সম্পর্ক নেই।
- **Related Concept:** `#pragma once` implementation-specific alternative হতে পারে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Header logically once।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0160

**Master-bank reference:** Question 0022
**Metadata:** Topic: Structured Programming > Unsigned Range | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. N-bit unsigned integer-এর range কোনটি?

A) −2^N থেকে 2^N−1
B) 0 থেকে 2^N−1
C) −2^(N−1) থেকে 2^(N−1)
D) 1 থেকে 2^N

**সঠিক উত্তর: B) 0 থেকে 2^N−1**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** N bit-এর 2^N pattern 0 থেকে 2^N−1 value প্রকাশ করে।
- **A option কেন ভুল:** Range অসম্ভব বড়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Signed range-এর কাছাকাছি।
- **D option কেন ভুল:** Zero বাদ এবং maximum ভুল।
- **Related Concept:** 8-bit unsigned range 0–255।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Unsigned minimum zero।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0161

**Master-bank reference:** Question 0023
**Metadata:** Topic: Structured Programming > Cast Placement | Difficulty: Medium | Type: Calculation
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `(double)(5/2)` expression-এর result কী?

A) 2.5
B) 3.0
C) 2.0
D) 2.25

**সঠিক উত্তর: C) 2.0**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Evaluation

```text
5 / 2 = 2        (integer division)
(double)2 = 2.0
```

#### Final Answer

```text
Result = 2.0
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Inner parentheses আগে evaluate হয়; `5/2` integer division-এ 2, পরে double cast হয়ে 2.0।
- **A option কেন ভুল:** `(double)5/2` হলে 2.5।
- **B option কেন ভুল:** Integer division round up করে না।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Expression থেকে আসে না।
- **Related Concept:** Cast-এর অবস্থান result বদলায়।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Parentheses-এর ভেতর আগে।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0162

**Master-bank reference:** Question 0024
**Metadata:** Topic: Structured Programming > Negative Integer Division | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Modern C-তে `-17/5`-এর result কী?

A) −4
B) 4
C) −3.4
D) −3

**সঠিক উত্তর: D) −3**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Integer division fractional অংশ zero-এর দিকে truncate করে; −3.4 → −3।
- **A option কেন ভুল:** এটি floor division হলে হতো।
- **B option কেন ভুল:** Sign বাদ দেওয়া হয়েছে।
- **C option কেন ভুল:** Integer operands floating result দেয় না।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `-17 % 5` সাধারণত −2, যাতে quotient-remainder identity বজায় থাকে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Truncate toward zero।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0163

**Master-bank reference:** Question 0025
**Metadata:** Topic: Structured Programming > Unsigned Wraparound | Difficulty: Medium | Type: Calculation
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. 8-bit unsigned value-এ `250+10` করলে result কত?

A) 4
B) 260
C) 5
D) 255

**সঠিক উত্তর: A) 4**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Calculation

```text
250 + 10 = 260
260 mod 256 = 4
```

#### Final Answer

```text
Result = 4
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Unsigned arithmetic modulo 2^8 = 256 অনুযায়ী wrap করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** 260 representable নয়।
- **C option কেন ভুল:** Modulo ভুল।
- **D option কেন ভুল:** Unsigned saturation করে না।
- **Related Concept:** Unsigned overflow defined; signed overflow undefined।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** N-bit unsigned → modulo 2^N।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0164

**Master-bank reference:** Question 0026
**Metadata:** Topic: Structured Programming > Floating Types | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. নিচের কোন statement সাধারণভাবে সঠিক?

A) `float` সবসময় বেশি precision
B) `double` সাধারণত `float`-এর চেয়ে বেশি precision
C) `float` শুধু integer রাখে
D) `double` arithmetic হয় না

**সঠিক উত্তর: B) `double` সাধারণত `float`-এর চেয়ে বেশি precision**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `double`-এর minimum precision requirement বেশি এবং common implementation-এ অধিক significant digit রাখে।
- **A option কেন ভুল:** উল্টো।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `float` floating-point value রাখে।
- **D option কেন ভুল:** `double` arithmetic বৈধ।
- **Related Concept:** `1.0` double literal; `1.0f` float।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Suffix `f` না থাকলে floating literal সাধারণত double।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0165

**Master-bank reference:** Question 0027
**Metadata:** Topic: Structured Programming > Signed-Unsigned Comparison | Difficulty: Hard | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `int x=-1; unsigned int y=1U;` হলে `x<y` অনেক common case-এ false কেন?

A) Negative zero হয়
B) `y` signed হয়
C) `x` unsigned-এ convert হয়ে বড় value হয়
D) Comparison বাদ যায়

**সঠিক উত্তর: C) `x` unsigned-এ convert হয়ে বড় value হয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Usual arithmetic conversion-এ −1 unsigned representation-এ `UINT_MAX`-সদৃশ বড় value হয়।
- **A option কেন ভুল:** Negative zero হয় না।
- **B option কেন ভুল:** সাধারণ সমান-rank case-এ signed operand unsigned হয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Comparison evaluate হয়।
- **Related Concept:** Signed ও unsigned mix subtle bug তৈরি করে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Comparison-এর আগে conversion ভাবুন।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0166

**Master-bank reference:** Question 0033
**Metadata:** Topic: Structured Programming > Short-Circuit | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `x!=0 && 10/x>1`-এ `x==0` হলে division execute হয় না কেন?

A) `&&` short-circuit করে
B) Compiler সব division বাদ দেয়
C) Integer division নিষিদ্ধ
D) x স্বয়ংক্রিয়ভাবে 1

**সঠিক উত্তর: A) `&&` short-circuit করে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** বাম operand false হলে AND result false নিশ্চিত; ডান operand evaluate হয় না।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** সব division বাদ যায় না।
- **C option কেন ভুল:** Integer division বৈধ।
- **D option কেন ভুল:** x পরিবর্তিত হয় না।
- **Related Concept:** `||`-এ বাম true হলে ডান evaluate হয় না।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Safety check বাম পাশে।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0167

**Master-bank reference:** Question 0034
**Metadata:** Topic: Structured Programming > Bitwise AND | Difficulty: Medium | Type: Calculation
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `12 & 10`-এর decimal value কত?

A) 6
B) 8
C) 14
D) 2

**সঠিক উত্তর: B) 8**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Binary Calculation

```text
12 = 1100
10 = 1010
AND  1000
```

#### Final Answer

```text
1000₂ = 8
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** দুই corresponding bit 1 হলে AND result 1।
- **A option কেন ভুল:** এটি XOR result।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এটি OR result।
- **D option কেন ভুল:** ভুল bit operation।
- **Related Concept:** AND mask দিয়ে bit test/clear করা যায়।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** AND-এ দুটোই 1।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0168

**Master-bank reference:** Question 0035
**Metadata:** Topic: Structured Programming > Assignment Associativity | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Assignment operator-এর associativity কী?

A) Left-to-right
B) নেই
C) Right-to-left
D) Operand type-নির্ভর

**সঠিক উত্তর: C) Right-to-left**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `a=b=5` group হয় `a=(b=5)`।
- **A option কেন ভুল:** `(a=b)=5` valid grouping নয়।
- **B option কেন ভুল:** Defined associativity আছে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Type অনুযায়ী বদলায় না।
- **Related Concept:** Precedence ও associativity ভিন্ন ধারণা।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Assignment chain ডান থেকে।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0169

**Master-bank reference:** Question 0036
**Metadata:** Topic: Structured Programming > sizeof | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Non-VLA operand-এর ক্ষেত্রে `sizeof(x++)` সাধারণত x increment করে না কেন?

A) `++` নিষিদ্ধ
B) `sizeof` zero দেয়
C) x constant হয়
D) Operand value evaluate হয় না

**সঠিক উত্তর: D) Operand value evaluate হয় না**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Compile-time type/size থেকে result নির্ণীত হয়; expression side effect execute হয় না।
- **A option কেন ভুল:** Increment বৈধ।
- **B option কেন ভুল:** Object size দেয়।
- **C option কেন ভুল:** x const হয় না।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** VLA ক্ষেত্রে evaluation rule ব্যতিক্রম হতে পারে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** সাধারণ sizeof expression চালায় না।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0170

**Master-bank reference:** Question 0037
**Metadata:** Topic: Structured Programming > Unsequenced Modification | Difficulty: Hard | Type: Code
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `int x=2; printf("%d",x+++ ++x);`-জাতীয় একই full expression-এ multiple unsequenced modification-এর behavior কী?

A) Undefined Behavior
B) সবসময় 6
C) সবসময় 5
D) Compilation বাধ্যতামূলকভাবে ব্যর্থ

**সঠিক উত্তর: A) Undefined Behavior**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একই scalar object-এর side effect-গুলোর relative order নির্ধারিত না থাকলে behavior undefined।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Fixed output guarantee নেই।
- **C option কেন ভুল:** Fixed output guarantee নেই।
- **D option কেন ভুল:** Compiler reject করতে বাধ্য নয়।
- **Related Concept:** Warning outcome নির্ধারণ করে না।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Multiple side effect আলাদা statement-এ করুন।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0171

**Master-bank reference:** Question 0038
**Metadata:** Topic: Structured Programming > Conditional Operator | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `?:` conditional operator-এর associativity কী?

A) Left-to-right
B) Right-to-left
C) নেই
D) শুধু integer-এ

**সঠিক উত্তর: B) Right-to-left**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Nested conditional expression right-to-left group হয়।
- **A option কেন ভুল:** সঠিক নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Defined associativity আছে।
- **D option কেন ভুল:** Compatible বিভিন্ন type-এ ব্যবহার হয়।
- **Related Concept:** `a?b:c?d:e` → `a?b:(c?d:e)`।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Conditional ও assignment right-associative।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0172

**Master-bank reference:** Question 0044
**Metadata:** Topic: Structured Programming > do-while | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `do-while` loop-এর প্রধান বৈশিষ্ট্য কী?

A) Condition পরীক্ষা হয় না
B) Infinite হওয়া বাধ্যতামূলক
C) Body শুধু false হলে চলে
D) Body অন্তত একবার চলে

**সঠিক উত্তর: D) Body অন্তত একবার চলে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Condition body-এর পরে পরীক্ষা হয়।
- **A option কেন ভুল:** প্রতি iteration শেষে condition পরীক্ষা হয়।
- **B option কেন ভুল:** False হলে শেষ হয়।
- **C option কেন ভুল:** প্রথমবার condition-এর আগেই body চলে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `while` entry-controlled; `do-while` exit-controlled।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Do first, check later।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0173

**Master-bank reference:** Question 0045
**Metadata:** Topic: Structured Programming > Dangling else | Difficulty: Hard | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Braces না থাকলে `else` সাধারণত কোন `if`-এর সঙ্গে bind করে?

A) Nearest unmatched `if`
B) প্রথম `if`
C) সব `if`
D) কোনোটির নয়

**সঠিক উত্তর: A) Nearest unmatched `if`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** C grammar অনুযায়ী `else` closest unmatched `if`-এর অংশ হয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** সবসময় outer/first নয়।
- **C option কেন ভুল:** একটি else একটি if-এর সঙ্গে bind করে।
- **D option কেন ভুল:** Defined matching rule আছে।
- **Related Concept:** Braces ambiguity দূর করে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Else nearest unmatched if।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0174

**Master-bank reference:** Question 0047
**Metadata:** Topic: Structured Programming > goto | Difficulty: Medium | Type: Scenario
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `goto` সম্পর্কে কোন statement সঠিক?

A) সব function-এর মধ্যে jump করে
B) Variable copy করে
C) একই function-এর labeled statement-এ control দেয়
D) Compile বন্ধ করে

**সঠিক উত্তর: C) একই function-এর labeled statement-এ control দেয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** C `goto` target label একই function body-এর মধ্যে থাকতে হয়।
- **A option কেন ভুল:** Function boundary পার হতে পারে না।
- **B option কেন ভুল:** Assignment নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Valid goto compile হতে পারে।
- **Related Concept:** Excessive goto readability কমায়।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Goto target same function।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0175

**Master-bank reference:** Question 0048
**Metadata:** Topic: Structured Programming > switch Fall-through | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `case` শেষে `break` না থাকলে সাধারণত কী হয়?

A) Program terminate
B) পরবর্তী case বাদ
C) main-এ return
D) পরবর্তী case-এ fall-through

**সঠিক উত্তর: D) পরবর্তী case-এ fall-through**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Control break বা switch end না পাওয়া পর্যন্ত পরবর্তী statement execute করতে পারে।
- **A option কেন ভুল:** Terminate হয় না।
- **B option কেন ভুল:** Compiler বাদ দেয় না।
- **C option কেন ভুল:** Function return নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Intentional fall-through কিছু design-এ ব্যবহৃত।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Break না থাকলে নিচে নামে।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0176

**Master-bank reference:** Question 0049
**Metadata:** Topic: Structured Programming > Nested Loop Count | Difficulty: Hard | Type: Calculation
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. নিচের nested loop-এ inner statement মোট কতবার execute হয়?

```c
for(int i=1;i<=4;i++)
  for(int j=1;j<=i;j++)
    statement;
```

A) 10
B) 16
C) 8
D) 6

**সঠিক উত্তর: A) 10**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Iteration Count

```text
i=1 → 1
i=2 → 2
i=3 → 3
i=4 → 4
```

#### Calculation

```text
Total = 1+2+3+4
      = 10
```

#### Final Answer

```text
Statement executes 10 times
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতি i-তে inner count i; মোট 1+2+3+4=10।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** প্রতি row 4 ধরে 4×4।
- **C option কেন ভুল:** ভুল average।
- **D option কেন ভুল:** শেষ iteration বাদ।
- **Related Concept:** Triangular sum n(n+1)/2; complexity Θ(n²)।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** 1 থেকে n sum formula মনে রাখুন।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0177

**Master-bank reference:** Question 0055
**Metadata:** Topic: Structured Programming > Partial Initialization | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `int a[5]={10,20};`-এর পরে `a[3]` কত?

A) Garbage
B) 0
C) 20
D) 10

**সঠিক উত্তর: B) 0**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Explicit initializer কম হলে বাকি element zero-initialize হয়।
- **A option কেন ভুল:** Partial initialization-এ garbage নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** 20 শুধু a[1]।
- **D option কেন ভুল:** 10 শুধু a[0]।
- **Related Concept:** `int a[5]={0};` সব zero।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** এক initializer থাকলেও rest zero।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0178

**Master-bank reference:** Question 0056
**Metadata:** Topic: Structured Programming > Array Bounds | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `int a[5];`-এর `a[5]` access করলে কী হতে পারে?

A) Undefined Behavior
B) সবসময় zero
C) Compilation বাধ্যতামূলকভাবে ব্যর্থ
D) a[0]-তে wrap

**সঠিক উত্তর: A) Undefined Behavior**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Valid index 0–4; boundary-এর বাইরে access standard-defined নয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Memory zero guarantee নেই।
- **C option কেন ভুল:** Compiler detect করতে বাধ্য নয়।
- **D option কেন ভুল:** C index wrap করে না।
- **Related Concept:** Out-of-bounds memory corruption ঘটাতে পারে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Size ও last index আলাদা।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0179

**Master-bank reference:** Question 0057
**Metadata:** Topic: Structured Programming > Null Termination | Difficulty: Hard | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `char text[3]={'I','C','T'};` সম্পর্কে কোনটি সঠিক?

A) নিশ্চিত valid string
B) Compiler extra byte যোগ করে
C) `strlen` সবসময় 3
D) Null terminator নেই

**সঠিক উত্তর: D) Null terminator নেই**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** তিন cell visible character-এ পূর্ণ; `\0` রাখার cell নেই।
- **A option কেন ভুল:** Null byte ছাড়া C string নয়।
- **B option কেন ভুল:** Declared boundary বাড়ে না।
- **C option কেন ভুল:** `strlen` boundary ছাড়িয়ে পড়তে পারে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `"ICT"`-এর জন্য 4 byte দরকার।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Visible chars + 1।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0180

**Master-bank reference:** Question 0058
**Metadata:** Topic: Structured Programming > strlen ও sizeof | Difficulty: Medium | Type: Code
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. নিচের output কী?

```c
char s[]="Hello";
printf("%zu %zu",strlen(s),sizeof(s));
```

A) `6 5`
B) `5 5`
C) `5 6`
D) `6 6`

**সঠিক উত্তর: C) `5 6`**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Memory

```text
H e l l o \0
strlen = 5
sizeof  = 6
```

#### Final Answer

```text
Output = 5 6
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `strlen` 5; array storage null byte-সহ 6।
- **A option কেন ভুল:** দুটি value উল্টো।
- **B option কেন ভুল:** Null storage বাদ।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** strlen null count করে না।
- **Related Concept:** Length ও storage size ভিন্ন।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Hello length 5, array 6।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0181

**Master-bank reference:** Question 0059
**Metadata:** Topic: Structured Programming > strcmp | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `strcmp(s1,s2)` zero return করলে কী বোঝায়?

A) Content সমান
B) s1 ছোট
C) s2 ছোট
D) Pointer address একই

**সঠিক উত্তর: A) Content সমান**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `strcmp` lexicographical content compare করে; equal হলে zero।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** s1 ছোট হলে negative।
- **C option কেন ভুল:** s1 বড় হলে positive।
- **D option কেন ভুল:** Address equality পরীক্ষা করে না।
- **Related Concept:** Nonzero exact magnitude standard নির্দিষ্ট করে না।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** strcmp == 0 → equal।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0182

**Master-bank reference:** Question 0060
**Metadata:** Topic: Structured Programming > Overlapping Memory | Difficulty: Hard | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Overlapping memory region copy করতে কোন function উপযুক্ত?

A) `strcpy`
B) `memmove`
C) `strlen`
D) `strcmp`

**সঠিক উত্তর: B) `memmove`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `memmove` overlap handle করার guarantee দেয়।
- **A option কেন ভুল:** Overlapping string copy unsafe।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Length function।
- **D option কেন ভুল:** Compare function।
- **Related Concept:** `memcpy` overlap guarantee দেয় না।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Overlap → memmove।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0183

**Master-bank reference:** Question 0066
**Metadata:** Topic: Structured Programming > Char Array Initialization | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `char name[4]="ICT";` সম্পর্কে কোনটি সঠিক?

A) Invalid, 5 দরকার
B) Null নেই
C) শুধু I,C store
D) Valid এবং null-সহ store

**সঠিক উত্তর: D) Valid এবং null-সহ store**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 3 visible character + 1 null = 4 cell।
- **A option কেন ভুল:** 4 যথেষ্ট।
- **B option কেন ভুল:** চতুর্থ cell null।
- **C option কেন ভুল:** T-ও store হয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `char name[3]="ICT"` null রাখতে পারে না।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** ICT storage 4।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0184

**Master-bank reference:** Question 0067
**Metadata:** Topic: Structured Programming > Reverse Traversal | Difficulty: Medium | Type: Code
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `char s[]="ABCDE"; for(int i=4;i>=0;i--) putchar(s[i]);` output কী?

A) ABCDE
B) EDCBA
C) BCDEA
D) EDABC

**সঠিক উত্তর: B) EDCBA**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Trace

```text
s[4]=E
s[3]=D
s[2]=C
s[1]=B
s[0]=A
```

#### Final Answer

```text
Output = EDCBA
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Index 4 থেকে 0; তাই character reverse order-এ print।
- **A option কেন ভুল:** Forward order।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Circular shift নয়।
- **D option কেন ভুল:** Index sequence ভুল।
- **Related Concept:** Last index = length−1।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Reverse loop-এ signed index ব্যবহার সতর্কভাবে।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0185

**Master-bank reference:** Question 0068
**Metadata:** Topic: Structured Programming > Array Element Count | Difficulty: Easy | Type: Calculation
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Actual array `int a[12];`-এর element count expression কোনটি?

A) `sizeof(a)/sizeof(a[0])`
B) `sizeof(a)`
C) `sizeof(a[0])/sizeof(a)`
D) `strlen(a)`

**সঠিক উত্তর: A) `sizeof(a)/sizeof(a[0])`**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Formula

```text
Element count = sizeof(a) / sizeof(a[0])
```

#### Example

```text
যদি int = 4 byte:
sizeof(a)=12×4=48
sizeof(a[0])=4
48/4=12
```

#### Final Answer

```text
Element count = 12
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Total array bytes-কে one-element bytes দিয়ে ভাগ করলে element count পাওয়া যায়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Byte count দেয়।
- **C option কেন ভুল:** Division উল্টো।
- **D option কেন ভুল:** Integer array string নয়।
- **Related Concept:** Function parameter-এ array decay করলে formula কাজ করে না।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Total bytes ÷ one element।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0186

**Master-bank reference:** Question 0069
**Metadata:** Topic: Structured Programming > Pointer Declaration | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `int` object-এর address ধারণকারী pointer declaration কোনটি?

A) `int p;`
B) `pointer int p;`
C) `int &p;`
D) `int *p;`

**সঠিক উত্তর: D) `int *p;`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `*` declarator p-কে pointer-to-int করে।
- **A option কেন ভুল:** Ordinary int।
- **B option কেন ভুল:** pointer keyword নেই।
- **C option কেন ভুল:** Standard C reference syntax নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `int *p,q;`-তে শুধু p pointer।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** প্রতিটি pointer name-এর সঙ্গে * দেখুন।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0187

**Master-bank reference:** Question 0070
**Metadata:** Topic: Structured Programming > Dereference | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. p যদি x-এর address রাখে, pointer দিয়ে x-এর value access কোন expression?

A) `&p`
B) `&x`
C) `*p`
D) `p*`

**সঠিক উত্তর: C) `*p`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `*` pointer-এর target object dereference করে।
- **A option কেন ভুল:** p-এর নিজের address।
- **B option কেন ভুল:** x-এর address।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Invalid syntax।
- **Related Concept:** `p=&x;` তারপর `*p` x-এর value।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** & address, * value।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0188

**Master-bank reference:** Question 0071
**Metadata:** Topic: Structured Programming > Pointer Arithmetic | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `int *p`-এর `p+1` কী নির্দেশ করে?

A) পরবর্তী byte
B) পরবর্তী int element
C) Pointed value+1
D) NULL

**সঠিক উত্তর: B) পরবর্তী int element**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Pointer arithmetic type-scaled; next `int` element।
- **A option কেন ভুল:** `char*` হলে byte step।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Pointer value/address বদলায়, target integer নয়।
- **D option কেন ভুল:** Addition null করে না।
- **Related Concept:** Byte increment = sizeof(*p)।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Pointer step = one element।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0189

**Master-bank reference:** Question 0077
**Metadata:** Topic: Structured Programming > Wild Pointer | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Initialize না করা pointer-কে কী বলা হয়?

A) Smart Pointer
B) Constant Pointer
C) Wild Pointer
D) Far Pointer

**সঠিক উত্তর: C) Wild Pointer**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Uninitialized pointer indeterminate address রাখে; commonly Wild Pointer।
- **A option কেন ভুল:** C++ resource abstraction।
- **B option কেন ভুল:** Address-fixed pointer।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Historical segmented memory term।
- **Related Concept:** Dereference UB।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Declare করে NULL বা valid address দিন।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0190

**Master-bank reference:** Question 0078
**Metadata:** Topic: Structured Programming > Pointer to Pointer | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `int` pointer-এর address রাখার declaration কোনটি?

A) `int *p;`
B) `int p**;`
C) `**int p;`
D) `int **p;`

**সঠিক উত্তর: D) `int **p;`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** দুটি star pointer-to-pointer-to-int প্রকাশ করে।
- **A option কেন ভুল:** শুধু pointer-to-int।
- **B option কেন ভুল:** Syntax ভুল।
- **C option কেন ভুল:** Syntax ভুল।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Caller-এর pointer বদলাতে `T **` লাগে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Pointer-এর pointer = **।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0191

**Master-bank reference:** Question 0079
**Metadata:** Topic: Structured Programming > Pointer to const | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `const int *p;`-এর অর্থ কী?

A) p address বদলাতে পারবে না
B) p দিয়ে pointed int modify করা যাবে না
C) p সবসময় NULL
D) Object compile-time constant

**সঠিক উত্তর: B) p দিয়ে pointed int modify করা যাবে না**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Const pointed type-এর সঙ্গে; p অন্য address নিতে পারে, কিন্তু `*p` দিয়ে write নয়।
- **A option কেন ভুল:** এটি `int *const p`।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Null constraint নেই।
- **D option কেন ভুল:** অন্য non-const path-এ object বদলাতে পারে।
- **Related Concept:** Pointer to const int।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** const star-এর আগে → data protected।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0192

**Master-bank reference:** Question 0080
**Metadata:** Topic: Structured Programming > Const Pointer | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `int *const p=&x;`-এর অর্থ কী?

A) p অন্য address নিতে পারবে না
B) *p read করা যাবে না
C) x সব path-এ immutable
D) Pointer-to-pointer

**সঠিক উত্তর: A) p অন্য address নিতে পারবে না**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Const pointer value fixed; pointed object modifiable হতে পারে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Read/write সম্ভব।
- **C option কেন ভুল:** x const declared নয়।
- **D option কেন ভুল:** Double star নেই।
- **Related Concept:** Const pointer to int।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** const star-এর পরে → address fixed।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0193

**Master-bank reference:** Question 0081
**Metadata:** Topic: Structured Programming > Pointer Subtraction | Difficulty: Hard | Type: Calculation
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. একই array-এ `p=&a[8]`, `q=&a[3]`; `p-q` কত?

A) 11
B) 20
C) 4
D) 5

**সঠিক উত্তর: D) 5**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Calculation

```text
p - q = 8 - 3
      = 5 elements
```

#### Final Answer

```text
Pointer difference = 5
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Pointer difference element distance দেয়, byte distance নয়।
- **A option কেন ভুল:** Index যোগ।
- **B option কেন ভুল:** 4-byte int ধরে byte difference।
- **C option কেন ভুল:** Off-by-one।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** শুধু same array-এর মধ্যে defined।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Higher index−lower index।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0194

**Master-bank reference:** Question 0082
**Metadata:** Topic: Structured Programming > void Pointer | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `void *` সম্পর্কে কোনটি সঠিক?

A) শুধু function address
B) Direct dereference করে যেকোনো type
C) Generic object pointer
D) Conversion অসম্ভব

**সঠিক উত্তর: C) Generic object pointer**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `void*` বিভিন্ন object type-এর address represent করতে পারে।
- **A option কেন ভুল:** Function pointer rule আলাদা।
- **B option কেন ভুল:** Dereference-এর আগে typed pointer দরকার।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Object pointer conversion supported।
- **Related Concept:** `malloc` void pointer return করে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Generic address, generic value নয়।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0195

**Master-bank reference:** Question 0088
**Metadata:** Topic: Structured Programming > extern | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `extern int count;` সাধারণত কী বোঝায়?

A) নতুন local storage
B) Definition অন্যত্র থাকতে পারে
C) Function pointer
D) Immutable constant

**সঠিক উত্তর: B) Definition অন্যত্র থাকতে পারে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Existing external object-এর declaration; সাধারণত storage definition নয়।
- **A option কেন ভুল:** Automatic storage তৈরি করে না।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Pointer syntax নয়।
- **D option কেন ভুল:** Const নয়।
- **Related Concept:** Initializer-সহ extern declaration definition হতে পারে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** extern = elsewhere।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0196

**Master-bank reference:** Question 0089
**Metadata:** Topic: Structured Programming > Automatic Storage | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. সাধারণ non-static local variable-এর storage duration কী?

A) Thread
B) Static
C) Allocated
D) Automatic

**সঠিক উত্তর: D) Automatic**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Block execution-এর সময় ordinary local object তৈরি ও destroy হয়।
- **A option কেন ভুল:** Thread storage নয়।
- **B option কেন ভুল:** static qualifier থাকলে।
- **C option কেন ভুল:** Dynamic allocation-এর object।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `auto` default local storage class।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Ordinary local = automatic।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0197

**Master-bank reference:** Question 0090
**Metadata:** Topic: Structured Programming > register | Difficulty: Medium | Type: Code
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `register int x=10; int *p=&x;`-এর সমস্যা কী?

A) register initialize করা যায় না
B) শুধু global-এ
C) register object-এর address নেওয়া যায় না
D) Pointer declaration invalid

**সঠিক উত্তর: C) register object-এর address নেওয়া যায় না**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Standard C constraint অনুযায়ী register-declared object-এর address `&` দিয়ে নেওয়া যায় না।
- **A option কেন ভুল:** Initialize করা যায়।
- **B option কেন ভুল:** Block scope/parameter-এ ব্যবহার।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Pointer declaration valid।
- **Related Concept:** Compiler hardware register-এ রাখবে—guarantee নেই।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** register লিখলে & নয়।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0198

**Master-bank reference:** Question 0091
**Metadata:** Topic: Structured Programming > Internal Linkage | Difficulty: Hard | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. File scope-এ `static int count;` কী linkage পায়?

A) Internal
B) External
C) কোনো storage নয়
D) Dynamic

**সঠিক উত্তর: A) Internal**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Name একই translation unit-এর মধ্যে সীমিত থাকে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** External visibility suppressed।
- **C option কেন ভুল:** Static storage duration আছে।
- **D option কেন ভুল:** Standard linkage category নয়।
- **Related Concept:** File static = file-private।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** static at file scope → internal linkage।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0199

**Master-bank reference:** Question 0092
**Metadata:** Topic: Structured Programming > extern Declaration | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Initializer ছাড়া `extern int total;` সাধারণত কোনটি?

A) Local definition
B) Declaration, সাধারণত definition নয়
C) Macro
D) Function definition

**সঠিক উত্তর: B) Declaration, সাধারণত definition নয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Compiler-কে external object-এর name/type জানায়।
- **A option কেন ভুল:** Automatic local নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Macro #define দিয়ে।
- **D option কেন ভুল:** Function syntax নয়।
- **Related Concept:** `int total;` file scope-এ tentative definition হতে পারে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Extern says object exists elsewhere।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0200

**Master-bank reference:** Question 0093
**Metadata:** Topic: Structured Programming > Arguments | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Function call-এর supplied value/expression-কে কী বলা হয়?

A) Local Label
B) Storage Class
C) Actual Argument
D) Formal Parameter

**সঠিক উত্তর: C) Actual Argument**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Call site-এর expression actual argument।
- **A option কেন ভুল:** goto target।
- **B option কেন ভুল:** Lifetime/linkage category।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Definition/prototype-এর parameter।
- **Related Concept:** `add(x,5)`-এ x ও 5 actual।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Call-এ actual, body-তে formal।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0201

**Master-bank reference:** Question 0099
**Metadata:** Topic: Structured Programming > Shadowing | Difficulty: Medium | Type: Code
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Outer `int x=10;` এবং inner block-এ `int x=20;` হলে inner print ও পরে outer print কী?

A) 20 10
B) 10 10
C) 20 20
D) Compilation Error

**সঠিক উত্তর: A) 20 10**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Trace

```text
Outer x = 10
Inner x = 20 → print 20
Inner block ends
Outer x visible → print 10
```

#### Final Answer

```text
Output = 20 10
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Inner declaration outer name shadow করে; block শেষে outer x আবার visible।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Inner declaration উপেক্ষা।
- **C option কেন ভুল:** Inner x outer object বদলায় না।
- **D option কেন ভুল:** Nested shadowing valid।
- **Related Concept:** Scope visibility নির্ধারণ করে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Hide করে, overwrite নয়।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0202

**Master-bank reference:** Question 0100
**Metadata:** Topic: Structured Programming > Reference Effect | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Function দিয়ে caller-এর variable modify করার প্রচলিত উপায় কী?

A) Name string পাঠানো
B) Address pointer argument পাঠানো
C) Keyword বানানো
D) শুধু global

**সঠিক উত্তর: B) Address pointer argument পাঠানো**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Function address value-এর copy পেয়ে dereference করে original object modify করতে পারে।
- **A option কেন ভুল:** Name string address নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Variable keyword হতে পারে না।
- **D option কেন ভুল:** Global বাধ্যতামূলক নয়।
- **Related Concept:** Mechanism call by value, effect reference-like।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Original বদলাতে address পাঠান।


## Batch 02 Quality Summary

```text
Questions          = 50
Theory/Scenario    = 35
Calculation/Code   = 15
Coverage           = Arrays, Strings, Pointers, Functions, Storage, Recursion
Math format        = Plain-text aligned
```

---

## MCQ 0203

**Master-bank reference:** Question 0101
**Metadata:** Topic: Structured Programming > Standard I/O Header | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `printf()` ও `scanf()` declaration কোন header-এ?

A) `<stdio.h>`
B) `<stdlib.h>`
C) `<string.h>`
D) `<ctype.h>`

**সঠিক উত্তর: A) `<stdio.h>`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Standard input/output function-গুলো `<stdio.h>`-এ declared।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Allocation/utility header।
- **C option কেন ভুল:** String function header।
- **D option কেন ভুল:** Character classification header।
- **Related Concept:** `fopen`, `fclose`, `fread`, `fwrite`-ও stdio.h।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Standard I/O → stdio.h।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0204

**Master-bank reference:** Question 0102
**Metadata:** Topic: Structured Programming > printf Return | Difficulty: Medium | Type: Code
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `int n=printf("ICT"); printf(" %d",n);` output কী?

A) ICT 0
B) ICT 3
C) 3 ICT
D) ICT 4

**সঠিক উত্তর: B) ICT 3**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Trace

```text
printf("ICT") prints 3 characters
n = 3
Second printf prints space and 3
```

#### Final Answer

```text
Output = ICT 3
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রথম printf তিন character print করে এবং 3 return করে।
- **A option কেন ভুল:** Successful printf zero নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Order উল্টো।
- **D option কেন ভুল:** Null terminator print count নয়।
- **Related Concept:** `printf` printed character count return করে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Visible output character count করুন।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0205

**Master-bank reference:** Question 0103
**Metadata:** Topic: Structured Programming > scanf Address | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `int x`-এ input নেওয়ার সঠিক statement কোনটি?

A) `scanf("%d",x);`
B) `scanf(x,"%d");`
C) `scanf("%d",&x);`
D) `scanf("&d",x);`

**সঠিক উত্তর: C) `scanf("%d",&x);`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `scanf`-কে storage address দিতে হয়।
- **A option কেন ভুল:** Value পাঠানো হয়েছে।
- **B option কেন ভুল:** Argument order ভুল।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Format invalid।
- **Related Concept:** Array name `%s`-এ pointer decay করে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Scalar input → &variable।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0206

**Master-bank reference:** Question 0110
**Metadata:** Topic: Structured Programming > Output Count | Difficulty: Hard | Type: Calculation
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `printf("[%4d]",25);` মোট কত character output করে?

A) 4
B) 6
C) 5
D) 7

**সঠিক উত্তর: B) 6**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Count

```text
%4d → "  25" = 4 chars
[ = 1
] = 1
```

#### Final Answer

```text
Total = 1 + 4 + 1 = 6 characters
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Field 4 character; দুই bracket যোগে মোট 6।
- **A option কেন ভুল:** শুধু formatted field।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এক bracket বাদ।
- **D option কেন ভুল:** Extra character।
- **Related Concept:** Literal character-ও count হয়।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Field width + surrounding literal।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0207

**Master-bank reference:** Question 0111
**Metadata:** Topic: Structured Programming > fopen Failure | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `fopen()` ব্যর্থ হলে কী return করে?

A) EOF
B) Character zero
C) NULL
D) Empty FILE object

**সঠিক উত্তর: C) NULL**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Success-এ stream pointer; failure-এ null pointer।
- **A option কেন ভুল:** Character I/O sentinel।
- **B option কেন ভুল:** Pointer failure signal নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Usable object পাওয়া যায় না।
- **Related Concept:** `if(fp==NULL)` check করুন।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Open failed → NULL।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0208

**Master-bank reference:** Question 0112
**Metadata:** Topic: Structured Programming > Write Mode | Difficulty: Medium | Type: Code
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `fopen("data.txt","w")` existing file-এর ওপর কী effect ফেলতে পারে?

A) Read-only
B) Content অপরিবর্তিত
C) শুধু append
D) Existing content truncate

**সঠিক উত্তর: D) Existing content truncate**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `w` mode file create করে বা existing content zero-length করে।
- **A option কেন ভুল:** Write mode।
- **B option কেন ভুল:** Preserve নয়।
- **C option কেন ভুল:** Append-এর জন্য a।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `w+`-ও truncate করে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** w = wipe then write।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0209

**Master-bank reference:** Question 0113
**Metadata:** Topic: Structured Programming > Append Mode | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Existing file-এর শেষে data যোগ করতে mode কোনটি?

A) `a`
B) `r`
C) `w`
D) `rb`

**সঠিক উত্তর: A) `a`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Append mode write position end-এ রাখে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Read only।
- **C option কেন ভুল:** Truncate।
- **D option কেন ভুল:** Binary read।
- **Related Concept:** Read+append → `a+`।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Append → a।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0210

**Master-bank reference:** Question 0114
**Metadata:** Topic: Structured Programming > fwrite Return | Difficulty: Medium | Type: Code
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `fwrite(a,sizeof(int),5,fp)` সব item লিখলে return কত?

A) `sizeof(int)*5`
B) 5
C) 1
D) File bytes

**সঠিক উত্তর: B) 5**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `fwrite` written element count return করে।
- **A option কেন ভুল:** Total byte হতে পারে, return নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এক element হলে।
- **D option কেন ভুল:** File total নয়।
- **Related Concept:** Bytes = return count × element size।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** fread/fwrite return items।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0211

**Master-bank reference:** Question 0121
**Metadata:** Topic: Structured Programming > Struct Member | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Structure object-এর member access operator কোনটি?

A) `.`
B) `->`
C) `::`
D) `#`

**সঠিক উত্তর: A) `.`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Direct object-এর member dot দিয়ে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Pointer member access।
- **C option কেন ভুল:** C++ scope resolution।
- **D option কেন ভুল:** Preprocessor marker।
- **Related Concept:** `ptr->x` = `(*ptr).x`।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Object dot, pointer arrow।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0212

**Master-bank reference:** Question 0122
**Metadata:** Topic: Structured Programming > Struct Pointer | Difficulty: Medium | Type: Code
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `Point p={4,7}; Point *ptr=&p; printf("%d",ptr->x+ptr->y);` output?

A) 3
B) 11
C) 28
D) 47

**সঠিক উত্তর: B) 11**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Trace

```text
ptr->x = 4
ptr->y = 7
4 + 7 = 11
```

#### Final Answer

```text
Output = 11
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 4+7=11।
- **A option কেন ভুল:** Difference।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Multiplication।
- **D option কেন ভুল:** Concatenation নয়।
- **Related Concept:** Arrow dereference+member access।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** ptr->x মানে (*ptr).x।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0213

**Master-bank reference:** Question 0123
**Metadata:** Topic: Structured Programming > Union Storage | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Union member storage সম্পর্কে কোনটি সঠিক?

A) সব আলাদা
B) শুধু heap
C) একই memory region share
D) Size নেই

**সঠিক উত্তর: C) একই memory region share**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** সব member common storage overlay করে।
- **A option কেন ভুল:** Structure-এর বৈশিষ্ট্য।
- **B option কেন ভুল:** Storage duration যেকোনো হতে পারে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Union size থাকে।
- **Related Concept:** Size largest member/alignment।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Union = shared।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0214

**Master-bank reference:** Question 0124
**Metadata:** Topic: Structured Programming > Struct Copy | Difficulty: Medium | Type: Code
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `struct Item a={10}; struct Item b=a; b.value=20;` print a,b কী?

A) 20 20
B) 10 10
C) Compilation Error
D) 10 20

**সঠিক উত্তর: D) 10 20**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Trace

```text
a.value = 10
b = a → b.value = 10
b.value = 20
```

#### Final Answer

```text
a = 10, b = 20
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Structure assignment member-wise value copy; b পরিবর্তনে a অপরিবর্তিত।
- **A option কেন ভুল:** Reference sharing ধরা।
- **B option কেন ভুল:** Assignment বাদ।
- **C option কেন ভুল:** Compatible struct assignment valid।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Pointer member হলে pointer value shallow copy হয়।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Struct assignment copies members।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0215

**Master-bank reference:** Question 0125
**Metadata:** Topic: Structured Programming > typedef | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `typedef` সম্পর্কে কোনটি সঠিক?

A) Existing type-এর alias
B) সবসময় distinct runtime type
C) Memory double
D) শুধু function

**সঠিক উত্তর: A) Existing type-এর alias**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Existing type-এর alternative name তৈরি করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Representation/type identity নতুন নয়।
- **C option কেন ভুল:** Size বদলায় না।
- **D option কেন ভুল:** বহু type-এ ব্যবহার।
- **Related Concept:** `typedef struct Node Node;`।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Name বদলায়, storage নয়।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0216

**Master-bank reference:** Question 0132
**Metadata:** Topic: OOP > Object | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Class থেকে তৈরি নির্দিষ্ট entity কী?

A) Package
B) Interface
C) Compiler
D) Object

**সঠিক উত্তর: D) Object**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Object class-এর instance।
- **A option কেন ভুল:** Grouping।
- **B option কেন ভুল:** Contract।
- **C option কেন ভুল:** Translator।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** এক class থেকে বহু object।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Instance = Object।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0217

**Master-bank reference:** Question 0133
**Metadata:** Topic: OOP > Encapsulation | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Data ও method এক unit-এ রেখে access control কী?

A) Encapsulation
B) Recursion
C) Tokenization
D) Compilation

**সঠিক উত্তর: A) Encapsulation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** State+behavior bundle এবং visibility control।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Self-call।
- **C option কেন ভুল:** Lexical process।
- **D option কেন ভুল:** Translation।
- **Related Concept:** Private field/public method common pattern।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Capsule-এর মতো আবদ্ধ।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0218

**Master-bank reference:** Question 0134
**Metadata:** Topic: OOP > Abstraction | Difficulty: Medium | Type: Scenario
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Driver controls car কিন্তু engine detail জানে না—কোন concept?

A) Inheritance
B) Abstraction
C) Multiple Dispatch
D) Recursion

**সঠিক উত্তর: B) Abstraction**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Essential interface visible, internal complexity hidden।
- **A option কেন ভুল:** Subtype relation নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Method dispatch নয়।
- **D option কেন ভুল:** Self-call নয়।
- **Related Concept:** Interface abstraction প্রকাশ করে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** What visible, how hidden।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0219

**Master-bank reference:** Question 0135
**Metadata:** Topic: OOP > Constructor | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Constructor-এর প্রধান উদ্দেশ্য কী?

A) Compile
B) Class delete
C) Object initialize
D) সব method private

**সঠিক উত্তর: C) Object initialize**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Object creation-এর সময় valid initial state/resource setup।
- **A option কেন ভুল:** Compiler কাজ।
- **B option কেন ভুল:** Destructor cleanup।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Access policy নয়।
- **Related Concept:** Constructor-এর return type সাধারণত থাকে না।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Construction → initialization।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0220

**Master-bank reference:** Question 0136
**Metadata:** Topic: OOP > Destructor | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Destructor-এর প্রধান কাজ কী?

A) Name নির্বাচন
B) Parent create
C) Overload
D) Lifetime শেষে cleanup

**সঠিক উত্তর: D) Lifetime শেষে cleanup**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Owned resource release ও final cleanup।
- **A option কেন ভুল:** Naming নয়।
- **B option কেন ভুল:** Inheritance নয়।
- **C option কেন ভুল:** Overloading নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** RAII language-এ গুরুত্বপূর্ণ।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Destruction → cleanup।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0221

**Master-bank reference:** Question 0143
**Metadata:** Topic: OOP > Overriding | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Derived class parent method-এর নতুন implementation দিলে কী?

A) Encapsulation
B) Aggregation
C) Overriding
D) সবসময় Hiding

**সঠিক উত্তর: C) Overriding**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Inherited method compatible signature-এ redefine করা হয়।
- **A option কেন ভুল:** Access concept।
- **B option কেন ভুল:** Whole-part।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Hiding language-specific ভিন্ন।
- **Related Concept:** Runtime polymorphism হতে পারে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Child replaces behavior।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0222

**Master-bank reference:** Question 0144
**Metadata:** Topic: OOP > Dynamic Binding | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Runtime actual object type দেখে overridden method নির্বাচন কী?

A) Static Allocation
B) Lexical Analysis
C) Early Preprocessing
D) Dynamic Binding

**সঠিক উত্তর: D) Dynamic Binding**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Call target runtime object type-এ resolve হয়।
- **A option কেন ভুল:** Memory concern।
- **B option কেন ভুল:** Token analysis।
- **C option কেন ভুল:** Preprocessor নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Overloading static; overriding dynamic হতে পারে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Runtime decision → dynamic।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0223

**Master-bank reference:** Question 0145
**Metadata:** Topic: OOP > Public | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `public` member সম্পর্কে সাধারণ statement?

A) External code থেকেও access
B) শুধু constructor
C) শুধু derived
D) কেউ access নয়

**সঠিক উত্তর: A) External code থেকেও access**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Visibility rule অনুযায়ী class-এর বাইরে accessible।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Constructor-only নয়।
- **C option কেন ভুল:** Protected-এর কাছাকাছি।
- **D option কেন ভুল:** Public-এর বিপরীত।
- **Related Concept:** সব data public করলে encapsulation দুর্বল।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Public = বাইরে visible।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0224

**Master-bank reference:** Question 0146
**Metadata:** Topic: OOP > Protected | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `protected` member-এর সাধারণ উদ্দেশ্য?

A) শুধু global
B) Class ও derived class access
C) সব থেকে hidden
D) Constant

**সঠিক উত্তর: B) Class ও derived class access**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Class family-এর access support করে।
- **A option কেন ভুল:** Global বিশেষাধিকার নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Derived access করতে পারে।
- **D option কেন ভুল:** Const নয়।
- **Related Concept:** Exact package rule language-dependent।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Protected = family।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0225

**Master-bank reference:** Question 0147
**Metadata:** Topic: OOP > Abstract Class | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Abstract Class-এর বৈশিষ্ট্য কোনটি?

A) Method নেই
B) সবসময় final
C) সাধারণত direct instantiate নয়
D) শুধু primitive data

**সঠিক উত্তর: C) সাধারণত direct instantiate নয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Incomplete base abstraction; subclass-এর জন্য।
- **A option কেন ভুল:** Concrete method থাকতে পারে।
- **B option কেন ভুল:** Final inheritance বন্ধ করে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Fields/methods নানা type।
- **Related Concept:** Abstract ও concrete method একসঙ্গে থাকতে পারে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Incomplete blueprint।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0226

**Master-bank reference:** Question 0154
**Metadata:** Topic: OOP > Overriding | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Overriding কখন ঘটে?

A) এক class-এ parameter ভিন্ন
B) Local shadowing
C) Unrelated same name
D) Derived class inherited method redefines

**সঠিক উত্তর: D) Derived class inherited method redefines**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Parent-child hierarchy-তে compatible method implementation বদলায়।
- **A option কেন ভুল:** Overloading।
- **B option কেন ভুল:** Variable shadowing।
- **C option কেন ভুল:** Override নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Runtime polymorphism possible।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Child নতুন behavior।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0227

**Master-bank reference:** Question 0155
**Metadata:** Topic: OOP > Static Binding | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Compile-time method resolution কী?

A) Static Binding
B) Dynamic Binding
C) Lazy Loading
D) Message Queue

**সঠিক উত্তর: A) Static Binding**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Call target compilation-এর সময় নির্ধারিত।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Runtime।
- **C option কেন ভুল:** Resource loading।
- **D option কেন ভুল:** Communication mechanism।
- **Related Concept:** Overloading সাধারণত static।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Static = আগে।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0228

**Master-bank reference:** Question 0156
**Metadata:** Topic: OOP > Dynamic Binding | Difficulty: Medium | Type: Scenario
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Base reference derived object ধরে এবং runtime derived override চলে—কোন mechanism?

A) Overloading
B) Dynamic Binding
C) Static Allocation
D) Data Hiding

**সঠিক উত্তর: B) Dynamic Binding**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Actual object type runtime dispatch নির্ধারণ করে।
- **A option কেন ভুল:** Compile-time matching।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Memory allocation নয়।
- **D option কেন ভুল:** Access control নয়।
- **Related Concept:** Virtual dispatch।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Runtime object decides।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0229

**Master-bank reference:** Question 0157
**Metadata:** Topic: OOP > Abstract Class | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Abstract Class সম্পর্কে কোনটি সঠিক?

A) Implemented method নেই
B) Multiple inheritance নিষিদ্ধ
C) সাধারণত direct instantiate নয়
D) Field নেই

**সঠিক উত্তর: C) সাধারণত direct instantiate নয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** অসম্পূর্ণ base abstraction হওয়ায় direct object তৈরি করা যায় না।
- **A option কেন ভুল:** Concrete method থাকতে পারে।
- **B option কেন ভুল:** Language-specific নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** State থাকতে পারে।
- **Related Concept:** Subclass common implementation পায়।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Abstract = incomplete base।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0230

**Master-bank reference:** Question 0158
**Metadata:** Topic: OOP > Interface | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Interface-এর design সুবিধা কোনটি?

A) Object size equal
B) Implementation পরিবর্তন নিষিদ্ধ
C) সব field public
D) Contract দিয়ে loose coupling

**সঠিক উত্তর: D) Contract দিয়ে loose coupling**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Client concrete implementation-এর বদলে abstraction-এর ওপর নির্ভর করে।
- **A option কেন ভুল:** Memory size নয়।
- **B option কেন ভুল:** Implementation change সহজ করে।
- **C option কেন ভুল:** Public data নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** DIP সমর্থন করে।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Depend on contract।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0231

**Master-bank reference:** Question 0165
**Metadata:** Topic: OOP > Aggregation | Difficulty: Hard | Type: Scenario
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. University destroy হলেও Professor independently থাকে—relation?

A) Inheritance
B) Composition
C) Aggregation
D) Overriding

**সঠিক উত্তর: C) Aggregation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Weak whole-part এবং independent lifetime।
- **A option কেন ভুল:** Subtype নয়।
- **B option কেন ভুল:** Strong lifetime ownership।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Method relation নয়।
- **Related Concept:** Weak has-a।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Whole gone, part survives।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0232

**Master-bank reference:** Question 0166
**Metadata:** Topic: C Safety > Undefined Behavior | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. কোনটি Undefined Behavior?

A) Valid array read
B) Null dereference
C) Matching printf int
D) return 0

**সঠিক উত্তর: B) Null dereference**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Null pointer valid object target করে না।
- **A option কেন ভুল:** Defined access।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Type match valid।
- **D option কেন ভুল:** Successful termination।
- **Related Concept:** Null check করুন।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** NULL দেখা যায়, dereference নয়।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0233

**Master-bank reference:** Question 0167
**Metadata:** Topic: C Portability > Implementation-Defined | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Plain `char` signed না unsigned—কী behavior?

A) Implementation-defined
B) Undefined
C) Syntax Error
D) Linker-defined

**সঠিক উত্তর: A) Implementation-defined**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Implementation choice নেয় ও document করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Invalid operation নয়।
- **C option কেন ভুল:** Syntax valid।
- **D option কেন ভুল:** Linker property নয়।
- **Related Concept:** Explicit `signed char`/`unsigned char` ব্যবহার।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Plain char signedness assume নয়।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0234

**Master-bank reference:** Question 0168
**Metadata:** Topic: C Safety > Signed Overflow | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Signed integer range-এর বাইরে result গেলে কী?

A) সবসময় zero
B) Saturate
C) Undefined Behavior
D) Auto long long

**সঠিক উত্তর: C) Undefined Behavior**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Signed overflow Standard-defined wrap নয়।
- **A option কেন ভুল:** Guarantee নেই।
- **B option কেন ভুল:** Saturating arithmetic নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Type auto widen নয়।
- **Related Concept:** Unsigned modulo wrap।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Unsigned wraps; signed overflow UB।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0235

**Master-bank reference:** Question 0169
**Metadata:** Topic: C Memory > Memory Leak | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Allocated memory release না করলে কী?

A) Memory Leak
B) Syntax Error
C) Integer Overflow
D) Name Collision

**সঠিক উত্তর: A) Memory Leak**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Unneeded allocation occupied থাকে বা reference হারায়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Compile হতে পারে।
- **C option কেন ভুল:** Integer range নয়।
- **D option কেন ভুল:** Identifier conflict নয়।
- **Related Concept:** Ownership ও release plan দরকার।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Allocate করলে free।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0236

**Master-bank reference:** Question 0176
**Metadata:** Topic: C File > Error Check | Difficulty: Easy | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. File open-এর পর প্রথম check?

A) fp NULL কি না
B) সব byte zero
C) Name keyword
D) Pointer integer

**সঠিক উত্তর: A) fp NULL কি না**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `fopen` failure-এ NULL।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Content irrelevant।
- **C option কেন ভুল:** Filename keyword rule নেই।
- **D option কেন ভুল:** FILE* integer নয়।
- **Related Concept:** `perror` diagnostic।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Open, check, use।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0237

**Master-bank reference:** Question 0177
**Metadata:** Topic: C Struct > Padding | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Struct size member sum-এর চেয়ে বড় কেন?

A) Recursion
B) Linker function যোগ
C) Member duplicate
D) Alignment ও Padding

**সঠিক উত্তর: D) Alignment ও Padding**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Hardware alignment পূরণে compiler gap যোগ করে।
- **A option কেন ভুল:** Layout নয়।
- **B option কেন ভুল:** Linker member যোগ করে না।
- **C option কেন ভুল:** Duplicate নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Member order optimization।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Invisible padding।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0238

**Master-bank reference:** Question 0178
**Metadata:** Topic: C Struct/Union > Memory | Difficulty: Medium | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Struct ও Union-এর memory পার্থক্য?

A) Struct separate, Union shared
B) Union member নেই
C) Struct one member
D) একই

**সঠিক উত্তর: A) Struct separate, Union shared**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Struct সব member simultaneously রাখে; union overlay।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Union multiple member।
- **C option কেন ভুল:** Struct multiple member।
- **D option কেন ভুল:** Fundamentally ভিন্ন।
- **Related Concept:** Union variant representation।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Struct together, union shared।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0239

**Master-bank reference:** Question 0179
**Metadata:** Topic: C Bit-field > Portability | Difficulty: Hard | Type: Theory
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Bit-field layout portable নয় কেন?

A) Runtime-only
B) Allocation order/alignment implementation-dependent
C) সবসময় pointer
D) শুধু file

**সঠিক উত্তর: B) Allocation order/alignment implementation-dependent**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Compiler/platform packing ও ordering ভিন্ন হতে পারে।
- **A option কেন ভুল:** Declaration-time layout।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Pointer নয়।
- **D option কেন ভুল:** Memory member।
- **Related Concept:** Hardware mapping-এ documentation প্রয়োজন।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Compact but not fully portable।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0240

**Master-bank reference:** Question 0180
**Metadata:** Topic: C Design > Modularity | Difficulty: Hard | Type: Scenario
**Section:** Programming Fundamentals & OOP
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Reusable function, limited file-scope data, header-এ প্রয়োজনীয় declaration—কোন quality উন্নত?

A) CPU clock
B) File extension
C) Modularity ও Maintainability
D) সব runtime error শেষ

**সঠিক উত্তর: C) Modularity ও Maintainability**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Responsibilities ও interface আলাদা হওয়ায় code test/change সহজ।
- **A option কেন ভুল:** Hardware speed নয়।
- **B option কেন ভুল:** Quality metric নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** সব error guarantee নয়।
- **Related Concept:** Separate compilation ও information hiding।

### সহজ Analogy

একটি programকে কারখানা ভাবুন—data কাঁচামাল, statement যন্ত্র, function workstation এবং class blueprint।

- **মনে রাখার টিপস:** Small focused module।


## Section 01 Completion Summary

```text
Question Range      = 001–180
Total MCQ           = 180
Covered             = Structured C + OOP
Difficulty          ≈ 25% Easy, 50% Medium, 25% Hard
Language            = Bangla with English technical keywords
```

---

# Section — Software Engineering

---

## MCQ 0241

**Master-bank reference:** Question 0181
**Metadata:** Topic: Software Engineering > Definition | Difficulty: Easy | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Software Engineering-এর সবচেয়ে যথাযথ সংজ্ঞা কোনটি?

A) শুধু programming শেখা
B) Software lifecycle-এ systematic disciplined engineering approach
C) শুধু hardware design
D) শুধু executable তৈরি

**সঠিক উত্তর: B) Software lifecycle-এ systematic disciplined engineering approach**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Requirement থেকে maintenance পর্যন্ত structured ও measurable practice Software Engineering।
- **A option কেন ভুল:** Programming একটি অংশ মাত্র।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Hardware circuit design নয়।
- **D option কেন ভুল:** Executable lifecycle-এর ছোট অংশ।
- **Related Concept:** Process, people, product ও quality সব অন্তর্ভুক্ত।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Code + Process + Quality + Management।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0242

**Master-bank reference:** Question 0187
**Metadata:** Topic: Software Engineering > SDLC Sequence | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. যৌক্তিক SDLC order কোনটি?

A) Testing→Requirement→Coding→Design
B) Coding→Deployment→Requirement
C) Planning→Requirement→Design→Implementation→Testing→Deployment
D) Maintenance→Planning→Coding

**সঠিক উত্তর: C) Planning→Requirement→Design→Implementation→Testing→Deployment**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Need বোঝা ও design-এর পরে build/test/release।
- **A option কেন ভুল:** Order ভুল।
- **B option কেন ভুল:** Requirement পরে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Maintenance deployment-এর পরে।
- **Related Concept:** Agile-এ phase iteration-এ repeat।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Understand, design, build, test, release।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0243

**Master-bank reference:** Question 0188
**Metadata:** Topic: Software Engineering > Requirements | Difficulty: Easy | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Requirements phase-এর প্রধান output কী?

A) Executable
B) Optimizer
C) Training report মাত্র
D) System behavior ও constraint-এর documented specification

**সঠিক উত্তর: D) System behavior ও constraint-এর documented specification**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** SRS functional ও non-functional expectation capture করে।
- **A option কেন ভুল:** Implementation পরে।
- **B option কেন ভুল:** Compiler concern।
- **C option কেন ভুল:** Requirement output নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Requirement কী; design কীভাবে।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Requirement = what।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0244

**Master-bank reference:** Question 0189
**Metadata:** Topic: Software Engineering > Design | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Design phase-এর প্রধান কাজ কী?

A) Requirement-কে architecture/component/interface/data design-এ রূপান্তর
B) Salary নির্ধারণ
C) Product বিক্রি
D) Bug report বন্ধ

**সঠিক উত্তর: A) Requirement-কে architecture/component/interface/data design-এ রূপান্তর**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Implementation blueprint তৈরি হয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Administration।
- **C option কেন ভুল:** Business activity।
- **D option কেন ভুল:** Testing/maintenance concern।
- **Related Concept:** High-level ও detailed design।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Requirement-এর technical solution।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0245

**Master-bank reference:** Question 0190
**Metadata:** Topic: Software Engineering > Productivity | Difficulty: Hard | Type: Calculation
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. 24 KLOC software 12 person-month effort-এ তৈরি হলে productivity কত?

A) 0.5
B) 2
C) 12
D) 288

**সঠিক উত্তর: B) 2**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Formula

```text
Productivity = Delivered Size / Effort
```

#### Substitution

```text
= 24 KLOC / 12 person-month
```

#### Calculation

```text
24 / 12 = 2
```

#### Final Answer

```text
Productivity = 2 KLOC/person-month
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Delivered size/effort = 2 KLOC/person-month।
- **A option কেন ভুল:** Division উল্টো।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Effort value।
- **D option কেন ভুল:** Multiplication।
- **Related Concept:** High productivity quality guarantee নয়।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Output ÷ Effort।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0246

**Master-bank reference:** Question 0191
**Metadata:** Topic: Software Engineering > Verification | Difficulty: Easy | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. “Are we building the product right?” কোন concept?

A) Validation
B) Deployment
C) Verification
D) Maintenance

**সঠিক উত্তর: C) Verification**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Specification অনুযায়ী artifact সঠিকভাবে তৈরি হচ্ছে কি না—Verification।
- **A option কেন ভুল:** Right product/user need।
- **B option কেন ভুল:** Release।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Post-release change।
- **Related Concept:** Review/static analysis verification technique।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Product right = Verification।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0247

**Master-bank reference:** Question 0192
**Metadata:** Topic: Software Engineering > Maintenance | Difficulty: Medium | Type: Scenario
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. নতুন OS version-এ চালাতে code change কোন maintenance?

A) Corrective
B) Perfective
C) Preventive
D) Adaptive

**সঠিক উত্তর: D) Adaptive**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** External environment change-এর সঙ্গে adaptation।
- **A option কেন ভুল:** Bug fix।
- **B option কেন ভুল:** Feature/performance।
- **C option কেন ভুল:** Future maintainability।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Hardware/regulation change-ও adaptive।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Environment বদল → Adaptive।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0248

**Master-bank reference:** Question 0198
**Metadata:** Topic: Software Quality > Availability | Difficulty: Hard | Type: Calculation
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. MTTF=900 hour, MTTR=100 hour হলে Availability কত?

A) 80%
B) 90%
C) 95%
D) 99%

**সঠিক উত্তর: B) 90%**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Formula

```text
Availability = MTTF / (MTTF + MTTR)
```

#### Substitution

```text
= 900 / (900 + 100)
```

#### Calculation

```text
= 900 / 1000
= 0.90
= 90%
```

#### Final Answer

```text
Availability = 90%
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 900/(900+100)=0.9=90%।
- **A option কেন ভুল:** Incorrect ratio।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Formula mismatch।
- **D option কেন ভুল:** Downtime খুব কম ধরে।
- **Related Concept:** MTTR কমলে availability বাড়ে।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Uptime fraction।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0249

**Master-bank reference:** Question 0199
**Metadata:** Topic: Software Quality > Efficiency | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. কম CPU, memory ও bandwidth-এ দ্রুত response কোন quality?

A) Portability
B) Maintainability
C) Efficiency
D) Correctness

**সঠিক উত্তর: C) Efficiency**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Resource use ও performance Efficiency।
- **A option কেন ভুল:** Platform।
- **B option কেন ভুল:** Modification।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Accuracy।
- **Related Concept:** Time/space efficiency পৃথক হতে পারে।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** কম resource, ভালো performance।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0250

**Master-bank reference:** Question 0200
**Metadata:** Topic: Software Quality > Reusability | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Authentication component বহু app-এ ব্যবহার কোন quality?

A) Reliability
B) Usability
C) Correctness
D) Reusability

**সঠিক উত্তর: D) Reusability**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Same component different context-এ reuse।
- **A option কেন ভুল:** Failure-free নয়।
- **B option কেন ভুল:** User ease নয়।
- **C option কেন ভুল:** Specification নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Generic interface ও low coupling সহায়ক।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Build once, use many।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0251

**Master-bank reference:** Question 0201
**Metadata:** Topic: Software Quality > Product Quality | Difficulty: Easy | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. কোনটি Product Quality attribute?

A) Attendance
B) Reliability
C) Office Rent
D) Meeting Duration

**সঠিক উত্তর: B) Reliability**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Reliability operational product behavior।
- **A option কেন ভুল:** Organization metric।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Cost item।
- **D option কেন ভুল:** Process activity।
- **Related Concept:** Maintainability/usability-ও product quality।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Product behavior = product quality।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0252

**Master-bank reference:** Question 0202
**Metadata:** Topic: Software Quality > Trade-off | Difficulty: Hard | Type: Scenario
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Security বাড়াতে MFA যোগে login ধীর হয়েছে—কী দেখায়?

A) Quality trade-off
B) সব quality একসঙ্গে বাড়ে
C) Security=Usability
D) Performance quality নয়

**সঠিক উত্তর: A) Quality trade-off**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Security improvement usability/performance cost আনতে পারে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Conflicting goals থাকে।
- **C option কেন ভুল:** Distinct attributes।
- **D option কেন ভুল:** Efficiency quality।
- **Related Concept:** Architecture-এ priority balance।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Maximum নয়, balanced quality।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0253

**Master-bank reference:** Question 0203
**Metadata:** Topic: Software Quality > Measurement | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Quality measurement-এর ভালো approach কী?

A) শুধু developer opinion
B) File name
C) Language popularity
D) Relevant measurable metric ও stakeholder goal

**সঠিক উত্তর: D) Relevant measurable metric ও stakeholder goal**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Quality context-dependent ও evidence-based হওয়া উচিত।
- **A option কেন ভুল:** Subjective only।
- **B option কেন ভুল:** Irrelevant।
- **C option কেন ভুল:** Guarantee নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Response time, defect density, success rate metric।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Goal measurable করুন।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0254

**Master-bank reference:** Question 0209
**Metadata:** Topic: Software Quality > Portability Practice | Difficulty: Medium | Type: Scenario
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Platform-specific code abstraction layer-এর পেছনে রাখলে কোন quality বাড়ে?

A) Portability
B) Defect Severity
C) Office Productivity
D) Marketing Reach

**সঠিক উত্তর: A) Portability**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Platform dependency isolate হলে migration সহজ।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Directly নয়।
- **C option কেন ভুল:** Organization নয়।
- **D option কেন ভুল:** Marketing নয়।
- **Related Concept:** Container/standard API-ও সহায়ক।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Platform detail isolate।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0255

**Master-bank reference:** Question 0210
**Metadata:** Topic: Software Quality > Maintainability Practice | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Maintainability কমায় কোনটি?

A) Clear Naming
B) High Coupling ও Duplicate Logic
C) Automated Test
D) Modular Architecture

**সঠিক উত্তর: B) High Coupling ও Duplicate Logic**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Change বহু জায়গায় ripple করে।
- **A option কেন ভুল:** বোঝা সহজ।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Safe change।
- **D option কেন ভুল:** Isolation।
- **Related Concept:** Technical debt maintainability কমায়।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Duplication + dependency।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0256

**Master-bank reference:** Question 0211
**Metadata:** Topic: Software Models > Waterfall | Difficulty: Easy | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Waterfall-এর প্রধান বৈশিষ্ট্য?

A) Documentation নেই
B) শুধু testing
C) Sequential phases
D) Daily release

**সঠিক উত্তর: C) Sequential phases**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** এক phase largely complete করে next phase।
- **A option কেন ভুল:** সাধারণত documentation-heavy।
- **B option কেন ভুল:** Multiple phases।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Required নয়।
- **Related Concept:** Stable requirement-এ উপযোগী।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Water falls one direction।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0257

**Master-bank reference:** Question 0212
**Metadata:** Topic: Software Models > Waterfall Limitation | Difficulty: Hard | Type: Scenario
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Requirement প্রতি মাসে বদলালে Waterfall ঝুঁকিপূর্ণ কেন?

A) Design নেই
B) Testing নিষিদ্ধ
C) শুধু ছোট code
D) Late change rework বাড়ায়

**সঠিক উত্তর: D) Late change rework বাড়ায়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Sequential baseline-এর আগের artifacts পুনরায় বদলাতে হয়।
- **A option কেন ভুল:** Design আছে।
- **B option কেন ভুল:** Testing আছে।
- **C option কেন ভুল:** Size একমাত্র factor নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Agile/iterative adaptive।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Changing need + late feedback = risk।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0258

**Master-bank reference:** Question 0213
**Metadata:** Topic: Software Models > V-Model | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. V-Model-এর শক্তি কী?

A) Testing বাদ
B) Development phase-এর corresponding test planning
C) Requirement ছাড়া coding
D) শুধু prototype

**সঠিক উত্তর: B) Development phase-এর corresponding test planning**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Verification artifact ও validation level traceableভাবে pair করে।
- **A option কেন ভুল:** Testing গুরুত্ব পায়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Requirement থাকে।
- **D option কেন ভুল:** Prototype-only নয়।
- **Related Concept:** Module design↔Unit test; Requirement↔Acceptance।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** V-এর দুই পাশ build ও test।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0259

**Master-bank reference:** Question 0214
**Metadata:** Topic: Software Models > Spiral | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Spiral Model-এর কেন্দ্রীয় বৈশিষ্ট্য?

A) Risk Analysis
B) No documentation
C) One final delivery
D) No feedback

**সঠিক উত্তর: A) Risk Analysis**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতি cycle-এ risk identify, analyze, mitigate।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** প্রয়োজনীয় documentation থাকে।
- **C option কেন ভুল:** Iterative।
- **D option কেন ভুল:** Evaluation থাকে।
- **Related Concept:** High-risk project।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Spiral দেখলে Risk।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0260

**Master-bank reference:** Question 0220
**Metadata:** Topic: Software Models > Model Selection | Difficulty: Hard | Type: Scenario
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Stable safety-critical medical system ও rigorous test traceability—উপযুক্ত model?

A) Prototype-only
B) Code-and-Fix
C) RAD no docs
D) V-Model

**সঠিক উত্তর: D) V-Model**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Formal development-test correspondence ও traceability।
- **A option কেন ভুল:** Requirement exploration যথেষ্ট নয়।
- **B option কেন ভুল:** Unsafe।
- **C option কেন ভুল:** Compliance দুর্বল।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Regulated context-এ controlled lifecycle।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Safety + trace test → V।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0261

**Master-bank reference:** Question 0221
**Metadata:** Topic: Software Models > Iterative vs Incremental | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. পার্থক্য কোনটি?

A) একসঙ্গে নয়
B) Iterative refine; Incremental capability যোগ
C) Iteration docs only
D) Increment-এ working software নেই

**সঠিক উত্তর: B) Iterative refine; Incremental capability যোগ**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Iteration quality/detail উন্নত; increment scope/functionality বাড়ায়।
- **A option কেন ভুল:** প্রায়ই একসঙ্গে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** ভুল।
- **D option কেন ভুল:** Usable হতে পারে।
- **Related Concept:** Agile দুটোই।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Iterate refine, increment add।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0262

**Master-bank reference:** Question 0222
**Metadata:** Topic: Software Models > Agile Velocity | Difficulty: Hard | Type: Calculation
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. তিন Sprint-এ 20,25,30 Story Point; average velocity?

A) 25
B) 20
C) 30
D) 75

**সঠিক উত্তর: A) 25**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Calculation

```text
Total = 20 + 25 + 30 = 75
Average = 75 / 3 = 25
```

#### Final Answer

```text
Average Velocity = 25 Story Points/Sprint
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Total 75/3=25।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** First sprint।
- **C option কেন ভুল:** Maximum।
- **D option কেন ভুল:** Total, average নয়।
- **Related Concept:** Team-to-team velocity comparison অনুচিত।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Completed total ÷ sprints।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0263

**Master-bank reference:** Question 0223
**Metadata:** Topic: Software Models > Requirement-Driven | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Requirement-Driven Development-এর control source কী?

A) Developer preference
B) Hardware brand
C) Office location
D) Prioritized traceable evolving requirements

**সঠিক উত্তর: D) Prioritized traceable evolving requirements**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Scope, design ও test requirement value/change দিয়ে চালিত।
- **A option কেন ভুল:** Formal driver নয়।
- **B option কেন ভুল:** Constraint হতে পারে।
- **C option কেন ভুল:** Irrelevant।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Traceability links requirement to test।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Requirements drive development।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0264

**Master-bank reference:** Question 0224
**Metadata:** Topic: Software Models > Spiral Activities | Difficulty: Hard | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Spiral cycle-এর logical sequence?

A) Deploy→cancel→code
B) Code without risk
C) Objective→Risk Analysis→Develop/Validate→Next Plan
D) Docs only

**সঠিক উত্তর: C) Objective→Risk Analysis→Develop/Validate→Next Plan**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতি loop goal, risk, engineering ও planning।
- **A option কেন ভুল:** Model flow নয়।
- **B option কেন ভুল:** Risk missing।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Iterative work নেই।
- **Related Concept:** Prototype risk reduction করতে পারে।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Objective, risk, build, plan।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0265

**Master-bank reference:** Question 0225
**Metadata:** Topic: Software Models > Waterfall Suitability | Difficulty: Easy | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Waterfall কখন উপযুক্ত?

A) Requirement daily change
B) Clear stable documented requirement
C) Unknown technology
D) Customer need unknown

**সঠিক উত্তর: B) Clear stable documented requirement**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Sequential baseline stable need-এ effective।
- **A option কেন ভুল:** Rework।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Risk/iteration দরকার।
- **D option কেন ভুল:** Prototype দরকার।
- **Related Concept:** Contract-driven project-এও।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Stable need → Waterfall।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0266

**Master-bank reference:** Question 0231
**Metadata:** Topic: Software Engineering > Modularity | Difficulty: Easy | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. বড় system-কে ছোট manageable অংশে ভাগ করার principle কোনটি?

A) Portability
B) Validation
C) Modularity
D) Serialization

**সঠিক উত্তর: C) Modularity**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Modularity system-কে focused ও relatively independent module-এ ভাঙে।
- **A option কেন ভুল:** Platform transfer।
- **B option কেন ভুল:** User need verification।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Data representation।
- **Related Concept:** Module testing/change সহজ করে।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** বড় system → ছোট module।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0267

**Master-bank reference:** Question 0232
**Metadata:** Topic: Software Engineering > Information Hiding | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Module internal data structure লুকিয়ে public operation প্রকাশ করলে কোন principle?

A) Information Hiding
B) Code Duplication
C) Global Coupling
D) Unstructured Design

**সঠিক উত্তর: A) Information Hiding**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** পরিবর্তনশীল implementation decision interface-এর পেছনে লুকানো হয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Repeated logic।
- **C option কেন ভুল:** Dependency বাড়ায়।
- **D option কেন ভুল:** Control/design disorder।
- **Related Concept:** Encapsulation implementation mechanism।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** How hidden, service visible।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0268

**Master-bank reference:** Question 0233
**Metadata:** Topic: Software Engineering > Abstraction | Difficulty: Medium | Type: Scenario
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `Database.save()` ব্যবহার করা হলেও disk detail না জানা—কোন principle?

A) Regression
B) Replication
C) Inheritance
D) Abstraction

**সঠিক উত্তর: D) Abstraction**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Essential operation visible, implementation detail hidden।
- **A option কেন ভুল:** Change-এর পর old feature break।
- **B option কেন ভুল:** Data copy।
- **C option কেন ভুল:** Subtype relation।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Interface abstraction দেয়।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** What দেখা, how লুকানো।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0269

**Master-bank reference:** Question 0234
**Metadata:** Topic: Software Engineering > Cohesion | Difficulty: Easy | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Module-এর function-গুলো একই responsibility-র সঙ্গে related হলে কোন quality ভালো?

A) Coupling
B) Cohesion
C) Volatility
D) Redundancy

**সঠিক উত্তর: B) Cohesion**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Internal elements-এর relatedness High Cohesion।
- **A option কেন ভুল:** Inter-module dependency।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Change rate।
- **D option কেন ভুল:** Duplication।
- **Related Concept:** High Cohesion maintainability বাড়ায়।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** ভেতরের সম্পর্ক = Cohesion।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0270

**Master-bank reference:** Question 0235
**Metadata:** Topic: Software Engineering > Coupling | Difficulty: Hard | Type: Scenario
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Module A সরাসরি B-এর internal variable বদলায়—প্রধান সমস্যা?

A) Tight Coupling
B) High Portability
C) Strong Validation
D) Functional Cohesion

**সঠিক উত্তর: A) Tight Coupling**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** A B-এর implementation detail-এর ওপর নির্ভরশীল।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Platform নয়।
- **C option কেন ভুল:** User need নয়।
- **D option কেন ভুল:** Internal focus নয়।
- **Related Concept:** Stable interface dependency কমায়।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** অন্য module-এর ভেতরে হাত দিলে coupling।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0271

**Master-bank reference:** Question 0236
**Metadata:** Topic: Software Engineering > Generality | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. এক sorting component int, string ও custom object-এ ব্যবহারযোগ্য—কোন principle?

A) Validation
B) Localization
C) Generality
D) Debugging

**সঠিক উত্তর: C) Generality**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** এক solution multiple related case handle করে।
- **A option কেন ভুল:** Need checking।
- **B option কেন ভুল:** Regional adaptation।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Defect fixing।
- **Related Concept:** Generic design reusability বাড়ায়।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** One solution, many related cases।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0272

**Master-bank reference:** Question 0242
**Metadata:** Topic: Software Engineering > Modular Design | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. ভালো modular design combination?

A) Low Cohesion, High Coupling
B) Low Cohesion, Low Coupling
C) High Cohesion, Low Coupling
D) High Cohesion, High Coupling

**সঠিক উত্তর: C) High Cohesion, Low Coupling**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** ভেতরে focused responsibility, বাইরে কম dependency।
- **A option কেন ভুল:** দুটিই খারাপ।
- **B option কেন ভুল:** Module unfocused।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** External dependency বেশি।
- **Related Concept:** Maintainable architecture goal।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** ভেতরে high, বাইরে low।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0273

**Master-bank reference:** Question 0243
**Metadata:** Topic: Requirements > Functional | Difficulty: Easy | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. “System password reset দেবে”—কোন requirement?

A) Portability
B) Functional
C) Legal only
D) Metric

**সঠিক উত্তর: B) Functional**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** System কী operation দেবে তা বলে।
- **A option কেন ভুল:** Platform move।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** System behavior।
- **D option কেন ভুল:** Measurement নয়।
- **Related Concept:** Use Case functional need capture করে।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** System কী করবে।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0274

**Master-bank reference:** Question 0244
**Metadata:** Topic: Requirements > Non-Functional | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. “Search result 2 second-এর মধ্যে”—কোন requirement?

A) Performance Non-Functional
B) Functional
C) Data Entry
D) Source-code

**সঠিক উত্তর: A) Performance Non-Functional**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Response-time quality constraint।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Search capability functional; time limit non-functional।
- **C option কেন ভুল:** Data entry নয়।
- **D option কেন ভুল:** Implementation structure নয়।
- **Related Concept:** Security/availability-ও NFR।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** কত ভালোভাবে কাজ করবে।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0275

**Master-bank reference:** Question 0245
**Metadata:** Topic: Requirements > SRS Quality | Difficulty: Hard | Type: Scenario
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. “System দ্রুত response দেবে”—প্রধান সমস্যা?

A) অতিরিক্ত complete
B) শুধু functional
C) Ambiguous ও unverifiable
D) Mathematically wrong

**সঠিক উত্তর: C) Ambiguous ও unverifiable**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `দ্রুত` measurable threshold ছাড়া ভিন্নভাবে interpreted হয়।
- **A option কেন ভুল:** বরং detail কম।
- **B option কেন ভুল:** Performance expectation হলেও অস্পষ্ট।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Math issue নয়।
- **Related Concept:** ভালো: 95% request ≤2 sec।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Measurable requirement লিখুন।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0276

**Master-bank reference:** Question 0246
**Metadata:** Topic: Requirements > Volatility | Difficulty: Medium | Type: Calculation
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Baseline 120 requirement-এর 15টি change হলে volatility কত?

A) 8%
B) 10%
C) 15%
D) 12.5%

**সঠিক উত্তর: D) 12.5%**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Formula

```text
Volatility% = Changed / Baseline × 100
```

#### Substitution

```text
= 15 / 120 × 100
```

#### Calculation

```text
15 / 120 = 0.125
0.125 × 100 = 12.5%
```

#### Final Answer

```text
Requirement Volatility = 12.5%
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 15/120×100=12.5%।
- **A option কেন ভুল:** Division ভুল।
- **B option কেন ভুল:** Approximation ভুল।
- **C option কেন ভুল:** Raw count percentage ধরা।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** High volatility schedule/test impact বাড়ায়।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Changed ÷ Baseline ×100।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0277

**Master-bank reference:** Question 0247
**Metadata:** Topic: Requirements > Stakeholder | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Stakeholder কাকে বলে?

A) শুধু programmer
B) System-এ interest/impact আছে এমন ব্যক্তি বা group
C) শুধু DBA
D) শুধু sponsor

**সঠিক উত্তর: B) System-এ interest/impact আছে এমন ব্যক্তি বা group**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** User, customer, regulator, operator, maintainer—সব stakeholder হতে পারে।
- **A option কেন ভুল:** এক ধরন।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এক ধরন।
- **D option কেন ভুল:** এক ধরন।
- **Related Concept:** Conflict analysis দরকার।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Interest বা impact থাকলে stakeholder।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0278

**Master-bank reference:** Question 0253
**Metadata:** Topic: Requirements > Change Control | Difficulty: Medium | Type: Scenario
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Approved baseline requirement change-এর আগে কী?

A) Direct code change
B) Old doc delete
C) Testing বন্ধ
D) Impact Analysis ও approval

**সঠিক উত্তর: D) Impact Analysis ও approval**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Cost, schedule, design ও test impact বুঝে formal decision।
- **A option কেন ভুল:** Uncontrolled।
- **B option কেন ভুল:** History হারায়।
- **C option কেন ভুল:** Testing আরও দরকার।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Configuration Management baseline control।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Understand, approve, implement।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0279

**Master-bank reference:** Question 0254
**Metadata:** Topic: Requirements > Conflict | Difficulty: Hard | Type: Scenario
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Security long password, usability short password চায়—সঠিক approach?

A) Negotiation, risk analysis, prioritized trade-off
B) দুটিই ignore
C) Developer preference
D) Doc hide

**সঠিক উত্তর: A) Negotiation, risk analysis, prioritized trade-off**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Stakeholder objective ও risk দিয়ে balanced decision।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Goal fail।
- **C option কেন ভুল:** Personal preference নয়।
- **D option কেন ভুল:** Conflict solve নয়।
- **Related Concept:** MFA balance দিতে পারে।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Conflict → negotiate ও prioritize।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0280

**Master-bank reference:** Question 0255
**Metadata:** Topic: Testing > Unit | Difficulty: Easy | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Individual function/class method test কোন level?

A) System
B) Unit
C) Acceptance
D) Deployment

**সঠিক উত্তর: B) Unit**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Smallest testable component।
- **A option কেন ভুল:** Whole system।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Customer need।
- **D option কেন ভুল:** Principal standard level নয়।
- **Related Concept:** Mock dependency isolate করে।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Smallest component = Unit।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0281

**Master-bank reference:** Question 0256
**Metadata:** Topic: Testing > Black-box | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Source code না দেখে input-output ভিত্তিক test?

A) Black-box
B) White-box
C) Static Linking
D) Code Generation

**সঠিক উত্তর: A) Black-box**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Externally visible behavior test।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Internal structure।
- **C option কেন ভুল:** Build process।
- **D option কেন ভুল:** Implementation।
- **Related Concept:** Boundary Value/Equivalence Partitioning।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Box-এর ভিতর দেখা হয় না।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0282

**Master-bank reference:** Question 0257
**Metadata:** Topic: Testing > Cyclomatic Complexity | Difficulty: Hard | Type: Calculation
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. CFG-এ Edge=14, Node=11, P=1 হলে complexity কত?

A) 2
B) 3
C) 5
D) 14

**সঠিক উত্তর: C) 5**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Formula

```text
V(G) = E - N + 2P
```

#### Substitution

```text
= 14 - 11 + 2(1)
```

#### Calculation

```text
14 - 11 = 3
2(1) = 2
3 + 2 = 5
```

#### Final Answer

```text
Cyclomatic Complexity = 5
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 14−11+2×1=5।
- **A option কেন ভুল:** শুধু 2P।
- **B option কেন ভুল:** E−N, 2P বাদ।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Edge count।
- **Related Concept:** Independent path count।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** E−N+2P।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0283

**Master-bank reference:** Question 0258
**Metadata:** Topic: Testing > White-box | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Branch Coverage ও Path Coverage কোন category?

A) Acceptance
B) Usability
C) Black-box
D) White-box

**সঠিক উত্তর: D) White-box**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Internal control structure-এর ওপর ভিত্তি করে।
- **A option কেন ভুল:** Business acceptance।
- **B option কেন ভুল:** User interaction।
- **C option কেন ভুল:** Internal path ব্যবহার করে না।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Statement/condition coverage-ও white-box।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Code-এর পথ = White-box।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0284

**Master-bank reference:** Question 0264
**Metadata:** Topic: Testing > Integration | Difficulty: Easy | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Module-গুলোর data exchange test কোন level?

A) Unit
B) Integration
C) Static
D) Acceptance

**সঠিক উত্তর: B) Integration**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Component interface ও interaction।
- **A option কেন ভুল:** Single component।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Execution ছাড়া।
- **D option কেন ভুল:** User need।
- **Related Concept:** Top-down/Bottom-up।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Module মিললে Integration।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0285

**Master-bank reference:** Question 0265
**Metadata:** Topic: Testing > Test Oracle | Difficulty: Hard | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Test Oracle কী?

A) Test hardware
B) Bug programmer
C) Random generator
D) Actual result correct কি না নির্ধারণের mechanism

**সঠিক উত্তর: D) Actual result correct কি না নির্ধারণের mechanism**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Expected output/spec/model/trusted implementation verdict দেয়।
- **A option কেন ভুল:** Environment।
- **B option কেন ভুল:** সবসময় নয়।
- **C option কেন ভুল:** Input দেয়, verdict নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Oracle Problem complex domain-এ।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Pass/fail বিচারক।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0286

**Master-bank reference:** Question 0266
**Metadata:** Topic: Testing > DRE | Difficulty: Hard | Type: Calculation
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Release আগে 90 defect remove, পরে 10 পাওয়া; DRE কত?

A) 10%
B) 80%
C) 90%
D) 100%

**সঠিক উত্তর: C) 90%**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Formula

```text
DRE = Pre-release Removed / (Pre + Post Defects) × 100
```

#### Calculation

```text
Total known = 90 + 10 = 100
DRE = 90 / 100 × 100 = 90%
```

#### Final Answer

```text
DRE = 90%
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 90/(90+10)×100=90%।
- **A option কেন ভুল:** Post-release proportion।
- **B option কেন ভুল:** Incorrect total।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Post-release defect থাকায় 100 নয়।
- **Related Concept:** High DRE pre-release effectiveness।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Before release ÷ total known।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0287

**Master-bank reference:** Question 0267
**Metadata:** Topic: Testing > Boundary Value | Difficulty: Medium | Type: Scenario
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Valid range 1–100; boundary test set কোনটি?

A) 50 only
B) 0,1,2,99,100,101
C) Random 10 only
D) Boundary বাদ

**সঠিক উত্তর: B) 0,1,2,99,100,101**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Lower/upper boundary-এর just below, on, just above।
- **A option কেন ভুল:** Middle only।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Boundary guarantee নয়।
- **D option কেন ভুল:** Technique-এর বিপরীত।
- **Related Concept:** Boundary-তে defect common।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Min−1,Min,Min+1; Max−1,Max,Max+1।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0288

**Master-bank reference:** Question 0268
**Metadata:** Topic: Testing > Stub/Driver | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Top-down integration-এ missing lower module-এর replacement কী?

A) Stub
B) Driver
C) Compiler
D) Linker Script

**সঠিক উত্তর: A) Stub**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Stub called lower-level component simulate করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Missing caller; bottom-up।
- **C option কেন ভুল:** Translator।
- **D option কেন ভুল:** Link layout।
- **Related Concept:** Top-down Stub, Bottom-up Driver।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** নিচের module → Stub।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0289

**Master-bank reference:** Question 0269
**Metadata:** Topic: UML > Use Case | Difficulty: Easy | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Actor ও service interaction কোন diagram?

A) Deployment
B) Class
C) Use Case
D) Package

**সঠিক উত্তর: C) Use Case**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** User goal ও system functionality relation।
- **A option কেন ভুল:** Physical nodes।
- **B option কেন ভুল:** Static classes।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Grouping।
- **Related Concept:** Actor system boundary-এর বাইরে।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** কে কী করে।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0290

**Master-bank reference:** Question 0275
**Metadata:** Topic: UML > Component vs Deployment | Difficulty: Hard | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. সঠিক পার্থক্য?

A) একই
B) Component software parts; Deployment physical node placement
C) Component শুধু user
D) Deployment class attribute

**সঠিক উত্তর: B) Component software parts; Deployment physical node placement**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Logical implementation component বনাম physical runtime topology।
- **A option কেন ভুল:** উদ্দেশ্য আলাদা।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Use Case actor।
- **D option কেন ভুল:** Class diagram।
- **Related Concept:** Server/device Deployment node।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Component কী, Deployment কোথায়।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0291

**Master-bank reference:** Question 0276
**Metadata:** Topic: UI Design > Consistency | Difficulty: Medium | Type: Scenario
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. সব screen-এ same button same কাজ—কোন principle?

A) Consistency
B) Hidden Navigation
C) Randomization
D) Maximum Complexity

**সঠিক উত্তর: A) Consistency**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Uniform behavior learning burden কমায়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Usability কমায়।
- **C option কেন ভুল:** Confusion।
- **D option কেন ভুল:** Design goal নয়।
- **Related Concept:** Platform convention external consistency।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** একই জিনিস একইভাবে।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0292

**Master-bank reference:** Question 0277
**Metadata:** Topic: UI Design > Feedback | Difficulty: Easy | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Save-এর পরে “Saved Successfully” message কোন principle?

A) Abstraction
B) Inheritance
C) Feedback
D) Coupling

**সঠিক উত্তর: C) Feedback**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** System action গ্রহণ ও result জানায়।
- **A option কেন ভুল:** Detail hiding।
- **B option কেন ভুল:** Class relation।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Dependency।
- **Related Concept:** Visibility of status।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Action-এর পরে response।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0293

**Master-bank reference:** Question 0278
**Metadata:** Topic: UI Design > Error Prevention | Difficulty: Medium | Type: Scenario
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Delete-এর আগে confirmation কেন?

A) Complexity
B) Accidental destructive action প্রতিরোধ
C) Network speed
D) Normalization

**সঠিক উত্তর: B) Accidental destructive action প্রতিরোধ**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** High-impact action-এর আগে user intent verify।
- **A option কেন ভুল:** Purpose নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Bandwidth নয়।
- **D option কেন ভুল:** DB concept।
- **Related Concept:** Undo error recovery।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Destructive action আগে confirm।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0294

**Master-bank reference:** Question 0279
**Metadata:** Topic: UI Design > Task Success | Difficulty: Medium | Type: Calculation
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. 50 user-এর 45 task complete; success rate কত?

A) 90%
B) 45%
C) 95%
D) 5%

**সঠিক উত্তর: A) 90%**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Formula

```text
Task Success Rate = Successful / Total × 100
```

#### Calculation

```text
45 / 50 = 0.9
0.9 × 100 = 90%
```

#### Final Answer

```text
Task Success Rate = 90%
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 45/50×100=90%।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Raw success count।
- **C option কেন ভুল:** Incorrect।
- **D option কেন ভুল:** Failed raw count।
- **Related Concept:** Failure rate 10%।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Successful ÷ Total।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0295

**Master-bank reference:** Question 0280
**Metadata:** Topic: UML > Modeling Purpose | Difficulty: Easy | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Software Model সম্পর্কে সঠিক statement?

A) সব detail ধারণ করে
B) Implementation লাগে না
C) Decoration
D) Selected important aspect সহজভাবে দেখায়

**সঠিক উত্তর: D) Selected important aspect সহজভাবে দেখায়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Model purposeful abstraction; communication ও analysis সহজ করে।
- **A option কেন ভুল:** কিছু detail ইচ্ছাকৃত বাদ।
- **B option কেন ভুল:** Implementation replace নয়।
- **C option কেন ভুল:** Analysis tool।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Different concern-এর different model।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Simplified purposeful view।


## Batch 06 Quality Summary

```text
Questions          = 50
Theory/Scenario    = 44
Calculation        = 6
Coverage           = Principles, Requirements, Testing, UML, UI
Math format        = Plain-text aligned
```

---

## MCQ 0296

**Master-bank reference:** Question 0286
**Metadata:** Topic: Estimation > COCOMO Effort | Difficulty: Hard | Type: Calculation
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. `Effort=2.4×(KLOC)^1.05`; KLOC=10 এবং `10^1.05≈11.22`; effort কত?

A) 11.22 person-month
B) 24.00 person-month
C) 21.53 person-month
D) 26.93 person-month

**সঠিক উত্তর: D) 26.93 person-month**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Formula

```text
Effort = 2.4 × (KLOC)^1.05
```

#### Given Data

```text
KLOC = 10
10^1.05 ≈ 11.22
```

#### Substitution

```text
Effort = 2.4 × 11.22
```

#### Calculation

```text
11.22 × 2.0 = 22.44
11.22 × 0.4 = 4.488
Total = 26.928
```

#### Final Answer

```text
Estimated Effort ≈ 26.93 person-month
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 2.4×11.22=26.928≈26.93 person-month।
- **A option কেন ভুল:** Coefficient apply হয়নি।
- **B option কেন ভুল:** Exponent বাদ।
- **C option কেন ভুল:** Multiplication ভুল।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Effort duration নয়।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** Power আগে, coefficient পরে।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0297

**Master-bank reference:** Question 0287
**Metadata:** Topic: Estimation > COCOMO Modes | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. কঠোর hardware/software/operational constraint কোন COCOMO mode?

A) Embedded
B) Organic
C) Informal
D) Prototype

**সঠিক উত্তর: A) Embedded**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Embedded project tightly constrained environment-এ।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Small familiar flexible।
- **C option কেন ভুল:** Standard mode নয়।
- **D option কেন ভুল:** Development model।
- **Related Concept:** Semi-detached মধ্যবর্তী।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** কঠোর environment → Embedded।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0298

**Master-bank reference:** Question 0288
**Metadata:** Topic: Metrics > LOC Limitation | Difficulty: Hard | Type: Scenario
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Same functionality-তে বেশি LOC team-কে বেশি productive বলা ভুল কেন?

A) LOC গোনা যায় না
B) Short code সবসময় wrong
C) LOC language/reuse/design/generated code-নির্ভর
D) Size irrelevant

**সঠিক উত্তর: C) LOC language/reuse/design/generated code-নির্ভর**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** More lines inefficiency বা duplication-ও হতে পারে।
- **A option কেন ভুল:** গোনা যায়।
- **B option কেন ভুল:** Length correctness নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Size useful but contextual।
- **Related Concept:** Value/effort বিবেচনা প্রয়োজন।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** More code ≠ more value।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0299

**Master-bank reference:** Question 0289
**Metadata:** Topic: Metrics > Function Point | Difficulty: Easy | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. Function Point-এর সুবিধা?

A) Formatting measure
B) Hardware speed
C) Defect severity
D) User-visible functionality-based size

**সঠিক উত্তর: D) User-visible functionality-based size**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Implementation language-এর বদলে functional input/output/data দেখে।
- **A option কেন ভুল:** Style নয়।
- **B option কেন ভুল:** Hardware নয়।
- **C option কেন ভুল:** Quality metric নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** LOC-এর তুলনায় language-independent।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** User function মাপে।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---

## MCQ 0300

**Master-bank reference:** Question 0290
**Metadata:** Topic: Function Point > Components | Difficulty: Medium | Type: Theory
**Section:** Software Engineering
**Reconstruction status:** AI-reviewed, corrected practice MCQ; scanned PDF-এর verbatim transcription নয়।

Q. কোনটি Function Point component নয়?

A) External Input
B) CPU Clock Frequency
C) External Output
D) Internal Logical File

**সঠিক উত্তর: B) CPU Clock Frequency**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** CPU frequency hardware metric।
- **A option কেন ভুল:** Standard EI।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Standard EO।
- **D option কেন ভুল:** Standard ILF।
- **Related Concept:** EQ ও EIF-ও আছে।

### সহজ Analogy

Software project একটি ভবন নির্মাণের মতো—requirements নকশা, design স্থাপত্য, testing মান যাচাই এবং maintenance মেরামত।

- **মনে রাখার টিপস:** FP functional size, CPU নয়।

### Study Note

এই প্রশ্নটি damaged scan-এর exact text হিসেবে দাবি করা হয়নি। Standard ICT syllabus, verified definition এবং master-bank analysis অনুসারে পরিষ্কার practice form-এ পুনর্গঠন করা হয়েছে।

---
