# ১৯তম নিবন্ধন — প্রভাষক ICT

## Section 3: Data Structure, Algorithm & Combinatorial Optimization

### Batch 8 — Question 301–350

**Subject Code:** 452  
**Covered Area:** Complexity, Asymptotic Notation, Loop Count, Recurrence, Linear Search, Binary Search এবং Sorting Fundamentals  
**Theory/Scenario MCQ:** 30  
**Math/Calculation/Tracing MCQ:** 20  
**Difficulty:** Easy 13, Medium 25, Hard 12  
**Answer Distribution:** A = 13, B = 13, C = 12, D = 12

> **Math-format policy:** এই file-এ raw LaTeX command ব্যবহার করা হয়নি। সব formula, substitution ও calculation plain-text aligned code block-এ দেওয়া হয়েছে, যাতে GitHub README, mobile view এবং copy-paste—সব জায়গায় পরিষ্কার দেখা যায়।

---

# Chapter Theory 24: Algorithm Analysis and Asymptotic Notation

## ১. Algorithm Analysis কেন প্রয়োজন

একটি algorithm সঠিক result দিলেই যথেষ্ট নয়; input বড় হলে algorithm কত সময় ও memory ব্যবহার করবে সেটিও গুরুত্বপূর্ণ। একই problem-এর জন্য দুটি correct algorithm থাকতে পারে, কিন্তু একটি ১,০০০ input-এ ভালো এবং অন্যটি ১০ লাখ input-এ সম্পূর্ণ অকার্যকর হতে পারে। তাই machine speed বা নির্দিষ্ট programming language-এর পরিবর্তে input size `n` বাড়ার সঙ্গে resource usage কীভাবে বাড়ে, সেটি বিশ্লেষণ করা হয়।

Algorithm analysis-এর দুটি প্রধান resource:

- **Time Complexity:** মৌলিক operation কতবার execute হয়।
- **Space Complexity:** input ছাড়াও অতিরিক্ত memory কত প্রয়োজন হয়।

## ২. Best, Average এবং Worst Case

- **Best Case:** সবচেয়ে সুবিধাজনক input-এ minimum কাজ।
- **Average Case:** সম্ভাব্য input distribution অনুযায়ী expected কাজ।
- **Worst Case:** সবচেয়ে প্রতিকূল input-এ maximum কাজ।

Competitive exam-এ কোনো qualifier না থাকলে complexity বলতে অনেক সময় worst-case complexity বোঝানো হয়; তবে question-এর wording অবশ্যই পড়তে হবে।

## ৩. Big-O, Big-Omega এবং Big-Theta

### Big-O: Upper Bound

`f(n) = O(g(n))` বোঝায় যথেষ্ট বড় `n`-এর জন্য `f(n)` সর্বোচ্চ constant multiple of `g(n)`-এর মতো বাড়ে। এটি upper bound।

### Big-Omega: Lower Bound

`f(n) = Ω(g(n))` বোঝায় যথেষ্ট বড় `n`-এর জন্য `f(n)` অন্তত constant multiple of `g(n)`-এর মতো বাড়ে। এটি lower bound।

### Big-Theta: Tight Bound

`f(n) = Θ(g(n))` তখনই, যখন `f(n)` একই সঙ্গে `O(g(n))` এবং `Ω(g(n))`। অর্থাৎ growth rate উপরে ও নিচে একই asymptotic function দিয়ে bound করা যায়।

## ৪. Dominant Term Rule

Asymptotic analysis-এ constant coefficient এবং lower-order term বাদ যায়।

```text
7n² + 5n + 20  →  Θ(n²)
3n log n + 50n →  Θ(n log n)
1000            →  Θ(1)
```

কারণ `n` অনেক বড় হলে dominant term-ই growth নির্ধারণ করে। তবে বাস্তব ছোট input-এ constant factor গুরুত্বপূর্ণ হতে পারে—এটি asymptotic notation-এর সীমাবদ্ধতা।

## ৫. Common Growth Order

কম থেকে বেশি growth:

```text
1 < log n < √n < n < n log n < n² < n³ < 2ⁿ < n!
```

## ৬. Time–Space Trade-off

সময় কমানোর জন্য অতিরিক্ত memory ব্যবহার বা memory কমানোর জন্য বেশি computation করা হলে Time–Space Trade-off ঘটে। উদাহরণ:

- Memoization result cache করে সময় কমায়, memory বাড়ায়।
- Hash table দ্রুত search দিতে অতিরিক্ত storage ব্যবহার করে।
- In-place algorithm memory কমায়, কিন্তু implementation জটিল হতে পারে।

## Common Mistakes

- Big-O-কে সবসময় exact complexity মনে করা।
- `O(n²)` বলা মানেই algorithm কখনো `O(n³)` নয়—এমন মনে করা। আসলে upper bound loose হতে পারে।
- Average case ও amortized case একই মনে করা।
- Constant factor সব practical situation-এ অপ্রাসঙ্গিক মনে করা।

## Exam Tips

- Tight complexity চাইলে `Θ` খুঁজুন।
- “At most” বা upper limit → `O`।
- “At least” বা lower limit → `Ω`।
- Polynomial expression-এ highest-degree term রাখুন।

---

# MCQ Practice: Complexity and Asymptotic Notation

## প্রশ্ন 301 | Topic: Algorithm > Asymptotic Notation > Big-O | Difficulty: Easy | Type: Theory

Q. `Big-O` notation প্রধানত কী প্রকাশ করে?

A) শুধু exact running time  
B) Algorithm-এর lower bound  
C) Asymptotic upper bound  
D) শুধু memory address

**সঠিক উত্তর: C) Asymptotic upper bound**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `Big-O` যথেষ্ট বড় input-এর জন্য কোনো function-এর growth সর্বোচ্চ কোন asymptotic rate-এর মধ্যে থাকে তা প্রকাশ করে। এটি exact operation count নয়; upper bound।
- **A option কেন ভুল:** Exact running time machine, compiler, implementation ও constant factor-এর ওপর নির্ভর করে।
- **B option কেন ভুল:** Lower bound বোঝাতে `Big-Omega` ব্যবহৃত হয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Memory address-এর সঙ্গে asymptotic notation-এর সম্পর্ক নেই।
- **Related Concept:** Tight upper ও lower bound এক হলে `Big-Theta` পাওয়া যায়।
- **মনে রাখার টিপস:** `O` দেখলে “উপরে সীমা” মনে করুন।

---

## প্রশ্ন 302 | Topic: Algorithm > Asymptotic Notation > Big-Theta | Difficulty: Easy | Type: Theory

Q. কোনো function-এর asymptotic upper bound ও lower bound একই growth rate হলে কোন notation সবচেয়ে উপযুক্ত?

A) `Θ`  
B) `O`  
C) `Ω`  
D) `o`

**সঠিক উত্তর: A) `Θ`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `Θ(g(n))` বোঝায় function-টি উপরে ও নিচে উভয় দিক থেকেই `g(n)`-এর constant multiple দ্বারা bound করা যায়; তাই এটি tight bound।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `O` শুধু upper bound দেয়, tight হওয়া বাধ্যতামূলক নয়।
- **C option কেন ভুল:** `Ω` শুধু lower bound দেয়।
- **D option কেন ভুল:** Small-o strict upper growth relation বোঝায়; standard tight bound নয়।
- **Related Concept:** `f(n)=Θ(g(n))` হলে `f(n)=O(g(n))` এবং `f(n)=Ω(g(n))` দুটোই সত্য।
- **মনে রাখার টিপস:** `Theta = Tight`—দুটোর প্রথম অক্ষর `T`।

---

## প্রশ্ন 303 | Topic: Algorithm > Asymptotic Notation > Big-Omega | Difficulty: Easy | Type: Theory

Q. `Big-Omega` notation কোন ধরনের asymptotic bound প্রকাশ করে?

A) Average bound  
B) Exact machine time  
C) Upper bound  
D) Lower bound

**সঠিক উত্তর: D) Lower bound**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `Ω(g(n))` বোঝায় algorithm-এর growth যথেষ্ট বড় `n`-এ অন্তত `g(n)`-এর constant multiple-এর মতো।
- **A option কেন ভুল:** Average case একটি case analysis; `Ω` নিজে average বোঝায় না।
- **B option কেন ভুল:** এটি hardware-independent growth notation।
- **C option কেন ভুল:** Upper bound হলো `O`।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Comparison sorting-এর worst-case lower bound `Ω(n log n)`।
- **মনে রাখার টিপস:** Omega = minimum asymptotic guarantee।

---

## প্রশ্ন 304 | Topic: Algorithm > Complexity > Single Loop Count | Difficulty: Medium | Type: Calculation

Q. নিচের loop body মোট কতবার execute হবে?

```c
for (int i = 0; i < 25; i++) {
    /* body */
}
```

A) 24  
B) 25  
C) 26  
D) 50

**সঠিক উত্তর: B) 25**

### গাণিতিক বিশ্লেষণ

#### Formula / Rule

```text
for (i = a; i < b; i++) হলে iteration count = b - a
```

#### Given Data

```text
Initial value = 0
Upper limit   = 25 (exclusive)
Increment     = 1
```

#### Step-by-step Calculation

```text
Valid i values:
0, 1, 2, ..., 24

Count = 25 - 0
      = 25
```

#### Final Answer

```text
Loop body executes = 25 times
```

### Option বিশ্লেষণ

