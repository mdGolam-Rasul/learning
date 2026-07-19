# ১৯তম শিক্ষক নিবন্ধন — প্রভাষক (Lecturer), ICT

## Consolidated README: Batch 01–07 | Question 001–300

**Subject Code:** 452  
**Covered Sections:**  
1. Structured & Object-Oriented Programming — Question 001–180  
2. Introduction to Software Engineering — Question 181–300  

> এই file-টি আগের Batch 01–07-এর একটি **সংকলিত, পরিমার্জিত ও GitHub-ready সংস্করণ**। Theory note ও MCQ analysis আগের তুলনায় বিস্তারিত করা হয়েছে। সব Math/Calculation plain-text aligned block-এ লেখা হয়েছে; raw LaTeX command ব্যবহার করা হয়নি।

---

## Table of Contents

- [Batch 01 — Question 001–050](#batch-01--question-001050)
- [Batch 02 — Question 051–100](#batch-02--question-051100)
- [Batch 03 — Question 101–150](#batch-03--question-101150)
- [Batch 04 — Question 151–180](#batch-04--question-151180)
- [Batch 05 — Question 181–230](#batch-05--question-181230)
- [Batch 06 — Question 231–280](#batch-06--question-231280)
- [Batch 07 — Question 281–300](#batch-07--question-281300)

---

## Formatting Policy

- প্রশ্ন, option ও বিশ্লেষণ বাংলা ভাষায়।
- Technical keyword, function, command, formula ও code English-এ।
- প্রতিটি MCQ-তে একটিমাত্র unambiguous correct answer।
- Math/Code question-এ step-by-step tracing।
- প্রতিটি wrong option-এর পৃথক কারণ।
- GitHub/mobile-friendly plain-text calculation।


# Batch 01 — Question 001–050

**Section:** Structured & Object-Oriented Programming  
**Coverage:** C fundamentals, program structure, preprocessing, compilation, linking, header files, data types, operators ও control statements  
**Composition:** Theory/Scenario 35, Calculation/Code 15


# Chapter Theory 01: C Fundamentals ও Program Translation

## মূল ধারণা

C একটি general-purpose, procedural ও structured programming language। একটি hosted C program-এর execution সাধারণত `main()` function থেকে শুরু হয়। Source code executable হওয়ার আগে সাধারণ pipeline:

```text
Source Code
   ↓
Preprocessing
   ↓
Compilation
   ↓
Assembly
   ↓
Linking
   ↓
Executable
```

`Preprocessor` `#include`, `#define` ও conditional directive process করে। Compiler syntax, type ও semantic rule যাচাই করে translation করে। Assembler object code তৈরি করে। Linker object file ও library combine করে external symbol resolve করে।

## C Token, Keyword ও Identifier

C program-এর ক্ষুদ্রতম meaningful lexical unit হলো `Token`। Token-এর মধ্যে keyword, identifier, literal, operator ও punctuator থাকে।

Identifier rule:

- Letter বা underscore দিয়ে শুরু হবে।
- পরে letter, digit বা underscore থাকতে পারে।
- Keyword ব্যবহার করা যাবে না।
- C case-sensitive; `Total` ও `total` আলাদা।

## Error-এর ধরন

- **Syntax Error:** Language grammar ভাঙে; compilation ব্যর্থ হতে পারে।
- **Semantic/Type Error:** Type বা declaration rule ভাঙে।
- **Linker Error:** Declared external symbol-এর definition পাওয়া যায় না বা duplicate definition থাকে।
- **Runtime Error:** Program চলার সময় failure।
- **Logical Error:** Program চলে, কিন্তু ভুল result দেয়।
- **Undefined Behavior:** Standard কোনো outcome guarantee করে না।

## Header ও Library

Header file সাধারণত declaration, macro ও type definition দেয়। Library actual compiled implementation দিতে পারে। `printf()`-এর declaration `<stdio.h>`-এ, কিন্তু definition standard library-তে থাকে। Include guard repeated inclusion-এর সমস্যা কমায়।

## Exam Tips

- `#` directive দেখলে Preprocessor ভাবুন।
- Declaration compiler-এর type checking-এ সাহায্য করে; definition linker-এর প্রয়োজন।
- Program চলে কিন্তু output ভুল → Logical Error।
- `sizeof(char)` সবসময় 1 byte; তবে byte-এর bit count `CHAR_BIT`-নির্ভর।


## প্রশ্ন 1 | Topic: Structured Programming > C Program Entry Point | Difficulty: Easy | Type: Theory

Q. Hosted C environment-এ program execution কোন function থেকে শুরু হয়?

A) `start()`
B) `init()`
C) `main()`
D) `execute()`

**সঠিক উত্তর: C) `main()`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `main()` hosted C program-এর standard entry function। Environment program চালু করলে control `main()`-এ দেয়।
- **A option কেন ভুল:** `start()` standard C entry function নয়।
- **B option কেন ভুল:** `init()` user-defined helper হতে পারে, entry point নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `execute()` নামে standard entry function নেই।
- **Related Concept:** `main()` সাধারণত `int main(void)` বা `int main(int argc, char *argv[])` form-এ লেখা হয়।
- **মনে রাখার টিপস:** C program শুরু হয় `main()` থেকে।


## প্রশ্ন 2 | Topic: Structured Programming > Tokens | Difficulty: Easy | Type: Theory

Q. C program-এর ক্ষুদ্রতম অর্থপূর্ণ lexical unit কোনটি?

A) Token
B) Module
C) Package
D) Procedure

**সঠিক উত্তর: A) Token**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Keyword, identifier, literal, operator ও punctuator—সবই token।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Module একটি বড় organizational unit।
- **C option কেন ভুল:** Package standard C lexical unit নয়।
- **D option কেন ভুল:** Procedure function/routine বোঝায়, lexical unit নয়।
- **Related Concept:** `int x = 5;`-এ `int`, `x`, `=`, `5`, `;` পৃথক token।
- **মনে রাখার টিপস:** Whitespace separator; semicolon-ও token।


## প্রশ্ন 3 | Topic: Structured Programming > Identifier | Difficulty: Easy | Type: Theory

Q. নিচের কোনটি valid C identifier?

A) `2ndValue`
B) `total_marks2`
C) `total-marks`
D) `float`

**সঠিক উত্তর: B) `total_marks2`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `total_marks2` letter দিয়ে শুরু হয়েছে এবং শুধু valid character ব্যবহার করেছে।
- **A option কেন ভুল:** Identifier digit দিয়ে শুরু করা যায় না।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Hyphen `-` subtraction operator হিসেবে ধরা হয়।
- **D option কেন ভুল:** `float` reserved keyword।
- **Related Concept:** C identifier case-sensitive।
- **মনে রাখার টিপস:** প্রথম character letter/underscore; পরে letter/digit/underscore।


## প্রশ্ন 4 | Topic: Structured Programming > Operator Precedence | Difficulty: Medium | Type: Code

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

- **সঠিক উত্তর কেন:** `*`-এর precedence `+`-এর চেয়ে বেশি; তাই আগে `3*2`, পরে `5+6`।
- **A option কেন ভুল:** সব value ভুলভাবে multiply করা হয়েছে।
- **B option কেন ভুল:** সঠিক operation order অনুসরণ করা হয়নি।
- **C option কেন ভুল:** শুধু `x*2` ধরনের ভুল করা হয়েছে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Parentheses precedence override করতে পারে।
- **মনে রাখার টিপস:** Multiplication আগে, addition পরে।


## প্রশ্ন 5 | Topic: Structured Programming > Program Errors | Difficulty: Medium | Type: Scenario

Q. Program compile ও run করে, কিন্তু addition-এর বদলে subtraction ব্যবহারের কারণে ভুল result দেয়। এটি কোন error?

A) Syntax Error
B) Linker Error
C) Logical Error
D) Preprocessing Error

**সঠিক উত্তর: C) Logical Error**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Program validভাবে চলে, কিন্তু algorithmic logic ভুল হওয়ায় output ভুল—এটাই Logical Error।
- **A option কেন ভুল:** Syntax Error হলে source grammar invalid হয়।
- **B option কেন ভুল:** Linker Error external symbol resolution-এর সমস্যা।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Preprocessing Error directive processing-এর সমস্যা।
- **Related Concept:** Testing Logical Error প্রকাশ করে; debugging root cause খুঁজে।
- **মনে রাখার টিপস:** Runs but wrong output = Logical Error।


## প্রশ্ন 6 | Topic: Structured Programming > Keyword | Difficulty: Easy | Type: Theory

Q. নিচের কোনটি C keyword?

A) `return`
B) `calculate`
C) `display`
D) `number`

**সঠিক উত্তর: A) `return`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `return` reserved keyword; function থেকে control/value ফেরায়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** User-defined identifier হতে পারে।
- **C option কেন ভুল:** Standard keyword নয়।
- **D option কেন ভুল:** Standard keyword নয়।
- **Related Concept:** Keyword identifier হিসেবে ব্যবহার করা যায় না।
- **মনে রাখার টিপস:** Reserved word দেখলে variable name নয়।


## প্রশ্ন 7 | Topic: Structured Programming > Token Count | Difficulty: Medium | Type: Calculation

Q. `int sum = a + 5;` statement-এ মোট কতটি token?

A) 6
B) 7
C) 8
D) 5

**সঠিক উত্তর: B) 7**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Token List

```text
1. int
2. sum
3. =
4. a
5. +
6. 5
7. ;
```

#### Final Answer

```text
Total token = 7
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Keyword, identifier, operator, literal ও semicolon আলাদা token।
- **A option কেন ভুল:** Semicolon বাদ দেওয়া হয়েছে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Whitespace-কে token ধরা হয়েছে।
- **D option কেন ভুল:** Operator/punctuator বাদ পড়েছে।
- **Related Concept:** Whitespace সাধারণত token separator।
- **মনে রাখার টিপস:** Semicolon count করতে ভুলবেন না।


## প্রশ্ন 8 | Topic: Structured Programming > main Declaration | Difficulty: Medium | Type: Theory

Q. Standard hosted C program-এর valid `main()` declaration কোনটি?

A) `void main()`
B) `main()`
C) `float main(void)`
D) `int main(void)`

**সঠিক উত্তর: D) `int main(void)`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Hosted C implementation-এ standard form-এর return type `int`।
- **A option কেন ভুল:** `void main()` standard hosted form নয়।
- **B option কেন ভুল:** Modern C-তে implicit `int` বৈধ নয়।
- **C option কেন ভুল:** `float` standard return type নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Command-line form: `int main(int argc, char *argv[])`।
- **মনে রাখার টিপস:** Standard `main()` returns `int`।


## প্রশ্ন 9 | Topic: Structured Programming > String Storage | Difficulty: Hard | Type: Code

Q. নিচের code-এর output কী?

```c
#include <stdio.h>
#include <string.h>
int main(void){ char text[]="ICT"; printf("%zu %zu",sizeof(text),strlen(text)); }
```

A) `4 3`
B) `3 3`
C) `4 4`
D) `3 4`

**সঠিক উত্তর: A) `4 3`**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Memory Layout

```text
'I'  'C'  'T'  '\0'
sizeof(text) = 4
strlen(text) = 3
```

#### Final Answer

```text
Output = 4 3
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `sizeof` null terminator-সহ array storage দেয়; `strlen` null terminator বাদ দিয়ে visible character count করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Null terminator-এর storage বাদ গেছে।
- **C option কেন ভুল:** `strlen()` null byte count করে না।
- **D option কেন ভুল:** দুটি value উল্টো।
- **Related Concept:** C string storage = visible characters + `\0`।
- **মনে রাখার টিপস:** Length ও array size এক নয়।


## প্রশ্ন 10 | Topic: Structured Programming > Undefined Behavior | Difficulty: Hard | Type: Theory

Q. একই full expression-এ scalar variable-কে unsequencedভাবে একাধিকবার modify করলে সাধারণত কী হতে পারে?

A) সবসময় Compilation Error
B) সবসময় Zero Result
C) Undefined Behavior
D) শুধু Linker Warning

**সঠিক উত্তর: C) Undefined Behavior**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** যেমন `i = i++ + ++i;`-তে side effect-গুলোর ordering নির্ধারিত নয়; Standard outcome guarantee করে না।
- **A option কেন ভুল:** Compiler diagnostic দিতে পারে, কিন্তু compilation বন্ধ করতে বাধ্য নয়।
- **B option কেন ভুল:** নির্দিষ্ট result নেই।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এটি linking-এর বিষয় নয়।
- **Related Concept:** Undefined Behavior-কে implementation-dependent fixed result হিসেবে ধরা যাবে না।
- **মনে রাখার টিপস:** এক expression-এ একই variable-এর multiple side effect এড়ান।


## প্রশ্ন 11 | Topic: Structured Programming > Preprocessor | Difficulty: Easy | Type: Theory

Q. `#include` ও `#define` কোন translation stage-এ process হয়?

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
- **D option কেন ভুল:** Execution program চালায়।
- **Related Concept:** Macro expansion ও conditional compilation-ও preprocessing।
- **মনে রাখার টিপস:** `#` দেখলে Preprocessor।


## প্রশ্ন 12 | Topic: Structured Programming > Linker | Difficulty: Easy | Type: Theory

Q. `printf()`-এর externally defined implementation-এর reference প্রধানত কে resolve করে?

A) Editor
B) Preprocessor
C) Debugger
D) Linker

**সঠিক উত্তর: D) Linker**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Linker library/object file থেকে external symbol-এর definition খুঁজে reference resolve করে।
- **A option কেন ভুল:** Editor code লেখার tool।
- **B option কেন ভুল:** Preprocessor declaration include করে, link নয়।
- **C option কেন ভুল:** Debugger runtime behavior পরীক্ষা করে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Header declaration দেয়; library implementation দেয়।
- **মনে রাখার টিপস:** External symbol resolve = Linker।


## প্রশ্ন 13 | Topic: Structured Programming > Object File | Difficulty: Medium | Type: Theory

Q. Object file সম্পর্কে কোন statement সঠিক?

A) Machine code-এর সঙ্গে symbol ও relocation information থাকতে পারে
B) শুধু source code থাকে
C) সবসময় সরাসরি executable
D) শুধু preprocessor directive থাকে

**সঠিক উত্তর: A) Machine code-এর সঙ্গে symbol ও relocation information থাকতে পারে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Object file final linking-এর জন্য machine instructions, symbol table ও relocation data ধারণ করতে পারে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Source file আলাদা থাকে।
- **C option কেন ভুল:** Unresolved external reference থাকতে পারে।
- **D option কেন ভুল:** Directive preprocessing-এ process হয়ে যায়।
- **Related Concept:** একাধিক object file link করে executable হয়।
- **মনে রাখার টিপস:** Object file প্রায় machine code, final executable নয়।


## প্রশ্ন 14 | Topic: Structured Programming > Macro Expansion | Difficulty: Medium | Type: Code

Q. নিচের code-এর output কী?

```c
#include <stdio.h>
#define SQR(x) ((x)*(x))
int main(void){ printf("%d",SQR(5)); }
```

A) 5
B) 10
C) 25
D) 50

**সঠিক উত্তর: C) 25**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Expansion

```text
SQR(5)
→ ((5) × (5))
→ 25
```

#### Final Answer

```text
Output = 25
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `SQR(5)` textual expansion হয়ে `((5)*(5))` হয়।
- **A option কেন ভুল:** Macro operation প্রয়োগ করা হয়নি।
- **B option কেন ভুল:** Addition ধরা হয়েছে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** ভুল multiplication।
- **Related Concept:** Macro parameter ও body parentheses-এ রাখা precedence bug কমায়।
- **মনে রাখার টিপস:** Macro textual substitution।


## প্রশ্ন 15 | Topic: Structured Programming > Include Guard | Difficulty: Medium | Type: Theory

Q. Header file-এ include guard-এর প্রধান উদ্দেশ্য কী?

A) Header encrypt করা
B) Repeated inclusion-এর সমস্যা প্রতিরোধ
C) Runtime speed বাড়ানো
D) `main()` declare করা

**সঠিক উত্তর: B) Repeated inclusion-এর সমস্যা প্রতিরোধ**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একই declaration/definition বারবার process হওয়া ঠেকাতে `#ifndef/#define/#endif` ব্যবহার হয়।
- **A option কেন ভুল:** Encryption নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** মূল উদ্দেশ্য runtime optimization নয়।
- **D option কেন ভুল:** `main()`-এর সঙ্গে সম্পর্ক নেই।
- **Related Concept:** `#pragma once` implementation-specific alternative হতে পারে।
- **মনে রাখার টিপস:** Header logically once।


## প্রশ্ন 16 | Topic: Structured Programming > Macro Precedence | Difficulty: Medium | Type: Code

Q. নিচের code-এর output কী?

```c
#include <stdio.h>
#define ADD(a,b) a+b
int main(void){ printf("%d",2*ADD(3,4)); }
```

A) 14
B) 24
C) 18
D) 10

**সঠিক উত্তর: D) 10**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Expansion

```text
2 * ADD(3,4)
→ 2 * 3 + 4
→ 6 + 4
→ 10
```

#### Final Answer

```text
Output = 10
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Expansion হয় `2*3+4`; multiplication আগে, তাই 6+4=10।
- **A option কেন ভুল:** `2*(3+4)` ধরে নেওয়া হয়েছে, কিন্তু macro body parenthesized নয়।
- **B option কেন ভুল:** সব operand multiply করা হয়েছে।
- **C option কেন ভুল:** ভুল expansion।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** নিরাপদ macro: `#define ADD(a,b) ((a)+(b))`।
- **মনে রাখার টিপস:** Expansion লিখে তারপর precedence প্রয়োগ করুন।


## প্রশ্ন 17 | Topic: Structured Programming > Static Linking | Difficulty: Hard | Type: Theory

Q. Static Linking সম্পর্কে কোন statement সঠিক?

A) প্রয়োজনীয় library object code executable-এ যুক্ত হয়
B) Library শুধু network থেকে runtime-এ আসে
C) Executable-এ কোনো library code থাকে না
D) Preprocessor static linking করে

**সঠিক উত্তর: A) প্রয়োজনীয় library object code executable-এ যুক্ত হয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Static linker প্রয়োজনীয় library module executable image-এর অংশ করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এটি static linking-এর সংজ্ঞা নয়।
- **C option কেন ভুল:** Selected library code থাকতে পারে।
- **D option কেন ভুল:** Linker কাজটি করে।
- **Related Concept:** Dynamic linking shared library runtime/load time-এ resolve করতে পারে।
- **মনে রাখার টিপস:** Static = executable-এর সঙ্গে code বাঁধা।


## প্রশ্ন 18 | Topic: Structured Programming > Standard Header | Difficulty: Easy | Type: Theory

Q. `printf()` declaration কোন header-এ?

A) `<stdlib.h>`
B) `<string.h>`
C) `<stdio.h>`
D) `<math.h>`

**সঠিক উত্তর: C) `<stdio.h>`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Formatted standard I/O function-গুলো `<stdio.h>`-এ declared।
- **A option কেন ভুল:** Utility ও allocation function।
- **B option কেন ভুল:** String function।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Mathematical function।
- **Related Concept:** `scanf`, `fopen`, `fclose`-ও `<stdio.h>`।
- **মনে রাখার টিপস:** Standard I/O → stdio.h।


## প্রশ্ন 19 | Topic: Structured Programming > Separate Compilation | Difficulty: Medium | Type: Code

Q. `gcc -c source.c` command সাধারণত কী তৈরি করে?

A) Program run করে
B) Object file তৈরি করে
C) শুধু preprocessed text
D) Source delete করে

**সঠিক উত্তর: B) Object file তৈরি করে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `-c` compile/assemble করে object file বানায়, linking করে না।
- **A option কেন ভুল:** Execution করে না।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Preprocess-only সাধারণত `-E`।
- **D option কেন ভুল:** Source অক্ষত থাকে।
- **Related Concept:** সাধারণ output `source.o`।
- **মনে রাখার টিপস:** `-c` = compile, no link।


## প্রশ্ন 20 | Topic: Structured Programming > Multiple Definition | Difficulty: Hard | Type: Scenario

Q. Ordinary non-`static` function-এর পূর্ণ definition একটি header-এ রেখে header-টি দুই source file-এ include করলে কী হতে পারে?

A) Runtime warning মাত্র
B) Header encrypted হবে
C) Function দুইবার run করবে
D) Linker multiple-definition error

**সঠিক উত্তর: D) Linker multiple-definition error**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি translation unit একই external function definition দিলে duplicate symbol তৈরি হয়।
- **A option কেন ভুল:** মূলত runtime সমস্যা নয়।
- **B option কেন ভুল:** Encryption হয় না।
- **C option কেন ভুল:** Definition count execution count নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Header-এ prototype; ordinary definition `.c` file-এ রাখা প্রচলিত।
- **মনে রাখার টিপস:** One external definition rule মানুন।


## প্রশ্ন 21 | Topic: Structured Programming > sizeof(char) | Difficulty: Easy | Type: Theory

Q. C Standard অনুযায়ী `sizeof(char)` কত?

A) 1
B) 2
C) 4
D) সবসময় implementation-dependent

**সঠিক উত্তর: A) 1**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** C byte-এর সংজ্ঞা `char`-এর size দিয়ে; তাই `sizeof(char)` সর্বদা 1।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** 2 byte বাধ্যতামূলক নয়।
- **C option কেন ভুল:** 4 common `int` size হতে পারে।
- **D option কেন ভুল:** Byte-এর bit count ভিন্ন হতে পারে, size result নয়।
- **Related Concept:** `CHAR_BIT` এক byte-এর bit সংখ্যা দেয়।
- **মনে রাখার টিপস:** `sizeof(char) == 1` সবসময়।


## প্রশ্ন 22 | Topic: Structured Programming > Unsigned Range | Difficulty: Medium | Type: Theory

Q. N-bit unsigned integer-এর range কোনটি?

A) −2^N থেকে 2^N−1
B) 0 থেকে 2^N−1
C) −2^(N−1) থেকে 2^(N−1)
D) 1 থেকে 2^N

**সঠিক উত্তর: B) 0 থেকে 2^N−1**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** N bit-এর 2^N pattern 0 থেকে 2^N−1 value প্রকাশ করে।
- **A option কেন ভুল:** Range অসম্ভব বড়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Signed range-এর কাছাকাছি।
- **D option কেন ভুল:** Zero বাদ এবং maximum ভুল।
- **Related Concept:** 8-bit unsigned range 0–255।
- **মনে রাখার টিপস:** Unsigned minimum zero।


## প্রশ্ন 23 | Topic: Structured Programming > Cast Placement | Difficulty: Medium | Type: Calculation

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

- **সঠিক উত্তর কেন:** Inner parentheses আগে evaluate হয়; `5/2` integer division-এ 2, পরে double cast হয়ে 2.0।
- **A option কেন ভুল:** `(double)5/2` হলে 2.5।
- **B option কেন ভুল:** Integer division round up করে না।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Expression থেকে আসে না।
- **Related Concept:** Cast-এর অবস্থান result বদলায়।
- **মনে রাখার টিপস:** Parentheses-এর ভেতর আগে।


## প্রশ্ন 24 | Topic: Structured Programming > Negative Integer Division | Difficulty: Easy | Type: Theory

Q. Modern C-তে `-17/5`-এর result কী?

A) −4
B) 4
C) −3.4
D) −3

**সঠিক উত্তর: D) −3**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Integer division fractional অংশ zero-এর দিকে truncate করে; −3.4 → −3।
- **A option কেন ভুল:** এটি floor division হলে হতো।
- **B option কেন ভুল:** Sign বাদ দেওয়া হয়েছে।
- **C option কেন ভুল:** Integer operands floating result দেয় না।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `-17 % 5` সাধারণত −2, যাতে quotient-remainder identity বজায় থাকে।
- **মনে রাখার টিপস:** Truncate toward zero।


## প্রশ্ন 25 | Topic: Structured Programming > Unsigned Wraparound | Difficulty: Medium | Type: Calculation

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

- **সঠিক উত্তর কেন:** Unsigned arithmetic modulo 2^8 = 256 অনুযায়ী wrap করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** 260 representable নয়।
- **C option কেন ভুল:** Modulo ভুল।
- **D option কেন ভুল:** Unsigned saturation করে না।
- **Related Concept:** Unsigned overflow defined; signed overflow undefined।
- **মনে রাখার টিপস:** N-bit unsigned → modulo 2^N।


## প্রশ্ন 26 | Topic: Structured Programming > Floating Types | Difficulty: Medium | Type: Theory

Q. নিচের কোন statement সাধারণভাবে সঠিক?

A) `float` সবসময় বেশি precision
B) `double` সাধারণত `float`-এর চেয়ে বেশি precision
C) `float` শুধু integer রাখে
D) `double` arithmetic হয় না

**সঠিক উত্তর: B) `double` সাধারণত `float`-এর চেয়ে বেশি precision**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `double`-এর minimum precision requirement বেশি এবং common implementation-এ অধিক significant digit রাখে।
- **A option কেন ভুল:** উল্টো।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `float` floating-point value রাখে।
- **D option কেন ভুল:** `double` arithmetic বৈধ।
- **Related Concept:** `1.0` double literal; `1.0f` float।
- **মনে রাখার টিপস:** Suffix `f` না থাকলে floating literal সাধারণত double।


## প্রশ্ন 27 | Topic: Structured Programming > Signed-Unsigned Comparison | Difficulty: Hard | Type: Theory

Q. `int x=-1; unsigned int y=1U;` হলে `x<y` অনেক common case-এ false কেন?

A) Negative zero হয়
B) `y` signed হয়
C) `x` unsigned-এ convert হয়ে বড় value হয়
D) Comparison বাদ যায়