- **A) 24:** শেষ index 24 দেখে iteration count-ও 24 ধরে নেওয়া হয়েছে।
- **B) 25:** এটি সঠিক উত্তর।
- **C) 26:** Exclusive condition `i < 25`-কে inclusive ধরা হয়েছে।
- **D) 50:** কোনো যৌক্তিক loop count rule অনুসরণ করে না।
- **Related Concept:** `i <= 25` হলে count হতো 26।
- **মনে রাখার টিপস:** Zero থেকে `n-1` পর্যন্ত মোট `n`টি value।

---

## প্রশ্ন 305 | Topic: Algorithm > Complexity > Dominant Term | Difficulty: Easy | Type: Theory

Q. `8n³ + 4n² + 100` expression-এর tight asymptotic complexity কোনটি?

A) `Θ(n²)`  
B) `Θ(n³)`  
C) `Θ(100)`  
D) `Θ(8n³ + 4n²)`

**সঠিক উত্তর: B) `Θ(n³)`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** বড় `n`-এর জন্য highest-degree term `n³` dominant। Constant coefficient 8 এবং lower-order term বাদ যায়।
- **A option কেন ভুল:** `n²` dominant term নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Constant term input বৃদ্ধির সঙ্গে grow করে না।
- **D option কেন ভুল:** Asymptotic notation-এ lower-order term রাখা প্রয়োজন নেই; tight simplified form `Θ(n³)`।
- **Related Concept:** Polynomial complexity-তে সর্বোচ্চ exponent নির্ধারক।
- **মনে রাখার টিপস:** Highest power রাখুন, বাকিগুলো বাদ দিন।

---

## প্রশ্ন 306 | Topic: Algorithm > Complexity > Nested Loop | Difficulty: Hard | Type: Calculation

Q. নিচের code-এর time complexity কত?

```c
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n / 2; j++) {
        /* constant-time work */
    }
}
```

A) `Θ(n)`  
B) `Θ(log n)`  
C) `Θ(n²)`  
D) `Θ(n³)`

**সঠিক উত্তর: C) `Θ(n²)`**

### গাণিতিক বিশ্লেষণ

#### Formula / Rule

```text
Total operations = Outer iterations × Inner iterations
```

#### Given Data

```text
Outer loop = n times
Inner loop = n/2 times for each outer iteration
```

#### Step-by-step Calculation

```text
T(n) = n × (n/2)
     = n²/2
```

Asymptotic simplification:

```text
Constant factor 1/2 বাদ দিলে:
T(n) = Θ(n²)
```

#### Final Answer

```text
Time Complexity = Θ(n²)
```

### Option বিশ্লেষণ

- **A) Θ(n):** শুধু একটি loop গণনা করা হয়েছে।
- **B) Θ(log n):** কোনো loop multiplicatively বৃদ্ধি বা অর্ধেক হচ্ছে না।
- **C) Θ(n²):** এটি সঠিক উত্তর।
- **D) Θ(n³):** তৃতীয় nested loop নেই।
- **Related Concept:** Inner loop `n/2` হলেও constant factor বাদ যায়।
- **মনে রাখার টিপস:** Independent nested loops-এর count সাধারণত গুণ হয়।

---

## প্রশ্ন 307 | Topic: Algorithm > Complexity > Case Analysis | Difficulty: Easy | Type: Theory

Q. Linear Search-এ target প্রথম element-এ থাকলে এটি কোন case?

A) Best Case  
B) Average Case  
C) Worst Case  
D) Amortized Case

**সঠিক উত্তর: A) Best Case**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রথম comparison-এই target পাওয়া যায়; minimum operation লাগে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Average case সম্ভাব্য position-গুলোর expected comparison বিবেচনা করে।
- **C option কেন ভুল:** Worst case-এ target শেষে থাকে বা উপস্থিত থাকে না।
- **D option কেন ভুল:** Amortized analysis operation sequence-এর average cost; একটি search input-এর position নয়।
- **Related Concept:** Linear Search best-case `Θ(1)`, worst-case `Θ(n)`।
- **মনে রাখার টিপস:** প্রথমেই পাওয়া = Best Case।

---

## প্রশ্ন 308 | Topic: Algorithm > Complexity > Time-Space Trade-off | Difficulty: Medium | Type: Scenario

Q. Recursive Fibonacci function-এর result cache করে পুনরায় calculation এড়ানো কোন ধারণার উদাহরণ?

A) Data Compression  
B) External Sorting  
C) Deadlock Prevention  
D) Time–Space Trade-off

**সঠিক উত্তর: D) Time–Space Trade-off**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Cache বা memo table অতিরিক্ত memory ব্যবহার করে repeated computation কমায়; memory বাড়িয়ে সময় কমানো হচ্ছে।
- **A option কেন ভুল:** Data compression storage representation ছোট করে।
- **B option কেন ভুল:** External sorting secondary storage-এ বড় data sort করে।
- **C option কেন ভুল:** Deadlock OS resource-allocation সমস্যা।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Memoization naive Fibonacci-কে exponential থেকে linear time-এ নামাতে পারে।
- **মনে রাখার টিপস:** Memory খরচ করে speed বাড়ানো = Time–Space Trade-off।

---

## প্রশ্ন 309 | Topic: Algorithm > Complexity > Logarithmic Loop | Difficulty: Hard | Type: Calculation

Q. নিচের loop body মোট কতবার execute হবে?

```c
for (int i = 1; i <= 64; i *= 2) {
    /* body */
}
```

A) 6  
B) 8  
C) 7  
D) 64

**সঠিক উত্তর: C) 7**

### গাণিতিক বিশ্লেষণ

#### Rule

প্রতি iteration-এ value দ্বিগুণ হলে iteration count logarithmic হয়।

#### Given Data

```text
Start = 1
Limit = 64 (inclusive)
Update = i × 2
```

#### Step-by-step Trace

```text
Iteration 1: i = 1
Iteration 2: i = 2
Iteration 3: i = 4
Iteration 4: i = 8
Iteration 5: i = 16
Iteration 6: i = 32
Iteration 7: i = 64
Next value  : i = 128 → condition false
```

#### Formula Check

```text
Count = log₂(64) + 1
      = 6 + 1
      = 7
```

#### Final Answer

```text
Loop body executes = 7 times
```

### Option বিশ্লেষণ

- **A) 6:** `log₂64 = 6` নেওয়া হয়েছে, কিন্তু starting value 1-এর iteration বাদ গেছে।
- **B) 8:** একটি অতিরিক্ত 128 iteration ধরা হয়েছে।
- **C) 7:** এটি সঠিক উত্তর।
- **D) 64:** Multiplicative loop-কে linear loop ধরা হয়েছে।
- **Related Concept:** `i < 64` হলে values 1–32, মোট 6 iteration হতো।
- **মনে রাখার টিপস:** Inclusive power limit হলে প্রায়ই `log + 1` হয়।

---

## প্রশ্ন 310 | Topic: Algorithm > Complexity > Combined Terms | Difficulty: Easy | Type: Theory

Q. `n² + n log n + n`-এর tight asymptotic complexity কোনটি?

A) `Θ(n log n)`  
B) `Θ(n²)`  
C) `Θ(n)`  
D) `Θ(log n)`

**সঠিক উত্তর: B) `Θ(n²)`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `n²`, `n log n`-এর চেয়ে দ্রুত বাড়ে; তাই dominant term `n²`।
- **A option কেন ভুল:** `n log n` lower-order term।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Linear term dominant নয়।
- **D option কেন ভুল:** Logarithmic term expression-এ dominant নয়।
- **Related Concept:** `n² + 1000n log n`-এও asymptotically `n²` dominant, যদিও ছোট input-এ coefficient প্রভাব ফেলতে পারে।
- **মনে রাখার টিপস:** Growth order compare করুন, coefficient নয়।

---

# Chapter Theory 25: Loop Counting, Recurrence and Amortized Analysis

## ১. Loop Count নির্ণয়ের পদ্ধতি

Loop complexity বের করতে তিনটি বিষয় দেখুন:

1. Initial value
2. Termination condition
3. Update rule

### Linear Update

```c
for (i = 0; i < n; i++)
```

Iteration `n`, complexity `Θ(n)`।

### Multiplicative Update

```c
for (i = 1; i < n; i *= 2)
```

Iteration প্রায় `log₂n`, complexity `Θ(log n)`।

### Triangular Nested Loop

```c
for (i = 1; i <= n; i++)
    for (j = 1; j <= i; j++)
```

Total:

```text
1 + 2 + 3 + ... + n
= n(n+1)/2
= Θ(n²)
```

## ২. Recurrence Relation

Recursive algorithm-এর running time নিজের ছোট input-এর running time দিয়ে প্রকাশ করলে recurrence হয়।

উদাহরণ:

```text
Binary Search: T(n) = T(n/2) + Θ(1)
Merge Sort   : T(n) = 2T(n/2) + Θ(n)
```

## ৩. Master Theorem

Standard form:

```text
T(n) = aT(n/b) + f(n)
```

Compare করতে হয় `f(n)` এবং `n^(log_b a)`।

- `f(n)` polynomially smaller → recursive part dominant।
- একই order → extra `log n` factor।
- `f(n)` polynomially larger এবং regularity condition পূরণ → `f(n)` dominant।

## ৪. Amortized Analysis

একটি operation sequence-এর total costকে operation সংখ্যা দিয়ে ভাগ করে average cost বের করা হয়। এটি probability-based average case নয়।