**সঠিক উত্তর: C) `x` unsigned-এ convert হয়ে বড় value হয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Usual arithmetic conversion-এ −1 unsigned representation-এ `UINT_MAX`-সদৃশ বড় value হয়।
- **A option কেন ভুল:** Negative zero হয় না।
- **B option কেন ভুল:** সাধারণ সমান-rank case-এ signed operand unsigned হয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Comparison evaluate হয়।
- **Related Concept:** Signed ও unsigned mix subtle bug তৈরি করে।
- **মনে রাখার টিপস:** Comparison-এর আগে conversion ভাবুন।


## প্রশ্ন 28 | Topic: Structured Programming > Arithmetic Conversion | Difficulty: Hard | Type: Code

Q. `1.0f + 1.0` expression-এর result type কী?

A) `int`
B) `float`
C) `long double`
D) `double`

**সঠিক উত্তর: D) `double`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `1.0f` float ও `1.0` double; usual conversion-এ float double হয়।
- **A option কেন ভুল:** Floating operands integer result দেয় না।
- **B option কেন ভুল:** Wider operand double।
- **C option কেন ভুল:** Long double operand নেই।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `1.0L` long double literal।
- **মনে রাখার টিপস:** Mixed floating arithmetic-এ wider type জয়ী।


## প্রশ্ন 29 | Topic: Structured Programming > enum | Difficulty: Medium | Type: Theory

Q. C-তে `enum` প্রধানত কী প্রকাশ করে?

A) Named integer constant-এর set
B) Dynamic memory block
C) Floating array
D) File descriptor

**সঠিক উত্তর: A) Named integer constant-এর set**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `enum` readable symbolic integer constants define করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Dynamic allocation `malloc`।
- **C option কেন ভুল:** Floating array নয়।
- **D option কেন ভুল:** OS resource identifier নয়।
- **Related Concept:** `enum Day {SUN,MON,TUE};`।
- **মনে রাখার টিপস:** Enum = named choices।


## প্রশ্ন 30 | Topic: Structured Programming > _Bool | Difficulty: Hard | Type: Theory

Q. `_Bool flag=25;` হলে stored value কী?

A) 25
B) 1
C) 0
D) Undefined

**সঠিক উত্তর: B) 1**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `_Bool`-এ zero → 0, যেকোনো nonzero → 1।
- **A option কেন ভুল:** Magnitude সংরক্ষণ করে না।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Input zero নয়।
- **D option কেন ভুল:** Conversion defined।
- **Related Concept:** `<stdbool.h>`-এর `bool` `_Bool`-ভিত্তিক।
- **মনে রাখার টিপস:** Nonzero becomes 1।


## প্রশ্ন 31 | Topic: Structured Programming > Operator Precedence | Difficulty: Easy | Type: Theory

Q. কোন operator-এর precedence `+`-এর চেয়ে বেশি?

A) `=`
B) `||`
C) `*`
D) `?:`

**সঠিক উত্তর: C) `*`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Multiplicative operators additive operators-এর আগে group হয়।
- **A option কেন ভুল:** Assignment precedence কম।
- **B option কেন ভুল:** Logical OR কম।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Conditional কম।
- **Related Concept:** Parentheses grouping control করে।
- **মনে রাখার টিপস:** Multiply আগে।


## প্রশ্ন 32 | Topic: Structured Programming > Arithmetic Precedence | Difficulty: Medium | Type: Calculation

Q. `2+3*4`-এর value কত?

A) 20
B) 24
C) 11
D) 14

**সঠিক উত্তর: D) 14**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Calculation

```text
3 × 4 = 12
2 + 12 = 14
```

#### Final Answer

```text
Result = 14
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Multiplication আগে হয়।
- **A option কেন ভুল:** `(2+3)*4` ধরা হয়েছে।
- **B option কেন ভুল:** সব multiply করা হয়েছে।
- **C option কেন ভুল:** Arithmetic ভুল।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Parentheses দিলে order বদলায়।
- **মনে রাখার টিপস:** Precedence লিখে solve করুন।


## প্রশ্ন 33 | Topic: Structured Programming > Short-Circuit | Difficulty: Easy | Type: Theory

Q. `x!=0 && 10/x>1`-এ `x==0` হলে division execute হয় না কেন?

A) `&&` short-circuit করে
B) Compiler সব division বাদ দেয়
C) Integer division নিষিদ্ধ
D) x স্বয়ংক্রিয়ভাবে 1

**সঠিক উত্তর: A) `&&` short-circuit করে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** বাম operand false হলে AND result false নিশ্চিত; ডান operand evaluate হয় না।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** সব division বাদ যায় না।
- **C option কেন ভুল:** Integer division বৈধ।
- **D option কেন ভুল:** x পরিবর্তিত হয় না।
- **Related Concept:** `||`-এ বাম true হলে ডান evaluate হয় না।
- **মনে রাখার টিপস:** Safety check বাম পাশে।


## প্রশ্ন 34 | Topic: Structured Programming > Bitwise AND | Difficulty: Medium | Type: Calculation

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
- **Related Concept:** AND mask দিয়ে bit test/clear করা যায়।
- **মনে রাখার টিপস:** AND-এ দুটোই 1।


## প্রশ্ন 35 | Topic: Structured Programming > Assignment Associativity | Difficulty: Medium | Type: Theory

Q. Assignment operator-এর associativity কী?

A) Left-to-right
B) নেই
C) Right-to-left
D) Operand type-নির্ভর

**সঠিক উত্তর: C) Right-to-left**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `a=b=5` group হয় `a=(b=5)`।
- **A option কেন ভুল:** `(a=b)=5` valid grouping নয়।
- **B option কেন ভুল:** Defined associativity আছে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Type অনুযায়ী বদলায় না।
- **Related Concept:** Precedence ও associativity ভিন্ন ধারণা।
- **মনে রাখার টিপস:** Assignment chain ডান থেকে।


## প্রশ্ন 36 | Topic: Structured Programming > sizeof | Difficulty: Medium | Type: Theory

Q. Non-VLA operand-এর ক্ষেত্রে `sizeof(x++)` সাধারণত x increment করে না কেন?

A) `++` নিষিদ্ধ
B) `sizeof` zero দেয়
C) x constant হয়
D) Operand value evaluate হয় না

**সঠিক উত্তর: D) Operand value evaluate হয় না**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Compile-time type/size থেকে result নির্ণীত হয়; expression side effect execute হয় না।
- **A option কেন ভুল:** Increment বৈধ।
- **B option কেন ভুল:** Object size দেয়।
- **C option কেন ভুল:** x const হয় না।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** VLA ক্ষেত্রে evaluation rule ব্যতিক্রম হতে পারে।
- **মনে রাখার টিপস:** সাধারণ sizeof expression চালায় না।


## প্রশ্ন 37 | Topic: Structured Programming > Unsequenced Modification | Difficulty: Hard | Type: Code

Q. `int x=2; printf("%d",x+++ ++x);`-জাতীয় একই full expression-এ multiple unsequenced modification-এর behavior কী?

A) Undefined Behavior
B) সবসময় 6
C) সবসময় 5
D) Compilation বাধ্যতামূলকভাবে ব্যর্থ

**সঠিক উত্তর: A) Undefined Behavior**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একই scalar object-এর side effect-গুলোর relative order নির্ধারিত না থাকলে behavior undefined।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Fixed output guarantee নেই।
- **C option কেন ভুল:** Fixed output guarantee নেই।
- **D option কেন ভুল:** Compiler reject করতে বাধ্য নয়।
- **Related Concept:** Warning outcome নির্ধারণ করে না।
- **মনে রাখার টিপস:** Multiple side effect আলাদা statement-এ করুন।


## প্রশ্ন 38 | Topic: Structured Programming > Conditional Operator | Difficulty: Medium | Type: Theory

Q. `?:` conditional operator-এর associativity কী?

A) Left-to-right
B) Right-to-left
C) নেই
D) শুধু integer-এ

**সঠিক উত্তর: B) Right-to-left**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Nested conditional expression right-to-left group হয়।
- **A option কেন ভুল:** সঠিক নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Defined associativity আছে।
- **D option কেন ভুল:** Compatible বিভিন্ন type-এ ব্যবহার হয়।
- **Related Concept:** `a?b:c?d:e` → `a?b:(c?d:e)`।
- **মনে রাখার টিপস:** Conditional ও assignment right-associative।


## প্রশ্ন 39 | Topic: Structured Programming > Signed Right Shift | Difficulty: Hard | Type: Theory

Q. Negative signed integer right shift-এর result সম্পর্কে কোনটি সঠিক?

A) সবসময় Logical Shift
B) সবসময় zero
C) Implementation-defined হতে পারে
D) Syntax Error

**সঠিক উত্তর: C) Implementation-defined হতে পারে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Negative signed value-এর right shift implementation-এর documented choice হতে পারে।
- **A option কেন ভুল:** সব implementation-এ zero-fill নয়।
- **B option কেন ভুল:** সবসময় zero নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Syntax বৈধ।
- **Related Concept:** Unsigned right shift zero-fill behavior দেয়।
- **মনে রাখার টিপস:** Predictable bit operation-এর জন্য unsigned ব্যবহার করুন।


## প্রশ্ন 40 | Topic: Structured Programming > Comma Operator | Difficulty: Medium | Type: Theory

Q. `(1,2,3)` expression-এর value কত?

A) 1
B) 2
C) 6
D) 3

**সঠিক উত্তর: D) 3**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Comma operator বাম থেকে ডানে evaluate করে শেষ expression-এর value দেয়।
- **A option কেন ভুল:** প্রথম value final নয়।
- **B option কেন ভুল:** দ্বিতীয় final নয়।
- **C option কেন ভুল:** Values যোগ হয় না।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Function argument separator সবসময় comma operator নয়।
- **মনে রাখার টিপস:** Comma expression-এর value শেষ operand।


## প্রশ্ন 41 | Topic: Structured Programming > if Condition | Difficulty: Easy | Type: Theory

Q. C condition-এ কোন value true?

A) যেকোনো nonzero
B) শুধু 1
C) শুধু positive
D) শুধু −1

**সঠিক উত্তর: A) যেকোনো nonzero**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** C-তে zero false; যেকোনো nonzero scalar value true।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** True 1-এ সীমাবদ্ধ নয়।
- **C option কেন ভুল:** Negative nonzero-ও true।
- **D option কেন ভুল:** শুধু −1 নয়।
- **Related Concept:** Relational expression সাধারণত 0 বা 1 produce করে।
- **মনে রাখার টিপস:** Zero false, nonzero true।


## প্রশ্ন 42 | Topic: Structured Programming > Loop Count | Difficulty: Medium | Type: Calculation

Q. `for(int i=2;i<10;i+=2)` loop body কতবার execute হয়?

A) 3
B) 4
C) 5
D) 8

**সঠিক উত্তর: B) 4**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Trace

```text
i=2  → 1st
 i=4  → 2nd
 i=6  → 3rd
 i=8  → 4th
 i=10 → condition false
```

#### Final Answer

```text
Total iterations = 4
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** i-এর valid values 2,4,6,8—চারটি।
- **A option কেন ভুল:** একটি iteration বাদ।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** i=10 ভুলভাবে count।
- **D option কেন ভুল:** Increment 1 ধরা।
- **Related Concept:** Arithmetic progression দিয়ে loop count নির্ণয় করা যায়।
- **মনে রাখার টিপস:** Actual i values লিখুন।


## প্রশ্ন 43 | Topic: Structured Programming > switch | Difficulty: Easy | Type: Theory

Q. `switch` controlling expression কোন type-এর হতে হয়?

A) শুধু float
B) শুধু pointer
C) Integer বা enumeration
D) শুধু structure

**সঠিক উত্তর: C) Integer বা enumeration**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Switch expression integer promotions-এর উপযোগী integral/enum type হয়।
- **A option কেন ভুল:** Floating type সরাসরি allowed নয়।
- **B option কেন ভুল:** Pointer নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Structure নয়।
- **Related Concept:** `case` label integer constant expression।
- **মনে রাখার টিপস:** Switch = discrete integral choice।


## প্রশ্ন 44 | Topic: Structured Programming > do-while | Difficulty: Medium | Type: Theory

Q. `do-while` loop-এর প্রধান বৈশিষ্ট্য কী?

A) Condition পরীক্ষা হয় না
B) Infinite হওয়া বাধ্যতামূলক
C) Body শুধু false হলে চলে
D) Body অন্তত একবার চলে

**সঠিক উত্তর: D) Body অন্তত একবার চলে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Condition body-এর পরে পরীক্ষা হয়।
- **A option কেন ভুল:** প্রতি iteration শেষে condition পরীক্ষা হয়।
- **B option কেন ভুল:** False হলে শেষ হয়।
- **C option কেন ভুল:** প্রথমবার condition-এর আগেই body চলে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `while` entry-controlled; `do-while` exit-controlled।
- **মনে রাখার টিপস:** Do first, check later।


## প্রশ্ন 45 | Topic: Structured Programming > Dangling else | Difficulty: Hard | Type: Theory

Q. Braces না থাকলে `else` সাধারণত কোন `if`-এর সঙ্গে bind করে?

A) Nearest unmatched `if`
B) প্রথম `if`
C) সব `if`
D) কোনোটির নয়

**সঠিক উত্তর: A) Nearest unmatched `if`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** C grammar অনুযায়ী `else` closest unmatched `if`-এর অংশ হয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** সবসময় outer/first নয়।
- **C option কেন ভুল:** একটি else একটি if-এর সঙ্গে bind করে।
- **D option কেন ভুল:** Defined matching rule আছে।
- **Related Concept:** Braces ambiguity দূর করে।
- **মনে রাখার টিপস:** Else nearest unmatched if।


## প্রশ্ন 46 | Topic: Structured Programming > continue | Difficulty: Medium | Type: Code

Q. নিচের code-এর output কী?

```c
int count=0;
for(int i=1;i<=5;i++){
  if(i==3) continue;
  count++;
}
printf("%d",count);
```

A) 3
B) 4
C) 5
D) 2

**সঠিক উত্তর: B) 4**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Trace

```text
i=1 → count=1
i=2 → count=2
i=3 → continue, count=2
i=4 → count=3
i=5 → count=4
```

#### Final Answer

```text
Output = 4
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** i=3 iteration-এ `count++` skip; অন্য চার iteration count হয়।
- **A option কেন ভুল:** দুই iteration skip ধরা।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** continue উপেক্ষা।
- **D option কেন ভুল:** অতিরিক্ত skip।
- **Related Concept:** `continue` loop শেষ করে না; current iteration remainder skip করে।
- **মনে রাখার টিপস:** Continue = skip this round।


## প্রশ্ন 47 | Topic: Structured Programming > goto | Difficulty: Medium | Type: Scenario

Q. `goto` সম্পর্কে কোন statement সঠিক?

A) সব function-এর মধ্যে jump করে
B) Variable copy করে
C) একই function-এর labeled statement-এ control দেয়
D) Compile বন্ধ করে

**সঠিক উত্তর: C) একই function-এর labeled statement-এ control দেয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** C `goto` target label একই function body-এর মধ্যে থাকতে হয়।
- **A option কেন ভুল:** Function boundary পার হতে পারে না।
- **B option কেন ভুল:** Assignment নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Valid goto compile হতে পারে।
- **Related Concept:** Excessive goto readability কমায়।
- **মনে রাখার টিপস:** Goto target same function।


## প্রশ্ন 48 | Topic: Structured Programming > switch Fall-through | Difficulty: Medium | Type: Theory

Q. `case` শেষে `break` না থাকলে সাধারণত কী হয়?

A) Program terminate
B) পরবর্তী case বাদ
C) main-এ return
D) পরবর্তী case-এ fall-through

**সঠিক উত্তর: D) পরবর্তী case-এ fall-through**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Control break বা switch end না পাওয়া পর্যন্ত পরবর্তী statement execute করতে পারে।
- **A option কেন ভুল:** Terminate হয় না।
- **B option কেন ভুল:** Compiler বাদ দেয় না।
- **C option কেন ভুল:** Function return নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Intentional fall-through কিছু design-এ ব্যবহৃত।
- **মনে রাখার টিপস:** Break না থাকলে নিচে নামে।


## প্রশ্ন 49 | Topic: Structured Programming > Nested Loop Count | Difficulty: Hard | Type: Calculation

Q. নিচের nested loop-এ inner statement মোট কতবার execute হয়?

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
- **মনে রাখার টিপস:** 1 থেকে n sum formula মনে রাখুন।


## প্রশ্ন 50 | Topic: Structured Programming > continue in Nested Loop | Difficulty: Hard | Type: Scenario

Q. Nested loop-এর inner loop-এ `continue` execute হলে কী হয়?

A) Outer loop শেষ
B) Inner loop-এর current iteration remainder skip
C) Program terminate
D) সব loop reset

**সঠিক উত্তর: B) Inner loop-এর current iteration remainder skip**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `continue` nearest enclosing loop-এর পরবর্তী iteration-এ control দেয়।
- **A option কেন ভুল:** Outer loop শেষ হয় না।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Termination নয়।
- **D option কেন ভুল:** Loop reset হয় না।
- **Related Concept:** `break` nearest loop থেকে বের হয়; `continue` next iteration।
- **মনে রাখার টিপস:** Nearest loop-কে প্রভাবিত করে।


## Batch 01 Quality Summary

```text
Questions          = 50
Theory/Scenario    = 35
Calculation/Code   = 15
Coverage           = C fundamentals, translation, types, operators, control flow
Math format        = Plain-text aligned
```

---

# Batch 02 — Question 051–100

**Section:** Structured & Object-Oriented Programming  
**Coverage:** Arrays, Strings, Pointers, Functions, Storage Classes ও Recursion  
**Composition:** Theory/Scenario 35, Calculation/Code 15


# Chapter Theory 02: Arrays, Strings, Pointers ও Functions

## Arrays

Array একই type-এর একাধিক element contiguous memory-তে রাখে। Index zero থেকে শুরু হয়। One-dimensional array-এর address:

```text
Address(A[i]) = Base + i × ElementSize
```

C multidimensional array row-major order-এ সংরক্ষণ করে:

```text
Address(A[i][j]) =
Base + ((i × NumberOfColumns) + j) × ElementSize
```

Partial initialization-এ অবশিষ্ট element zero হয়। Array boundary-এর বাইরে access Undefined Behavior।

## Strings

C string হলো null-terminated `char` array। `"ICT"` memory-তে `I`, `C`, `T`, `\0`—চার byte নেয়। `strlen()` visible character count করে; `sizeof(array)` পুরো array storage দেয়।

Common functions:

- `strlen` — length
- `strcpy/strncpy` — copy
- `strcat` — concatenate
- `strcmp` — lexicographical compare
- `memmove` — overlapping memory-safe copy

String literal modify করা Undefined Behavior।

## Pointers

Pointer address ধারণ করে। `&x` address নেয় এবং `*p` dereference করে value access করে। Pointer arithmetic pointed type-এর unit অনুযায়ী scale হয়:

```text
p + 1 = next element, not necessarily next byte
```

বিশেষ pointer:

- NULL Pointer
- Wild Pointer
- Dangling Pointer
- Void Pointer
- Pointer to Pointer
- Function Pointer

`p[i]` ও `*(p+i)` সমতুল্য।

## Functions ও Parameter Passing

C সব argument call by value-তে পাঠায়। Pointer value পাঠিয়ে caller-এর object modify করা যায়, কিন্তু mechanism এখনও call by value। Function prototype argument ও return type compile-time check করতে সাহায্য করে।

## Storage Class ও Recursion

- `auto` — ordinary block local
- `register` — fast access-এর request; address নেওয়া যায় না
- `static` local — program lifetime, block scope
- `static` file-scope — internal linkage
- `extern` — অন্যত্র defined entity declare

Recursive function-এ Base Case, Recursive Case এবং Base Case-এর দিকে progress প্রয়োজন। Tower of Hanoi minimum moves:

```text
Moves = 2^n - 1
```


## প্রশ্ন 51 | Topic: Structured Programming > Array Indexing | Difficulty: Easy | Type: Theory

Q. `int data[10];`-এর সর্বশেষ valid index কোনটি?

A) 10
B) 9
C) 11
D) 8

**সঠিক উত্তর: B) 9**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 10টি element-এর index 0 থেকে 9।
- **A option কেন ভুল:** Index 10 out of bounds।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Array size-এর চেয়েও বেশি।
- **D option কেন ভুল:** Valid, কিন্তু শেষ নয়।
- **Related Concept:** Last index = length−1।
- **মনে রাখার টিপস:** 10 elements → 0–9।


## প্রশ্ন 52 | Topic: Structured Programming > Array Size | Difficulty: Medium | Type: Calculation

Q. `sizeof(int)=4` byte হলে `int values[6];`-এর total size কত?

A) 6 byte
B) 10 byte
C) 20 byte
D) 24 byte

**সঠিক উত্তর: D) 24 byte**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Given Data

```text
Element count = 6
Size of int = 4 byte
```

#### Calculation

```text
Total = 6 × 4
      = 24 byte
```

#### Final Answer

```text
Array size = 24 byte
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Array size = element count × element size।
- **A option কেন ভুল:** শুধু element count।
- **B option কেন ভুল:** Addition করা হয়েছে।
- **C option কেন ভুল:** 5 element ধরে হিসাব।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `sizeof(values)` 24 হবে।
- **মনে রাখার টিপস:** Count × size।


## প্রশ্ন 53 | Topic: Structured Programming > 2D Array Address | Difficulty: Hard | Type: Calculation

Q. `int A[3][4]` row-major, base address 1000, `sizeof(int)=4` হলে `A[2][1]`-এর address কত?

A) 1036
B) 1024
C) 1040
D) 1032

**সঠিক উত্তর: A) 1036**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Formula

```text
Address = Base + ((i × Columns) + j) × w
```

#### Substitution

```text
= 1000 + ((2 × 4) + 1) × 4
```

#### Calculation

```text
Element offset = 8 + 1 = 9
Byte offset = 9 × 4 = 36
Address = 1000 + 36 = 1036
```

#### Final Answer

```text
Address(A[2][1]) = 1036
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Row-major offset = (row×columns+column)×size।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Column offset অসম্পূর্ণ।
- **C option কেন ভুল:** একটি extra element count।
- **D option কেন ভুল:** j offset ভুল।
- **Related Concept:** C array row-major।
- **মনে রাখার টিপস:** আগে element offset, পরে byte offset।


## প্রশ্ন 54 | Topic: Structured Programming > Array Decay | Difficulty: Hard | Type: Theory

Q. কোন context-এ array name সাধারণত first-element pointer-এ decay করে না?

A) Function argument
B) Pointer arithmetic
C) `sizeof` operand
D) Assignment right side

**সঠিক উত্তর: C) `sizeof` operand**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `sizeof(array)` পুরো array object-এর size নেয়; decay ঘটে না।
- **A option কেন ভুল:** Parameter-এ pointer-এ adjust হয়।
- **B option কেন ভুল:** Pointer arithmetic-এ decay হয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Most expression-এ decay হয়।
- **Related Concept:** Unary `&array`-তেও decay হয় না।
- **মনে রাখার টিপস:** Decay exception: sizeof ও unary &।


## প্রশ্ন 55 | Topic: Structured Programming > Partial Initialization | Difficulty: Easy | Type: Theory

Q. `int a[5]={10,20};`-এর পরে `a[3]` কত?

A) Garbage
B) 0
C) 20
D) 10

**সঠিক উত্তর: B) 0**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Explicit initializer কম হলে বাকি element zero-initialize হয়।
- **A option কেন ভুল:** Partial initialization-এ garbage নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** 20 শুধু a[1]।
- **D option কেন ভুল:** 10 শুধু a[0]।
- **Related Concept:** `int a[5]={0};` সব zero।
- **মনে রাখার টিপস:** এক initializer থাকলেও rest zero।


## প্রশ্ন 56 | Topic: Structured Programming > Array Bounds | Difficulty: Medium | Type: Theory

Q. `int a[5];`-এর `a[5]` access করলে কী হতে পারে?

A) Undefined Behavior
B) সবসময় zero
C) Compilation বাধ্যতামূলকভাবে ব্যর্থ
D) a[0]-তে wrap

**সঠিক উত্তর: A) Undefined Behavior**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Valid index 0–4; boundary-এর বাইরে access standard-defined নয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Memory zero guarantee নেই।
- **C option কেন ভুল:** Compiler detect করতে বাধ্য নয়।
- **D option কেন ভুল:** C index wrap করে না।
- **Related Concept:** Out-of-bounds memory corruption ঘটাতে পারে।
- **মনে রাখার টিপস:** Size ও last index আলাদা।


## প্রশ্ন 57 | Topic: Structured Programming > Null Termination | Difficulty: Hard | Type: Theory

Q. `char text[3]={'I','C','T'};` সম্পর্কে কোনটি সঠিক?

A) নিশ্চিত valid string
B) Compiler extra byte যোগ করে
C) `strlen` সবসময় 3
D) Null terminator নেই

**সঠিক উত্তর: D) Null terminator নেই**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** তিন cell visible character-এ পূর্ণ; `\0` রাখার cell নেই।
- **A option কেন ভুল:** Null byte ছাড়া C string নয়।
- **B option কেন ভুল:** Declared boundary বাড়ে না।
- **C option কেন ভুল:** `strlen` boundary ছাড়িয়ে পড়তে পারে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `"ICT"`-এর জন্য 4 byte দরকার।
- **মনে রাখার টিপস:** Visible chars + 1।


## প্রশ্ন 58 | Topic: Structured Programming > strlen ও sizeof | Difficulty: Medium | Type: Code

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
- **মনে রাখার টিপস:** Hello length 5, array 6।


## প্রশ্ন 59 | Topic: Structured Programming > strcmp | Difficulty: Medium | Type: Theory

Q. `strcmp(s1,s2)` zero return করলে কী বোঝায়?

A) Content সমান
B) s1 ছোট
C) s2 ছোট
D) Pointer address একই

**সঠিক উত্তর: A) Content সমান**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `strcmp` lexicographical content compare করে; equal হলে zero।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** s1 ছোট হলে negative।
- **C option কেন ভুল:** s1 বড় হলে positive।
- **D option কেন ভুল:** Address equality পরীক্ষা করে না।
- **Related Concept:** Nonzero exact magnitude standard নির্দিষ্ট করে না।
- **মনে রাখার টিপস:** strcmp == 0 → equal।


## প্রশ্ন 60 | Topic: Structured Programming > Overlapping Memory | Difficulty: Hard | Type: Theory

Q. Overlapping memory region copy করতে কোন function উপযুক্ত?

A) `strcpy`
B) `memmove`
C) `strlen`
D) `strcmp`

**সঠিক উত্তর: B) `memmove`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `memmove` overlap handle করার guarantee দেয়।
- **A option কেন ভুল:** Overlapping string copy unsafe।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Length function।
- **D option কেন ভুল:** Compare function।
- **Related Concept:** `memcpy` overlap guarantee দেয় না।
- **মনে রাখার টিপস:** Overlap → memmove।


## প্রশ্ন 61 | Topic: Structured Programming > String Input | Difficulty: Easy | Type: Theory

Q. Space-সহ bounded line input-এর জন্য কোনটি তুলনামূলক নিরাপদ?

A) `gets`
B) Width ছাড়া `scanf("%s")`
C) `strcpy`
D) `fgets`

**সঠিক উত্তর: D) `fgets`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `fgets(buffer,size,stdin)` maximum character count জানে এবং space পড়তে পারে।
- **A option কেন ভুল:** Unsafe ও removed।
- **B option কেন ভুল:** Overflow risk এবং whitespace-এ থামে।
- **C option কেন ভুল:** Input function নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `fgets` newline রাখতে পারে।
- **মনে রাখার টিপস:** Safe line input → fgets।


## প্রশ্ন 62 | Topic: Structured Programming > 2D Array | Difficulty: Medium | Type: Code

Q. `int a[2][3]={{1,2,3},{4,5,6}}; printf("%d",a[1][2]);` output কী?

A) 3
B) 5
C) 6
D) 4

**সঠিক উত্তর: C) 6**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Index [1][2] দ্বিতীয় row-এর তৃতীয় element—6।
- **A option কেন ভুল:** a[0][2]।
- **B option কেন ভুল:** a[1][1]।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** a[1][0]।
- **Related Concept:** প্রথম index row, দ্বিতীয় column।
- **মনে রাখার টিপস:** দুই index-ই zero-based।


## প্রশ্ন 63 | Topic: Structured Programming > Array Parameter | Difficulty: Hard | Type: Code

Q. 64-bit system-এ pointer size 8 byte হলে `void f(int a[10]){printf("%zu",sizeof(a));}` সাধারণত কী print করে?

A) 8
B) 40
C) 10
D) 4

**সঠিক উত্তর: A) 8**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Adjustment

```text
int a[10]  →  int *a
```

#### Final Answer

```text
sizeof(a) = pointer size = 8 byte
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Function parameter `int a[10]` adjust হয়ে `int *a`; sizeof pointer = 8।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Original array size ধরা হয়েছে।
- **C option কেন ভুল:** Element count byte হিসেবে।
- **D option কেন ভুল:** sizeof(int) নেওয়া।
- **Related Concept:** Array length আলাদা argument হিসেবে পাঠান।
- **মনে রাখার টিপস:** Array parameter আসলে pointer।