Dynamic array append-এ মাঝে মাঝে resize costly `O(n)`, কিন্তু বহু append-এর ওপর average বা amortized cost `O(1)`।

## Common Mistakes

- Nested loop মানেই সবসময় `O(n²)`—ভুল; inner bounds দেখতে হবে।
- Multiplicative update-কে linear count করা।
- Master theorem-এর `a`, `b`, `f(n)` ভুল শনাক্ত করা।
- Average case ও amortized analysis একই মনে করা।

---

# MCQ Practice: Loop, Recurrence and Amortized Analysis

## প্রশ্ন 311 | Topic: Algorithm > Loop Count > Triangular Loop | Difficulty: Hard | Type: Calculation

Q. নিচের code-এ statement মোট কতবার execute হবে, যদি `n = 5`?

```c
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= i; j++) {
        statement;
    }
}
```

A) 15  
B) 10  
C) 25  
D) 5

**সঠিক উত্তর: A) 15**

### গাণিতিক বিশ্লেষণ

#### Formula

```text
1 + 2 + ... + n = n(n+1)/2
```

#### Given Data

```text
n = 5
```

#### Step-by-step Trace

```text
i = 1 → 1 বার
i = 2 → 2 বার
i = 3 → 3 বার
i = 4 → 4 বার
i = 5 → 5 বার
```

#### Calculation

```text
Total = 1 + 2 + 3 + 4 + 5
      = 15
```

Formula দিয়ে:

```text
Total = 5(5+1)/2
      = 5×6/2
      = 15
```

#### Final Answer

```text
Statement executes = 15 times
```

### Option বিশ্লেষণ

- **A) 15:** এটি সঠিক উত্তর।
- **B) 10:** শেষ row বা কিছু iteration বাদ গেছে।
- **C) 25:** Inner loop সবসময় 5 বার চলে ধরে `5×5` করা হয়েছে।
- **D) 5:** শুধু outer loop count নেওয়া হয়েছে।
- **Related Concept:** General complexity `Θ(n²)`।
- **মনে রাখার টিপস:** Inner limit `i` হলে triangular sum চিনুন।

---

## প্রশ্ন 312 | Topic: Algorithm > Recurrence > Linear Recurrence | Difficulty: Medium | Type: Theory

Q. `T(n) = T(n−1) + Θ(1)` recurrence-এর solution কোনটি?

A) `Θ(log n)`  
B) `Θ(n log n)`  
C) `Θ(n²)`  
D) `Θ(n)`

**সঠিক উত্তর: D) `Θ(n)`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Recurrence expand করলে `T(n)=T(n-1)+c`, তারপর `T(n-2)+2c`—এভাবে base case পর্যন্ত প্রায় `n`টি constant term যোগ হয়।
- **A option কেন ভুল:** Input প্রতি ধাপে অর্ধেক হলে logarithmic হতো।
- **B option কেন ভুল:** প্রতিটি level-এ linear work নেই।
- **C option কেন ভুল:** প্রতিটি recursive level-এ বাড়তে থাকা linear work যোগ হচ্ছে না।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Recursive factorial-এর time recurrence সাধারণত একই form।
- **মনে রাখার টিপস:** `n` থেকে প্রতি ধাপে 1 কমলে depth `n`।

---

## প্রশ্ন 313 | Topic: Algorithm > Recurrence > Merge-Sort Form | Difficulty: Hard | Type: Calculation

Q. নিচের recurrence-এর tight solution কোনটি?

```text
T(n) = 2T(n/2) + n
```

A) `Θ(n)`  
B) `Θ(n log n)`  
C) `Θ(log n)`  
D) `Θ(n²)`

**সঠিক উত্তর: B) `Θ(n log n)`**

### গাণিতিক বিশ্লেষণ

#### Master-Theorem Form

```text
T(n) = aT(n/b) + f(n)
```

#### Given Data

```text
a    = 2
b    = 2
f(n) = n
```

#### Critical Term

```text
n^(log_b a)
= n^(log₂2)
= n¹
= n
```

#### Comparison

```text
f(n) = n
Critical term = n

দুটির order একই।
```

একই order হলে একটি অতিরিক্ত `log n` factor হয়:

```text
T(n) = Θ(n log n)
```

#### Final Answer

```text
T(n) = Θ(n log n)
```

### Option বিশ্লেষণ

- **A) Θ(n):** Recursion level-এর সংখ্যা `log n` বাদ গেছে।
- **B) Θ(n log n):** এটি সঠিক উত্তর।
- **C) Θ(log n):** প্রতি level-এর মোট linear work উপেক্ষা করা হয়েছে।
- **D) Θ(n²):** Growth অতিরিক্ত ধরা হয়েছে।
- **Related Concept:** Merge Sort-এর standard recurrence এটি।
- **মনে রাখার টিপস:** `2T(n/2)+n` দেখলে Merge Sort → `n log n`।

---

## প্রশ্ন 314 | Topic: Algorithm > Recurrence > Binary-Search Form | Difficulty: Medium | Type: Theory

Q. `T(n) = T(n/2) + Θ(1)` recurrence-এর solution কোনটি?

A) `Θ(n)`  
B) `Θ(n²)`  
C) `Θ(log n)`  
D) `Θ(n log n)`

**সঠিক উত্তর: C) `Θ(log n)`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Input প্রতি recursive step-এ অর্ধেক হয়। `n/2^k = 1` হলে `k = log₂n`। প্রতি level-এ constant work, তাই total `Θ(log n)`।
- **A option কেন ভুল:** Input 1 করে কমছে না।
- **B option কেন ভুল:** Nested quadratic work নেই।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** প্রতি level-এ `n` work নেই।
- **Related Concept:** Binary Search-এর standard recurrence।
- **মনে রাখার টিপস:** Half each step → logarithmic depth।

---

## প্রশ্ন 315 | Topic: Algorithm > Recurrence > Master Theorem | Difficulty: Hard | Type: Calculation

Q. নিচের recurrence-এর dominant asymptotic complexity কোনটি?

```text
T(n) = 3T(n/2) + n
```

A) `Θ(n)`  
B) `Θ(n log n)`  
C) `Θ(n²)`  
D) `Θ(n^(log₂3))`

**সঠিক উত্তর: D) `Θ(n^(log₂3))`**

### গাণিতিক বিশ্লেষণ

#### Given Data

```text
a    = 3
b    = 2
f(n) = n
```

#### Critical Term

```text
n^(log_b a)
= n^(log₂3)
≈ n^1.585
```

#### Comparison

```text
Critical term ≈ n^1.585
f(n)          = n^1
```

`f(n)` critical term-এর তুলনায় polynomially smaller। তাই recursive অংশ dominant।

#### Final Answer

```text
T(n) = Θ(n^(log₂3))
```

### Option বিশ্লেষণ

- **A) Θ(n):** তিনটি recursive branch-এর growth উপেক্ষা করা হয়েছে।
- **B) Θ(n log n):** এটি `2T(n/2)+n`-এর ফল; এখানে `a=3`।
- **C) Θ(n²):** Upper estimate হতে পারে, কিন্তু tight নয়।
- **D) Θ(n^(log₂3)):** এটি সঠিক উত্তর।
- **Related Concept:** `log₂3 ≈ 1.585`।
- **মনে রাখার টিপস:** Master theorem-এ `a` পরিবর্তিত হলে critical exponent বদলায়।

---

## প্রশ্ন 316 | Topic: Algorithm > Analysis > Amortized Cost | Difficulty: Hard | Type: Theory

Q. Dynamic array-এ মাঝে মাঝে resize operation `O(n)` হলেও append-এর amortized cost সাধারণত কেন `O(1)`?

A) Expensive resize cost বহু cheap append-এর ওপর ছড়িয়ে যায়  
B) প্রতিটি append-এ নতুন array তৈরি হয়  
C) Resize কখনো ঘটে না  
D) Average-case probability সবসময় zero

**সঠিক উত্তর: A) Expensive resize cost বহু cheap append-এর ওপর ছড়িয়ে যায়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Capacity সাধারণত geometricভাবে বাড়ানো হয়। `n`টি append-এর মধ্যে resize cost-এর মোট যোগফল linear, তাই প্রতি append average amortized cost constant।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** প্রতিবার নতুন array তৈরি হলে cost constant থাকত না।
- **C option কেন ভুল:** Capacity পূর্ণ হলে resize ঘটে।
- **D option কেন ভুল:** Amortized analysis probability-based নয়।
- **Related Concept:** Aggregate, Accounting এবং Potential method amortized analysis-এর কৌশল।
- **মনে রাখার টিপস:** Rare expensive operation + many cheap operations = amortized constant হতে পারে।

---

# Chapter Theory 26: Linear Search and Binary Search

## ১. Linear Search

Array বা list-এর element একে একে পরীক্ষা করা হয়। Sorted হওয়া প্রয়োজন নেই।

```text
Best case  = 1 comparison   → Θ(1)
Worst case = n comparisons  → Θ(n)
Average    ≈ (n+1)/2        → Θ(n)
```

Linked list ও unsorted small collection-এ Linear Search সরল ও কার্যকর হতে পারে।

## ২. Binary Search

Sorted random-access collection-এ middle element-এর সঙ্গে key compare করে search interval অর্ধেক করা হয়।

```text
Worst-case time = Θ(log n)
Iterative space = Θ(1)
Recursive extra stack = Θ(log n)
```

### Core Rule

- `key == a[mid]` → found
- `key < a[mid]` → right boundary `mid−1`
- `key > a[mid]` → left boundary `mid+1`

Overflow-safe midpoint:

```c
mid = low + (high - low) / 2;
```

## ৩. Maximum Comparison

Successful বা unsuccessful binary search-এর convention অনুযায়ী exact count ভিন্নভাবে লেখা হতে পারে। Inclusive indexed array-এ common upper bound:

```text
Maximum comparisons = floor(log₂n) + 1
```

## ৪. Binary Search-এর সীমাবদ্ধতা

- Data sorted থাকতে হয়।
- Linked list-এ middle access `O(n)` হওয়ায় সাধারণ binary search সুবিধা হারায়।
- Frequent insertion/deletion হলে sorted array maintain করা costly।

## Common Mistakes

- Unsorted data-তে Binary Search প্রয়োগ করা।
- `low = mid` বা `high = mid` দিয়ে interval না কমিয়ে infinite loop তৈরি করা।
- Midpoint overflow উপেক্ষা করা।
- Comparison count ও loop iteration count গুলিয়ে ফেলা।

---

# MCQ Practice: Searching

## প্রশ্ন 317 | Topic: Algorithm > Searching > Linear Search | Difficulty: Easy | Type: Theory

Q. Linear Search প্রয়োগের জন্য data sorted হওয়া কি আবশ্যক?

A) শুধু descending order আবশ্যক  
B) শুধু ascending order আবশ্যক  
C) না, sorted হওয়া আবশ্যক নয়  
D) Hash order আবশ্যক

**সঠিক উত্তর: C) না, sorted হওয়া আবশ্যক নয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Linear Search sequentialভাবে প্রতিটি element পরীক্ষা করে; order-এর ওপর নির্ভর করে না।
- **A option কেন ভুল:** Descending order প্রয়োজন নেই।
- **B option কেন ভুল:** Ascending order-ও প্রয়োজন নেই।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Hashing পৃথক searching technique।
- **Related Concept:** Sorted data থাকলেও small input-এ Linear Search acceptable হতে পারে।
- **মনে রাখার টিপস:** Linear = একে একে; order যেকোনো।

---

## প্রশ্ন 318 | Topic: Algorithm > Searching > Linear Search Comparisons | Difficulty: Medium | Type: Calculation

Q. 12টি element-এর array-এ target অনুপস্থিত হলে Linear Search সর্বোচ্চ কতটি comparison করবে?

A) 11  
B) 12  
C) 6  
D) 13

**সঠিক উত্তর: B) 12**

### গাণিতিক বিশ্লেষণ

#### Rule

```text
Target absent হলে প্রতিটি element পরীক্ষা করতে হয়।
Worst-case comparisons = n
```

#### Given Data

```text
n = 12
```

#### Calculation

```text
Comparisons = n
            = 12
```

#### Final Answer

```text
Maximum comparisons = 12
```

### Option বিশ্লেষণ

- **A) 11:** শেষ element পরীক্ষা করা হয়নি ধরে নেওয়া হয়েছে।
- **B) 12:** এটি সঠিক উত্তর।
- **C) 6:** Average-এর কাছাকাছি value, worst-case নয়।
- **D) 13:** Array size-এর চেয়ে একটি অতিরিক্ত comparison ধরা হয়েছে।
- **Related Concept:** Target last position-এ থাকলেও 12 comparison লাগে।
- **মনে রাখার টিপস:** Absent বা last position → Linear Search worst case `n`।

---

## প্রশ্ন 319 | Topic: Algorithm > Searching > Binary Search Requirement | Difficulty: Easy | Type: Theory

Q. Standard Binary Search-এর মৌলিক prerequisite কোনটি?

A) Data অবশ্যই linked list হতে হবে  
B) Data অবশ্যই duplicated হবে  
C) Data random order-এ থাকবে  
D) Search range sorted থাকতে হবে

**সঠিক উত্তর: D) Search range sorted থাকতে হবে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Middle comparison-এর ভিত্তিতে অর্ধেক range বাদ দেওয়ার যুক্তি কেবল sorted order-এ valid।
- **A option কেন ভুল:** Array বা random-access structure বেশি উপযোগী।
- **B option কেন ভুল:** Duplicate থাকা বাধ্যতামূলক নয়।
- **C option কেন ভুল:** Random order-এ কোন অর্ধেক বাদ দিতে হবে জানা যায় না।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Monotonic predicate-এর ওপরও binary search প্রয়োগ করা যায়।
- **মনে রাখার টিপস:** Binary Search-এর প্রাণ হলো order।

---

## প্রশ্ন 320 | Topic: Algorithm > Searching > Binary Search Comparisons | Difficulty: Hard | Type: Calculation

Q. 16টি sorted element-এর array-এ standard inclusive Binary Search সর্বোচ্চ কতটি key comparison করতে পারে?

A) 5  
B) 4  
C) 8  
D) 16

**সঠিক উত্তর: A) 5**

### গাণিতিক বিশ্লেষণ

#### Common Formula

```text
Maximum comparisons = floor(log₂n) + 1
```

#### Given Data

```text
n = 16
```

#### Step-by-step Calculation

```text
log₂16 = 4

Maximum comparisons
= 4 + 1
= 5
```

Interval-size view:

```text
16 → 8 → 4 → 2 → 1
```

এখানে পাঁচটি candidate level পরীক্ষা হতে পারে।

#### Final Answer

```text
Maximum comparisons = 5
```

### Option বিশ্লেষণ

- **A) 5:** এটি সঠিক উত্তর।
- **B) 4:** শুধু `log₂16` নেওয়া হয়েছে; final single candidate comparison বাদ গেছে।
- **C) 8:** প্রথম halving-এর size নেওয়া হয়েছে।
- **D) 16:** Linear Search-এর মতো গণনা করা হয়েছে।
- **Related Concept:** Exact count implementation ও success/unsuccessful convention অনুযায়ী wording দেখে নিতে হবে।
- **মনে রাখার টিপস:** Inclusive search-এর common max = floor(log₂n)+1।

---

## প্রশ্ন 321 | Topic: Algorithm > Searching > Binary Search Update | Difficulty: Medium | Type: Theory

Q. Ascending sorted array-এ `key < a[mid]` হলে পরবর্তী step কী?

A) `low = mid + 1`  
B) `high = mid - 1`  
C) পুরো array আবার শুরু থেকে search  
D) `low` ও `high` দুটোই zero

**সঠিক উত্তর: B) `high = mid - 1`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Key middle value-এর চেয়ে ছোট হলে key কেবল left half-এ থাকতে পারে।
- **A option কেন ভুল:** এটি right half নির্বাচন করে, যা বড় value-র জন্য।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এতে Binary Search-এর logarithmic সুবিধা নষ্ট হয়।
- **D option কেন ভুল:** Search interval ভুলভাবে reset হবে।
- **Related Concept:** `key > a[mid]` হলে `low = mid + 1`।
- **মনে রাখার টিপস:** Key ছোট → high কমান।

---

## প্রশ্ন 322 | Topic: Algorithm > Searching > Iterative vs Recursive Binary Search | Difficulty: Medium | Type: Theory

Q. Iterative Binary Search-এর তুলনায় Recursive Binary Search-এর অতিরিক্ত space সাধারণত কত?

A) `Θ(n)`  
B) `Θ(n²)`  
C) `Θ(1)`  
D) `Θ(log n)` call stack

**সঠিক উত্তর: D) `Θ(log n)` call stack**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Recursive depth প্রায় `log n`; প্রতিটি call stack frame ব্যবহার করে। Iterative version সাধারণত constant extra variables ব্যবহার করে।
- **A option কেন ভুল:** Depth linear নয়, কারণ input অর্ধেক হয়।
- **B option কেন ভুল:** Quadratic storage লাগে না।
- **C option কেন ভুল:** এটি iterative version-এর space; recursive call stack constant নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** উভয়ের time complexity `Θ(log n)`।
- **মনে রাখার টিপস:** Recursion time একই হলেও stack space যোগ করে।

---

## প্রশ্ন 323 | Topic: Algorithm > Searching > Binary Search Trace | Difficulty: Hard | Type: Calculation

Q. Sorted array `[1,2,3,...,15]`-এ standard Binary Search দিয়ে `14` খুঁজতে কতটি comparison লাগে?

A) 3  
B) 2  
C) 4  
D) 14

**সঠিক উত্তর: A) 3**

### Step-by-step Tracing

Index 0–14 ধরে:

```text
Step 1:
low=0, high=14
mid=(0+14)/2=7
value=8
14 > 8 → right half

Step 2:
low=8, high=14
mid=(8+14)/2=11
value=12
14 > 12 → right half

Step 3:
low=12, high=14
mid=(12+14)/2=13
value=14 → found
```

#### Final Answer

```text
Total comparisons = 3
```

### Option বিশ্লেষণ

- **A) 3:** এটি সঠিক উত্তর।
- **B) 2:** Final comparison বাদ দেওয়া হয়েছে।
- **C) 4:** একটি অতিরিক্ত step ধরা হয়েছে।
- **D) 14:** Linear Search-এর মতো ধরে নেওয়া হয়েছে।
- **Related Concept:** Search path midpoint calculation rule-এর ওপর নির্ভর করে।
- **মনে রাখার টিপস:** প্রতিটি visited midpoint একটি comparison।