## প্রশ্ন 64 | Topic: Structured Programming > String Literal | Difficulty: Hard | Type: Theory

Q. `char *p="ICT"; p[0]='A';`-এর behavior কী?

A) নিশ্চিত ACT
B) Undefined Behavior
C) p NULL হয়
D) Compiler array copy করে

**সঠিক উত্তর: B) Undefined Behavior**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** String literal modify করার চেষ্টা Undefined Behavior।
- **A option কেন ভুল:** Success guarantee নেই।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Pointer null হয় না।
- **D option কেন ভুল:** Pointer শুধু literal address পায়।
- **Related Concept:** Modifiable copy: `char p[]="ICT";`।
- **মনে রাখার টিপস:** Literal পড়ুন, modify নয়।


## প্রশ্ন 65 | Topic: Structured Programming > strcat | Difficulty: Medium | Type: Theory

Q. `strcat(destination,source)` নিরাপদ হওয়ার অপরিহার্য শর্ত কী?

A) Source empty
B) Pointers একই
C) Destination-এ combined string+null-এর জায়গা
D) Destination literal

**সঠিক উত্তর: C) Destination-এ combined string+null-এর জায়গা**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `strcat` capacity পরীক্ষা করে না; destination যথেষ্ট বড় হতে হবে।
- **A option কেন ভুল:** Source empty হওয়া লাগে না।
- **B option কেন ভুল:** Overlap unsafe।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Literal modifiable destination নয়।
- **Related Concept:** Required size = dest length + source length + 1।
- **মনে রাখার টিপস:** Concatenate-এর আগে capacity।


## প্রশ্ন 66 | Topic: Structured Programming > Char Array Initialization | Difficulty: Medium | Type: Theory

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
- **C option কেন ভুল:** T-ও store হয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `char name[3]="ICT"` null রাখতে পারে না।
- **মনে রাখার টিপস:** ICT storage 4।


## প্রশ্ন 67 | Topic: Structured Programming > Reverse Traversal | Difficulty: Medium | Type: Code

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
- **C option কেন ভুল:** Circular shift নয়।
- **D option কেন ভুল:** Index sequence ভুল।
- **Related Concept:** Last index = length−1।
- **মনে রাখার টিপস:** Reverse loop-এ signed index ব্যবহার সতর্কভাবে।


## প্রশ্ন 68 | Topic: Structured Programming > Array Element Count | Difficulty: Easy | Type: Calculation

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

- **সঠিক উত্তর কেন:** Total array bytes-কে one-element bytes দিয়ে ভাগ করলে element count পাওয়া যায়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Byte count দেয়।
- **C option কেন ভুল:** Division উল্টো।
- **D option কেন ভুল:** Integer array string নয়।
- **Related Concept:** Function parameter-এ array decay করলে formula কাজ করে না।
- **মনে রাখার টিপস:** Total bytes ÷ one element।


## প্রশ্ন 69 | Topic: Structured Programming > Pointer Declaration | Difficulty: Easy | Type: Theory

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
- **C option কেন ভুল:** Standard C reference syntax নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `int *p,q;`-তে শুধু p pointer।
- **মনে রাখার টিপস:** প্রতিটি pointer name-এর সঙ্গে * দেখুন।


## প্রশ্ন 70 | Topic: Structured Programming > Dereference | Difficulty: Easy | Type: Theory

Q. p যদি x-এর address রাখে, pointer দিয়ে x-এর value access কোন expression?

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
- **মনে রাখার টিপস:** & address, * value।


## প্রশ্ন 71 | Topic: Structured Programming > Pointer Arithmetic | Difficulty: Medium | Type: Theory

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
- **C option কেন ভুল:** Pointer value/address বদলায়, target integer নয়।
- **D option কেন ভুল:** Addition null করে না।
- **Related Concept:** Byte increment = sizeof(*p)।
- **মনে রাখার টিপস:** Pointer step = one element।


## প্রশ্ন 72 | Topic: Structured Programming > Pointer Subscript | Difficulty: Medium | Type: Theory

Q. `p[i]`-এর সমতুল্য কোনটি?

A) `*p+i`
B) `&(p+i)`
C) `p+*i`
D) `*(p+i)`

**সঠিক উত্তর: D) `*(p+i)`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Subscript operator সংজ্ঞাগতভাবে offset করে dereference করে।
- **A option কেন ভুল:** Pointed value-এর সঙ্গে i যোগ।
- **B option কেন ভুল:** Address expression equivalence নয়।
- **C option কেন ভুল:** i pointer নাও হতে পারে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `i[p]`-ও technically same।
- **মনে রাখার টিপস:** Advance then dereference।


## প্রশ্ন 73 | Topic: Structured Programming > Call by Value | Difficulty: Medium | Type: Theory

Q. C argument passing সম্পর্কে কোনটি সঠিক?

A) সব argument call by value
B) সব call by reference
C) Array call by name
D) Compiler বেছে নেয়

**সঠিক উত্তর: A) সব argument call by value**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Parameter argument value-এর copy পায়; pointer argument-ও address value-এর copy।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Built-in reference parameter নেই।
- **C option কেন ভুল:** Array pointer-এ adjust হয়।
- **D option কেন ভুল:** Language semantics fixed।
- **Related Concept:** Pointer দিয়ে reference-like effect।
- **মনে রাখার টিপস:** C = call by value।


## প্রশ্ন 74 | Topic: Structured Programming > Pointer Swap | Difficulty: Medium | Type: Code

Q. `swap(&x,&y)` function pointer dereference করে x=3,y=7 exchange করলে output কী?

A) 3 7
B) 7 7
C) 7 3
D) 3 3

**সঠিক উত্তর: C) 7 3**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Trace

```text
temp = x = 3
x = y = 7
y = temp = 3
```

#### Final Answer

```text
Output = 7 3
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Address পেয়ে function original object-এর value swap করে।
- **A option কেন ভুল:** Modification উপেক্ষা।
- **B option কেন ভুল:** শেষ assignment বাদ।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** প্রথম assignment ভুল।
- **Related Concept:** Pointer values call by value-তে গেছে।
- **মনে রাখার টিপস:** Original বদলাতে address পাঠান।


## প্রশ্ন 75 | Topic: Structured Programming > NULL Pointer | Difficulty: Easy | Type: Theory

Q. NULL pointer সম্পর্কে কোনটি সঠিক?

A) Representation সবসময় all-bits-zero
B) কোনো valid object নির্দেশ না করার ধারণা
C) Uninitialized pointer-এর সমান
D) Dereference নিরাপদ

**সঠিক উত্তর: B) কোনো valid object নির্দেশ না করার ধারণা**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Null pointer valid object/function target করে না।
- **A option কেন ভুল:** Representation implementation-dependent হতে পারে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Uninitialized pointer indeterminate।
- **D option কেন ভুল:** Null dereference UB।
- **Related Concept:** `p!=NULL` validity check-এর অংশ।
- **মনে রাখার টিপস:** NULL means no valid object।


## প্রশ্ন 76 | Topic: Structured Programming > Dangling Pointer | Difficulty: Medium | Type: Theory

Q. কখন Dangling Pointer তৈরি হয়?

A) Object lifetime শেষ, pointer পুরোনো address রাখে
B) Pointer NULL
C) নতুন valid object
D) Identifier undeclared

**সঠিক উত্তর: A) Object lifetime শেষ, pointer পুরোনো address রাখে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Pointed object destroy/free হওয়ার পর pointer stale address ধরে রাখে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Null dangling নয়।
- **C option কেন ভুল:** Valid target dangling নয়।
- **D option কেন ভুল:** Compilation error।
- **Related Concept:** `free(p); p=NULL;` accidental reuse কমায়।
- **মনে রাখার টিপস:** Object gone, pointer remains।


## প্রশ্ন 77 | Topic: Structured Programming > Wild Pointer | Difficulty: Easy | Type: Theory

Q. Initialize না করা pointer-কে কী বলা হয়?

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
- **মনে রাখার টিপস:** Declare করে NULL বা valid address দিন।


## প্রশ্ন 78 | Topic: Structured Programming > Pointer to Pointer | Difficulty: Medium | Type: Theory

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
- **মনে রাখার টিপস:** Pointer-এর pointer = **।


## প্রশ্ন 79 | Topic: Structured Programming > Pointer to const | Difficulty: Medium | Type: Theory

Q. `const int *p;`-এর অর্থ কী?

A) p address বদলাতে পারবে না
B) p দিয়ে pointed int modify করা যাবে না
C) p সবসময় NULL
D) Object compile-time constant

**সঠিক উত্তর: B) p দিয়ে pointed int modify করা যাবে না**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Const pointed type-এর সঙ্গে; p অন্য address নিতে পারে, কিন্তু `*p` দিয়ে write নয়।
- **A option কেন ভুল:** এটি `int *const p`।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Null constraint নেই।
- **D option কেন ভুল:** অন্য non-const path-এ object বদলাতে পারে।
- **Related Concept:** Pointer to const int।
- **মনে রাখার টিপস:** const star-এর আগে → data protected।


## প্রশ্ন 80 | Topic: Structured Programming > Const Pointer | Difficulty: Medium | Type: Theory

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
- **C option কেন ভুল:** x const declared নয়।
- **D option কেন ভুল:** Double star নেই।
- **Related Concept:** Const pointer to int।
- **মনে রাখার টিপস:** const star-এর পরে → address fixed।


## প্রশ্ন 81 | Topic: Structured Programming > Pointer Subtraction | Difficulty: Hard | Type: Calculation

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

- **সঠিক উত্তর কেন:** Pointer difference element distance দেয়, byte distance নয়।
- **A option কেন ভুল:** Index যোগ।
- **B option কেন ভুল:** 4-byte int ধরে byte difference।
- **C option কেন ভুল:** Off-by-one।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** শুধু same array-এর মধ্যে defined।
- **মনে রাখার টিপস:** Higher index−lower index।


## প্রশ্ন 82 | Topic: Structured Programming > void Pointer | Difficulty: Medium | Type: Theory

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
- **মনে রাখার টিপস:** Generic address, generic value নয়।


## প্রশ্ন 83 | Topic: Structured Programming > Function Pointer | Difficulty: Hard | Type: Theory

Q. দুটি int parameter নিয়ে int return করা function pointer declaration কোনটি?

A) `int *fp(int,int);`
B) `int (*fp)(int,int);`
C) `int fp*(int,int);`
D) `(*int fp)(int,int);`

**সঠিক উত্তর: B) `int (*fp)(int,int);`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Parenthesized `(*fp)` p-কে function-এর pointer করে।
- **A option কেন ভুল:** Function returning pointer-to-int।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Invalid syntax।
- **D option কেন ভুল:** Invalid declaration order।
- **Related Concept:** Callback ও dispatch table-এ ব্যবহার।
- **মনে রাখার টিপস:** Function pointer name: (*name)।


## প্রশ্ন 84 | Topic: Structured Programming > Recursive Factorial | Difficulty: Easy | Type: Code

Q. `fact(n){ if(n<=1)return 1; return n*fact(n-1); }`-এ `fact(5)` কত?

A) 120
B) 25
C) 60
D) 24

**সঠিক উত্তর: A) 120**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Expansion

```text
fact(5)=5×fact(4)
       =5×4×3×2×1
       =120
```

#### Final Answer

```text
fact(5) = 120
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 5! = 5×4×3×2×1 = 120।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** 5×5।
- **C option কেন ভুল:** Factor বাদ।
- **D option কেন ভুল:** 4!।
- **Related Concept:** `0!` ও `1!` = 1।
- **মনে রাখার টিপস:** Factorial recurrence expand করুন।


## প্রশ্ন 85 | Topic: Structured Programming > Base Case | Difficulty: Easy | Type: Theory

Q. Recursive function-এ Base Case-এর উদ্দেশ্য কী?

A) দুইবার call
B) Global variable
C) Recursion stop condition
D) Pointer arithmetic

**সঠিক উত্তর: C) Recursion stop condition**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Base case reached হলে আর recursive call হয় না।
- **A option কেন ভুল:** Call count নয়।
- **B option কেন ভুল:** Scope নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Pointer operation নয়।
- **Related Concept:** Unreachable base case stack overflow ঘটাতে পারে।
- **মনে রাখার টিপস:** Base case recursion বন্ধ করে।


## প্রশ্ন 86 | Topic: Structured Programming > Stack Overflow | Difficulty: Medium | Type: Theory

Q. Recursive function Base Case-এ না পৌঁছালে কী হতে পারে?

A) Compiler recursion সরায়
B) Automatic zero return
C) Heap সবসময় পূর্ণ
D) Call Stack Overflow

**সঠিক উত্তর: D) Call Stack Overflow**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতি call stack frame জমে finite stack exhaust হতে পারে।
- **A option কেন ভুল:** Optimization guarantee নেই।
- **B option কেন ভুল:** Automatic return নেই।
- **C option কেন ভুল:** প্রধানত stack issue।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Tail-call optimization standard guarantee নয়।
- **মনে রাখার টিপস:** Infinite recursion → stack exhausted।


## প্রশ্ন 87 | Topic: Structured Programming > Static Local | Difficulty: Medium | Type: Theory

Q. Local `static` variable-এর lifetime কত?

A) পুরো program execution
B) শুধু function call
C) এক statement
D) প্রথম loop iteration

**সঠিক উত্তর: A) পুরো program execution**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Scope block-level হলেও storage duration static।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Automatic local-এর মতো নয়।
- **C option কেন ভুল:** Statement শেষে নষ্ট হয় না।
- **D option কেন ভুল:** Loop-এর সঙ্গে বাঁধা নয়।
- **Related Concept:** একবার initialize হয়ে value ধরে রাখে।
- **মনে রাখার টিপস:** Scope local, lifetime long।


## প্রশ্ন 88 | Topic: Structured Programming > extern | Difficulty: Medium | Type: Theory

Q. `extern int count;` সাধারণত কী বোঝায়?

A) নতুন local storage
B) Definition অন্যত্র থাকতে পারে
C) Function pointer
D) Immutable constant

**সঠিক উত্তর: B) Definition অন্যত্র থাকতে পারে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Existing external object-এর declaration; সাধারণত storage definition নয়।
- **A option কেন ভুল:** Automatic storage তৈরি করে না।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Pointer syntax নয়।
- **D option কেন ভুল:** Const নয়।
- **Related Concept:** Initializer-সহ extern declaration definition হতে পারে।
- **মনে রাখার টিপস:** extern = elsewhere।


## প্রশ্ন 89 | Topic: Structured Programming > Automatic Storage | Difficulty: Easy | Type: Theory

Q. সাধারণ non-static local variable-এর storage duration কী?

A) Thread
B) Static
C) Allocated
D) Automatic

**সঠিক উত্তর: D) Automatic**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Block execution-এর সময় ordinary local object তৈরি ও destroy হয়।
- **A option কেন ভুল:** Thread storage নয়।
- **B option কেন ভুল:** static qualifier থাকলে।
- **C option কেন ভুল:** Dynamic allocation-এর object।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `auto` default local storage class।
- **মনে রাখার টিপস:** Ordinary local = automatic।


## প্রশ্ন 90 | Topic: Structured Programming > register | Difficulty: Medium | Type: Code

Q. `register int x=10; int *p=&x;`-এর সমস্যা কী?

A) register initialize করা যায় না
B) শুধু global-এ
C) register object-এর address নেওয়া যায় না
D) Pointer declaration invalid

**সঠিক উত্তর: C) register object-এর address নেওয়া যায় না**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Standard C constraint অনুযায়ী register-declared object-এর address `&` দিয়ে নেওয়া যায় না।
- **A option কেন ভুল:** Initialize করা যায়।
- **B option কেন ভুল:** Block scope/parameter-এ ব্যবহার।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Pointer declaration valid।
- **Related Concept:** Compiler hardware register-এ রাখবে—guarantee নেই।
- **মনে রাখার টিপস:** register লিখলে & নয়।


## প্রশ্ন 91 | Topic: Structured Programming > Internal Linkage | Difficulty: Hard | Type: Theory

Q. File scope-এ `static int count;` কী linkage পায়?

A) Internal
B) External
C) কোনো storage নয়
D) Dynamic

**সঠিক উত্তর: A) Internal**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Name একই translation unit-এর মধ্যে সীমিত থাকে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** External visibility suppressed।
- **C option কেন ভুল:** Static storage duration আছে।
- **D option কেন ভুল:** Standard linkage category নয়।
- **Related Concept:** File static = file-private।
- **মনে রাখার টিপস:** static at file scope → internal linkage।


## প্রশ্ন 92 | Topic: Structured Programming > extern Declaration | Difficulty: Medium | Type: Theory

Q. Initializer ছাড়া `extern int total;` সাধারণত কোনটি?

A) Local definition
B) Declaration, সাধারণত definition নয়
C) Macro
D) Function definition

**সঠিক উত্তর: B) Declaration, সাধারণত definition নয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Compiler-কে external object-এর name/type জানায়।
- **A option কেন ভুল:** Automatic local নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Macro #define দিয়ে।
- **D option কেন ভুল:** Function syntax নয়।
- **Related Concept:** `int total;` file scope-এ tentative definition হতে পারে।
- **মনে রাখার টিপস:** Extern says object exists elsewhere।


## প্রশ্ন 93 | Topic: Structured Programming > Arguments | Difficulty: Easy | Type: Theory

Q. Function call-এর supplied value/expression-কে কী বলা হয়?

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
- **মনে রাখার টিপস:** Call-এ actual, body-তে formal।


## প্রশ্ন 94 | Topic: Structured Programming > Function Prototype | Difficulty: Medium | Type: Theory

Q. Function prototype-এর প্রধান সুবিধা কী?

A) Runtime delete
B) Local global করা
C) Recursion নিষিদ্ধ
D) Argument ও return type check

**সঠিক উত্তর: D) Argument ও return type check**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Compiler function interface আগে থেকে জেনে call type-check করে।
- **A option কেন ভুল:** Runtime deletion নয়।
- **B option কেন ভুল:** Scope বদলায় না।
- **C option কেন ভুল:** Recursion allowed।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Definition-এর আগে call সম্ভব।
- **মনে রাখার টিপস:** Prototype = type contract।


## প্রশ্ন 95 | Topic: Structured Programming > Recursive Output | Difficulty: Medium | Type: Code

Q. `printDown(3)` প্রতিবার recursive call-এর আগে n print করে এবং n=0-এ return করলে output কী?

A) 123
B) 321
C) 333
D) 0123

**সঠিক উত্তর: B) 321**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Trace

```text
printDown(3): print 3
printDown(2): print 2
printDown(1): print 1
printDown(0): return
```

#### Final Answer

```text
Output = 321
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Print call-এর আগে; n 3→2→1, zero print হয় না।
- **A option কেন ভুল:** Print call-এর পরে হলে ascending হতে পারত।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** n decrement হয়।
- **D option কেন ভুল:** Base zero print হয় না।
- **Related Concept:** Operation call-এর আগে/পরে output order বদলায়।
- **মনে রাখার টিপস:** Call-এর আগে print → descending।


## প্রশ্ন 96 | Topic: Structured Programming > Tail Recursion | Difficulty: Hard | Type: Theory

Q. Tail-recursive function-এর বৈশিষ্ট্য কী?

A) Recursive call শেষ কার্যকর operation
B) Parameter নেই
C) দুইবার self-call
D) Stack না লাগা guaranteed

**সঠিক উত্তর: A) Recursive call শেষ কার্যকর operation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Recursive call-এর result পাওয়ার পরে আর pending computation থাকে না।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Parameter থাকতে পারে।
- **C option কেন ভুল:** একটি call-ও হতে পারে।
- **D option কেন ভুল:** Optimization compiler-dependent।
- **Related Concept:** Accumulator tail recursion তৈরিতে সাহায্য করে।
- **মনে রাখার টিপস:** Call-এর পরে কাজ নেই।


## প্রশ্ন 97 | Topic: Structured Programming > Tower of Hanoi | Difficulty: Hard | Type: Calculation

Q. ৫টি disk-এর Tower of Hanoi minimum move কত?

A) 15
B) 25
C) 31
D) 32

**সঠিক উত্তর: C) 31**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Formula

```text
Moves = 2^n - 1
```

#### Substitution

```text
= 2^5 - 1
```

#### Calculation

```text
2^5 = 32
32 - 1 = 31
```

#### Final Answer

```text
Minimum moves = 31
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Minimum moves = 2^n−1।
- **A option কেন ভুল:** 4 disk-এর result।
- **B option কেন ভুল:** n²।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** −1 বাদ।
- **Related Concept:** Recurrence T(n)=2T(n−1)+1।
- **মনে রাখার টিপস:** Power of two-এর এক কম।


## প্রশ্ন 98 | Topic: Structured Programming > Static Local State | Difficulty: Hard | Type: Code

Q. `show()`-এ `static int x=0; x++; printf("%d ",x);` তিনবার call করলে output কী?

A) 1 1 1
B) 0 0 0
C) 3 3 3
D) 1 2 3

**সঠিক উত্তর: D) 1 2 3**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Trace

```text
1st call: 0→1
2nd call: 1→2
3rd call: 2→3
```

#### Final Answer

```text
Output = 1 2 3
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Static local একবার initialize হয় এবং call-এর মধ্যে state রাখে।
- **A option কেন ভুল:** প্রতি call reinitialize ধরা।
- **B option কেন ভুল:** Increment বাদ।
- **C option কেন ভুল:** Final value সববার নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Automatic local হলে প্রতিবার 1 হতো।
- **মনে রাখার টিপস:** Static local আগের value মনে রাখে।


## প্রশ্ন 99 | Topic: Structured Programming > Shadowing | Difficulty: Medium | Type: Code

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
- **C option কেন ভুল:** Inner x outer object বদলায় না।
- **D option কেন ভুল:** Nested shadowing valid।
- **Related Concept:** Scope visibility নির্ধারণ করে।
- **মনে রাখার টিপস:** Hide করে, overwrite নয়।


## প্রশ্ন 100 | Topic: Structured Programming > Reference Effect | Difficulty: Easy | Type: Theory

Q. Function দিয়ে caller-এর variable modify করার প্রচলিত উপায় কী?

A) Name string পাঠানো
B) Address pointer argument পাঠানো
C) Keyword বানানো
D) শুধু global

**সঠিক উত্তর: B) Address pointer argument পাঠানো**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Function address value-এর copy পেয়ে dereference করে original object modify করতে পারে।
- **A option কেন ভুল:** Name string address নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Variable keyword হতে পারে না।
- **D option কেন ভুল:** Global বাধ্যতামূলক নয়।
- **Related Concept:** Mechanism call by value, effect reference-like।
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

# Batch 03 — Question 101–150

**Section:** Structured & Object-Oriented Programming  
**Coverage:** Console I/O, File I/O, Structures, Unions, `typedef`, Bit-fields এবং OOP Fundamentals  
**Composition:** Theory/Scenario 35, Calculation/Code 15


# Chapter Theory 03: Console/File I/O, Structures ও OOP Fundamentals

## Console I/O

`<stdio.h>`-এর গুরুত্বপূর্ণ function:

- `printf` — formatted output
- `scanf` — formatted input
- `getchar/putchar` — single character I/O
- `fgets/puts` — line/string I/O

Format match অত্যন্ত গুরুত্বপূর্ণ। `scanf`-এ scalar variable-এর address দিতে হয়। `scanf`-এ `double` input-এর জন্য `%lf`; `printf`-এ `double` output-এর জন্য `%f`।

## File I/O

File stream `FILE *` দিয়ে handle করা হয়। `fopen` failure-এ `NULL` return করে।

```text
r   read, file must exist
w   write, create/truncate
a   append
r+  read/write, must exist
w+  read/write, create/truncate
a+  read/append
```

`fread` ও `fwrite` byte count নয়, successfully processed element count return করে। EOF loop-এ read function-এর return value সরাসরি পরীক্ষা করা উচিত।

## Structure, Union ও typedef

`struct`-এর member আলাদা storage পায়; alignment-এর কারণে padding থাকতে পারে। `union` member একই storage share করে এবং size সাধারণত largest member ও alignment-এর ওপর নির্ভর করে। `typedef` existing type-এর alias তৈরি করে। Bit-field compact flag storage দিতে পারে, কিন্তু exact layout implementation-dependent এবং bit-field-এর address নেওয়া যায় না।

## OOP Fundamentals

- Class — blueprint
- Object — class instance
- Encapsulation — data ও method bundle, access control
- Abstraction — essential interface, hidden detail
- Inheritance — existing class থেকে specialization
- Polymorphism — one interface, multiple behavior
- Constructor — initialization
- Destructor — cleanup
- Interface — operation contract
- Composition — strong has-a
- Aggregation — weak has-a

## Overloading, Overriding ও Binding

Overloading: same method name, different parameter list; সাধারণত compile-time।  
Overriding: derived class parent method-এর নতুন implementation; runtime dynamic binding হতে পারে।  
Access specifier: `public`, `private`, `protected`—exact rule language অনুযায়ী ভিন্ন।


## প্রশ্ন 101 | Topic: Structured Programming > Standard I/O Header | Difficulty: Easy | Type: Theory

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
- **মনে রাখার টিপস:** Standard I/O → stdio.h।


## প্রশ্ন 102 | Topic: Structured Programming > printf Return | Difficulty: Medium | Type: Code

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
- **A option কেন ভুল:** Successful printf zero নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Order উল্টো।
- **D option কেন ভুল:** Null terminator print count নয়।
- **Related Concept:** `printf` printed character count return করে।
- **মনে রাখার টিপস:** Visible output character count করুন।


## প্রশ্ন 103 | Topic: Structured Programming > scanf Address | Difficulty: Easy | Type: Theory

Q. `int x`-এ input নেওয়ার সঠিক statement কোনটি?

A) `scanf("%d",x);`
B) `scanf(x,"%d");`
C) `scanf("%d",&x);`
D) `scanf("&d",x);`

**সঠিক উত্তর: C) `scanf("%d",&x);`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `scanf`-কে storage address দিতে হয়।
- **A option কেন ভুল:** Value পাঠানো হয়েছে।
- **B option কেন ভুল:** Argument order ভুল।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Format invalid।
- **Related Concept:** Array name `%s`-এ pointer decay করে।
- **মনে রাখার টিপস:** Scalar input → &variable।


## প্রশ্ন 104 | Topic: Structured Programming > Character I/O | Difficulty: Medium | Type: Code

Q. Input-এর প্রথম character A হলে `int ch=getchar(); putchar(ch+1);` output কী?

A) A
B) C
C) 65
D) B

**সঠিক উত্তর: D) B**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Trace

```text
ch = 'A'
ch + 1 = 'B'
putchar prints B
```

#### Final Answer

```text
Output = B
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 'A' character code-এর পরের code 'B'।
- **A option কেন ভুল:** Increment বাদ।
- **B option কেন ভুল:** দুই step নয়।
- **C option কেন ভুল:** putchar character print করে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `getchar` int return করে যাতে EOF রাখা যায়।
- **মনে রাখার টিপস:** Character arithmetic code value-এ হয়।


## প্রশ্ন 105 | Topic: Structured Programming > String Input | Difficulty: Easy | Type: Theory

Q. Space-সহ bounded line input-এর জন্য কোনটি উপযুক্ত?

A) `fgets`
B) `gets`
C) `putchar`
D) `strlen`

**সঠিক উত্তর: A) `fgets`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `fgets` buffer size মেনে line পড়ে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Unsafe ও removed।
- **C option কেন ভুল:** Output function।
- **D option কেন ভুল:** Length function।
- **Related Concept:** Newline buffer-এ থাকতে পারে।
- **মনে রাখার টিপস:** Safe line input → fgets।


## প্রশ্ন 106 | Topic: Structured Programming > Integer Formatting | Difficulty: Medium | Type: Code

Q. `printf("%05d",42);` output কী?

A) 42
B) 00042
C) 42000
D)    42

**সঠিক উত্তর: B) 00042**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Calculation

```text
Digits in 42 = 2
Field width = 5
Padding = 5 - 2 = 3
```

#### Final Answer

```text
Output = 00042
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Width 5 ও zero flag বাম পাশে তিন zero যোগ করে।
- **A option কেন ভুল:** Width ignored।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Right padding নয়।
- **D option কেন ভুল:** Zero flag না থাকলে space।
- **Related Concept:** `%5d` space; `%05d` zero।
- **মনে রাখার টিপস:** Field width-এর আগে 0 → zero padding।


## প্রশ্ন 107 | Topic: Structured Programming > scanf Return | Difficulty: Medium | Type: Theory

Q. `scanf()` সফল হলে কী return করে?

A) Input byte count
B) Last value
C) Successfully assigned item count
D) সবসময় 1

**সঠিক উত্তর: C) Successfully assigned item count**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Successful conversion ও assignment-এর সংখ্যা return করে।
- **A option কেন ভুল:** Byte count নয়।
- **B option কেন ভুল:** Value variable-এ যায়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Multiple item হলে বেশি হতে পারে।
- **Related Concept:** EOF/input failure আলাদা return হতে পারে।
- **মনে রাখার টিপস:** scanf return = assignments।


## প্রশ্ন 108 | Topic: Structured Programming > Format Mismatch | Difficulty: Hard | Type: Code

Q. `double x=3.5; printf("%d",x);`-এর behavior কী?

A) সবসময় 3
B) সবসময় 4
C) Compilation বাধ্যতামূলকভাবে ব্যর্থ
D) Undefined Behavior

**সঠিক উত্তর: D) Undefined Behavior**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `%d` int আশা করে কিন্তু argument double; variadic format mismatch UB।
- **A option কেন ভুল:** Automatic int cast হয় না।
- **B option কেন ভুল:** Rounding নয়।
- **C option কেন ভুল:** Warning হতে পারে, reject বাধ্যতামূলক নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Double print → `%f`।
- **মনে রাখার টিপস:** Format ও argument type match করুন।


## প্রশ্ন 109 | Topic: Structured Programming > scanf Double | Difficulty: Medium | Type: Theory

Q. `double value` input-এর `scanf` format কোনটি?

A) `%lf`
B) `%f`
C) `%d`
D) `%Lf`

**সঠিক উত্তর: A) `%lf`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `%lf` `double *` আশা করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `float *`।
- **C option কেন ভুল:** `int *`।
- **D option কেন ভুল:** `long double *`।
- **Related Concept:** printf-এ double `%f`।
- **মনে রাখার টিপস:** Scan double → %lf।


## প্রশ্ন 110 | Topic: Structured Programming > Output Count | Difficulty: Hard | Type: Calculation

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
- **Related Concept:** Literal character-ও count হয়।
- **মনে রাখার টিপস:** Field width + surrounding literal।


## প্রশ্ন 111 | Topic: Structured Programming > fopen Failure | Difficulty: Easy | Type: Theory

Q. `fopen()` ব্যর্থ হলে কী return করে?

A) EOF
B) Character zero
C) NULL
D) Empty FILE object

**সঠিক উত্তর: C) NULL**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Success-এ stream pointer; failure-এ null pointer।
- **A option কেন ভুল:** Character I/O sentinel।
- **B option কেন ভুল:** Pointer failure signal নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Usable object পাওয়া যায় না।
- **Related Concept:** `if(fp==NULL)` check করুন।
- **মনে রাখার টিপস:** Open failed → NULL।


## প্রশ্ন 112 | Topic: Structured Programming > Write Mode | Difficulty: Medium | Type: Code

Q. `fopen("data.txt","w")` existing file-এর ওপর কী effect ফেলতে পারে?

A) Read-only
B) Content অপরিবর্তিত
C) শুধু append
D) Existing content truncate

**সঠিক উত্তর: D) Existing content truncate**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `w` mode file create করে বা existing content zero-length করে।
- **A option কেন ভুল:** Write mode।
- **B option কেন ভুল:** Preserve নয়।
- **C option কেন ভুল:** Append-এর জন্য a।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `w+`-ও truncate করে।
- **মনে রাখার টিপস:** w = wipe then write।


## প্রশ্ন 113 | Topic: Structured Programming > Append Mode | Difficulty: Easy | Type: Theory

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
- **মনে রাখার টিপস:** Append → a।


## প্রশ্ন 114 | Topic: Structured Programming > fwrite Return | Difficulty: Medium | Type: Code

Q. `fwrite(a,sizeof(int),5,fp)` সব item লিখলে return কত?

A) `sizeof(int)*5`
B) 5
C) 1
D) File bytes

**সঠিক উত্তর: B) 5**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `fwrite` written element count return করে।
- **A option কেন ভুল:** Total byte হতে পারে, return নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এক element হলে।
- **D option কেন ভুল:** File total নয়।
- **Related Concept:** Bytes = return count × element size।
- **মনে রাখার টিপস:** fread/fwrite return items।


## প্রশ্ন 115 | Topic: Structured Programming > File Position | Difficulty: Medium | Type: Theory

Q. Current file position জানতে function কোনটি?

A) `fseek`
B) `rewind`
C) `ftell`
D) `fclose`

**সঠিক উত্তর: C) `ftell`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `ftell` current position indicator report করে।
- **A option কেন ভুল:** Position বদলায়।
- **B option কেন ভুল:** Start-এ নেয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Stream বন্ধ করে।
- **Related Concept:** `fseek` + `ftell` random access-এ।
- **মনে রাখার টিপস:** Tell position → ftell।


## প্রশ্ন 116 | Topic: Structured Programming > EOF Loop | Difficulty: Hard | Type: Code

Q. Character-by-character file read-এর সঠিক loop কোনটি?

A) `while(!feof(fp)){ch=fgetc(fp);putchar(ch);}`
B) `while(fp) putchar(fgetc(fp));`
C) `while((ch=fgetc(fp))!=EOF) putchar(ch);`
D) `while(EOF) putchar(fgetc(fp));`

**সঠিক উত্তর: C) `while((ch=fgetc(fp))!=EOF) putchar(ch);`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Read result সঙ্গে সঙ্গে EOF-এর বিরুদ্ধে পরীক্ষা করা হয়।
- **A option কেন ভুল:** feof read attempt-এর পরে set; extra processing হতে পারে।
- **B option কেন ভুল:** fp non-null থাকলে loop থামে না।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Meaningful condition নয়।
- **Related Concept:** `ch` int হওয়া উচিত।
- **মনে রাখার টিপস:** Read first, test return।


## প্রশ্ন 117 | Topic: Structured Programming > rewind | Difficulty: Medium | Type: Theory

Q. `rewind(fp)` কী করে?

A) Start-এ নেয় ও error indicator clear করে
B) File delete
C) Content reverse
D) Append mode

**সঠিক উত্তর: A) Start-এ নেয় ও error indicator clear করে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Position beginning-এ এবং error state reset।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Delete নয়।
- **C option কেন ভুল:** Content বদলায় না।
- **D option কেন ভুল:** Mode বদলায় না।
- **Related Concept:** `fseek(fp,0,SEEK_SET)`-এর মতো position effect।
- **মনে রাখার টিপস:** Rewind → শুরু।


## প্রশ্ন 118 | Topic: Structured Programming > Binary Size | Difficulty: Hard | Type: Calculation

Q. 100 record, প্রতিটি 32 byte হলে raw data size কত?

A) 320
B) 3200
C) 132
D) 32000

**সঠিক উত্তর: B) 3200**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Calculation

```text
100 × 32 = 3200 byte
```

#### Final Answer

```text
Raw size = 3200 byte
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Count × size।
- **A option কেন ভুল:** 10 record।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Addition।
- **D option কেন ভুল:** Extra zero।
- **Related Concept:** Metadata/padding থাকলে actual file size ভিন্ন হতে পারে।
- **মনে রাখার টিপস:** Records × bytes।


## প্রশ্ন 119 | Topic: Structured Programming > Text vs Binary | Difficulty: Medium | Type: Theory

Q. Text ও binary mode সম্পর্কে কোনটি সঠিক?

A) Binary-তে শুধু int
B) Text file-এ character নেই
C) Text mode-এ newline translation হতে পারে
D) Binary সবসময় ছোট

**সঠিক উত্তর: C) Text mode-এ newline translation হতে পারে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Platform text representation newline translate করতে পারে।
- **A option কেন ভুল:** যেকোনো byte sequence।
- **B option কেন ভুল:** Text character representation।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Size representation-নির্ভর।
- **Related Concept:** Binary raw byte হলেও portability automatic নয়।
- **মনে রাখার টিপস:** Text may translate newline।


## প্রশ্ন 120 | Topic: Structured Programming > fseek | Difficulty: Hard | Type: Code

Q. Zero-based 10th int element-এ file start থেকে যেতে call কোনটি?

A) `fseek(fp,10,SEEK_SET)`
B) `fseek(fp,sizeof(int),SEEK_CUR)`
C) `fseek(fp,9,SEEK_END)`
D) `fseek(fp,10L*sizeof(int),SEEK_SET)`

**সঠিক উত্তর: D) `fseek(fp,10L*sizeof(int),SEEK_SET)`**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Calculation

```text
Target index = 10
Offset = 10 × sizeof(int)
```

#### Final Answer

```text
fseek(fp, 10L*sizeof(int), SEEK_SET)
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Byte offset = index × element size।
- **A option কেন ভুল:** 10 byte, 10 int নয়।
- **B option কেন ভুল:** Current থেকে one int।
- **C option কেন ভুল:** End origin ভুল।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `fseek` offset byte unit।
- **মনে রাখার টিপস:** Element index → byte offset।


## প্রশ্ন 121 | Topic: Structured Programming > Struct Member | Difficulty: Easy | Type: Theory

Q. Structure object-এর member access operator কোনটি?

A) `.`
B) `->`
C) `::`
D) `#`

**সঠিক উত্তর: A) `.`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Direct object-এর member dot দিয়ে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Pointer member access।
- **C option কেন ভুল:** C++ scope resolution।
- **D option কেন ভুল:** Preprocessor marker।
- **Related Concept:** `ptr->x` = `(*ptr).x`।
- **মনে রাখার টিপস:** Object dot, pointer arrow।


## প্রশ্ন 122 | Topic: Structured Programming > Struct Pointer | Difficulty: Medium | Type: Code

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
- **D option কেন ভুল:** Concatenation নয়।
- **Related Concept:** Arrow dereference+member access।
- **মনে রাখার টিপস:** ptr->x মানে (*ptr).x।


## প্রশ্ন 123 | Topic: Structured Programming > Union Storage | Difficulty: Easy | Type: Theory

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
- **মনে রাখার টিপস:** Union = shared।


## প্রশ্ন 124 | Topic: Structured Programming > Struct Copy | Difficulty: Medium | Type: Code

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
- **Related Concept:** Pointer member হলে pointer value shallow copy হয়।
- **মনে রাখার টিপস:** Struct assignment copies members।


## প্রশ্ন 125 | Topic: Structured Programming > typedef | Difficulty: Medium | Type: Theory

Q. `typedef` সম্পর্কে কোনটি সঠিক?

A) Existing type-এর alias
B) সবসময় distinct runtime type
C) Memory double
D) শুধু function

**সঠিক উত্তর: A) Existing type-এর alias**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Existing type-এর alternative name তৈরি করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Representation/type identity নতুন নয়।
- **C option কেন ভুল:** Size বদলায় না।
- **D option কেন ভুল:** বহু type-এ ব্যবহার।
- **Related Concept:** `typedef struct Node Node;`।
- **মনে রাখার টিপস:** Name বদলায়, storage নয়।


## প্রশ্ন 126 | Topic: Structured Programming > Union Size | Difficulty: Hard | Type: Calculation

Q. `int=4,double=8,char=1`, alignment 8 হলে union size কত?

A) 13
B) 8
C) 4
D) 16

**সঠিক উত্তর: B) 8**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Members

```text
int = 4
double = 8
char = 1
```

#### Calculation

```text
Largest = 8
Required alignment = 8
Union size = 8
```

#### Final Answer

```text
Size = 8 byte
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Largest member 8 এবং alignment 8; shared storage 8।
- **A option কেন ভুল:** সব member যোগ।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** শুধু int।
- **D option কেন ভুল:** Extra block।
- **Related Concept:** Exact size implementation-dependent; assumption দেওয়া।
- **মনে রাখার টিপস:** Union ≈ largest member।


## প্রশ্ন 127 | Topic: Structured Programming > Nested Structure | Difficulty: Medium | Type: Theory

Q. Structure-এর member হিসেবে আরেক structure object থাকলে কী?

A) Circular Macro
B) Dynamic Union
C) Nested Structure
D) Recursive Function

**সঠিক উত্তর: C) Nested Structure**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Structure inside structure = nested structure।
- **A option কেন ভুল:** Macro নয়।
- **B option কেন ভুল:** Union নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Function নয়।
- **Related Concept:** Self-referential struct নিজের type-এর pointer রাখতে পারে।
- **মনে রাখার টিপস:** Structure inside structure।


## প্রশ্ন 128 | Topic: Structured Programming > Struct Padding | Difficulty: Hard | Type: Calculation

Q. `struct {char c; int x;}`; char align1, int size/align4, struct align4 হলে size কত?

A) 5
B) 4
C) 6
D) 8

**সঠিক উত্তর: D) 8**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Layout

```text
offset 0 : char c (1 byte)
offset 1-3 : padding (3 byte)
offset 4-7 : int x (4 byte)
```

#### Final Answer

```text
Total size = 8 byte
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** char-এর পর int 4-byte boundary-তে আনতে 3 padding; total 8।
- **A option কেন ভুল:** Padding বাদ।
- **B option কেন ভুল:** শুধু int।
- **C option কেন ভুল:** Padding ভুল।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Member order size বদলাতে পারে।
- **মনে রাখার টিপস:** Invisible padding গণনা করুন।


## প্রশ্ন 129 | Topic: Structured Programming > Bit-field | Difficulty: Medium | Type: Theory

Q. Bit-field member-এর address নেওয়া যায়?

A) Standard C-তে যায় না
B) সবসময় char*
C) Width1 হলে
D) Union হলে

**সঠিক উত্তর: A) Standard C-তে যায় না**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Bit-field আলাদা addressable object নাও হতে পারে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Pointer result নেই।
- **C option কেন ভুল:** Width-নির্ভর exception নেই।
- **D option কেন ভুল:** Union-এও restriction।
- **Related Concept:** Direct sizeof-ও bit-field-এ নয়।
- **মনে রাখার টিপস:** Bit-field addressable নয়।


## প্রশ্ন 130 | Topic: Structured Programming > Union Active Member | Difficulty: Hard | Type: Code

Q. `u.i=10; u.f=2.5f;`-এর পরে সর্বশেষ stored member কোনটি?

A) u.i
B) u.f
C) দুইটি আলাদা storage
D) কোনোটিই নয়

**সঠিক উত্তর: B) u.f**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** শেষ assignment shared storage-এ float representation লিখেছে।
- **A option কেন ভুল:** Integer representation overwrite।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Shared storage।
- **D option কেন ভুল:** u.f assigned।
- **Related Concept:** Non-active member read portability-sensitive।
- **মনে রাখার টিপস:** Union last write wins।


## প্রশ্ন 131 | Topic: OOP > Class | Difficulty: Easy | Type: Theory

Q. OOP-তে Class কী?

A) Object current value
B) শুধু function
C) Object blueprint
D) Machine code

**সঠিক উত্তর: C) Object blueprint**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Class object-এর state ও behavior structure নির্ধারণ করে।
- **A option কেন ভুল:** Object state।
- **B option কেন ভুল:** Class method-এর চেয়ে বড় abstraction।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Machine instruction নয়।
- **Related Concept:** Object class-এর instance।
- **মনে রাখার টিপস:** Class নকশা, object বাস্তব।


## প্রশ্ন 132 | Topic: OOP > Object | Difficulty: Medium | Type: Theory

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
- **মনে রাখার টিপস:** Instance = Object।


## প্রশ্ন 133 | Topic: OOP > Encapsulation | Difficulty: Easy | Type: Theory

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
- **মনে রাখার টিপস:** Capsule-এর মতো আবদ্ধ।


## প্রশ্ন 134 | Topic: OOP > Abstraction | Difficulty: Medium | Type: Scenario

Q. Driver controls car কিন্তু engine detail জানে না—কোন concept?

A) Inheritance
B) Abstraction
C) Multiple Dispatch
D) Recursion

**সঠিক উত্তর: B) Abstraction**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Essential interface visible, internal complexity hidden।
- **A option কেন ভুল:** Subtype relation নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Method dispatch নয়।
- **D option কেন ভুল:** Self-call নয়।
- **Related Concept:** Interface abstraction প্রকাশ করে।
- **মনে রাখার টিপস:** What visible, how hidden।


## প্রশ্ন 135 | Topic: OOP > Constructor | Difficulty: Medium | Type: Theory

Q. Constructor-এর প্রধান উদ্দেশ্য কী?

A) Compile
B) Class delete
C) Object initialize
D) সব method private

**সঠিক উত্তর: C) Object initialize**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Object creation-এর সময় valid initial state/resource setup।
- **A option কেন ভুল:** Compiler কাজ।
- **B option কেন ভুল:** Destructor cleanup।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Access policy নয়।
- **Related Concept:** Constructor-এর return type সাধারণত থাকে না।
- **মনে রাখার টিপস:** Construction → initialization।


## প্রশ্ন 136 | Topic: OOP > Destructor | Difficulty: Medium | Type: Theory

Q. Destructor-এর প্রধান কাজ কী?

A) Name নির্বাচন
B) Parent create
C) Overload
D) Lifetime শেষে cleanup

**সঠিক উত্তর: D) Lifetime শেষে cleanup**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Owned resource release ও final cleanup।
- **A option কেন ভুল:** Naming নয়।
- **B option কেন ভুল:** Inheritance নয়।
- **C option কেন ভুল:** Overloading নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** RAII language-এ গুরুত্বপূর্ণ।
- **মনে রাখার টিপস:** Destruction → cleanup।


## প্রশ্ন 137 | Topic: OOP > Interface | Difficulty: Medium | Type: Theory

Q. Interface প্রধানত কী প্রকাশ করে?

A) Operation contract
B) Physical address
C) শুধু private data
D) Executable format

**সঠিক উত্তর: A) Operation contract**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Type কী service দেবে তা নির্ধারণ করে, implementation detail নয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Memory address নয়।
- **C option কেন ভুল:** Data storage নয়।
- **D option কেন ভুল:** File format নয়।
- **Related Concept:** একাধিক class একই interface implement করতে পারে।
- **মনে রাখার টিপস:** Interface = what, implementation = how।


## প্রশ্ন 138 | Topic: OOP > Composition | Difficulty: Hard | Type: Scenario

Q. House destroy হলে owned Room-গুলোর lifetime-ও শেষ—সম্পর্ক কোনটি?

A) Association
B) Composition
C) Weak Dependency
D) Overloading

**সঠিক উত্তর: B) Composition**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Strong whole-part ownership ও lifetime dependency Composition।
- **A option কেন ভুল:** General association ownership guarantee নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Standard whole-part term নয়।
- **D option কেন ভুল:** Method signature নয়।
- **Related Concept:** Aggregation-এ part independently থাকতে পারে।
- **মনে রাখার টিপস:** Strong has-a → Composition।


## প্রশ্ন 139 | Topic: OOP > Package/Namespace | Difficulty: Medium | Type: Theory

Q. Package/Namespace-এর প্রধান সুবিধা কী?

A) CPU speed
B) Object size zero
C) Related type organize ও name collision কমানো
D) সব class abstract

**সঠিক উত্তর: C) Related type organize ও name collision কমানো**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Logical grouping ও qualified naming conflict কমায়।
- **A option কেন ভুল:** Hardware speed নয়।
- **B option কেন ভুল:** Memory size নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Abstract বাধ্যতামূলক নয়।
- **Related Concept:** Java package; C++/C# namespace।
- **মনে রাখার টিপস:** নামের সংগঠিত এলাকা।


## প্রশ্ন 140 | Topic: OOP > Encapsulation vs Abstraction | Difficulty: Hard | Type: Theory

Q. সঠিক পার্থক্য কোনটি?

A) একই
B) Encapsulation শুধু inheritance
C) Abstraction memory allocation
D) Encapsulation bundle/control; Abstraction essential interface