---

## প্রশ্ন 324 | Topic: Algorithm > Searching > Linear Search Best Case | Difficulty: Easy | Type: Theory

Q. Linear Search-এর best-case time complexity কোনটি?

A) `Θ(n)`  
B) `Θ(log n)`  
C) `Θ(1)`  
D) `Θ(n²)`

**সঠিক উত্তর: C) `Θ(1)`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Target প্রথম element-এ থাকলে একটি comparison-এই search শেষ হয়।
- **A option কেন ভুল:** এটি worst-case tight bound।
- **B option কেন ভুল:** এটি Binary Search-এর complexity।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Nested processing নেই।
- **Related Concept:** Average ও worst case `Θ(n)`।
- **মনে রাখার টিপস:** First hit = constant time।

---

# Chapter Theory 27: Sorting Fundamentals

## ১. Sorting-এর উদ্দেশ্য

Data নির্দিষ্ট key অনুযায়ী ascending বা descending order-এ সাজানোকে Sorting বলা হয়। Sorting-এর পরে search, duplicate detection, reporting এবং merging সহজ হয়।

## ২. গুরুত্বপূর্ণ বৈশিষ্ট্য

### Stable Sort

Equal key-যুক্ত record-এর original relative order বজায় থাকে। Multi-key sorting-এ stability গুরুত্বপূর্ণ।

### In-place Sort

Input storage-এর বাইরে খুব কম অতিরিক্ত memory ব্যবহার করে। সাধারণভাবে `O(1)` auxiliary space বোঝানো হয়, তবে recursion stack-এর treatment context অনুযায়ী উল্লেখ করা দরকার।

### Adaptive Sort

Input আংশিক sorted হলে কম কাজ করে। Insertion Sort adaptive; standard Selection Sort সাধারণত নয়।

### Comparison Sort

Element comparison-এর ওপর order নির্ধারণ করে। General comparison model-এ worst-case lower bound `Ω(n log n)`।

## ৩. Elementary Sorting Algorithms

### Selection Sort

প্রতি pass-এ unsorted অংশ থেকে minimum নির্বাচন করে সামনে আনে।

```text
Comparisons = n(n-1)/2
Swaps ≤ n-1
Time = Θ(n²) in best/average/worst
```

সাধারণ implementation unstable, কিন্তু কম swap করে।

### Insertion Sort

প্রতিটি নতুন element sorted prefix-এর সঠিক স্থানে insert করে।

```text
Best = Θ(n)
Average/Worst = Θ(n²)
```

Stable, in-place এবং small/nearly-sorted input-এ কার্যকর।

### Bubble Sort

Adjacent out-of-order pair swap করে বড় element শেষে “bubble” করে। Optimized early-exit version sorted input-এ `Θ(n)`। Standard stable ও in-place।

## Common Mistakes

- Selection Sort-কে stable মনে করা।
- Bubble Sort-এর optimized best case ও unoptimized version গুলিয়ে ফেলা।
- Comparison ও swap count একই মনে করা।
- In-place মানেই recursion stack শূন্য—এমন ধরে নেওয়া।

---

# MCQ Practice: Sorting Fundamentals

## প্রশ্ন 325 | Topic: Algorithm > Sorting > Stability | Difficulty: Easy | Type: Theory

Q. Stable Sorting Algorithm-এর বৈশিষ্ট্য কোনটি?

A) সবসময় `O(n)` time নেয়  
B) Extra memory ব্যবহার করে না  
C) Equal key-যুক্ত element-এর relative order বজায় রাখে  
D) Duplicate element delete করে

**সঠিক উত্তর: C) Equal key-যুক্ত element-এর relative order বজায় রাখে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Stability equality-এর ক্ষেত্রে input order preserve করে।
- **A option কেন ভুল:** Stable algorithm quadratic বা `n log n`—দুটিই হতে পারে।
- **B option কেন ভুল:** Stability ও auxiliary space আলাদা property।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Sorting duplicate remove করে না।
- **Related Concept:** Insertion, Bubble ও Merge Sort সাধারণ implementation-এ stable।
- **মনে রাখার টিপস:** Equal records-এর আগের order বাঁচলে Stable।

---

## প্রশ্ন 326 | Topic: Algorithm > Sorting > Selection Sort Comparisons | Difficulty: Hard | Type: Calculation

Q. 8টি element-এর array-এ Selection Sort মোট কতটি key comparison করে?

A) 28  
B) 56  
C) 16  
D) 7

**সঠিক উত্তর: A) 28**

### গাণিতিক বিশ্লেষণ

#### Formula

```text
Comparisons = (n-1) + (n-2) + ... + 1
            = n(n-1)/2
```

#### Given Data

```text
n = 8
```

#### Calculation

```text
Comparisons = 8(8-1)/2
            = 8×7/2
            = 56/2
            = 28
```

#### Final Answer

```text
Total comparisons = 28
```

### Option বিশ্লেষণ

- **A) 28:** এটি সঠিক উত্তর।
- **B) 56:** Division by 2 বাদ গেছে।
- **C) 16:** `n×2` করা হয়েছে।
- **D) 7:** এটি maximum swaps-এর কাছাকাছি, comparisons নয়।
- **Related Concept:** Input sorted হলেও standard Selection Sort 28 comparison-ই করে।
- **মনে রাখার টিপস:** Selection comparisons = `n choose 2`।

---

## প্রশ্ন 327 | Topic: Algorithm > Sorting > Insertion Sort | Difficulty: Medium | Type: Theory

Q. ইতোমধ্যে sorted input-এর ক্ষেত্রে Insertion Sort-এর best-case complexity কোনটি?

A) `Θ(n²)`  
B) `Θ(n)`  
C) `Θ(log n)`  
D) `Θ(1)`

**সঠিক উত্তর: B) `Θ(n)`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি element আগের element-এর সঙ্গে একবার compare হয়ে যথাস্থানে থাকে; shift প্রয়োজন হয় না।
- **A option কেন ভুল:** Average/worst case।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Binary reduction নেই।
- **D option কেন ভুল:** সব `n` element অন্তত inspect করতে হয়।
- **Related Concept:** এই adaptive behavior nearly-sorted data-তেও ভালো ফল দেয়।
- **মনে রাখার টিপস:** Sorted input + Insertion Sort = linear।

---

## প্রশ্ন 328 | Topic: Algorithm > Sorting > Bubble Sort Comparisons | Difficulty: Medium | Type: Calculation

Q. 6টি element-এর array-এ unoptimized Bubble Sort-এর worst-case total comparison কত?

A) 6  
B) 30  
C) 12  
D) 15

**সঠিক উত্তর: D) 15**

### গাণিতিক বিশ্লেষণ

#### Formula

```text
Comparisons = (n-1) + (n-2) + ... + 1
            = n(n-1)/2
```

#### Given Data

```text
n = 6
```

#### Calculation

```text
Comparisons = 6×5/2
            = 30/2
            = 15
```

#### Final Answer

```text
Total comparisons = 15
```

### Option বিশ্লেষণ

- **A) 6:** শুধু element count নেওয়া হয়েছে।
- **B) 30:** Division by 2 বাদ গেছে।
- **C) 12:** Pass count ও comparison count ভুলভাবে মেশানো হয়েছে।
- **D) 15:** এটি সঠিক উত্তর।
- **Related Concept:** Worst-case swap-ও reverse-sorted input-এ 15 হতে পারে।
- **মনে রাখার টিপস:** Bubble comparison sum-ও triangular।

---

## প্রশ্ন 329 | Topic: Algorithm > Sorting > Selection Sort Swaps | Difficulty: Easy | Type: Theory

Q. Standard Selection Sort সর্বোচ্চ কতটি swap করে?

A) `n−1`  
B) `n(n−1)/2`  
C) `log n`  
D) `n²`

**সঠিক উত্তর: A) `n−1`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি pass-এ সর্বোচ্চ একটি swap, মোট `n−1` pass।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এটি comparison count।
- **C option কেন ভুল:** Selection Sort logarithmic pass ব্যবহার করে না।
- **D option কেন ভুল:** Swap count quadratic নয়, যদিও time complexity quadratic।
- **Related Concept:** Write operation costly হলে Selection Sort-এর কম swap সুবিধাজনক হতে পারে।
- **মনে রাখার টিপস:** Selection অনেক compare, অল্প swap।

---

## প্রশ্ন 330 | Topic: Algorithm > Sorting > Optimized Bubble Sort | Difficulty: Medium | Type: Theory

Q. Swap flag-যুক্ত optimized Bubble Sort-এর sorted input-এ best-case complexity কত?

A) `Θ(n²)`  
B) `Θ(log n)`  
C) `Θ(n)`  
D) `Θ(1)`

**সঠিক উত্তর: C) `Θ(n)`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রথম pass-এ `n−1` comparison হয়; কোনো swap না হলে algorithm early exit করে।
- **A option কেন ভুল:** Unoptimized version সব pass চালালে quadratic হতে পারে।
- **B option কেন ভুল:** Input half করা হয় না।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Sorted কিনা বুঝতে অন্তত linear scan প্রয়োজন।
- **Related Concept:** Bubble Sort adaptive করতে swap flag প্রয়োজন।
- **মনে রাখার টিপস:** No swap in first pass → already sorted।

---

## প্রশ্ন 331 | Topic: Algorithm > Sorting > Insertion Operation | Difficulty: Medium | Type: Calculation

Q. Sorted list `[2, 4, 6, 8]`-এ Insertion Sort logic দিয়ে `5` insert করতে কতটি element right shift করতে হবে?

A) 4  
B) 1  
C) 3  
D) 2

**সঠিক উত্তর: D) 2**

### Step-by-step Tracing

```text
List = [2, 4, 6, 8]
Key  = 5
```

Right থেকে compare:

```text
8 > 5 → 8 এক ঘর right shift
6 > 5 → 6 এক ঘর right shift
4 < 5 → stop
```

Result:

```text
[2, 4, 5, 6, 8]
```

#### Final Answer

```text
Shifted elements = 2
```

### Option বিশ্লেষণ

- **A) 4:** সব element shift করা হয়েছে ধরে নেওয়া হয়েছে।
- **B) 1:** শুধু 8 shift ধরা হয়েছে; 6 বাদ গেছে।
- **C) 3:** 4-কেও ভুলভাবে shift করা হয়েছে।
- **D) 2:** এটি সঠিক উত্তর।
- **Related Concept:** Shift count key-এর চেয়ে বড় predecessor-এর সংখ্যার সমান।
- **মনে রাখার টিপস:** Key-এর চেয়ে বড় element-গুলোকেই সরান।

---

## প্রশ্ন 332 | Topic: Algorithm > Sorting > Comparison Lower Bound | Difficulty: Hard | Type: Theory

Q. General comparison-based sorting-এর worst-case lower bound কোনটি?

A) `Ω(n)`  
B) `Ω(n log n)`  
C) `Ω(log n)`  
D) `Ω(n²)`

**সঠিক উত্তর: B) `Ω(n log n)`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Decision tree-তে `n!` permutation আলাদা করতে height অন্তত `log₂(n!)`, যা `Ω(n log n)`।
- **A option কেন ভুল:** Linear lower bound যথেষ্ট tight নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `n!` outcome আলাদা করতে শুধু logarithmic comparison যথেষ্ট নয়।
- **D option কেন ভুল:** Merge Sort ও Heap Sort `O(n log n)` হওয়ায় quadratic universal lower bound হতে পারে না।
- **Related Concept:** Counting/Radix Sort comparison model-এর সীমাবদ্ধতা এড়িয়ে যেতে পারে।
- **মনে রাখার টিপস:** Comparison sort barrier = `n log n`।

---

# Chapter Theory 28: Merge Sort, Quick Sort, Radix Sort and Sorting Selection

## ১. Merge Sort

Divide-and-Conquer algorithm:

1. Array দুই ভাগ
2. দুই ভাগ recursively sort
3. Sorted halves merge

```text
Best/Average/Worst Time = Θ(n log n)
Typical Auxiliary Space = Θ(n)
Stable                  = Yes
```

Linked list ও external sorting-এ Merge Sort সুবিধাজনক।

## ২. Quick Sort

1. Pivot নির্বাচন
2. Partition
3. Left/right অংশ recursively sort

```text
Best/Average or Expected = Θ(n log n)
Worst                    = Θ(n²)
```

সাধারণ array implementation প্রায় in-place, cache-friendly, কিন্তু standard partition সাধারণত unstable। Random pivot worst-case probability কমায়; worst case অসম্ভব করে না।

## ৩. Radix Sort

Digit/character position অনুযায়ী stable sub-sort ব্যবহার করে। এটি comparison-based নয়।

```text
Time ≈ Θ(d(n + k))
```

যেখানে `d` digit সংখ্যা এবং `k` radix/base range। Sub-sort stable না হলে overall correctness নষ্ট হতে পারে।

## ৪. Algorithm Selection

- Small/nearly sorted → Insertion Sort
- Guaranteed `n log n`, stability → Merge Sort
- Fast average array sorting, memory সীমিত → Quick Sort
- Bounded integer digits/keys → Radix বা Counting Sort
- Minimum swaps গুরুত্বপূর্ণ → Selection Sort

## ৫. Merge Sort Work by Level

Balanced Merge Sort recursion tree-তে:

```text
Levels ≈ log₂n
Merge work per level ≈ n
Total ≈ n log₂n
```

## Common Mistakes

- Quick Sort-কে guaranteed `O(n log n)` বলা।
- Merge Sort-কে in-place বলা without implementation qualification।
- Radix Sort-এর sub-sort stability উপেক্ষা করা।
- Stable ও in-place property এক মনে করা।

---

# MCQ Practice: Advanced Sorting

## প্রশ্ন 333 | Topic: Algorithm > Sorting > Merge Sort | Difficulty: Medium | Type: Theory

Q. Standard Merge Sort সম্পর্কে কোন statement সঠিক?

A) Worst-case `Θ(n²)` এবং unstable  
B) Worst-case `Θ(n log n)` এবং সাধারণত stable  
C) শুধু sorted input-এ কাজ করে  
D) Comparison ব্যবহার করে না

**সঠিক উত্তর: B) Worst-case `Θ(n log n)` এবং সাধারণত stable**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Balanced divide এবং linear merge-এর কারণে worst-case `Θ(n log n)`; equal element merge rule ঠিক রাখলে stable।
- **A option কেন ভুল:** Quadratic worst case Quick Sort-এর poor partition-এ হতে পারে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Unsorted input sort করার জন্যই ব্যবহৃত হয়।
- **D option কেন ভুল:** Merge step element comparison করে।
- **Related Concept:** Typical array Merge Sort `Θ(n)` extra space ব্যবহার করে।
- **মনে রাখার টিপস:** Merge = guaranteed `n log n` + stable।

---

## প্রশ্ন 334 | Topic: Algorithm > Sorting > Merge Comparisons | Difficulty: Medium | Type: Calculation

Q. Sorted list `[1,4,7]` এবং `[2,3,8]` standardভাবে merge করতে কতটি comparison লাগে?

A) 3  
B) 6  
C) 5  
D) 4

**সঠিক উত্তর: C) 5**

### Step-by-step Tracing

```text
Left  = [1,4,7]
Right = [2,3,8]
```

Comparisons:

```text
1 vs 2 → take 1        (1)
4 vs 2 → take 2        (2)
4 vs 3 → take 3        (3)
4 vs 8 → take 4        (4)
7 vs 8 → take 7        (5)
```

Left list শেষ; remaining `8` comparison ছাড়াই copy হয়।

#### Final Answer

```text
Total comparisons = 5
```

### Option বিশ্লেষণ

- **A) 3:** শুধু প্রথম তিনটি selection গণনা করা হয়েছে।
- **B) 6:** Remaining last element copy-কেও comparison ধরা হয়েছে।
- **C) 5:** এটি সঠিক উত্তর।
- **D) 4:** Final `7 vs 8` comparison বাদ গেছে।
- **Related Concept:** Two lists length `m` ও `n` merge-এ worst-case comparison `m+n−1`। এখানে `3+3−1=5`।
- **মনে রাখার টিপস:** Merge worst comparison = total elements − 1।

---

## প্রশ্ন 335 | Topic: Algorithm > Sorting > Quick Sort Worst Case | Difficulty: Medium | Type: Theory

Q. Quick Sort-এর worst-case `Θ(n²)` সাধারণত কখন ঘটে?

A) প্রতিবার partition অত্যন্ত unbalanced হলে  
B) প্রতিবার pivot median হলে  
C) Array size power of two হলে  
D) Duplicate না থাকলে

**সঠিক উত্তর: A) প্রতিবার partition অত্যন্ত unbalanced হলে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Partition যদি `0` ও `n−1` আকারে ভাগ হয়, recurrence `T(n)=T(n−1)+Θ(n)`, ফলে quadratic।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Median pivot balanced partition দিয়ে `Θ(n log n)` দেয়।
- **C option কেন ভুল:** Power-of-two size নিজে worst-case নয়।
- **D option কেন ভুল:** Distinct element থাকলেও pivot choice অনুযায়ী ভালো বা খারাপ partition হতে পারে।
- **Related Concept:** Randomization expected performance উন্নত করে।
- **মনে রাখার টিপস:** Quick Sort-এর বিপদ = বারবার one-sided partition।

---

## প্রশ্ন 336 | Topic: Algorithm > Sorting > Lomuto Partition Trace | Difficulty: Hard | Type: Calculation

Q. Lomuto partition-এ array `[4,2,7,3]`-এর শেষ element `3` pivot। Partition শেষে pivot-এর zero-based index কত হবে?

A) 0  
B) 2  
C) 3  
D) 1

**সঠিক উত্তর: D) 1**

### Step-by-step Tracing

Initial:

```text
Array = [4,2,7,3]
Pivot = 3
```

`3`-এর চেয়ে ছোট element:

```text
2 only
```

Partition-এর পরে:

```text
[2,3,7,4]
```

Pivot-এর বামে 1টি ছোট element আছে, তাই zero-based position:

```text
Pivot index = 1
```

### Option বিশ্লেষণ

- **A) 0:** Pivot-এর আগে থাকা `2` উপেক্ষা করা হয়েছে।
- **B) 2:** One-based position বা ভুল swap sequence নেওয়া হয়েছে।
- **C) 3:** Initial pivot position-ই final ধরে নেওয়া হয়েছে।
- **D) 1:** এটি সঠিক উত্তর।
- **Related Concept:** Partition শেষে pivot তার final sorted position-এ থাকে।
- **মনে রাখার টিপস:** Pivot-এর চেয়ে ছোট element count = final zero-based pivot index, যখন পুরো range index 0 থেকে শুরু।