**সঠিক উত্তর: D) Encapsulation bundle/control; Abstraction essential interface**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Encapsulation packaging/access control; abstraction relevant view ও hidden detail।
- **A option কেন ভুল:** Related হলেও identical নয়।
- **B option কেন ভুল:** Inheritance নয়।
- **C option কেন ভুল:** Allocation নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Private data বনাম interface view।
- **মনে রাখার টিপস:** Wrap বনাম hide detail।


## প্রশ্ন 141 | Topic: OOP > Inheritance | Difficulty: Easy | Type: Theory

Q. Existing class-এর বৈশিষ্ট্য নিয়ে নতুন class তৈরি কোন mechanism?

A) Inheritance
B) Encapsulation
C) Parsing
D) Linking

**সঠিক উত্তর: A) Inheritance**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Derived class base class specialize/reuse করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Bundle/access।
- **C option কেন ভুল:** Syntax analysis।
- **D option কেন ভুল:** Object code combine।
- **Related Concept:** Child override করতে পারে।
- **মনে রাখার টিপস:** Parent থেকে child।


## প্রশ্ন 142 | Topic: OOP > Overloading | Difficulty: Medium | Type: Theory

Q. Method Overloading কী?

A) Parent method delete
B) Same name, different parameter list
C) সব একই body
D) শুধু return type change

**সঠিক উত্তর: B) Same name, different parameter list**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Parameter number/type/order আলাদা থাকে।
- **A option কেন ভুল:** Deletion নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Signature variation নেই।
- **D option কেন ভুল:** শুধু return type সাধারণত যথেষ্ট নয়।
- **Related Concept:** Compile-time polymorphism।
- **মনে রাখার টিপস:** Same name, different parameters।


## প্রশ্ন 143 | Topic: OOP > Overriding | Difficulty: Easy | Type: Theory

Q. Derived class parent method-এর নতুন implementation দিলে কী?

A) Encapsulation
B) Aggregation
C) Overriding
D) সবসময় Hiding

**সঠিক উত্তর: C) Overriding**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Inherited method compatible signature-এ redefine করা হয়।
- **A option কেন ভুল:** Access concept।
- **B option কেন ভুল:** Whole-part।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Hiding language-specific ভিন্ন।
- **Related Concept:** Runtime polymorphism হতে পারে।
- **মনে রাখার টিপস:** Child replaces behavior।


## প্রশ্ন 144 | Topic: OOP > Dynamic Binding | Difficulty: Medium | Type: Theory

Q. Runtime actual object type দেখে overridden method নির্বাচন কী?

A) Static Allocation
B) Lexical Analysis
C) Early Preprocessing
D) Dynamic Binding

**সঠিক উত্তর: D) Dynamic Binding**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Call target runtime object type-এ resolve হয়।
- **A option কেন ভুল:** Memory concern।
- **B option কেন ভুল:** Token analysis।
- **C option কেন ভুল:** Preprocessor নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Overloading static; overriding dynamic হতে পারে।
- **মনে রাখার টিপস:** Runtime decision → dynamic।


## প্রশ্ন 145 | Topic: OOP > Public | Difficulty: Easy | Type: Theory

Q. `public` member সম্পর্কে সাধারণ statement?

A) External code থেকেও access
B) শুধু constructor
C) শুধু derived
D) কেউ access নয়

**সঠিক উত্তর: A) External code থেকেও access**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Visibility rule অনুযায়ী class-এর বাইরে accessible।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Constructor-only নয়।
- **C option কেন ভুল:** Protected-এর কাছাকাছি।
- **D option কেন ভুল:** Public-এর বিপরীত।
- **Related Concept:** সব data public করলে encapsulation দুর্বল।
- **মনে রাখার টিপস:** Public = বাইরে visible।


## প্রশ্ন 146 | Topic: OOP > Protected | Difficulty: Medium | Type: Theory

Q. `protected` member-এর সাধারণ উদ্দেশ্য?

A) শুধু global
B) Class ও derived class access
C) সব থেকে hidden
D) Constant

**সঠিক উত্তর: B) Class ও derived class access**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Class family-এর access support করে।
- **A option কেন ভুল:** Global বিশেষাধিকার নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Derived access করতে পারে।
- **D option কেন ভুল:** Const নয়।
- **Related Concept:** Exact package rule language-dependent।
- **মনে রাখার টিপস:** Protected = family।


## প্রশ্ন 147 | Topic: OOP > Abstract Class | Difficulty: Medium | Type: Theory

Q. Abstract Class-এর বৈশিষ্ট্য কোনটি?

A) Method নেই
B) সবসময় final
C) সাধারণত direct instantiate নয়
D) শুধু primitive data

**সঠিক উত্তর: C) সাধারণত direct instantiate নয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Incomplete base abstraction; subclass-এর জন্য।
- **A option কেন ভুল:** Concrete method থাকতে পারে।
- **B option কেন ভুল:** Final inheritance বন্ধ করে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Fields/methods নানা type।
- **Related Concept:** Abstract ও concrete method একসঙ্গে থাকতে পারে।
- **মনে রাখার টিপস:** Incomplete blueprint।


## প্রশ্ন 148 | Topic: OOP > Multiple Inheritance | Difficulty: Hard | Type: Theory

Q. Diamond Problem কখন?

A) No parent
B) Private constructor
C) Overloading
D) Common ancestor দুই path-এ inherited

**সঠিক উত্তর: D) Common ancestor দুই path-এ inherited**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একই base member দুই inheritance route দিয়ে ambiguous হয়।
- **A option কেন ভুল:** Diamond নয়।
- **B option কেন ভুল:** Visibility issue।
- **C option কেন ভুল:** Signature issue।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** C++ virtual inheritance সমাধান করতে পারে।
- **মনে রাখার টিপস:** Common base, two paths।


## প্রশ্ন 149 | Topic: OOP > Liskov Substitution | Difficulty: Hard | Type: Scenario

Q. Bird base-এর জায়গায় Penguin ব্যবহার করে fly contract ভাঙলে কোন principle লঙ্ঘিত?

A) Liskov Substitution
B) Single Compilation
C) Token Replacement
D) File Locality

**সঠিক উত্তর: A) Liskov Substitution**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Subtype base contract রক্ষা করে substitutable হওয়া উচিত।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Standard OO principle নয়।
- **C option কেন ভুল:** Preprocessing নয়।
- **D option কেন ভুল:** File organization নয়।
- **Related Concept:** Inheritance behavioral relation।
- **মনে রাখার টিপস:** Child must honor parent contract।


## প্রশ্ন 150 | Topic: OOP > Polymorphism | Difficulty: Easy | Type: Theory

Q. এক interface-এ বিভিন্ন object ভিন্ন behavior দিলে কী?

A) Encapsulation
B) Polymorphism
C) Compilation
D) Aggregation

**সঠিক উত্তর: B) Polymorphism**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একই operation call object অনুযায়ী many forms নেয়।
- **A option কেন ভুল:** Bundle/access।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Translation।
- **D option কেন ভুল:** Whole-part।
- **Related Concept:** Overloading compile-time, overriding runtime।
- **মনে রাখার টিপস:** One interface, many forms।


## Batch 03 Quality Summary

```text
Questions          = 50
Theory/Scenario    = 35
Calculation/Code   = 15
Coverage           = Console/File I/O, Struct/Union, OOP Fundamentals
Math format        = Plain-text aligned
```

---

# Batch 04 — Question 151–180

**Section:** Structured & Object-Oriented Programming  
**Coverage:** Advanced OOP, Design Principles, C Safety, Portability ও Final Review  
**Composition:** Theory/Scenario 30


# Chapter Theory 04: Advanced OOP ও C Safety

## Advanced OOP

Inheritance একটি সত্যিকারের `is-a` relationship প্রকাশ করা উচিত। `has-a` relation হলে Composition বা Aggregation বেশি উপযোগী হতে পারে।

```text
Overloading = Same name, different parameter list
Overriding  = Child class redefines inherited method
Static Binding  = Compile-time selection
Dynamic Binding = Runtime selection
```

ভালো OO design সাধারণত High Cohesion ও Low Coupling চায়।

## Selected Design Principles

- **SRP:** একটি class-এর পরিবর্তনের একটি প্রধান কারণ।
- **OCP:** Extension-এর জন্য open, stable modification-এর জন্য closed।
- **LSP:** Subtype base type-এর স্থানে contract না ভেঙে ব্যবহারযোগ্য।
- **DIP:** High-level module concrete low-level detail নয়, abstraction-এর ওপর নির্ভর করবে।

## Association Family

- Association — general relation
- Aggregation — weak whole-part; part independently exist করতে পারে
- Composition — strong ownership; part lifetime whole-এর সঙ্গে যুক্ত

## C Behavior Categories

- Defined Behavior — Standard outcome নির্ধারণ করে
- Implementation-Defined — implementation choice document করে
- Unspecified — allowed choice, documentation বাধ্যতামূলক নয়
- Undefined Behavior — Standard কোনো requirement দেয় না

Common UB: null dereference, out-of-bounds, signed overflow, string literal modification, use-after-free, double free।

## Memory Safety

- Memory Leak — allocated memory release না করা
- Dangling Pointer — target lifetime শেষ
- Use-after-free — free-এর পরে access
- Double Free — একই allocation দুইবার release
- Buffer Overflow — capacity-এর বাইরে write

`free(NULL)` নিরাপদ, কিন্তু non-NULL dangling pointer free করা নিরাপদ নয়।


## প্রশ্ন 151 | Topic: OOP > Inheritance Relationship | Difficulty: Easy | Type: Theory

Q. কোন relationship সাধারণত Inheritance বোঝায়?

A) has-a
B) is-a
C) uses-a
D) part-of

**সঠিক উত্তর: B) is-a**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Derived class base class-এর বিশেষায়িত ধরন হলে `is-a` relation।
- **A option কেন ভুল:** Composition/Aggregation।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Dependency বোঝাতে পারে।
- **D option কেন ভুল:** Whole-part relation।
- **Related Concept:** `Dog is an Animal`।
- **মনে রাখার টিপস:** Child যদি parent-এর ধরন হয়।


## প্রশ্ন 152 | Topic: OOP > Composition | Difficulty: Easy | Type: Theory

Q. `Car`-এর owned `Engine` থাকলে relation কী?

A) Composition
B) Overloading
C) Generalization
D) Dynamic Binding

**সঠিক উত্তর: A) Composition**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Strong `has-a` ownership Composition।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Method signature।
- **C option কেন ভুল:** Inheritance abstraction।
- **D option কেন ভুল:** Runtime dispatch।
- **Related Concept:** Lifetime ownership শক্তিশালী।
- **মনে রাখার টিপস:** Strong has-a → Composition।


## প্রশ্ন 153 | Topic: OOP > Overloading | Difficulty: Medium | Type: Theory

Q. Method Overloading-এর জন্য সাধারণত কী পরিবর্তিত হয়?

A) শুধু return type
B) শুধু access
C) Parameter list
D) শুধু body

**সঠিক উত্তর: C) Parameter list**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Parameter count/type/order ভিন্ন হয়।
- **A option কেন ভুল:** Return type alone যথেষ্ট নয়।
- **B option কেন ভুল:** Signature difference নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Duplicate definition হতে পারে।
- **Related Concept:** Compile-time resolution।
- **মনে রাখার টিপস:** Same name, different parameters।


## প্রশ্ন 154 | Topic: OOP > Overriding | Difficulty: Medium | Type: Theory

Q. Overriding কখন ঘটে?

A) এক class-এ parameter ভিন্ন
B) Local shadowing
C) Unrelated same name
D) Derived class inherited method redefines

**সঠিক উত্তর: D) Derived class inherited method redefines**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Parent-child hierarchy-তে compatible method implementation বদলায়।
- **A option কেন ভুল:** Overloading।
- **B option কেন ভুল:** Variable shadowing।
- **C option কেন ভুল:** Override নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Runtime polymorphism possible।
- **মনে রাখার টিপস:** Child নতুন behavior।


## প্রশ্ন 155 | Topic: OOP > Static Binding | Difficulty: Medium | Type: Theory

Q. Compile-time method resolution কী?

A) Static Binding
B) Dynamic Binding
C) Lazy Loading
D) Message Queue

**সঠিক উত্তর: A) Static Binding**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Call target compilation-এর সময় নির্ধারিত।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Runtime।
- **C option কেন ভুল:** Resource loading।
- **D option কেন ভুল:** Communication mechanism।
- **Related Concept:** Overloading সাধারণত static।
- **মনে রাখার টিপস:** Static = আগে।


## প্রশ্ন 156 | Topic: OOP > Dynamic Binding | Difficulty: Medium | Type: Scenario

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
- **C option কেন ভুল:** Memory allocation নয়।
- **D option কেন ভুল:** Access control নয়।
- **Related Concept:** Virtual dispatch।
- **মনে রাখার টিপস:** Runtime object decides।


## প্রশ্ন 157 | Topic: OOP > Abstract Class | Difficulty: Medium | Type: Theory

Q. Abstract Class সম্পর্কে কোনটি সঠিক?

A) Implemented method নেই
B) Multiple inheritance নিষিদ্ধ
C) সাধারণত direct instantiate নয়
D) Field নেই

**সঠিক উত্তর: C) সাধারণত direct instantiate নয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** অসম্পূর্ণ base abstraction হওয়ায় direct object তৈরি করা যায় না।
- **A option কেন ভুল:** Concrete method থাকতে পারে।
- **B option কেন ভুল:** Language-specific নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** State থাকতে পারে।
- **Related Concept:** Subclass common implementation পায়।
- **মনে রাখার টিপস:** Abstract = incomplete base।


## প্রশ্ন 158 | Topic: OOP > Interface | Difficulty: Medium | Type: Theory

Q. Interface-এর design সুবিধা কোনটি?

A) Object size equal
B) Implementation পরিবর্তন নিষিদ্ধ
C) সব field public
D) Contract দিয়ে loose coupling

**সঠিক উত্তর: D) Contract দিয়ে loose coupling**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Client concrete implementation-এর বদলে abstraction-এর ওপর নির্ভর করে।
- **A option কেন ভুল:** Memory size নয়।
- **B option কেন ভুল:** Implementation change সহজ করে।
- **C option কেন ভুল:** Public data নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** DIP সমর্থন করে।
- **মনে রাখার টিপস:** Depend on contract।


## প্রশ্ন 159 | Topic: OOP > Cohesion | Difficulty: Medium | Type: Theory

Q. High Cohesion কী?

A) Module responsibility পরস্পর related
B) সব class internal data access
C) এক class সব কাজ
D) সব global state

**সঠিক উত্তর: A) Module responsibility পরস্পর related**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Focused module-এর element একই purpose-এর দিকে কাজ করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** High coupling।
- **C option কেন ভুল:** Low cohesion।
- **D option কেন ভুল:** Shared dependency।
- **Related Concept:** Maintainability বাড়ে।
- **মনে রাখার টিপস:** One focused responsibility।


## প্রশ্ন 160 | Topic: OOP > Coupling | Difficulty: Medium | Type: Theory

Q. Low Coupling-এর সুবিধা কী?

A) সব class merge
B) এক component change-এর ripple কম
C) সব global
D) Inheritance নিষিদ্ধ

**সঠিক উত্তর: B) এক component change-এর ripple কম**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Dependency কম হলে change/test/reuse সহজ।
- **A option কেন ভুল:** Responsibility মিশে যায়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Dependency বাড়ে।
- **D option কেন ভুল:** Definition নয়।
- **Related Concept:** Interface ও DI coupling কমায়।
- **মনে রাখার টিপস:** কম dependency।


## প্রশ্ন 161 | Topic: OOP > SRP | Difficulty: Medium | Type: Scenario

Q. এক class report, DB, email ও authentication সব করছে—কোন principle ভাঙে?

A) ISP
B) LSP
C) Single Responsibility
D) Encapsulation সম্পূর্ণ

**সঠিক উত্তর: C) Single Responsibility**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Unrelated multiple responsibility ও multiple reasons to change।
- **A option কেন ভুল:** Large interface split concern।
- **B option কেন ভুল:** Subtype concern।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Encapsulation থাকলেও responsibility সমস্যা।
- **Related Concept:** Services ভাগ করা যায়।
- **মনে রাখার টিপস:** One main reason to change।


## প্রশ্ন 162 | Topic: OOP > OCP | Difficulty: Hard | Type: Theory

Q. Open-Closed Principle কী?

A) সব field public
B) Extension open, modification closed
C) Source কখনো বদলাবে না
D) Open-source only

**সঠিক উত্তর: B) Extension open, modification closed**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** নতুন behavior extension-এ যোগ, stable code কম বদলানো।
- **A option কেন ভুল:** Encapsulation দুর্বল।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Absolute ban নয়।
- **D option কেন ভুল:** Licensing নয়।
- **Related Concept:** Strategy/polymorphism সহায়ক।
- **মনে রাখার টিপস:** Extend, don't repeatedly edit stable core।


## প্রশ্ন 163 | Topic: OOP > LSP | Difficulty: Hard | Type: Scenario

Q. Subclass parent contract ভাঙলে কোন principle লঙ্ঘিত?

A) DIP
B) SRP
C) OCP
D) Liskov Substitution

**সঠিক উত্তর: D) Liskov Substitution**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Subtype base-এর জায়গায় ব্যবহারযোগ্য থাকতে হবে।
- **A option কেন ভুল:** Abstraction dependency।
- **B option কেন ভুল:** Responsibility।
- **C option কেন ভুল:** Extension policy।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Precondition শক্তিশালী না করা।
- **মনে রাখার টিপস:** Child behaves as valid parent।


## প্রশ্ন 164 | Topic: OOP > DIP | Difficulty: Hard | Type: Theory

Q. High-level module কিসের ওপর নির্ভর করবে?

A) Abstraction
B) Global variable
C) Concrete private field
D) Hardware register

**সঠিক উত্তর: A) Abstraction**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** High ও low-level module abstraction-এর ওপর depend করলে coupling কমে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Global dependency।
- **C option কেন ভুল:** Concrete detail-এর বিপরীত।
- **D option কেন ভুল:** General principle নয়।
- **Related Concept:** Interface/DI বাস্তবায়ন সহায়ক।
- **মনে রাখার টিপস:** Depend on abstractions।


## প্রশ্ন 165 | Topic: OOP > Aggregation | Difficulty: Hard | Type: Scenario

Q. University destroy হলেও Professor independently থাকে—relation?

A) Inheritance
B) Composition
C) Aggregation
D) Overriding

**সঠিক উত্তর: C) Aggregation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Weak whole-part এবং independent lifetime।
- **A option কেন ভুল:** Subtype নয়।
- **B option কেন ভুল:** Strong lifetime ownership।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Method relation নয়।
- **Related Concept:** Weak has-a।
- **মনে রাখার টিপস:** Whole gone, part survives।


## প্রশ্ন 166 | Topic: C Safety > Undefined Behavior | Difficulty: Easy | Type: Theory

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
- **মনে রাখার টিপস:** NULL দেখা যায়, dereference নয়।


## প্রশ্ন 167 | Topic: C Portability > Implementation-Defined | Difficulty: Medium | Type: Theory

Q. Plain `char` signed না unsigned—কী behavior?

A) Implementation-defined
B) Undefined
C) Syntax Error
D) Linker-defined

**সঠিক উত্তর: A) Implementation-defined**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Implementation choice নেয় ও document করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Invalid operation নয়।
- **C option কেন ভুল:** Syntax valid।
- **D option কেন ভুল:** Linker property নয়।
- **Related Concept:** Explicit `signed char`/`unsigned char` ব্যবহার।
- **মনে রাখার টিপস:** Plain char signedness assume নয়।


## প্রশ্ন 168 | Topic: C Safety > Signed Overflow | Difficulty: Medium | Type: Theory

Q. Signed integer range-এর বাইরে result গেলে কী?

A) সবসময় zero
B) Saturate
C) Undefined Behavior
D) Auto long long

**সঠিক উত্তর: C) Undefined Behavior**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Signed overflow Standard-defined wrap নয়।
- **A option কেন ভুল:** Guarantee নেই।
- **B option কেন ভুল:** Saturating arithmetic নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Type auto widen নয়।
- **Related Concept:** Unsigned modulo wrap।
- **মনে রাখার টিপস:** Unsigned wraps; signed overflow UB।


## প্রশ্ন 169 | Topic: C Memory > Memory Leak | Difficulty: Easy | Type: Theory

Q. Allocated memory release না করলে কী?

A) Memory Leak
B) Syntax Error
C) Integer Overflow
D) Name Collision

**সঠিক উত্তর: A) Memory Leak**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Unneeded allocation occupied থাকে বা reference হারায়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Compile হতে পারে।
- **C option কেন ভুল:** Integer range নয়।
- **D option কেন ভুল:** Identifier conflict নয়।
- **Related Concept:** Ownership ও release plan দরকার।
- **মনে রাখার টিপস:** Allocate করলে free।


## প্রশ্ন 170 | Topic: C Memory > Use-after-free | Difficulty: Hard | Type: Scenario

Q. `free(p);`-এর পরে `*p` access কী?

A) Safe read
B) Auto reallocation
C) Leak মাত্র
D) Use-after-free ও UB

**সঠিক উত্তর: D) Use-after-free ও UB**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Object lifetime শেষ; p dangling।
- **A option কেন ভুল:** Read/write দুটো unsafe।
- **B option কেন ভুল:** Auto allocation নয়।
- **C option কেন ভুল:** Memory released, invalid access মূল সমস্যা।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `p=NULL` accidental access কমায়।
- **মনে রাখার টিপস:** Free-এর পরে object নেই।


## প্রশ্ন 171 | Topic: C Memory > Double Free | Difficulty: Hard | Type: Theory

Q. এক allocation দুইবার free করলে?

A) Program দ্রুত
B) Undefined Behavior
C) সবসময় harmless
D) নতুন block

**সঠিক উত্তর: B) Undefined Behavior**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রথম free-এর পর allocation invalid; second free UB।
- **A option কেন ভুল:** Release পুনরাবৃত্তি valid নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Heap corruption হতে পারে।
- **D option কেন ভুল:** free allocate নয়।
- **Related Concept:** `free(NULL)` safe, dangling non-null নয়।
- **মনে রাখার টিপস:** One allocation, one free।


## প্রশ্ন 172 | Topic: C Safety > Buffer Overflow | Difficulty: Medium | Type: Theory

Q. Buffer boundary-এর বাইরে write কী?

A) Buffer Overflow
B) Encapsulation
C) Static Binding
D) Fragmentation

**সঠিক উত্তর: A) Buffer Overflow**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Adjacent memory corrupt হতে পারে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** OOP concept।
- **C option কেন ভুল:** Dispatch।
- **D option কেন ভুল:** Storage layout।
- **Related Concept:** `gets`, unbounded `%s`, `strcpy` risk।
- **মনে রাখার টিপস:** Capacity মানুন।


## প্রশ্ন 173 | Topic: C Lifetime > Local Address Return | Difficulty: Hard | Type: Theory

Q. Function local automatic variable-এর address return করা unsafe কেন?

A) Global হয়
B) Pointer arithmetic নিষিদ্ধ
C) Return-এর পর lifetime শেষ
D) Address NULL

**সঠিক উত্তর: C) Return-এর পর lifetime শেষ**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Returned pointer dangling হয়।
- **A option কেন ভুল:** Global হয় না।
- **B option কেন ভুল:** মূল সমস্যা lifetime।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Non-null দেখাতে পারে।
- **Related Concept:** Caller storage/static local alternative।
- **মনে রাখার টিপস:** Local address বাইরে নয়।


## প্রশ্ন 174 | Topic: C Function > Pointer Passing | Difficulty: Medium | Type: Theory

Q. Pointer argument পাঠালে আসলে কী pass হয়?

A) Original pointer variable
B) Pointer value-এর copy
C) Pointer name
D) Deep copy

**সঠিক উত্তর: B) Pointer value-এর copy**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** C call by value; address value copy হয়।
- **A option কেন ভুল:** Caller variable-এর reference নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Identifier runtime data নয়।
- **D option কেন ভুল:** Pointed memory copy হয় না।
- **Related Concept:** `T**` দিয়ে caller pointer বদলানো যায়।
- **মনে রাখার টিপস:** Pointer pass-ও value pass।


## প্রশ্ন 175 | Topic: C Function > Function Pointer | Difficulty: Medium | Type: Theory

Q. Function Pointer-এর সাধারণ ব্যবহার?

A) Array resize
B) Header encrypt
C) Callback
D) Padding remove

**সঠিক উত্তর: C) Callback**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Function address argument হিসেবে দিয়ে later invocation callback।
- **A option কেন ভুল:** Memory resize নয়।
- **B option কেন ভুল:** Encryption নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Alignment নয়।
- **Related Concept:** `qsort` comparator।
- **মনে রাখার টিপস:** Functionকে data-এর মতো pass।


## প্রশ্ন 176 | Topic: C File > Error Check | Difficulty: Easy | Type: Theory

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
- **D option কেন ভুল:** FILE* integer নয়।
- **Related Concept:** `perror` diagnostic।
- **মনে রাখার টিপস:** Open, check, use।


## প্রশ্ন 177 | Topic: C Struct > Padding | Difficulty: Medium | Type: Theory

Q. Struct size member sum-এর চেয়ে বড় কেন?

A) Recursion
B) Linker function যোগ
C) Member duplicate
D) Alignment ও Padding

**সঠিক উত্তর: D) Alignment ও Padding**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Hardware alignment পূরণে compiler gap যোগ করে।
- **A option কেন ভুল:** Layout নয়।
- **B option কেন ভুল:** Linker member যোগ করে না।
- **C option কেন ভুল:** Duplicate নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Member order optimization।
- **মনে রাখার টিপস:** Invisible padding।


## প্রশ্ন 178 | Topic: C Struct/Union > Memory | Difficulty: Medium | Type: Theory

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
- **মনে রাখার টিপস:** Struct together, union shared।