---

## প্রশ্ন 337 | Topic: Algorithm > Sorting > Randomized Quick Sort | Difficulty: Medium | Type: Theory

Q. Randomized Quick Sort-এর expected time complexity কোনটি?

A) `Θ(n²)`  
B) `Θ(n)`  
C) `Θ(n log n)`  
D) `Θ(log n)`

**সঠিক উত্তর: C) `Θ(n log n)`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Random pivot expectedভাবে balanced-enough partition তৈরি করে; expected running time `Θ(n log n)`।
- **A option কেন ভুল:** এটি worst case, expected নয়।
- **B option কেন ভুল:** General sorting-এর জন্য linear expected comparison time নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** শুধু recursion depth প্রায় logarithmic; প্রতিটি level-এ total linear partition work হয়।
- **Related Concept:** Randomization worst case eliminate করে না, probability কমায়।
- **মনে রাখার টিপস:** Quick Sort expected fast, worst quadratic।

---

## প্রশ্ন 338 | Topic: Algorithm > Sorting > Merge Sort Space | Difficulty: Medium | Type: Theory

Q. Standard array-based Merge Sort-এর auxiliary space সাধারণত কত?

A) `Θ(1)`  
B) `Θ(n)`  
C) `Θ(log n)` মাত্র  
D) `Θ(n²)`

**সঠিক উত্তর: B) `Θ(n)`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Merge করার জন্য temporary array সাধারণত input-এর proportional storage নেয়।
- **A option কেন ভুল:** Standard array implementation in-place নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Recursion stack `Θ(log n)` হলেও merge buffer `Θ(n)` dominant।
- **D option কেন ভুল:** Quadratic storage প্রয়োজন হয় না।
- **Related Concept:** Linked-list Merge Sort pointer relinking দিয়ে কম auxiliary merge storage ব্যবহার করতে পারে।
- **মনে রাখার টিপস:** Array Merge Sort: time `n log n`, extra space `n`।

---

## প্রশ্ন 339 | Topic: Algorithm > Sorting > Radix Sort Passes | Difficulty: Medium | Type: Calculation

Q. Base-10 LSD Radix Sort দিয়ে সর্বোচ্চ 5-digit nonnegative integer sort করতে কয়টি digit pass প্রয়োজন?

A) 5  
B) 10  
C) 4  
D) `n log n`

**সঠিক উত্তর: A) 5**

### গাণিতিক বিশ্লেষণ

#### Rule

```text
LSD Radix Sort passes = maximum digit count
```

#### Given Data

```text
Maximum digits = 5
Base           = 10
```

#### Step-by-step

```text
Pass 1 → units digit
Pass 2 → tens digit
Pass 3 → hundreds digit
Pass 4 → thousands digit
Pass 5 → ten-thousands digit
```

#### Final Answer

```text
Required passes = 5
```

### Option বিশ্লেষণ

- **A) 5:** এটি সঠিক উত্তর।
- **B) 10:** Base value-কে pass count ধরা হয়েছে।
- **C) 4:** সবচেয়ে significant digit-এর pass বাদ গেছে।
- **D) n log n:** এটি comparison sorting complexity expression, pass count নয়।
- **Related Concept:** প্রতিটি digit pass-এর sub-sort stable হওয়া প্রয়োজন।
- **মনে রাখার টিপস:** যত digit, তত LSD pass।

---

## প্রশ্ন 340 | Topic: Algorithm > Sorting > Stable Multi-Key Sort | Difficulty: Medium | Type: Scenario

Q. প্রথমে `Name` এবং পরে `Department` key দিয়ে sort করে প্রতিটি Department-এর ভেতরে Name order বজায় রাখতে দ্বিতীয় sort-এর কোন property দরকার?

A) In-place  
B) Recursive  
C) Randomized  
D) Stable

**সঠিক উত্তর: D) Stable**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Department key সমান হলে stable দ্বিতীয় sort আগের Name order বজায় রাখবে।
- **A option কেন ভুল:** In-place memory property; equal-key order guarantee করে না।
- **B option কেন ভুল:** Recursion stability নির্ধারণ করে না।
- **C option কেন ভুল:** Randomization order preservation নিশ্চিত করে না।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Multi-key stable sorting সাধারণত least-significant key আগে sort করে।
- **মনে রাখার টিপস:** আগের key order রাখতে পরের sort stable হতে হবে।

---

## প্রশ্ন 341 | Topic: Algorithm > Sorting > Non-Comparison Sort | Difficulty: Easy | Type: Theory

Q. নিচের কোনটি non-comparison sorting algorithm?

A) Merge Sort  
B) Heap Sort  
C) Radix Sort  
D) Quick Sort

**সঠিক উত্তর: C) Radix Sort**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Radix Sort digit position ও bucket/stable sub-sort ব্যবহার করে; pairwise key comparison-এর ওপর সম্পূর্ণ নির্ভর করে না।
- **A option কেন ভুল:** Merge Sort comparison-based।
- **B option কেন ভুল:** Heap order comparison দিয়ে তৈরি হয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Partition comparison ব্যবহার করে।
- **Related Concept:** Counting Sort-ও non-comparison algorithm।
- **মনে রাখার টিপস:** Digit বা count ভিত্তিক হলে comparison barrier এড়াতে পারে।

---

## প্রশ্ন 342 | Topic: Algorithm > Searching > Binary Search Scale | Difficulty: Hard | Type: Calculation

Q. 1000টি sorted element-এর array-এ standard Binary Search-এর common maximum comparison কত?

A) 10  
B) 9  
C) 500  
D) 1000

**সঠিক উত্তর: A) 10**

### গাণিতিক বিশ্লেষণ

#### Formula

```text
Maximum comparisons = floor(log₂n) + 1
```

#### Given Data

```text
n = 1000
```

#### Power Comparison

```text
2⁹  = 512
2¹⁰ = 1024
```

তাই:

```text
9 < log₂1000 < 10
floor(log₂1000) = 9
```

#### Calculation

```text
Maximum comparisons = 9 + 1
                    = 10
```

#### Final Answer

```text
Maximum comparisons = 10
```

### Option বিশ্লেষণ

- **A) 10:** এটি সঠিক উত্তর।
- **B) 9:** Final candidate comparison বাদ গেছে।
- **C) 500:** একবার half করার পর element count নেওয়া হয়েছে।
- **D) 1000:** Linear Search-এর worst-case ধরা হয়েছে।
- **Related Concept:** 1024 element-এও common maximum 11 হতে পারে, formula convention অনুসারে।
- **মনে রাখার টিপস:** কাছাকাছি power of two খুঁজুন।

---

## প্রশ্ন 343 | Topic: Algorithm > Loop Analysis > Decreasing Inner Range | Difficulty: Medium | Type: Theory

Q. নিচের code-এর tight time complexity কত?

```c
for (int i = 0; i < n; i++) {
    for (int j = i; j < n; j++) {
        /* constant work */
    }
}
```

A) `Θ(n)`  
B) `Θ(log n)`  
C) `Θ(n log n)`  
D) `Θ(n²)`

**সঠিক উত্তর: D) `Θ(n²)`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Inner count `n, n−1, ..., 1`; total `n(n+1)/2`, যা `Θ(n²)`।
- **A option কেন ভুল:** শুধু outer loop দেখা হয়েছে।
- **B option কেন ভুল:** Multiplicative halving নেই।
- **C option কেন ভুল:** Inner total harmonic/logarithmic নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Bound পরিবর্তিত হলেও triangular sum quadratic।
- **মনে রাখার টিপস:** `n + (n−1) + ... + 1` দেখলে quadratic।

---

## প্রশ্ন 344 | Topic: Algorithm > Recurrence > Dominant Combine Cost | Difficulty: Hard | Type: Calculation

Q. নিচের recurrence-এর tight complexity কোনটি?

```text
T(n) = 2T(n/2) + n²
```

A) `Θ(n log n)`  
B) `Θ(n²)`  
C) `Θ(log n)`  
D) `Θ(n³)`

**সঠিক উত্তর: B) `Θ(n²)`**

### গাণিতিক বিশ্লেষণ

#### Given Data

```text
a    = 2
b    = 2
f(n) = n²
```

#### Critical Term

```text
n^(log₂2) = n
```

#### Comparison

```text
f(n) = n²
Critical term = n
```

`n²` polynomially larger। Regularity check:

```text
2 × (n/2)²
= 2 × n²/4
= n²/2
≤ c n², যেখানে c = 1/2 < 1
```

তাই combine cost dominant।

#### Final Answer

```text
T(n) = Θ(n²)
```

### Option বিশ্লেষণ

- **A) Θ(n log n):** `f(n)=n` ধরে ভুল করা হয়েছে।
- **B) Θ(n²):** এটি সঠিক উত্তর।
- **C) Θ(log n):** Recursion depthমাত্র নেওয়া হয়েছে।
- **D) Θ(n³):** অতিরিক্ত factor যোগ করা হয়েছে।
- **Related Concept:** Master theorem case যেখানে `f(n)` dominant।
- **মনে রাখার টিপস:** Critical `n` বনাম combine `n²`—বড়টি জেতে।

---

## প্রশ্ন 345 | Topic: Algorithm > Asymptotic Bound > Combining O and Omega | Difficulty: Medium | Type: Theory