## প্রশ্ন 179 | Topic: C Bit-field > Portability | Difficulty: Hard | Type: Theory

Q. Bit-field layout portable নয় কেন?

A) Runtime-only
B) Allocation order/alignment implementation-dependent
C) সবসময় pointer
D) শুধু file

**সঠিক উত্তর: B) Allocation order/alignment implementation-dependent**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Compiler/platform packing ও ordering ভিন্ন হতে পারে।
- **A option কেন ভুল:** Declaration-time layout।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Pointer নয়।
- **D option কেন ভুল:** Memory member।
- **Related Concept:** Hardware mapping-এ documentation প্রয়োজন।
- **মনে রাখার টিপস:** Compact but not fully portable।


## প্রশ্ন 180 | Topic: C Design > Modularity | Difficulty: Hard | Type: Scenario

Q. Reusable function, limited file-scope data, header-এ প্রয়োজনীয় declaration—কোন quality উন্নত?

A) CPU clock
B) File extension
C) Modularity ও Maintainability
D) সব runtime error শেষ

**সঠিক উত্তর: C) Modularity ও Maintainability**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Responsibilities ও interface আলাদা হওয়ায় code test/change সহজ।
- **A option কেন ভুল:** Hardware speed নয়।
- **B option কেন ভুল:** Quality metric নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** সব error guarantee নয়।
- **Related Concept:** Separate compilation ও information hiding।
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

# Batch 05 — Question 181–230

**Section:** Introduction to Software Engineering  
**Coverage:** Fundamentals, Software Crisis, SDLC, Quality Attributes এবং Development Models  
**Composition:** Theory/Scenario 44, Calculation 6


# Chapter Theory 05: Software Engineering Fundamentals, Quality ও SDLC Models

## Software Engineering ও Software Crisis

Software Engineering হলো systematic, disciplined ও measurable approach-এ software development, operation, maintenance ও evolution পরিচালনা। এটি শুধু coding নয়; requirement, design, testing, deployment, quality, project ও risk management অন্তর্ভুক্ত।

Software Crisis-এর লক্ষণ:

- সময় ও budget overrun
- Requirement mismatch
- Low reliability
- Maintenance difficulty
- Large-system complexity
- Poor estimation ও coordination

## SDLC

একটি সাধারণ lifecycle:

```text
Planning/Feasibility
        ↓
Requirements
        ↓
Design
        ↓
Implementation
        ↓
Testing
        ↓
Deployment
        ↓
Maintenance
```

Verification: specification অনুযায়ী ঠিকভাবে তৈরি করছি কি?  
Validation: user-এর প্রয়োজনীয় সঠিক product তৈরি করছি কি?

## Maintenance

- Corrective — defect fix
- Adaptive — environment change
- Perfective — feature/performance improvement
- Preventive — future maintenance সহজ করা

## Software Quality

গুরুত্বপূর্ণ quality attributes:

- Correctness
- Reliability
- Robustness
- Usability
- Efficiency
- Maintainability
- Portability
- Reusability
- Testability

Availability:

```text
Availability = MTTF / (MTTF + MTTR)
```

Defect Density:

```text
Defect Density = Defects / Software Size
```

## Development Models

- Waterfall — sequential; stable requirement
- V-Model — development phase-এর সঙ্গে corresponding test phase
- Spiral — risk-driven iterative
- Agile — short iteration, feedback, change responsiveness
- RAD — rapid tool/prototype/component-driven
- Prototype — unclear requirement
- Incremental — usable capability ধাপে ধাপে
- Iterative — solution বারবার refine


## প্রশ্ন 181 | Topic: Software Engineering > Definition | Difficulty: Easy | Type: Theory

Q. Software Engineering-এর সবচেয়ে যথাযথ সংজ্ঞা কোনটি?

A) শুধু programming শেখা
B) Software lifecycle-এ systematic disciplined engineering approach
C) শুধু hardware design
D) শুধু executable তৈরি

**সঠিক উত্তর: B) Software lifecycle-এ systematic disciplined engineering approach**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Requirement থেকে maintenance পর্যন্ত structured ও measurable practice Software Engineering।
- **A option কেন ভুল:** Programming একটি অংশ মাত্র।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Hardware circuit design নয়।
- **D option কেন ভুল:** Executable lifecycle-এর ছোট অংশ।
- **Related Concept:** Process, people, product ও quality সব অন্তর্ভুক্ত।
- **মনে রাখার টিপস:** Code + Process + Quality + Management।


## প্রশ্ন 182 | Topic: Software Engineering > Software Crisis | Difficulty: Easy | Type: Theory

Q. Software Crisis প্রধানত কী নির্দেশ করে?

A) Delay, excessive cost, low quality, maintenance difficulty
B) Power failure
C) Language কমে যাওয়া
D) সব software open source

**সঠিক উত্তর: A) Delay, excessive cost, low quality, maintenance difficulty**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Large software project-এর schedule, budget, quality ও complexity failure-এর সমষ্টি।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Hardware power issue।
- **C option কেন ভুল:** Language count নয়।
- **D option কেন ভুল:** Licensing নয়।
- **Related Concept:** Software Engineering Crisis মোকাবিলায় বিকশিত।
- **মনে রাখার টিপস:** Late + costly + defective।


## প্রশ্ন 183 | Topic: Software Engineering > Crisis Causes | Difficulty: Medium | Type: Theory

Q. Software Crisis-এর গুরুত্বপূর্ণ কারণ কোনটি?

A) সব program-এ comment
B) Memory বাড়া
C) UI সহজ হওয়া
D) Software size ও complexity দ্রুত বৃদ্ধি

**সঠিক উত্তর: D) Software size ও complexity দ্রুত বৃদ্ধি**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Ad-hoc technique বড় system-এর coordination ও complexity সামলাতে ব্যর্থ হয়।
- **A option কেন ভুল:** Comment সাহায্য করতে পারে।
- **B option কেন ভুল:** Memory increase crisis নয়।
- **C option কেন ভুল:** Usability উন্নতি।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Complexity disciplined process দাবি করে।
- **মনে রাখার টিপস:** System বড় → coordination কঠিন।


## প্রশ্ন 184 | Topic: Software Engineering > Product vs Project | Difficulty: Easy | Type: Theory

Q. Software Product ও Project-এর পার্থক্য কী?

A) Product শুধু code, Project document
B) Product temporary, Project permanent
C) Product deliverable; Project time-bound effort
D) কোনো পার্থক্য নেই

**সঠিক উত্তর: C) Product deliverable; Project time-bound effort**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Project product তৈরির temporary initiative; product operation-এ দীর্ঘস্থায়ী হতে পারে।
- **A option কেন ভুল:** দুটিই বহু artifact ধারণ করে।
- **B option কেন ভুল:** উল্টো।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Concept আলাদা।
- **Related Concept:** Project success ও product success এক নয়।
- **মনে রাখার টিপস:** Project builds, Product serves।


## প্রশ্ন 185 | Topic: Software Engineering > Multidisciplinary | Difficulty: Hard | Type: Scenario

Q. Algorithm-এ CS, schedule-এ Project Management, UI-তে HCI ব্যবহার কী দেখায়?

A) SE বিচ্ছিন্ন
B) SE multidisciplinary
C) SE শুধু management
D) SE শুধু UI

**সঠিক উত্তর: B) SE multidisciplinary**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Software Engineering technical, managerial ও human discipline integrate করে।
- **A option কেন ভুল:** বিভিন্ন knowledge প্রয়োজন।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Management এক অংশ।
- **D option কেন ভুল:** UI এক অংশ।
- **Related Concept:** Security/domain knowledge-ও লাগে।
- **মনে রাখার টিপস:** SE = বহু discipline-এর সমন্বয়।


## প্রশ্ন 186 | Topic: Software Engineering > SDLC | Difficulty: Easy | Type: Theory

Q. SDLC-এর প্রধান উদ্দেশ্য কী?

A) Structured lifecycle-এ development পরিচালনা
B) শুধু language নির্বাচন
C) Testing বাদ
D) Hardware assembly

**সঠিক উত্তর: A) Structured lifecycle-এ development পরিচালনা**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Planning থেকে maintenance পর্যন্ত activity organize করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** একটি decision মাত্র।
- **C option কেন ভুল:** Testing গুরুত্বপূর্ণ।
- **D option কেন ভুল:** Software lifecycle নয়।
- **Related Concept:** Model phase flow নির্ধারণ করে।
- **মনে রাখার টিপস:** Software-এর lifecycle map।


## প্রশ্ন 187 | Topic: Software Engineering > SDLC Sequence | Difficulty: Medium | Type: Theory

Q. যৌক্তিক SDLC order কোনটি?

A) Testing→Requirement→Coding→Design
B) Coding→Deployment→Requirement
C) Planning→Requirement→Design→Implementation→Testing→Deployment
D) Maintenance→Planning→Coding

**সঠিক উত্তর: C) Planning→Requirement→Design→Implementation→Testing→Deployment**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Need বোঝা ও design-এর পরে build/test/release।
- **A option কেন ভুল:** Order ভুল।
- **B option কেন ভুল:** Requirement পরে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Maintenance deployment-এর পরে।
- **Related Concept:** Agile-এ phase iteration-এ repeat।
- **মনে রাখার টিপস:** Understand, design, build, test, release।


## প্রশ্ন 188 | Topic: Software Engineering > Requirements | Difficulty: Easy | Type: Theory

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
- **C option কেন ভুল:** Requirement output নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Requirement কী; design কীভাবে।
- **মনে রাখার টিপস:** Requirement = what।


## প্রশ্ন 189 | Topic: Software Engineering > Design | Difficulty: Medium | Type: Theory

Q. Design phase-এর প্রধান কাজ কী?

A) Requirement-কে architecture/component/interface/data design-এ রূপান্তর
B) Salary নির্ধারণ
C) Product বিক্রি
D) Bug report বন্ধ

**সঠিক উত্তর: A) Requirement-কে architecture/component/interface/data design-এ রূপান্তর**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Implementation blueprint তৈরি হয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Administration।
- **C option কেন ভুল:** Business activity।
- **D option কেন ভুল:** Testing/maintenance concern।
- **Related Concept:** High-level ও detailed design।
- **মনে রাখার টিপস:** Requirement-এর technical solution।


## প্রশ্ন 190 | Topic: Software Engineering > Productivity | Difficulty: Hard | Type: Calculation

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
- **Related Concept:** High productivity quality guarantee নয়।
- **মনে রাখার টিপস:** Output ÷ Effort।


## প্রশ্ন 191 | Topic: Software Engineering > Verification | Difficulty: Easy | Type: Theory

Q. “Are we building the product right?” কোন concept?

A) Validation
B) Deployment
C) Verification
D) Maintenance

**সঠিক উত্তর: C) Verification**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Specification অনুযায়ী artifact সঠিকভাবে তৈরি হচ্ছে কি না—Verification।
- **A option কেন ভুল:** Right product/user need।
- **B option কেন ভুল:** Release।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Post-release change।
- **Related Concept:** Review/static analysis verification technique।
- **মনে রাখার টিপস:** Product right = Verification।


## প্রশ্ন 192 | Topic: Software Engineering > Maintenance | Difficulty: Medium | Type: Scenario

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
- **মনে রাখার টিপস:** Environment বদল → Adaptive।


## প্রশ্ন 193 | Topic: Software Quality > Correctness | Difficulty: Easy | Type: Theory

Q. Specification অনুযায়ী সঠিক output কোন attribute?

A) Portability
B) Correctness
C) Reusability
D) Scalability

**সঠিক উত্তর: B) Correctness**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Specified functional behavior পূরণ।
- **A option কেন ভুল:** Platform move।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Reuse।
- **D option কেন ভুল:** Load growth।
- **Related Concept:** Correct হলেও মাঝে মাঝে fail করলে reliability কম।
- **মনে রাখার টিপস:** Correct result = Correctness।


## প্রশ্ন 194 | Topic: Software Quality > Robustness | Difficulty: Hard | Type: Scenario

Q. Invalid input-এ crash না করে meaningful error দিলে কোন quality?

A) Robustness
B) Portability
C) Reusability
D) Interoperability

**সঠিক উত্তর: A) Robustness**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Unexpected condition controlledভাবে handle করা Robustness।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Platform নয়।
- **C option কেন ভুল:** Reuse নয়।
- **D option কেন ভুল:** System communication নয়।
- **Related Concept:** Reliability ও robustness related কিন্তু distinct।
- **মনে রাখার টিপস:** Bad input সামলালে Robust।


## প্রশ্ন 195 | Topic: Software Quality > Usability | Difficulty: Medium | Type: Scenario

Q. কম training-এ user application ব্যবহার করতে পারে—কোন quality?

A) Maintainability
B) Reliability
C) Usability
D) Portability

**সঠিক উত্তর: C) Usability**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Learnability ও ease of use Usability।
- **A option কেন ভুল:** Developer change ease।
- **B option কেন ভুল:** Failure-free operation।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Platform move।
- **Related Concept:** Accessibility ও satisfaction-ও usability।
- **মনে রাখার টিপস:** User সহজে শেখে।


## প্রশ্ন 196 | Topic: Software Quality > Portability | Difficulty: Easy | Type: Theory

Q. Windows থেকে Linux-এ কম change-এ চালানো কোন attribute?

A) Correctness
B) Robustness
C) Testability
D) Portability

**সঠিক উত্তর: D) Portability**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Environment/platform migration ease।
- **A option কেন ভুল:** Output accuracy।
- **B option কেন ভুল:** Unexpected condition।
- **C option কেন ভুল:** Test ease।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Standard API portability বাড়ায়।
- **মনে রাখার টিপস:** Move platforms → Portability।


## প্রশ্ন 197 | Topic: Software Quality > Maintainability | Difficulty: Medium | Type: Theory

Q. Maintainability সবচেয়ে বাড়ায় কোন design?

A) Modular, clear interface, low coupling
B) এক huge function
C) Undocumented global
D) Duplicate code

**সঠিক উত্তর: A) Modular, clear interface, low coupling**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Change impact isolate হয় এবং code বোঝা সহজ।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Monolithic।
- **C option কেন ভুল:** Hidden dependency।
- **D option কেন ভুল:** Multiple change points।
- **Related Concept:** High cohesion-ও সহায়ক।
- **মনে রাখার টিপস:** Small modules, clear contract।


## প্রশ্ন 198 | Topic: Software Quality > Availability | Difficulty: Hard | Type: Calculation

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
- **Related Concept:** MTTR কমলে availability বাড়ে।
- **মনে রাখার টিপস:** Uptime fraction।


## প্রশ্ন 199 | Topic: Software Quality > Efficiency | Difficulty: Medium | Type: Theory

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
- **মনে রাখার টিপস:** কম resource, ভালো performance।


## প্রশ্ন 200 | Topic: Software Quality > Reusability | Difficulty: Medium | Type: Theory

Q. Authentication component বহু app-এ ব্যবহার কোন quality?

A) Reliability
B) Usability
C) Correctness
D) Reusability

**সঠিক উত্তর: D) Reusability**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Same component different context-এ reuse।
- **A option কেন ভুল:** Failure-free নয়।
- **B option কেন ভুল:** User ease নয়।
- **C option কেন ভুল:** Specification নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Generic interface ও low coupling সহায়ক।
- **মনে রাখার টিপস:** Build once, use many।


## প্রশ্ন 201 | Topic: Software Quality > Product Quality | Difficulty: Easy | Type: Theory

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
- **মনে রাখার টিপস:** Product behavior = product quality।


## প্রশ্ন 202 | Topic: Software Quality > Trade-off | Difficulty: Hard | Type: Scenario

Q. Security বাড়াতে MFA যোগে login ধীর হয়েছে—কী দেখায়?

A) Quality trade-off
B) সব quality একসঙ্গে বাড়ে
C) Security=Usability
D) Performance quality নয়

**সঠিক উত্তর: A) Quality trade-off**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Security improvement usability/performance cost আনতে পারে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Conflicting goals থাকে।
- **C option কেন ভুল:** Distinct attributes।
- **D option কেন ভুল:** Efficiency quality।
- **Related Concept:** Architecture-এ priority balance।
- **মনে রাখার টিপস:** Maximum নয়, balanced quality।


## প্রশ্ন 203 | Topic: Software Quality > Measurement | Difficulty: Medium | Type: Theory

Q. Quality measurement-এর ভালো approach কী?

A) শুধু developer opinion
B) File name
C) Language popularity
D) Relevant measurable metric ও stakeholder goal

**সঠিক উত্তর: D) Relevant measurable metric ও stakeholder goal**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Quality context-dependent ও evidence-based হওয়া উচিত।
- **A option কেন ভুল:** Subjective only।
- **B option কেন ভুল:** Irrelevant।
- **C option কেন ভুল:** Guarantee নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Response time, defect density, success rate metric।
- **মনে রাখার টিপস:** Goal measurable করুন।


## প্রশ্ন 204 | Topic: Software Quality > Process Metric | Difficulty: Easy | Type: Theory

Q. কোনটি Process Metric?

A) Button color
B) Executable icon
C) Requirement change resolve-এর average time
D) Product name

**সঠিক উত্তর: C) Requirement change resolve-এর average time**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Development process change কত দ্রুত handle করে তা মাপে।
- **A option কেন ভুল:** UI property।
- **B option কেন ভুল:** Appearance।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Branding।
- **Related Concept:** Review effectiveness process metric।
- **মনে রাখার টিপস:** Process-এর কাজ মাপুন।


## প্রশ্ন 205 | Topic: Software Quality > Correctness vs Reliability | Difficulty: Medium | Type: Theory

Q. সঠিক পার্থক্য কোনটি?

A) একই
B) Correctness=spec compliance; Reliability=failure-free probability
C) Correctness hardware only
D) Reliability docs only

**সঠিক উত্তর: B) Correctness=spec compliance; Reliability=failure-free probability**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একটি result accuracy, অন্যটি dependable operation over time।
- **A option কেন ভুল:** Identical নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Software-এও।
- **D option কেন ভুল:** Runtime property।
- **Related Concept:** Latent defect observed reliability-এ পরে ধরা পড়তে পারে।
- **মনে রাখার টিপস:** Correct result বনাম dependable operation।


## প্রশ্ন 206 | Topic: Software Quality > Defect Density | Difficulty: Medium | Type: Theory

Q. Defect Density কী মাপে?

A) Software size-এর প্রতি unit-এ defect
B) Salary
C) Electrical power
D) Login frequency

**সঠিক উত্তর: A) Software size-এর প্রতি unit-এ defect**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Defect count size দিয়ে normalize করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Cost।
- **C option কেন ভুল:** Hardware।
- **D option কেন ভুল:** Usage।
- **Related Concept:** Defects/KLOC বা per FP।
- **মনে রাখার টিপস:** Defects ÷ Size।


## প্রশ্ন 207 | Topic: Software Quality > Defect Density | Difficulty: Hard | Type: Calculation

Q. 40 KLOC software-এ 120 defect হলে density কত defects/KLOC?

A) 0.33
B) 2
C) 3
D) 4.8

**সঠিক উত্তর: C) 3**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Formula

```text
Defect Density = Defects / Size
```

#### Substitution

```text
= 120 / 40 KLOC
```

#### Calculation

```text
120 / 40 = 3
```

#### Final Answer

```text
Defect Density = 3 defects/KLOC
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 120/40=3।
- **A option কেন ভুল:** Division উল্টো।
- **B option কেন ভুল:** Arithmetic ভুল।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Incorrect scaling।
- **Related Concept:** Severity-ও বিবেচ্য।
- **মনে রাখার টিপস:** Defects ÷ KLOC।


## প্রশ্ন 208 | Topic: Software Quality > Usability Evaluation | Difficulty: Medium | Type: Scenario

Q. Task time, error rate, satisfaction কোন quality evaluate করে?

A) Portability
B) Maintainability
C) Reusability
D) Usability

**সঠিক উত্তর: D) Usability**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** User effectiveness, efficiency ও satisfaction usability-এর core।
- **A option কেন ভুল:** Platform।
- **B option কেন ভুল:** Developer modification।
- **C option কেন ভুল:** Component reuse।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Representative users/tasks ব্যবহার।
- **মনে রাখার টিপস:** User task metrics → Usability।


## প্রশ্ন 209 | Topic: Software Quality > Portability Practice | Difficulty: Medium | Type: Scenario

Q. Platform-specific code abstraction layer-এর পেছনে রাখলে কোন quality বাড়ে?

A) Portability
B) Defect Severity
C) Office Productivity
D) Marketing Reach

**সঠিক উত্তর: A) Portability**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Platform dependency isolate হলে migration সহজ।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Directly নয়।
- **C option কেন ভুল:** Organization নয়।
- **D option কেন ভুল:** Marketing নয়।
- **Related Concept:** Container/standard API-ও সহায়ক।
- **মনে রাখার টিপস:** Platform detail isolate।


## প্রশ্ন 210 | Topic: Software Quality > Maintainability Practice | Difficulty: Medium | Type: Theory

Q. Maintainability কমায় কোনটি?

A) Clear Naming
B) High Coupling ও Duplicate Logic
C) Automated Test
D) Modular Architecture

**সঠিক উত্তর: B) High Coupling ও Duplicate Logic**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Change বহু জায়গায় ripple করে।
- **A option কেন ভুল:** বোঝা সহজ।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Safe change।
- **D option কেন ভুল:** Isolation।
- **Related Concept:** Technical debt maintainability কমায়।
- **মনে রাখার টিপস:** Duplication + dependency।


## প্রশ্ন 211 | Topic: Software Models > Waterfall | Difficulty: Easy | Type: Theory

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
- **D option কেন ভুল:** Required নয়।
- **Related Concept:** Stable requirement-এ উপযোগী।
- **মনে রাখার টিপস:** Water falls one direction।


## প্রশ্ন 212 | Topic: Software Models > Waterfall Limitation | Difficulty: Hard | Type: Scenario

Q. Requirement প্রতি মাসে বদলালে Waterfall ঝুঁকিপূর্ণ কেন?

A) Design নেই
B) Testing নিষিদ্ধ
C) শুধু ছোট code
D) Late change rework বাড়ায়

**সঠিক উত্তর: D) Late change rework বাড়ায়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Sequential baseline-এর আগের artifacts পুনরায় বদলাতে হয়।
- **A option কেন ভুল:** Design আছে।
- **B option কেন ভুল:** Testing আছে।
- **C option কেন ভুল:** Size একমাত্র factor নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Agile/iterative adaptive।
- **মনে রাখার টিপস:** Changing need + late feedback = risk।


## প্রশ্ন 213 | Topic: Software Models > V-Model | Difficulty: Medium | Type: Theory

Q. V-Model-এর শক্তি কী?

A) Testing বাদ
B) Development phase-এর corresponding test planning
C) Requirement ছাড়া coding
D) শুধু prototype

**সঠিক উত্তর: B) Development phase-এর corresponding test planning**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Verification artifact ও validation level traceableভাবে pair করে।
- **A option কেন ভুল:** Testing গুরুত্ব পায়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Requirement থাকে।
- **D option কেন ভুল:** Prototype-only নয়।
- **Related Concept:** Module design↔Unit test; Requirement↔Acceptance।
- **মনে রাখার টিপস:** V-এর দুই পাশ build ও test।


## প্রশ্ন 214 | Topic: Software Models > Spiral | Difficulty: Medium | Type: Theory

Q. Spiral Model-এর কেন্দ্রীয় বৈশিষ্ট্য?

A) Risk Analysis
B) No documentation
C) One final delivery
D) No feedback

**সঠিক উত্তর: A) Risk Analysis**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতি cycle-এ risk identify, analyze, mitigate।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** প্রয়োজনীয় documentation থাকে।
- **C option কেন ভুল:** Iterative।
- **D option কেন ভুল:** Evaluation থাকে।
- **Related Concept:** High-risk project।
- **মনে রাখার টিপস:** Spiral দেখলে Risk।


## প্রশ্ন 215 | Topic: Software Models > Risk Exposure | Difficulty: Hard | Type: Calculation

Q. Risk probability 0.25, loss 80,000 টাকা; exposure কত?

A) 10,000
B) 80,000
C) 20,000
D) 320,000

**সঠিক উত্তর: C) 20,000**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Formula

```text
Risk Exposure = Probability × Loss
```

#### Substitution

```text
= 0.25 × 80,000
```

#### Calculation

```text
= 20,000
```

#### Final Answer

```text
Risk Exposure = 20,000 টাকা
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Probability×Loss = 20,000।
- **A option কেন ভুল:** Probability ভুল।
- **B option কেন ভুল:** Probability apply হয়নি।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Divide করা হয়েছে।
- **Related Concept:** Expected risk value।
- **মনে রাখার টিপস:** Chance × Loss।


## প্রশ্ন 216 | Topic: Software Models > Agile | Difficulty: Medium | Type: Theory

Q. Agile কিসে জোর দেয়?

A) No customer
B) No change
C) Only final delivery
D) Iterative delivery, feedback, responsiveness

**সঠিক উত্তর: D) Iterative delivery, feedback, responsiveness**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Short cycle ও frequent working increment।
- **A option কেন ভুল:** Customer collaboration core।
- **B option কেন ভুল:** Change welcome।
- **C option কেন ভুল:** Frequent delivery।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Scrum/XP Agile family।
- **মনে রাখার টিপস:** Small delivery + feedback।


## প্রশ্ন 217 | Topic: Software Models > RAD | Difficulty: Medium | Type: Theory

Q. RAD পূর্ণরূপ?

A) Rapid Application Development
B) Reliable Algorithm Design
C) Requirement Analysis Diagram
D) Runtime Application Debugging

**সঠিক উত্তর: A) Rapid Application Development**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Fast prototype/tool/component-driven development।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Standard expansion নয়।
- **C option কেন ভুল:** Diagram নয়।
- **D option কেন ভুল:** Debugging নয়।
- **Related Concept:** Modular scope ও skilled team উপযোগী।
- **মনে রাখার টিপস:** R = Rapid।


## প্রশ্ন 218 | Topic: Software Models > Prototype | Difficulty: Medium | Type: Scenario

Q. Client requirement স্পষ্ট নয়—কোন model সরাসরি সহায়ক?

A) Pure Waterfall
B) Prototype Model
C) Maintenance only
D) Big-bang

**সঠিক উত্তর: B) Prototype Model**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Working model দেখে feedback দিয়ে requirement clarify হয়।
- **A option কেন ভুল:** Early freeze risky।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Post-release।
- **D option কেন ভুল:** Discovery নয়।
- **Related Concept:** Throwaway বা evolutionary।
- **মনে রাখার টিপস:** Unclear need → show prototype।


## প্রশ্ন 219 | Topic: Software Models > Incremental | Difficulty: Easy | Type: Theory

Q. Incremental Model-এ delivery কীভাবে?

A) শুধু documents
B) সব শেষে
C) Usable increments
D) শুধু tests

**সঠিক উত্তর: C) Usable increments**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি increment নতুন usable capability যোগ করে।
- **A option কেন ভুল:** Working product নয়।
- **B option কেন ভুল:** Incremental নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Test case product নয়।
- **Related Concept:** Priority feature আগে।
- **মনে রাখার টিপস:** Usable parts ধাপে ধাপে।


## প্রশ্ন 220 | Topic: Software Models > Model Selection | Difficulty: Hard | Type: Scenario

Q. Stable safety-critical medical system ও rigorous test traceability—উপযুক্ত model?

A) Prototype-only
B) Code-and-Fix
C) RAD no docs
D) V-Model

**সঠিক উত্তর: D) V-Model**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Formal development-test correspondence ও traceability।
- **A option কেন ভুল:** Requirement exploration যথেষ্ট নয়।
- **B option কেন ভুল:** Unsafe।
- **C option কেন ভুল:** Compliance দুর্বল।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Regulated context-এ controlled lifecycle।
- **মনে রাখার টিপস:** Safety + trace test → V।


## প্রশ্ন 221 | Topic: Software Models > Iterative vs Incremental | Difficulty: Medium | Type: Theory

Q. পার্থক্য কোনটি?

A) একসঙ্গে নয়
B) Iterative refine; Incremental capability যোগ
C) Iteration docs only
D) Increment-এ working software নেই

**সঠিক উত্তর: B) Iterative refine; Incremental capability যোগ**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Iteration quality/detail উন্নত; increment scope/functionality বাড়ায়।
- **A option কেন ভুল:** প্রায়ই একসঙ্গে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** ভুল।
- **D option কেন ভুল:** Usable হতে পারে।
- **Related Concept:** Agile দুটোই।
- **মনে রাখার টিপস:** Iterate refine, increment add।


## প্রশ্ন 222 | Topic: Software Models > Agile Velocity | Difficulty: Hard | Type: Calculation

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
- **D option কেন ভুল:** Total, average নয়।
- **Related Concept:** Team-to-team velocity comparison অনুচিত।
- **মনে রাখার টিপস:** Completed total ÷ sprints।


## প্রশ্ন 223 | Topic: Software Models > Requirement-Driven | Difficulty: Medium | Type: Theory

Q. Requirement-Driven Development-এর control source কী?

A) Developer preference
B) Hardware brand
C) Office location
D) Prioritized traceable evolving requirements

**সঠিক উত্তর: D) Prioritized traceable evolving requirements**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Scope, design ও test requirement value/change দিয়ে চালিত।
- **A option কেন ভুল:** Formal driver নয়।
- **B option কেন ভুল:** Constraint হতে পারে।
- **C option কেন ভুল:** Irrelevant।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Traceability links requirement to test।
- **মনে রাখার টিপস:** Requirements drive development।


## প্রশ্ন 224 | Topic: Software Models > Spiral Activities | Difficulty: Hard | Type: Theory

Q. Spiral cycle-এর logical sequence?

A) Deploy→cancel→code
B) Code without risk
C) Objective→Risk Analysis→Develop/Validate→Next Plan
D) Docs only

**সঠিক উত্তর: C) Objective→Risk Analysis→Develop/Validate→Next Plan**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতি loop goal, risk, engineering ও planning।
- **A option কেন ভুল:** Model flow নয়।
- **B option কেন ভুল:** Risk missing।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Iterative work নেই।
- **Related Concept:** Prototype risk reduction করতে পারে।
- **মনে রাখার টিপস:** Objective, risk, build, plan।


## প্রশ্ন 225 | Topic: Software Models > Waterfall Suitability | Difficulty: Easy | Type: Theory

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
- **মনে রাখার টিপস:** Stable need → Waterfall।


## প্রশ্ন 226 | Topic: Software Models > Agile Values | Difficulty: Medium | Type: Theory

Q. Agile কোনটিকে বেশি গুরুত্ব দেয়?

A) Plan অন্ধভাবে নয়, change response
B) Working software-এর চেয়ে docs
C) Collaboration-এর চেয়ে conflict
D) No communication

**সঠিক উত্তর: A) Plan অন্ধভাবে নয়, change response**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Change response ও customer collaboration core।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Working software valued।
- **C option কেন ভুল:** Collaboration valued।
- **D option কেন ভুল:** Communication essential।
- **Related Concept:** Agile documentation-free নয়।
- **মনে রাখার টিপস:** Flexible, not careless।


## প্রশ্ন 227 | Topic: Software Models > RAD Limitation | Difficulty: Medium | Type: Scenario

Q. RAD কম উপযুক্ত কখন?

A) Skilled team
B) Fast feedback
C) Very large tightly coupled system
D) Short deadline

**সঠিক উত্তর: C) Very large tightly coupled system**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Rapid parallel component development-এর জন্য modular decomposition দরকার।
- **A option কেন ভুল:** Favorable।
- **B option কেন ভুল:** Favorable।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** RAD goal।
- **Related Concept:** Performance-critical system-এও caution।
- **মনে রাখার টিপস:** RAD needs modularity।


## প্রশ্ন 228 | Topic: Software Engineering > Schedule Overrun | Difficulty: Hard | Type: Calculation

Q. Planned 40 week, actual 50; overrun percentage?

A) 10%
B) 20%
C) 40%
D) 25%

**সঠিক উত্তর: D) 25%**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Formula

```text
Overrun% = (Actual - Planned) / Planned × 100
```

#### Calculation

```text
Difference = 50 - 40 = 10
10 / 40 = 0.25
0.25 × 100 = 25%
```

#### Final Answer

```text
Schedule Overrun = 25%
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** (50−40)/40×100=25%।
- **A option কেন ভুল:** Week difference percentage নয়।
- **B option কেন ভুল:** Actual denominator।
- **C option কেন ভুল:** Planned raw।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Baseline planned value denominator।
- **মনে রাখার টিপস:** Extra ÷ planned।


## প্রশ্ন 229 | Topic: Software Models > V-Model Mapping | Difficulty: Medium | Type: Theory

Q. User Requirement-এর corresponding test level?

A) Acceptance Testing
B) Unit Testing
C) Code Formatting
D) Compiler Testing

**সঠিক উত্তর: A) Acceptance Testing**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Acceptance Test user/business need verify করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Module design।
- **C option কেন ভুল:** Test level নয়।
- **D option কেন ভুল:** Product acceptance নয়।
- **Related Concept:** System requirement↔System Test।
- **মনে রাখার টিপস:** User need → Acceptance।


## প্রশ্ন 230 | Topic: Software Models > Hybrid | Difficulty: Hard | Type: Scenario

Q. Regulated banking-এ formal governance ও frequent UI feedback—logical approach?

A) No process
B) Formal governance + iterative delivery hybrid
C) No-test prototype
D) No requirement docs

**সঠিক উত্তর: B) Formal governance + iterative delivery hybrid**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Compliance ও adaptability balanced হয়।
- **A option কেন ভুল:** Audit/compliance ব্যর্থ।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Production quality নয়।
- **D option কেন ভুল:** Traceability হারায়।
- **Related Concept:** Real project-এ model tailoring common।
- **মনে রাখার টিপস:** Context অনুযায়ী hybrid।


## Batch 05 Quality Summary

```text
Questions          = 50
Theory/Scenario    = 44
Calculation        = 6
Coverage           = SE Fundamentals, Quality, SDLC Models
Math format        = Plain-text aligned
```

---

# Batch 06 — Question 231–280

**Section:** Introduction to Software Engineering  
**Coverage:** Engineering Principles, Requirements, Specification, Verification, Testing, UML ও UI Design  
**Composition:** Theory/Scenario 44, Calculation 6


# Chapter Theory 06: Principles, Requirements, Testing ও UML

## Software Engineering Principles

গুরুত্বপূর্ণ design principle:

- Modularity
- Abstraction
- Information Hiding
- Separation of Concerns
- Generality
- High Cohesion
- Low Coupling
- Structured Development
- Object-Oriented Development
- Component-Oriented Development

High Cohesion মানে module-এর internal responsibility related। Low Coupling মানে module-গুলোর অপ্রয়োজনীয় dependency কম।

## Requirements Engineering

প্রধান activity:

```text
Elicitation
Analysis
Prioritization
Specification
Validation
Change Management
Traceability
```

Functional Requirement বলে system কী করবে। Non-Functional Requirement বলে performance, security, usability, availability-এর মতো constraint/quality কী হবে।

ভালো SRS: Correct, Complete, Consistent, Unambiguous, Verifiable, Traceable, Modifiable।

## Verification, Testing ও Debugging

Testing levels:

- Unit
- Integration
- System
- Acceptance

Black-box internal code না দেখে behavior test করে। White-box statement, branch, condition ও path দেখে। Static Analysis program execute না করে; Dynamic Analysis program চালিয়ে।

```text
Statement Coverage =
Executed Statements / Total Statements × 100

Cyclomatic Complexity =
E - N + 2P
```

## UML

- Use Case — actor ও service
- Class — class, attribute, method, relation
- Sequence — message order over time
- Activity — workflow
- State Machine — state transition
- Component — software component
- Deployment — physical node ও artifact placement

UML methodology নয়; modeling language।

## UI Design

গুরুত্বপূর্ণ principle:

- Consistency
- Visibility of System Status
- Feedback
- Error Prevention
- User Control
- Accessibility
- Clear Navigation
- Recognition rather than Recall
- Error Recovery


## প্রশ্ন 231 | Topic: Software Engineering > Modularity | Difficulty: Easy | Type: Theory

Q. বড় system-কে ছোট manageable অংশে ভাগ করার principle কোনটি?

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
- **মনে রাখার টিপস:** বড় system → ছোট module।


## প্রশ্ন 232 | Topic: Software Engineering > Information Hiding | Difficulty: Medium | Type: Theory

Q. Module internal data structure লুকিয়ে public operation প্রকাশ করলে কোন principle?

A) Information Hiding
B) Code Duplication
C) Global Coupling
D) Unstructured Design

**সঠিক উত্তর: A) Information Hiding**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** পরিবর্তনশীল implementation decision interface-এর পেছনে লুকানো হয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Repeated logic।
- **C option কেন ভুল:** Dependency বাড়ায়।
- **D option কেন ভুল:** Control/design disorder।
- **Related Concept:** Encapsulation implementation mechanism।
- **মনে রাখার টিপস:** How hidden, service visible।


## প্রশ্ন 233 | Topic: Software Engineering > Abstraction | Difficulty: Medium | Type: Scenario

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
- **Related Concept:** Interface abstraction দেয়।
- **মনে রাখার টিপস:** What দেখা, how লুকানো।


## প্রশ্ন 234 | Topic: Software Engineering > Cohesion | Difficulty: Easy | Type: Theory

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
- **Related Concept:** High Cohesion maintainability বাড়ায়।
- **মনে রাখার টিপস:** ভেতরের সম্পর্ক = Cohesion।


## প্রশ্ন 235 | Topic: Software Engineering > Coupling | Difficulty: Hard | Type: Scenario

Q. Module A সরাসরি B-এর internal variable বদলায়—প্রধান সমস্যা?

A) Tight Coupling
B) High Portability
C) Strong Validation
D) Functional Cohesion

**সঠিক উত্তর: A) Tight Coupling**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** A B-এর implementation detail-এর ওপর নির্ভরশীল।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Platform নয়।
- **C option কেন ভুল:** User need নয়।
- **D option কেন ভুল:** Internal focus নয়।
- **Related Concept:** Stable interface dependency কমায়।
- **মনে রাখার টিপস:** অন্য module-এর ভেতরে হাত দিলে coupling।


## প্রশ্ন 236 | Topic: Software Engineering > Generality | Difficulty: Medium | Type: Theory

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
- **Related Concept:** Generic design reusability বাড়ায়।
- **মনে রাখার টিপস:** One solution, many related cases।


## প্রশ্ন 237 | Topic: Software Engineering > Component-Oriented | Difficulty: Medium | Type: Theory

Q. Component-Oriented Development-এর ধারণা কী?

A) সব code এক file
B) Reusable replaceable component
C) Testing বাদ
D) শুধু inheritance

**সঠিক উত্তর: B) Reusable replaceable component**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Well-defined interface-সহ building block integrate করা হয়।
- **A option কেন ভুল:** Monolithic।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Integration test প্রয়োজন।
- **D option কেন ভুল:** Reuse inheritance-সীমিত নয়।
- **Related Concept:** Component implementation replace করা যায়।
- **মনে রাখার টিপস:** Software Lego blocks।


## প্রশ্ন 238 | Topic: Software Engineering > Structured Development | Difficulty: Hard | Type: Theory

Q. Structured control-এর মৌলিক construct কোনগুলো?

A) Class,Object,Interface
B) Compile,Link,Load
C) Table,Row,Column
D) Sequence,Selection,Iteration

**সঠিক উত্তর: D) Sequence,Selection,Iteration**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Structured flow sequential action, decision ও repetition দিয়ে গঠিত।
- **A option কেন ভুল:** OOP।
- **B option কেন ভুল:** Translation।
- **C option কেন ভুল:** Database।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** if=selection, loop=iteration।
- **মনে রাখার টিপস:** ধারা, সিদ্ধান্ত, পুনরাবৃত্তি।


## প্রশ্ন 239 | Topic: Software Engineering > Separation of Concerns | Difficulty: Easy | Type: Theory

Q. UI, Business Logic ও Database Access আলাদা layer-এ রাখা কোন principle?

A) Separation of Concerns
B) Obfuscation
C) Circular Dependency
D) Data Duplication

**সঠিক উত্তর: A) Separation of Concerns**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Different concern পৃথক করলে change/test isolate হয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Code লুকিয়ে কঠিন করা।
- **C option কেন ভুল:** Undesirable dependency।
- **D option কেন ভুল:** Repeated data।
- **Related Concept:** Layered architecture।
- **মনে রাখার টিপস:** ভিন্ন কাজ, ভিন্ন layer।


## প্রশ্ন 240 | Topic: Software Engineering > Modularity Trade-off | Difficulty: Medium | Type: Scenario

Q. System এত ক্ষুদ্র module-এ ভাগ যে সামান্য কাজেও বহু call লাগে—কী বোঝায়?

A) যত বেশি modular তত ভালো
B) Over-decomposition overhead বাড়ায়
C) Interface লাগে না
D) Cohesion irrelevant

**সঠিক উত্তর: B) Over-decomposition overhead বাড়ায়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** অতিরিক্ত fragmentation coordination, comprehension ও runtime overhead বাড়াতে পারে।
- **A option কেন ভুল:** Balanced granularity দরকার।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Interface অপরিহার্য।
- **D option কেন ভুল:** Design quality-তে relevant।
- **Related Concept:** Under ও over-modularization দুটোই সমস্যা।
- **মনে রাখার টিপস:** ছোট, কিন্তু অকারণে ক্ষুদ্র নয়।


## প্রশ্ন 241 | Topic: Software Engineering > Reuse Strategy | Difficulty: Hard | Type: Scenario

Q. True is-a relation নেই, শুধু behavior reuse দরকার—Inheritance-এর ভালো বিকল্প?

A) Global Variable
B) goto
C) Duplication
D) Composition

**সঠিক উত্তর: D) Composition**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Composition behavior reuse দেয় subtype contract ছাড়াই।
- **A option কেন ভুল:** Global coupling।
- **B option কেন ভুল:** Control flow।
- **C option কেন ভুল:** Maintainability কম।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Favor composition over inheritance।
- **মনে রাখার টিপস:** is-a না হলে has-a ভাবুন।


## প্রশ্ন 242 | Topic: Software Engineering > Modular Design | Difficulty: Medium | Type: Theory

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
- **মনে রাখার টিপস:** ভেতরে high, বাইরে low।


## প্রশ্ন 243 | Topic: Requirements > Functional | Difficulty: Easy | Type: Theory

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
- **D option কেন ভুল:** Measurement নয়।
- **Related Concept:** Use Case functional need capture করে।
- **মনে রাখার টিপস:** System কী করবে।


## প্রশ্ন 244 | Topic: Requirements > Non-Functional | Difficulty: Medium | Type: Theory

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
- **C option কেন ভুল:** Data entry নয়।
- **D option কেন ভুল:** Implementation structure নয়।
- **Related Concept:** Security/availability-ও NFR।
- **মনে রাখার টিপস:** কত ভালোভাবে কাজ করবে।


## প্রশ্ন 245 | Topic: Requirements > SRS Quality | Difficulty: Hard | Type: Scenario

Q. “System দ্রুত response দেবে”—প্রধান সমস্যা?

A) অতিরিক্ত complete
B) শুধু functional
C) Ambiguous ও unverifiable
D) Mathematically wrong

**সঠিক উত্তর: C) Ambiguous ও unverifiable**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `দ্রুত` measurable threshold ছাড়া ভিন্নভাবে interpreted হয়।
- **A option কেন ভুল:** বরং detail কম।
- **B option কেন ভুল:** Performance expectation হলেও অস্পষ্ট।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Math issue নয়।
- **Related Concept:** ভালো: 95% request ≤2 sec।
- **মনে রাখার টিপস:** Measurable requirement লিখুন।


## প্রশ্ন 246 | Topic: Requirements > Volatility | Difficulty: Medium | Type: Calculation

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
- **Related Concept:** High volatility schedule/test impact বাড়ায়।
- **মনে রাখার টিপস:** Changed ÷ Baseline ×100।


## প্রশ্ন 247 | Topic: Requirements > Stakeholder | Difficulty: Medium | Type: Theory

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
- **মনে রাখার টিপস:** Interest বা impact থাকলে stakeholder।


## প্রশ্ন 248 | Topic: Requirements > Use Case | Difficulty: Easy | Type: Theory

Q. Use Case-এর external participant কী?

A) Compiler
B) Module
C) Actor
D) Attribute

**সঠিক উত্তর: C) Actor**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Actor মানুষ, device বা external system হতে পারে।
- **A option কেন ভুল:** Translator।
- **B option কেন ভুল:** Component।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Property।
- **Related Concept:** Actor সবসময় human নয়।
- **মনে রাখার টিপস:** System বাইরে interactionকারী।


## প্রশ্ন 249 | Topic: Requirements > Descriptive Specification | Difficulty: Hard | Type: Theory

Q. Descriptive Specification-এর বৈশিষ্ট্য?

A) Externally observable behavior বলে, internal implementation বাধ্যতামূলক নয়
B) শুধু LOC
C) Hardware wiring
D) Password storage

**সঠিক উত্তর: A) Externally observable behavior বলে, internal implementation বাধ্যতামূলক নয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Specification what নির্ধারণ করে; how design-এর জন্য রেখে দিতে পারে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Metric।
- **C option কেন ভুল:** Hardware diagram।
- **D option কেন ভুল:** Security violation।
- **Related Concept:** Declarative specification।
- **মনে রাখার টিপস:** কী চাই, কীভাবে নয়।


## প্রশ্ন 250 | Topic: Requirements > Traceability | Difficulty: Medium | Type: Theory

Q. Requirement Traceability-এর উদ্দেশ্য?

A) Requirement delete
B) Attendance
C) Page বাড়ানো
D) Source, design, code ও test relation track

**সঠিক উত্তর: D) Source, design, code ও test relation track**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Implementation/testing coverage ও change impact বোঝা যায়।
- **A option কেন ভুল:** Delete technique নয়।
- **B option কেন ভুল:** Admin।
- **C option কেন ভুল:** Formatting নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Traceability Matrix।
- **মনে রাখার টিপস:** Requirement কোথা থেকে কোথায়।


## প্রশ্ন 251 | Topic: Requirements > Feasibility | Difficulty: Easy | Type: Theory

Q. Technology দিয়ে project সম্ভব কি না—কোন feasibility?

A) Legal
B) Schedule
C) Technical
D) Cultural

**সঠিক উত্তর: C) Technical**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Skill, platform, infrastructure ও technical constraint যাচাই।
- **A option কেন ভুল:** Law।
- **B option কেন ভুল:** Time।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Primary standard category নয়।
- **Related Concept:** Economic/Operational-ও আছে।
- **মনে রাখার টিপস:** Technology দিয়ে সম্ভব? Technical।


## প্রশ্ন 252 | Topic: Requirements > Validation | Difficulty: Medium | Type: Theory

Q. Requirement Validation কী পরীক্ষা করে?

A) Compiler speed
B) Stakeholder need সঠিকভাবে capture হয়েছে কি না
C) Indentation
D) Disk brand

**সঠিক উত্তর: B) Stakeholder need সঠিকভাবে capture হয়েছে কি না**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Correctness, completeness, consistency, realism ও verifiability।
- **A option কেন ভুল:** Compiler metric।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Implementation formatting।
- **D option কেন ভুল:** Brand নয়।
- **Related Concept:** Review/prototype/test-case derivation সহায়ক।
- **মনে রাখার টিপস:** Written need আসল need কি না।


## প্রশ্ন 253 | Topic: Requirements > Change Control | Difficulty: Medium | Type: Scenario

Q. Approved baseline requirement change-এর আগে কী?

A) Direct code change
B) Old doc delete
C) Testing বন্ধ
D) Impact Analysis ও approval

**সঠিক উত্তর: D) Impact Analysis ও approval**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Cost, schedule, design ও test impact বুঝে formal decision।
- **A option কেন ভুল:** Uncontrolled।
- **B option কেন ভুল:** History হারায়।
- **C option কেন ভুল:** Testing আরও দরকার।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Configuration Management baseline control।
- **মনে রাখার টিপস:** Understand, approve, implement।


## প্রশ্ন 254 | Topic: Requirements > Conflict | Difficulty: Hard | Type: Scenario

Q. Security long password, usability short password চায়—সঠিক approach?

A) Negotiation, risk analysis, prioritized trade-off
B) দুটিই ignore
C) Developer preference
D) Doc hide

**সঠিক উত্তর: A) Negotiation, risk analysis, prioritized trade-off**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Stakeholder objective ও risk দিয়ে balanced decision।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Goal fail।
- **C option কেন ভুল:** Personal preference নয়।
- **D option কেন ভুল:** Conflict solve নয়।
- **Related Concept:** MFA balance দিতে পারে।
- **মনে রাখার টিপস:** Conflict → negotiate ও prioritize।


## প্রশ্ন 255 | Topic: Testing > Unit | Difficulty: Easy | Type: Theory

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
- **D option কেন ভুল:** Principal standard level নয়।
- **Related Concept:** Mock dependency isolate করে।
- **মনে রাখার টিপস:** Smallest component = Unit।


## প্রশ্ন 256 | Topic: Testing > Black-box | Difficulty: Medium | Type: Theory

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
- **মনে রাখার টিপস:** Box-এর ভিতর দেখা হয় না।


## প্রশ্ন 257 | Topic: Testing > Cyclomatic Complexity | Difficulty: Hard | Type: Calculation

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
- **মনে রাখার টিপস:** E−N+2P।


## প্রশ্ন 258 | Topic: Testing > White-box | Difficulty: Medium | Type: Theory

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
- **মনে রাখার টিপস:** Code-এর পথ = White-box।


## প্রশ্ন 259 | Topic: Testing > Debugging | Difficulty: Easy | Type: Theory

Q. Failure-এর root cause খুঁজে fix করাকে কী বলে?

A) Validation
B) Debugging
C) Deployment
D) Estimation

**সঠিক উত্তর: B) Debugging**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Defect locate, diagnose ও correct।
- **A option কেন ভুল:** Need check।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Release।
- **D option কেন ভুল:** Forecast।
- **Related Concept:** Testing failure দেখায়, debugging cause।
- **মনে রাখার টিপস:** কোথায় ও কেন = Debugging।


## প্রশ্ন 260 | Topic: Testing > Static Analysis | Difficulty: Medium | Type: Theory

Q. Program run না করে defect খোঁজা?

A) Load Testing
B) Dynamic Analysis
C) Static Analysis
D) Acceptance

**সঠিক উত্তর: C) Static Analysis**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Source/intermediate representation execution ছাড়া inspect।
- **A option কেন ভুল:** Runtime workload।
- **B option কেন ভুল:** Program চালায়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** User requirement।
- **Related Concept:** Compiler warning basic static analysis।
- **মনে রাখার টিপস:** Run না করে inspect।


## প্রশ্ন 261 | Topic: Testing > Verification vs Validation | Difficulty: Hard | Type: Scenario

Q. Specification ঠিকভাবে implement, কিন্তু business problem solve নয়—কী?

A) Verification pass, Validation fail
B) Verification fail, Validation pass
C) দুটিই pass
D) Irrelevant

**সঠিক উত্তর: A) Verification pass, Validation fail**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Product rightভাবে বানানো, কিন্তু right product নয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** উল্টো।
- **C option কেন ভুল:** User need fail।
- **D option কেন ভুল:** দুটি concept সরাসরি।
- **Related Concept:** Wrong requirement correctly implement হতে পারে।
- **মনে রাখার টিপস:** Rightভাবে wrong product।


## প্রশ্ন 262 | Topic: Testing > Statement Coverage | Difficulty: Medium | Type: Calculation

Q. 80 executable statement-এর 72 execute হলে coverage কত?

A) 72%
B) 80%
C) 85%
D) 90%

**সঠিক উত্তর: D) 90%**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Formula

```text
Statement Coverage = Executed / Total × 100
```

#### Substitution

```text
= 72 / 80 × 100
```

#### Calculation

```text
72 / 80 = 0.9
0.9 × 100 = 90%
```

#### Final Answer

```text
Statement Coverage = 90%
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 72/80×100=90%।
- **A option কেন ভুল:** Raw executed count।
- **B option কেন ভুল:** Total count।
- **C option কেন ভুল:** Division ভুল।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** 100% statement ≠ 100% branch।
- **মনে রাখার টিপস:** Executed ÷ Total।