Q. যদি `T(n)=O(n)` এবং `T(n)=Ω(n)`—দুটিই সত্য হয়, তবে কোনটি অবশ্যই সত্য?

A) `T(n)=Θ(log n)`  
B) `T(n)=Θ(n²)`  
C) `T(n)=Θ(n)`  
D) `T(n)=O(1)`

**সঠিক উত্তর: C) `T(n)=Θ(n)`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একই `n` function upper ও lower bound হলে tight bound `Θ(n)`।
- **A option কেন ভুল:** Logarithmic lower/upper তথ্য দেওয়া হয়নি।
- **B option কেন ভুল:** Quadratic growth linear upper bound লঙ্ঘন করবে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Linear lower bound থাকলে constant upper bound সম্ভব নয়।
- **Related Concept:** Theta definition সরাসরি প্রয়োগ।
- **মনে রাখার টিপস:** Same O + same Ω = Θ।

---

## প্রশ্ন 346 | Topic: Algorithm > Sorting > Decision-Tree Lower Bound | Difficulty: Hard | Type: Calculation

Q. 8টি distinct element comparison-এর মাধ্যমে sort করতে worst case-এ অন্তত কতটি comparison প্রয়োজন হতে পারে? `ceil(log₂(8!))` ব্যবহার করুন।

A) 15  
B) 16  
C) 8  
D) 28

**সঠিক উত্তর: B) 16**

### গাণিতিক বিশ্লেষণ

#### Formula

```text
Minimum worst-case comparisons ≥ ceil(log₂(n!))
```

#### Given Data

```text
n = 8
8! = 40320
```

#### Power Comparison

```text
2¹⁵ = 32768
2¹⁶ = 65536
```

যেহেতু:

```text
32768 < 40320 ≤ 65536
```

তাই:

```text
15 < log₂(40320) ≤ 16
ceil(log₂(40320)) = 16
```

#### Final Answer

```text
Minimum worst-case comparisons = 16
```

### Option বিশ্লেষণ

- **A) 15:** `2¹⁵` সব 40320 permutation-এর জন্য যথেষ্ট leaf দেয় না।
- **B) 16:** এটি সঠিক উত্তর।
- **C) 8:** শুধু element count নেওয়া হয়েছে।
- **D) 28:** Selection Sort-এর comparison count; universal minimum নয়।
- **Related Concept:** Lower bound নির্দিষ্ট algorithm-এর actual count নয়; comparison model-এর বাধা।
- **মনে রাখার টিপস:** `n!` possible order আলাদা করতে binary decision tree-এর leaf দরকার।

---

## প্রশ্ন 347 | Topic: Algorithm > Sorting > Adaptiveness | Difficulty: Medium | Type: Theory

Q. Insertion Sort ও Selection Sort-এর adaptiveness সম্পর্কে কোন statement সঠিক?

A) Insertion Sort adaptive; standard Selection Sort সাধারণত adaptive নয়  
B) দুটোই সব input-এ `Θ(n)`  
C) Selection Sort adaptive; Insertion Sort নয়  
D) দুটোই comparison ব্যবহার করে না

**সঠিক উত্তর: A) Insertion Sort adaptive; standard Selection Sort সাধারণত adaptive নয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Nearly-sorted input-এ Insertion Sort কম shift/comparison করতে পারে; Selection Sort প্রতিবার remaining minimum খোঁজে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Worst case উভয়ই quadratic।
- **C option কেন ভুল:** Statement উল্টো।
- **D option কেন ভুল:** দুটোই comparison-based।
- **Related Concept:** Optimized Bubble Sort-ও adaptive হতে পারে।
- **মনে রাখার টিপস:** Insertion existing order-এর সুবিধা নেয়।

---

## প্রশ্ন 348 | Topic: Algorithm > Sorting > Merge-Sort Level Work | Difficulty: Medium | Type: Calculation

Q. `n = 8` element-এর Merge Sort-এ প্রতিটি merge level-এ মোট 8 unit কাজ এবং মোট `log₂8 = 3` merge level হলে merge work মোট কত unit?

A) 8  
B) 16  
C) 64  
D) 24

**সঠিক উত্তর: D) 24**

### গাণিতিক বিশ্লেষণ

#### Formula

```text
Total merge work = Work per level × Number of levels
```

#### Given Data

```text
Work per level = 8
Levels         = log₂8 = 3
```

#### Calculation

```text
Total = 8 × 3
      = 24
```

#### Final Answer

```text
Merge work = 24 units
```

### Option বিশ্লেষণ

- **A) 8:** শুধু একটি level-এর কাজ নেওয়া হয়েছে।
- **B) 16:** দুই level ধরা হয়েছে।
- **C) 64:** `n²` করা হয়েছে।
- **D) 24:** এটি সঠিক উত্তর।
- **Related Concept:** General total `n log₂n`।
- **মনে রাখার টিপস:** Merge tree: linear work per level × logarithmic levels।

---

## প্রশ্ন 349 | Topic: Algorithm > Sorting > In-place Algorithm | Difficulty: Easy | Type: Theory

Q. In-place sorting algorithm বলতে সাধারণত কী বোঝায়?

A) Input storage-এর বাইরে constant বা খুব অল্প auxiliary space ব্যবহার করে  
B) সবসময় stable হয়  
C) সবসময় `Θ(n)` time নেয়  
D) Disk ছাড়া কাজ করে না

**সঠিক উত্তর: A) Input storage-এর বাইরে constant বা খুব অল্প auxiliary space ব্যবহার করে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** In-place property auxiliary memory usage-এর সঙ্গে সম্পর্কিত।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Quick Sort প্রায় in-place হলেও সাধারণত unstable।
- **C option কেন ভুল:** Selection Sort in-place কিন্তু `Θ(n²)`।
- **D option কেন ভুল:** In-place মূল memory/storage usage concept।
- **Related Concept:** Recursion stack গণনা করা হবে কি না—question context দেখতে হবে।
- **মনে রাখার টিপস:** In-place = extra জায়গা খুব কম।

---

## প্রশ্ন 350 | Topic: Algorithm > Sorting > Bubble Sort Trace | Difficulty: Medium | Type: Calculation

Q. Ascending Bubble Sort-এর একটি সম্পূর্ণ left-to-right pass শেষে array `[4,1,3,2]` কী হবে?

A) `[1,2,3,4]`  
B) `[1,3,2,4]`  
C) `[4,1,2,3]`  
D) `[1,4,2,3]`

**সঠিক উত্তর: B) `[1,3,2,4]`**

### Step-by-step Tracing

Initial:

```text
[4,1,3,2]
```

Adjacent comparisons:

```text
4 vs 1 → swap
[1,4,3,2]

4 vs 3 → swap
[1,3,4,2]

4 vs 2 → swap
[1,3,2,4]
```

#### Final Answer

```text
After one full pass = [1,3,2,4]
```

### Option বিশ্লেষণ

- **A) [1,2,3,4]:** পুরো sorting complete ধরে নেওয়া হয়েছে; এক pass-এ শুধু largest element শেষে নিশ্চিত হয়েছে।
- **B) [1,3,2,4]:** এটি সঠিক উত্তর।
- **C) [4,1,2,3]:** প্রথম comparison-এর swap উপেক্ষা করা হয়েছে।
- **D) [1,4,2,3]:** দ্বিতীয় ও তৃতীয় comparison trace ভুল।
- **Related Concept:** Bubble Sort-এর প্রতি pass-এ unsorted অংশের largest element ডান প্রান্তে যায়।
- **মনে রাখার টিপস:** এক pass মানে পুরো sort নয়; শুধু একটি extreme element final position পায়।

---

# Batch Quality Summary

## Question Count

```text
Question Range          = 301–350
Total Questions         = 50
Theory/Scenario         = 30
Math/Calculation/Trace  = 20
```

## Difficulty Distribution

```text
Easy   = 13
Medium = 25
Hard   = 12
Total  = 50
```

## Answer Distribution

```text
A = 13
B = 13
C = 12
D = 12
```

## Covered Subtopics

- Big-O, Big-Omega ও Big-Theta
- Best, Average ও Worst Case
- Dominant Term এবং Growth Order
- Time–Space Trade-off
- Single, Nested, Logarithmic ও Triangular Loop Count
- Recurrence Relation
- Master Theorem
- Amortized Analysis
- Linear Search
- Binary Search
- Comparison Count ও Search Trace
- Stable, In-place ও Adaptive Sort
- Selection Sort
- Insertion Sort
- Bubble Sort
- Merge Sort
- Quick Sort
- Radix Sort
- Comparison-Sorting Lower Bound

## Math Formatting Audit

প্রতিটি numerical/trace question-এ রাখা হয়েছে:

- Formula বা Rule
- Given Data
- Substitution
- Plain-text aligned Step-by-step Calculation
- Final Answer
- Wrong-option error source
- Related Concept
- Exam Tip

## Quality Checks

```text
Numbering continuity       : Passed
Syllabus relevance         : Passed
Calculation verification   : Passed
Raw LaTeX rendering issue  : Removed
Bangla explanation         : Passed
Technical keywords         : Preserved
Duplicate check            : Passed
```

---

## Next Coverage

পরবর্তী batch-এ থাকবে:

- Linked List
- Stack ও Queue
- Circular Queue ও Deque
- Prefix, Infix ও Postfix Conversion
- Expression Evaluation
- Recursion এবং Tower of Hanoi