## প্রশ্ন 263 | Topic: Testing > Regression | Difficulty: Medium | Type: Theory

Q. Change-এর পরে old functionality ভাঙল কি না কোন test?

A) Regression
B) Alpha only
C) Installation only
D) Mutation only

**সঠিক উত্তর: A) Regression**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Existing behavior change-এর পর recheck।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Internal pre-release broader test।
- **C option কেন ভুল:** Install environment।
- **D option কেন ভুল:** Test-suite strength।
- **Related Concept:** Automation সহায়ক।
- **মনে রাখার টিপস:** Change-এর পর পুরোনো feature test।


## প্রশ্ন 264 | Topic: Testing > Integration | Difficulty: Easy | Type: Theory

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
- **C option কেন ভুল:** Execution ছাড়া।
- **D option কেন ভুল:** User need।
- **Related Concept:** Top-down/Bottom-up।
- **মনে রাখার টিপস:** Module মিললে Integration।


## প্রশ্ন 265 | Topic: Testing > Test Oracle | Difficulty: Hard | Type: Theory

Q. Test Oracle কী?

A) Test hardware
B) Bug programmer
C) Random generator
D) Actual result correct কি না নির্ধারণের mechanism

**সঠিক উত্তর: D) Actual result correct কি না নির্ধারণের mechanism**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Expected output/spec/model/trusted implementation verdict দেয়।
- **A option কেন ভুল:** Environment।
- **B option কেন ভুল:** সবসময় নয়।
- **C option কেন ভুল:** Input দেয়, verdict নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Oracle Problem complex domain-এ।
- **মনে রাখার টিপস:** Pass/fail বিচারক।


## প্রশ্ন 266 | Topic: Testing > DRE | Difficulty: Hard | Type: Calculation

Q. Release আগে 90 defect remove, পরে 10 পাওয়া; DRE কত?

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
- **D option কেন ভুল:** Post-release defect থাকায় 100 নয়।
- **Related Concept:** High DRE pre-release effectiveness।
- **মনে রাখার টিপস:** Before release ÷ total known।


## প্রশ্ন 267 | Topic: Testing > Boundary Value | Difficulty: Medium | Type: Scenario

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
- **C option কেন ভুল:** Boundary guarantee নয়।
- **D option কেন ভুল:** Technique-এর বিপরীত।
- **Related Concept:** Boundary-তে defect common।
- **মনে রাখার টিপস:** Min−1,Min,Min+1; Max−1,Max,Max+1।


## প্রশ্ন 268 | Topic: Testing > Stub/Driver | Difficulty: Medium | Type: Theory

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
- **মনে রাখার টিপস:** নিচের module → Stub।


## প্রশ্ন 269 | Topic: UML > Use Case | Difficulty: Easy | Type: Theory

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
- **মনে রাখার টিপস:** কে কী করে।


## প্রশ্ন 270 | Topic: UML > Class Diagram | Difficulty: Medium | Type: Theory

Q. Class, Attribute, Method, Association কোন diagram?

A) Activity
B) Sequence
C) State
D) Class Diagram

**সঠিক উত্তর: D) Class Diagram**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Static OO structure।
- **A option কেন ভুল:** Workflow।
- **B option কেন ভুল:** Temporal messages।
- **C option কেন ভুল:** Lifecycle state।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Generalization/composition-ও দেখায়।
- **মনে রাখার টিপস:** Class-এর গঠন।


## প্রশ্ন 271 | Topic: UML > Sequence | Difficulty: Hard | Type: Scenario

Q. `UI→Auth Service→Database` message order কোন diagram?

A) Class
B) Sequence
C) Deployment
D) ER

**সঠিক উত্তর: B) Sequence**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Participants-এর message exchange time order।
- **A option কেন ভুল:** Static structure।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Physical placement।
- **D option কেন ভুল:** Data entities।
- **Related Concept:** Lifeline ও message।
- **মনে রাখার টিপস:** কে কাকে কখন message।


## প্রশ্ন 272 | Topic: UML > Activity | Difficulty: Medium | Type: Theory

Q. Workflow, decision, parallel activity কোন diagram?

A) Component
B) Object
C) Activity
D) Deployment

**সঠিক উত্তর: C) Activity**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Process flow, branch, fork/join model করে।
- **A option কেন ভুল:** Software parts।
- **B option কেন ভুল:** Object snapshot।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Physical topology।
- **Related Concept:** Fork/join parallelism।
- **মনে রাখার টিপস:** কাজের flow।


## প্রশ্ন 273 | Topic: UML > State Machine | Difficulty: Easy | Type: Theory

Q. Order-এর Created/Paid/Shipped/Cancelled state কোন diagram?

A) State Machine
B) Use Case
C) Package
D) Component

**সঠিক উত্তর: A) State Machine**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Event-driven state transition।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** User goals।
- **C option কেন ভুল:** Grouping।
- **D option কেন ভুল:** Implementation parts।
- **Related Concept:** Transition-এ event/guard/action।
- **মনে রাখার টিপস:** Object lifecycle।


## প্রশ্ন 274 | Topic: Requirements > Traceability Coverage | Difficulty: Medium | Type: Calculation

Q. 80 requirement-এর 72 test-এর সঙ্গে linked; coverage কত?

A) 72%
B) 80%
C) 85%
D) 90%

**সঠিক উত্তর: D) 90%**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Formula

```text
Traceability Coverage = Linked / Total × 100
```

#### Calculation

```text
72 / 80 = 0.9
0.9 × 100 = 90%
```

#### Final Answer

```text
Traceability Coverage = 90%
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 72/80×100=90%।
- **A option কেন ভুল:** Raw count।
- **B option কেন ভুল:** Total count।
- **C option কেন ভুল:** Math ভুল।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** 100% link test quality guarantee নয়।
- **মনে রাখার টিপস:** Linked ÷ Total।


## প্রশ্ন 275 | Topic: UML > Component vs Deployment | Difficulty: Hard | Type: Theory

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
- **মনে রাখার টিপস:** Component কী, Deployment কোথায়।


## প্রশ্ন 276 | Topic: UI Design > Consistency | Difficulty: Medium | Type: Scenario

Q. সব screen-এ same button same কাজ—কোন principle?

A) Consistency
B) Hidden Navigation
C) Randomization
D) Maximum Complexity

**সঠিক উত্তর: A) Consistency**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Uniform behavior learning burden কমায়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Usability কমায়।
- **C option কেন ভুল:** Confusion।
- **D option কেন ভুল:** Design goal নয়।
- **Related Concept:** Platform convention external consistency।
- **মনে রাখার টিপস:** একই জিনিস একইভাবে।


## প্রশ্ন 277 | Topic: UI Design > Feedback | Difficulty: Easy | Type: Theory

Q. Save-এর পরে “Saved Successfully” message কোন principle?

A) Abstraction
B) Inheritance
C) Feedback
D) Coupling

**সঠিক উত্তর: C) Feedback**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** System action গ্রহণ ও result জানায়।
- **A option কেন ভুল:** Detail hiding।
- **B option কেন ভুল:** Class relation।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Dependency।
- **Related Concept:** Visibility of status।
- **মনে রাখার টিপস:** Action-এর পরে response।


## প্রশ্ন 278 | Topic: UI Design > Error Prevention | Difficulty: Medium | Type: Scenario

Q. Delete-এর আগে confirmation কেন?

A) Complexity
B) Accidental destructive action প্রতিরোধ
C) Network speed
D) Normalization

**সঠিক উত্তর: B) Accidental destructive action প্রতিরোধ**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** High-impact action-এর আগে user intent verify।
- **A option কেন ভুল:** Purpose নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Bandwidth নয়।
- **D option কেন ভুল:** DB concept।
- **Related Concept:** Undo error recovery।
- **মনে রাখার টিপস:** Destructive action আগে confirm।


## প্রশ্ন 279 | Topic: UI Design > Task Success | Difficulty: Medium | Type: Calculation

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
- **মনে রাখার টিপস:** Successful ÷ Total।


## প্রশ্ন 280 | Topic: UML > Modeling Purpose | Difficulty: Easy | Type: Theory

Q. Software Model সম্পর্কে সঠিক statement?

A) সব detail ধারণ করে
B) Implementation লাগে না
C) Decoration
D) Selected important aspect সহজভাবে দেখায়

**সঠিক উত্তর: D) Selected important aspect সহজভাবে দেখায়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Model purposeful abstraction; communication ও analysis সহজ করে।
- **A option কেন ভুল:** কিছু detail ইচ্ছাকৃত বাদ।
- **B option কেন ভুল:** Implementation replace নয়।
- **C option কেন ভুল:** Analysis tool।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Different concern-এর different model।
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

# Batch 07 — Question 281–300

**Section:** Introduction to Software Engineering  
**Coverage:** Project Management, Metrics, COCOMO, Function Point, Estimation ও Risk Management  
**Composition:** Theory/Scenario 17, Calculation 3


# Chapter Theory 07: Project Management, Estimation ও Risk

## Project Management

Software Project Management scope, time, cost, quality, people, communication ও risk coordinate করে। Triple Constraint:

```text
Scope
Time
Cost
```

একটি constraint বদলালে অন্যগুলোর ওপর প্রভাব পড়তে পারে। `WBS` project scope-কে manageable work package-এ ভাঙে। Milestone হলো গুরুত্বপূর্ণ checkpoint; Deliverable হলো measurable output।

## Project Metrics ও Baseline

Approved scope/schedule/cost plan হলো baseline। Actual performance baseline-এর সঙ্গে তুলনা করে variance বের করা হয়।

ভালো metric:

- Relevant
- Measurable
- Actionable
- Consistent
- Context-aware

LOC language ও coding style-নির্ভর। Function Point user-visible functional size মাপে।

## COCOMO

Basic COCOMO:

```text
Effort = a × (KLOC)^b
Development Time = c × (Effort)^d
```

Modes:

- Organic — ছোট, পরিচিত, flexible
- Semi-detached — মাঝারি complexity ও mixed experience
- Embedded — কঠোর hardware/software/operational constraint

Estimate exact prediction নয়; assumption, historical data ও recalibration প্রয়োজন।

## Function Point

Common component:

- External Input (EI)
- External Output (EO)
- External Inquiry (EQ)
- Internal Logical File (ILF)
- External Interface File (EIF)

Adjustment:

```text
VAF = 0.65 + 0.01 × TDI
Adjusted FP = UFP × VAF
```

## Risk Management

Risk = uncertain event with probability ও impact।

```text
Risk Exposure = Probability × Loss
```

Response:

- Avoid
- Mitigate
- Transfer
- Accept

Risk Register-এ description, probability, impact, owner, response ও status থাকে।


## প্রশ্ন 281 | Topic: Project Management > Triple Constraint | Difficulty: Easy | Type: Theory

Q. Project-এর Triple Constraint কোনগুলো?

A) Code,Test,Deploy
B) Scope,Time,Cost
C) Input,Process,Output
D) Hardware,Software,Network

**সঠিক উত্তর: B) Scope,Time,Cost**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Project-এর পরিধি, সময় ও budget পরস্পর সম্পর্কিত প্রধান constraint।
- **A option কেন ভুল:** Development activities।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** System model।
- **D option কেন ভুল:** Resource categories।
- **Related Concept:** Quality balance-এর ওপর নির্ভর করে।
- **মনে রাখার টিপস:** কী, কত সময়ে, কত খরচে।


## প্রশ্ন 282 | Topic: Project Management > Scope Creep | Difficulty: Medium | Type: Scenario

Q. Formal approval ছাড়া ধারাবাহিক নতুন feature যোগ হওয়া কী?

A) Risk Transfer
B) Refactoring
C) Project Closure
D) Scope Creep

**সঠিক উত্তর: D) Scope Creep**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Uncontrolled scope expansion project plan নষ্ট করে।
- **A option কেন ভুল:** Risk responsibility shift।
- **B option কেন ভুল:** Internal code improvement।
- **C option কেন ভুল:** Project ending।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Change Control scope creep কমায়।
- **মনে রাখার টিপস:** অনুমোদন ছাড়া scope বাড়া।


## প্রশ্ন 283 | Topic: Project Planning > WBS | Difficulty: Easy | Type: Theory

Q. WBS-এর প্রধান উদ্দেশ্য?

A) Scope-কে manageable work package-এ ভাগ
B) সব risk বাদ
C) Compile
D) Salary

**সঠিক উত্তর: A) Scope-কে manageable work package-এ ভাগ**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Estimation, assignment ও tracking সহজ হয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Risk eliminate করা যায় না।
- **C option কেন ভুল:** Build activity।
- **D option কেন ভুল:** Administrative।
- **Related Concept:** Deliverable-oriented decomposition।
- **মনে রাখার টিপস:** বড় কাজকে ছোট করুন।


## প্রশ্ন 284 | Topic: Project Planning > Milestone | Difficulty: Medium | Type: Theory

Q. Milestone ও Deliverable-এর পার্থক্য?

A) Milestone code, deliverable meeting
B) Milestone long duration
C) Milestone checkpoint; Deliverable measurable output
D) একই

**সঠিক উত্তর: C) Milestone checkpoint; Deliverable measurable output**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Milestone status/event; deliverable tangible/verifiable result।
- **A option কেন ভুল:** Fixed category নয়।
- **B option কেন ভুল:** Milestone সাধারণত zero duration।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** ভিন্ন।
- **Related Concept:** SRS approved milestone; approved SRS deliverable।
- **মনে রাখার টিপস:** Milestone অবস্থান, Deliverable ফল।


## প্রশ্ন 285 | Topic: Project Metrics > Good Metric | Difficulty: Medium | Type: Theory

Q. ভালো metric-এর বৈশিষ্ট্য?

A) সুন্দর
B) Relevant, measurable, actionable
C) সব project-এ same target
D) শুধু manager বোঝে

**সঠিক উত্তর: B) Relevant, measurable, actionable**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Decision ও corrective action-এ সহায়তা করে।
- **A option কেন ভুল:** Presentation যথেষ্ট নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Context ভিন্ন।
- **D option কেন ভুল:** Stakeholder-understandable হওয়া উচিত।
- **Related Concept:** Vanity metric এড়িয়ে চলুন।
- **মনে রাখার টিপস:** Measure for action।


## প্রশ্ন 286 | Topic: Estimation > COCOMO Effort | Difficulty: Hard | Type: Calculation

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
- **A option কেন ভুল:** Coefficient apply হয়নি।
- **B option কেন ভুল:** Exponent বাদ।
- **C option কেন ভুল:** Multiplication ভুল।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Effort duration নয়।
- **মনে রাখার টিপস:** Power আগে, coefficient পরে।


## প্রশ্ন 287 | Topic: Estimation > COCOMO Modes | Difficulty: Medium | Type: Theory

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
- **C option কেন ভুল:** Standard mode নয়।
- **D option কেন ভুল:** Development model।
- **Related Concept:** Semi-detached মধ্যবর্তী।
- **মনে রাখার টিপস:** কঠোর environment → Embedded।


## প্রশ্ন 288 | Topic: Metrics > LOC Limitation | Difficulty: Hard | Type: Scenario

Q. Same functionality-তে বেশি LOC team-কে বেশি productive বলা ভুল কেন?

A) LOC গোনা যায় না
B) Short code সবসময় wrong
C) LOC language/reuse/design/generated code-নির্ভর
D) Size irrelevant

**সঠিক উত্তর: C) LOC language/reuse/design/generated code-নির্ভর**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** More lines inefficiency বা duplication-ও হতে পারে।
- **A option কেন ভুল:** গোনা যায়।
- **B option কেন ভুল:** Length correctness নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Size useful but contextual।
- **Related Concept:** Value/effort বিবেচনা প্রয়োজন।
- **মনে রাখার টিপস:** More code ≠ more value।


## প্রশ্ন 289 | Topic: Metrics > Function Point | Difficulty: Easy | Type: Theory

Q. Function Point-এর সুবিধা?

A) Formatting measure
B) Hardware speed
C) Defect severity
D) User-visible functionality-based size

**সঠিক উত্তর: D) User-visible functionality-based size**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Implementation language-এর বদলে functional input/output/data দেখে।
- **A option কেন ভুল:** Style নয়।
- **B option কেন ভুল:** Hardware নয়।
- **C option কেন ভুল:** Quality metric নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** LOC-এর তুলনায় language-independent।
- **মনে রাখার টিপস:** User function মাপে।


## প্রশ্ন 290 | Topic: Function Point > Components | Difficulty: Medium | Type: Theory

Q. কোনটি Function Point component নয়?

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
- **মনে রাখার টিপস:** FP functional size, CPU নয়।


## প্রশ্ন 291 | Topic: Risk Management > Components | Difficulty: Easy | Type: Theory

Q. Risk priority-র মূল দুটি factor?

A) Age,Location
B) File size,Extension
C) Probability,Impact
D) Language,Indentation

**সঠিক উত্তর: C) Probability,Impact**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** ঘটার chance ও ঘটলে ক্ষতি risk significance নির্ধারণ করে।
- **A option কেন ভুল:** Core factor নয়।
- **B option কেন ভুল:** Core factor নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Specific context, fundamental pair নয়।
- **Related Concept:** Exposure probability×loss।
- **মনে রাখার টিপস:** Chance কত, ক্ষতি কত।


## প্রশ্ন 292 | Topic: Estimation > COCOMO Time | Difficulty: Hard | Type: Calculation

Q. `TDEV=2.5×Effort^0.38`; Effort=32, `32^0.38≈3.73`; time কত?

A) 9.33 month
B) 12.80 month
C) 5.98 month
D) 80.00 month

**সঠিক উত্তর: A) 9.33 month**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Formula

```text
TDEV = 2.5 × (Effort)^0.38
```

#### Given Data

```text
Effort = 32 person-month
32^0.38 ≈ 3.73
```

#### Substitution

```text
TDEV = 2.5 × 3.73
```

#### Calculation

```text
3.73 × 2.0 = 7.46
3.73 × 0.5 = 1.865
Total = 9.325
```

#### Final Answer

```text
Estimated Development Time ≈ 9.33 month
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 2.5×3.73=9.325≈9.33 month।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** 32×0.4 ধরনের ভুল।
- **C option কেন ভুল:** Coefficient/exponent ভুল।
- **D option কেন ভুল:** Exponent বাদ।
- **Related Concept:** Effort দ্বিগুণ মানে duration দ্বিগুণ নয়।
- **মনে রাখার টিপস:** Effort ও time আলাদা।


## প্রশ্ন 293 | Topic: Risk Management > Transfer | Difficulty: Medium | Type: Scenario

Q. Cyber-risk financial loss cover করতে insurance—কোন response?

A) Avoid
B) Accept
C) Mitigate
D) Transfer

**সঠিক উত্তর: D) Transfer**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Financial responsibility third party-তে shift।
- **A option কেন ভুল:** Activity eliminate।
- **B option কেন ভুল:** Risk retain।
- **C option কেন ভুল:** Probability/impact reduce।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** সব operational responsibility দূর নাও হয়।
- **মনে রাখার টিপস:** Insurance → Transfer।


## প্রশ্ন 294 | Topic: Risk Management > Risk Register | Difficulty: Medium | Type: Theory

Q. Risk Register-এ কী থাকে?

A) শুধু source
B) Description, probability, impact, owner, response
C) Attendance
D) Password

**সঠিক উত্তর: B) Description, probability, impact, owner, response**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Risk tracking ও ownership-এর central record।
- **A option কেন ভুল:** Risk record নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Admin।
- **D option কেন ভুল:** Security violation।
- **Related Concept:** Status/review date-ও থাকে।
- **মনে রাখার টিপস:** কী risk, কত বড়, কে দেখবে।


## প্রশ্ন 295 | Topic: Estimation > Uncertainty | Difficulty: Hard | Type: Theory

Q. Project শুরুতে estimate বেশি uncertain কেন?

A) Requirement/design/technical info অসম্পূর্ণ
B) সব defect জানা
C) Historical data নিষিদ্ধ
D) Team size কখনো জানা যায় না

**সঠিক উত্তর: A) Requirement/design/technical info অসম্পূর্ণ**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Scope, complexity, dependency ও risk সম্পর্কে তথ্য সীমিত।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Defect অজানা।
- **C option কেন ভুল:** Historical data useful।
- **D option কেন ভুল:** জানা থাকতে পারে।
- **Related Concept:** Progressive refinement দরকার।
- **মনে রাখার টিপস:** কম তথ্য → বড় range।


## প্রশ্ন 296 | Topic: Project Control > Baseline | Difficulty: Medium | Type: Theory

Q. Baseline-এর ব্যবহার?

A) সব change নিষিদ্ধ
B) Project name
C) Actual performance approved plan-এর সঙ্গে compare
D) Code execute

**সঠিক উত্তর: C) Actual performance approved plan-এর সঙ্গে compare**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Variance baseline reference থেকে মাপা হয়।
- **A option কেন ভুল:** Approved change সম্ভব।
- **B option কেন ভুল:** Naming নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Development activity।
- **Related Concept:** Unauthorized baseline change metric বিকৃত করে।
- **মনে রাখার টিপস:** Approved comparison point।


## প্রশ্ন 297 | Topic: Project Control > Corrective Action | Difficulty: Medium | Type: Scenario

Q. Project পিছিয়ে গেলে প্রথম logical step?

A) Analysis ছাড়া team double
B) Variance/root cause analyze করে action plan
C) সব requirement delete
D) Report বন্ধ

**সঠিক উত্তর: B) Variance/root cause analyze করে action plan**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Cause না বুঝে action করলে overhead বা নতুন সমস্যা হতে পারে।
- **A option কেন ভুল:** Brooks-type communication overhead।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Formal scope analysis ছাড়া নয়।
- **D option কেন ভুল:** Control দুর্বল।
- **Related Concept:** Measure, diagnose, correct।
- **মনে রাখার টিপস:** আগে কারণ।


## প্রশ্ন 298 | Topic: Function Point > Adjusted FP | Difficulty: Hard | Type: Calculation

Q. UFP=60, TDI=40; `VAF=0.65+0.01×TDI`, Adjusted FP কত?

A) 60
B) 40
C) 64
D) 63

**সঠিক উত্তর: D) 63**

### গাণিতিক/ধাপে ধাপে বিশ্লেষণ

#### Formula

```text
VAF = 0.65 + (0.01 × TDI)
Adjusted FP = UFP × VAF
```

#### Given Data

```text
UFP = 60
TDI = 40
```

#### Calculation

```text
0.01 × 40 = 0.40
VAF = 0.65 + 0.40 = 1.05
Adjusted FP = 60 × 1.05 = 63
```

#### Final Answer

```text
Adjusted Function Point = 63
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** VAF=1.05; 60×1.05=63।
- **A option কেন ভুল:** Adjustment বাদ।
- **B option কেন ভুল:** TDI final ধরা।
- **C option কেন ভুল:** Arithmetic ভুল।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** আগে VAF, পরে multiply।
- **মনে রাখার টিপস:** TDI influence adjustment।


## প্রশ্ন 299 | Topic: Estimation > COCOMO Calibration | Difficulty: Medium | Type: Theory

Q. Historical COCOMO modern project-এ calibration কেন দরকার?

A) Practice/tool/reuse/productivity বদলায়
B) Formula নেই
C) Voltage measure
D) Project data নিষিদ্ধ

**সঠিক উত্তর: A) Practice/tool/reuse/productivity বদলায়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Local environment অনুযায়ী coefficient ও driver adjust দরকার।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Mathematical model।
- **C option কেন ভুল:** Hardware voltage নয়।
- **D option কেন ভুল:** Historical data essential।
- **Related Concept:** Expert judgment combine করা যায়।
- **মনে রাখার টিপস:** Old model, new context → calibrate।


## প্রশ্ন 300 | Topic: Project Management > Closure | Difficulty: Easy | Type: Theory

Q. Project Closure-এর গুরুত্বপূর্ণ কাজ?

A) Unapproved feature
B) Test result delete
C) Deliverable acceptance, lessons learned, archive
D) Risk register hide

**সঠিক উত্তর: C) Deliverable acceptance, lessons learned, archive**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Formal acceptance, resource release ও organizational learning সম্পন্ন হয়।
- **A option কেন ভুল:** Scope creep।
- **B option কেন ভুল:** Evidence রাখতে হয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Transparency দরকার।
- **Related Concept:** Post-project review future estimate উন্নত করে।
- **মনে রাখার টিপস:** Accept, learn, archive, close।


# Section 02 Completion Report

```text
Question Range       = 181–300
Total Questions      = 120
Theory/Scenario      = 105
Calculation          = 15
Coverage             = Software Engineering full section
Difficulty           ≈ 25% Easy, 50% Medium, 25% Hard
```

# Consolidated Audit: Batch 01–07

```text
Total Question Range = 001–300
Section 01           = 001–180
Section 02           = 181–300
Total MCQ            = 300
Numbering            = Continuous
Raw LaTeX Commands   = Not used
Math Alignment       = Plain-text blocks
Language             = Bangla + English technical keywords
```
