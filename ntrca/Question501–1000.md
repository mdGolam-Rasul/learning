# ১৯তম নিবন্ধন — প্রভাষক ICT

## Combined README: Question 501–1000

**Subject Code:** 452  
**Total MCQ:** 500  
**Language:** বাংলা, Technical keywords English  
**Math/Tracing Format:** Plain-text aligned; GitHub ও mobile-friendly

---

# Coverage Overview

| Question Range | Section | Status |
|---|---|---|
| 501–520 | Data Structure, Algorithm & Combinatorial Optimization | Section completed |
| 521–620 | Web Technology | Section completed |
| 621–790 | Operating System | Section completed |
| 791–980 | Database Management System | Section completed |
| 981–1000 | Computer Networking | Initial 20 questions completed |

## Question Composition

```text
Total Questions       = 500
Theory/Scenario       = 362
Calculation/Code      = 138

Easy                  = 130
Medium                = 250
Hard                  = 120

Correct Answer A      = 130
Correct Answer B      = 130
Correct Answer C      = 120
Correct Answer D      = 120
```

## Batch Map

```text
Batch 12 : Question 501–550
Batch 13 : Question 551–600
Batch 14 : Question 601–650
Batch 15 : Question 651–700
Batch 16 : Question 701–750
Batch 17 : Question 751–800
Batch 18 : Question 801–850
Batch 19 : Question 851–900
Batch 20 : Question 901–950
Batch 21 : Question 951–1000
```

> প্রতিটি সম্পূর্ণ ৫০-question block-এ Easy 13, Medium 25, Hard 12 এবং answer distribution A=13, B=13, C=12, D=12 রাখা হয়েছে।

---


# Chapter Theory 40: Divide and Conquer ও Dynamic Programming

## বিস্তারিত Theory Note

Divide and Conquer subproblem-গুলোকে সাধারণত independentভাবে solve করে; Dynamic Programming একই state বারবার আসলে result reuse করে। Merge Sort-এর merge phase linear এবং recursion balanced হওয়ায় worst-case O(n log n)। Quick Sort-এর performance pivot ও partition balance-এর ওপর নির্ভরশীল।

DP solution design-এর সাধারণ ধাপ:

```text
1. State define
2. Recurrence তৈরি
3. Base case নির্ধারণ
4. Evaluation order বা memoization
5. Final state read
```

LCS, Matrix Chain Multiplication ও Coin Change-এ একই state structure বারবার ব্যবহৃত হয়।

## মূল ধারণার মানচিত্র

- **Divide and Conquer:** সমস্যাকে ছোট independent subproblem-এ ভাগ, পৃথকভাবে solve এবং ফল combine করার strategy।
- **Merge Sort:** Array-কে অর্ধেক ভাগ করে recursively sort এবং linear-time merge করে; worst-case O(n log n)।
- **Quick Sort:** Pivot-এর ভিত্তিতে partition করে ছোট ও বড় অংশ recursively sort করে; average O(n log n), worst O(n²)।
- **Partition:** Pivot-এর তুলনায় element-গুলোকে দুই পাশে পুনর্বিন্যাস করার Quick Sort operation।
- **Dynamic Programming:** Overlapping subproblem-এর result সংরক্ষণ করে repeated computation এড়িয়ে optimal solution তৈরি করার technique।
- **Memoization:** Top-down recursion-এর সঙ্গে computed state cache করার DP পদ্ধতি।
- **Tabulation:** Base state থেকে bottom-up table পূরণ করে solution তৈরির DP পদ্ধতি।
- **Longest Common Subsequence:** দুই sequence-এর order বজায় রেখে উভয়ের common সর্বাধিক দীর্ঘ subsequence খোঁজার problem।
- **Matrix Chain Multiplication:** Matrix order অপরিবর্তিত রেখে parenthesization নির্বাচন করে scalar multiplication কমানোর DP problem।
- **Coin Change DP:** Amount তৈরির minimum coin বা total combination count state recurrence দিয়ে সমাধান করা।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Divide and Conquer ও Dynamic Programming

# Batch 12 — Question 501–550

## প্রশ্ন 501 | Topic: Data Structure and Algorithm > Advanced Algorithm Design | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`সমস্যাকে ছোট independent subproblem-এ ভাগ, পৃথকভাবে solve এবং ফল combine করার strategy।`

A) Matrix Chain Multiplication
B) Longest Common Subsequence
C) Divide and Conquer
D) Memoization

**সঠিক উত্তর: C) Divide and Conquer**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** সমস্যাকে ছোট independent subproblem-এ ভাগ, পৃথকভাবে solve এবং ফল combine করার strategy।
- **A option কেন ভুল:** `Matrix Chain Multiplication` বলতে Matrix order অপরিবর্তিত রেখে parenthesization নির্বাচন করে scalar multiplication কমানোর DP problem। বোঝায়; প্রশ্নের বর্ণনা `Divide and Conquer`-এর।
- **B option কেন ভুল:** `Longest Common Subsequence` বলতে দুই sequence-এর order বজায় রেখে উভয়ের common সর্বাধিক দীর্ঘ subsequence খোঁজার problem। বোঝায়; প্রশ্নের বর্ণনা `Divide and Conquer`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Memoization` বলতে Top-down recursion-এর সঙ্গে computed state cache করার DP পদ্ধতি। বোঝায়; প্রশ্নের বর্ণনা `Divide and Conquer`-এর।
- **Related Concept:** Merge Sort ও Quick Sort এই paradigm ব্যবহার করে।
- **মনে রাখার টিপস:** Divide → Solve → Combine।

---

## প্রশ্ন 502 | Topic: Data Structure and Algorithm > Advanced Algorithm Design | Difficulty: Medium | Type: Calculation

Q. ৮টি element-এর array Merge Sort দিয়ে ভাগ করলে single-element subarray পেতে split level কত? `log₂8` ব্যবহার করুন।

A) 2 level
B) 3 level
C) 4 level
D) 8 level

**সঠিক উত্তর: B) 3 level**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতি level-এ size অর্ধেক হয়; 8→4→2→1, তাই 3টি split level।

#### Step-by-step সমাধান

```text
n = 8
8 -> 4 -> 2 -> 1
Number of halving steps = 3
```
- **A option কেন ভুল:** দুই split-এর পরে size 2 থাকে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** একটি অতিরিক্ত level গণনা হয়েছে।
- **D option কেন ভুল:** Element count-কে level count ধরা হয়েছে।
- **Related Concept:** Balanced divide-and-conquer recursion depth log₂n।
- **মনে রাখার টিপস:** 8=2³, তাই depth 3।

---

## প্রশ্ন 503 | Topic: Data Structure and Algorithm > Advanced Algorithm Design | Difficulty: Easy | Type: Calculation

Q. Quick Sort-এ প্রতিবার smallest element pivot হয়ে partitions `0` ও `n−1` হলে recurrence `T(n)=T(n−1)+n`। এর asymptotic complexity কত?

A) O(log n)
B) O(n)
C) O(n log n)
D) O(n²)

**সঠিক উত্তর: D) O(n²)**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** n+(n−1)+...+1 summation quadratic।

#### Step-by-step সমাধান

```text
T(n) = n + (n-1) + ... + 1
     = n(n+1)/2
     = O(n^2)
```
- **A option কেন ভুল:** শুধু recursion depth নয়; প্রতিটি level-এর partition cost যোগ হয়।
- **B option কেন ভুল:** সব level-এর linear work যোগ করা হয়নি।
- **C option কেন ভুল:** Balanced partition assumption এখানে নেই।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Poor pivot selection Quick Sort worst case তৈরি করে।
- **মনে রাখার টিপস:** Highly unbalanced partition → n²।

---

## প্রশ্ন 504 | Topic: Data Structure and Algorithm > Advanced Algorithm Design | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Pivot-এর তুলনায় element-গুলোকে দুই পাশে পুনর্বিন্যাস করার Quick Sort operation।`

A) Partition
B) Merge Sort
C) Coin Change DP
D) Divide and Conquer

**সঠিক উত্তর: A) Partition**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Pivot-এর তুলনায় element-গুলোকে দুই পাশে পুনর্বিন্যাস করার Quick Sort operation।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Merge Sort` বলতে Array-কে অর্ধেক ভাগ করে recursively sort এবং linear-time merge করে; worst-case O(n log n)। বোঝায়; প্রশ্নের বর্ণনা `Partition`-এর।
- **C option কেন ভুল:** `Coin Change DP` বলতে Amount তৈরির minimum coin বা total combination count state recurrence দিয়ে সমাধান করা। বোঝায়; প্রশ্নের বর্ণনা `Partition`-এর।
- **D option কেন ভুল:** `Divide and Conquer` বলতে সমস্যাকে ছোট independent subproblem-এ ভাগ, পৃথকভাবে solve এবং ফল combine করার strategy। বোঝায়; প্রশ্নের বর্ণনা `Partition`-এর।
- **Related Concept:** Lomuto ও Hoare partition প্রচলিত।
- **মনে রাখার টিপস:** Partition sorted করে না; pivot-এর দুই side তৈরি করে।

---

## প্রশ্ন 505 | Topic: Data Structure and Algorithm > Advanced Algorithm Design | Difficulty: Easy | Type: Theory

Q. `Dynamic Programming` সম্পর্কে কোন statement সঠিক?

A) Overlapping subproblem-এর result সংরক্ষণ করে repeated computation এড়িয়ে optimal solution তৈরি করার technique।
B) সমস্যাকে ছোট independent subproblem-এ ভাগ, পৃথকভাবে solve এবং ফল combine করার strategy।
C) দুই sequence-এর order বজায় রেখে উভয়ের common সর্বাধিক দীর্ঘ subsequence খোঁজার problem।
D) Matrix order অপরিবর্তিত রেখে parenthesization নির্বাচন করে scalar multiplication কমানোর DP problem।

**সঠিক উত্তর: A) Overlapping subproblem-এর result সংরক্ষণ করে repeated computation এড়িয়ে optimal solution তৈরি করার technique।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Overlapping subproblem-এর result সংরক্ষণ করে repeated computation এড়িয়ে optimal solution তৈরি করার technique।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Divide and Conquer` ধারণাকে বর্ণনা করে; `Dynamic Programming`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Longest Common Subsequence` ধারণাকে বর্ণনা করে; `Dynamic Programming`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Matrix Chain Multiplication` ধারণাকে বর্ণনা করে; `Dynamic Programming`-কে নয়।
- **Related Concept:** Optimal substructure ও overlapping subproblem প্রয়োজন।
- **মনে রাখার টিপস:** Repeat state দেখলে DP ভাবুন।

---

## প্রশ্ন 506 | Topic: Data Structure and Algorithm > Advanced Algorithm Design | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Top-down recursion-এর সঙ্গে computed state cache করার DP পদ্ধতি।`—এখানে কোন concept প্রযোজ্য?

A) Memoization
B) Dynamic Programming
C) Matrix Chain Multiplication
D) Merge Sort

**সঠিক উত্তর: A) Memoization**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Top-down recursion-এর সঙ্গে computed state cache করার DP পদ্ধতি।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Dynamic Programming` বলতে Overlapping subproblem-এর result সংরক্ষণ করে repeated computation এড়িয়ে optimal solution তৈরি করার technique। বোঝায়; প্রশ্নের বর্ণনা `Memoization`-এর।
- **C option কেন ভুল:** `Matrix Chain Multiplication` বলতে Matrix order অপরিবর্তিত রেখে parenthesization নির্বাচন করে scalar multiplication কমানোর DP problem। বোঝায়; প্রশ্নের বর্ণনা `Memoization`-এর।
- **D option কেন ভুল:** `Merge Sort` বলতে Array-কে অর্ধেক ভাগ করে recursively sort এবং linear-time merge করে; worst-case O(n log n)। বোঝায়; প্রশ্নের বর্ণনা `Memoization`-এর।
- **Related Concept:** শুধু প্রয়োজনীয় state compute হয়।
- **মনে রাখার টিপস:** Memo = remember recursive result।

---

## প্রশ্ন 507 | Topic: Data Structure and Algorithm > Advanced Algorithm Design | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Base state থেকে bottom-up table পূরণ করে solution তৈরির DP পদ্ধতি।`

A) Longest Common Subsequence
B) Tabulation
C) Matrix Chain Multiplication
D) Divide and Conquer

**সঠিক উত্তর: B) Tabulation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Base state থেকে bottom-up table পূরণ করে solution তৈরির DP পদ্ধতি।
- **A option কেন ভুল:** `Longest Common Subsequence` বলতে দুই sequence-এর order বজায় রেখে উভয়ের common সর্বাধিক দীর্ঘ subsequence খোঁজার problem। বোঝায়; প্রশ্নের বর্ণনা `Tabulation`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Matrix Chain Multiplication` বলতে Matrix order অপরিবর্তিত রেখে parenthesization নির্বাচন করে scalar multiplication কমানোর DP problem। বোঝায়; প্রশ্নের বর্ণনা `Tabulation`-এর।
- **D option কেন ভুল:** `Divide and Conquer` বলতে সমস্যাকে ছোট independent subproblem-এ ভাগ, পৃথকভাবে solve এবং ফল combine করার strategy। বোঝায়; প্রশ্নের বর্ণনা `Tabulation`-এর।
- **Related Concept:** Recursion stack এড়াতে পারে।
- **মনে রাখার টিপস:** Table নিচ থেকে ওপরে।

---

## প্রশ্ন 508 | Topic: Data Structure and Algorithm > Advanced Algorithm Design | Difficulty: Easy | Type: Theory

Q. `Longest Common Subsequence` সম্পর্কে কোন statement সঠিক?

A) Top-down recursion-এর সঙ্গে computed state cache করার DP পদ্ধতি।
B) Amount তৈরির minimum coin বা total combination count state recurrence দিয়ে সমাধান করা।
C) Matrix order অপরিবর্তিত রেখে parenthesization নির্বাচন করে scalar multiplication কমানোর DP problem।
D) দুই sequence-এর order বজায় রেখে উভয়ের common সর্বাধিক দীর্ঘ subsequence খোঁজার problem।

**সঠিক উত্তর: D) দুই sequence-এর order বজায় রেখে উভয়ের common সর্বাধিক দীর্ঘ subsequence খোঁজার problem।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** দুই sequence-এর order বজায় রেখে উভয়ের common সর্বাধিক দীর্ঘ subsequence খোঁজার problem।
- **A option কেন ভুল:** এই statementটি `Memoization` ধারণাকে বর্ণনা করে; `Longest Common Subsequence`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Coin Change DP` ধারণাকে বর্ণনা করে; `Longest Common Subsequence`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Matrix Chain Multiplication` ধারণাকে বর্ণনা করে; `Longest Common Subsequence`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Substring-এর মতো contiguous হওয়া প্রয়োজন নেই।
- **মনে রাখার টিপস:** Subsequence gap নিতে পারে।

---

## প্রশ্ন 509 | Topic: Data Structure and Algorithm > Advanced Algorithm Design | Difficulty: Medium | Type: Calculation

Q. Matrix dimensions `A:10×30`, `B:30×5`, `C:5×60`। `(AB)C` parenthesization-এ scalar multiplication কত?

A) 4500
B) 9000
C) 27000
D) 18000

**সঠিক উত্তর: A) 4500**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** AB cost 10×30×5=1500; resulting 10×5 matrix-এর সঙ্গে C cost 10×5×60=3000; total 4500।

#### Step-by-step সমাধান

```text
AB cost        = 10 x 30 x 5 = 1500
AB dimension   = 10 x 5
(AB)C cost     = 10 x 5 x 60 = 3000
Total          = 1500 + 3000 = 4500
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** দ্বিতীয় multiplication ভুল দ্বিগুণ করা হয়েছে।
- **C option কেন ভুল:** A(BC) cost-এর কাছাকাছি, asked parenthesization নয়।
- **D option কেন ভুল:** Dimension multiplication ভুল।
- **Related Concept:** MCM parenthesization cost তুলনা করে।
- **মনে রাখার টিপস:** প্রথমে intermediate dimension লিখুন।

---

## প্রশ্ন 510 | Topic: Data Structure and Algorithm > Advanced Algorithm Design | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Amount তৈরির minimum coin বা total combination count state recurrence দিয়ে সমাধান করা।`

A) Dynamic Programming
B) Longest Common Subsequence
C) Coin Change DP
D) Tabulation

**সঠিক উত্তর: C) Coin Change DP**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Amount তৈরির minimum coin বা total combination count state recurrence দিয়ে সমাধান করা।
- **A option কেন ভুল:** `Dynamic Programming` বলতে Overlapping subproblem-এর result সংরক্ষণ করে repeated computation এড়িয়ে optimal solution তৈরি করার technique। বোঝায়; প্রশ্নের বর্ণনা `Coin Change DP`-এর।
- **B option কেন ভুল:** `Longest Common Subsequence` বলতে দুই sequence-এর order বজায় রেখে উভয়ের common সর্বাধিক দীর্ঘ subsequence খোঁজার problem। বোঝায়; প্রশ্নের বর্ণনা `Coin Change DP`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Tabulation` বলতে Base state থেকে bottom-up table পূরণ করে solution তৈরির DP পদ্ধতি। বোঝায়; প্রশ্নের বর্ণনা `Coin Change DP`-এর।
- **Related Concept:** Greedy arbitrary denomination-এ ব্যর্থ হতে পারে।
- **মনে রাখার টিপস:** Coin system arbitrary হলে DP নিরাপদ।

---


# Chapter Theory 41: Combinatorial Optimization ও Search

## বিস্তারিত Theory Note

Combinatorial problem-এ সম্ভাব্য solution-এর সংখ্যা দ্রুত exponential বা factorial হতে পারে। Backtracking feasibility constraint দিয়ে invalid partial solution কাটে। Branch and Bound objective-এর optimistic bound ব্যবহার করে এমন valid branch-ও কাটে, যেখান থেকে বর্তমান best solution উন্নত করা সম্ভব নয়।

TSP, N-Queen, Assignment ও scheduling problem-এ state-space tree ব্যবহার করা হয়। Exact search worst case exponential হলেও pruning practical input-এ বড় উন্নতি দিতে পারে।

## মূল ধারণার মানচিত্র

- **Backtracking:** Partial solution constraint ভাঙলে সেই branch ত্যাগ করে আগের decision-এ ফিরে অন্য choice পরীক্ষা করা search technique।
- **Branch and Bound:** Optimization search-এ bound ব্যবহার করে এমন branch prune করা যার থেকে incumbent-এর চেয়ে ভালো solution সম্ভব নয়।
- **Travelling Salesperson Problem:** সব city একবার visit করে শুরুতে ফিরে minimum-cost Hamiltonian cycle খোঁজার NP-hard optimization problem।
- **State-space Tree:** Search problem-এর partial decision-গুলোকে node এবং choice-গুলোকে branch হিসেবে প্রকাশ করা tree।
- **Feasibility Constraint:** Partial বা complete candidate problem-এর বাধ্যতামূলক constraint মানছে কি না নির্ধারণ করে।
- **Objective Function:** Optimization problem-এ যে numeric value minimize বা maximize করা হয়।
- **Viterbi Algorithm:** Hidden Markov Model-এ সবচেয়ে probable hidden-state sequence Dynamic Programming দিয়ে নির্ণয় করে।
- **Assembly Line Scheduling:** একাধিক production line ও transfer cost-এর মধ্যে minimum completion time DP দিয়ে নির্ণয় করার problem।
- **NP-hard:** যে optimization problem polynomial time-এ solve করা পরিচিত নয় এবং NP-এর সব problem তার কাছে polynomial reduction করা যায়।
- **Approximation Algorithm:** Polynomial time-এ provable boundসহ optimal-এর কাছাকাছি solution প্রদান করে।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Combinatorial Optimization ও Search

## প্রশ্ন 511 | Topic: Data Structure and Algorithm > Backtracking and Optimization | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Partial solution constraint ভাঙলে সেই branch ত্যাগ করে আগের decision-এ ফিরে অন্য choice পরীক্ষা করা search technique।`

A) NP-hard
B) Approximation Algorithm
C) Backtracking
D) Travelling Salesperson Problem

**সঠিক উত্তর: C) Backtracking**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Partial solution constraint ভাঙলে সেই branch ত্যাগ করে আগের decision-এ ফিরে অন্য choice পরীক্ষা করা search technique।
- **A option কেন ভুল:** `NP-hard` বলতে যে optimization problem polynomial time-এ solve করা পরিচিত নয় এবং NP-এর সব problem তার কাছে polynomial reduction করা যায়। বোঝায়; প্রশ্নের বর্ণনা `Backtracking`-এর।
- **B option কেন ভুল:** `Approximation Algorithm` বলতে Polynomial time-এ provable boundসহ optimal-এর কাছাকাছি solution প্রদান করে। বোঝায়; প্রশ্নের বর্ণনা `Backtracking`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Travelling Salesperson Problem` বলতে সব city একবার visit করে শুরুতে ফিরে minimum-cost Hamiltonian cycle খোঁজার NP-hard optimization problem। বোঝায়; প্রশ্নের বর্ণনা `Backtracking`-এর।
- **Related Concept:** N-Queen, Sudoku ও subset search-এ ব্যবহৃত।
- **মনে রাখার টিপস:** Choose → Check → Undo।

---

## প্রশ্ন 512 | Topic: Data Structure and Algorithm > Backtracking and Optimization | Difficulty: Hard | Type: Theory

Q. `Branch and Bound` সম্পর্কে কোন statement সঠিক?

A) একাধিক production line ও transfer cost-এর মধ্যে minimum completion time DP দিয়ে নির্ণয় করার problem।
B) Optimization search-এ bound ব্যবহার করে এমন branch prune করা যার থেকে incumbent-এর চেয়ে ভালো solution সম্ভব নয়।
C) Search problem-এর partial decision-গুলোকে node এবং choice-গুলোকে branch হিসেবে প্রকাশ করা tree।
D) Partial বা complete candidate problem-এর বাধ্যতামূলক constraint মানছে কি না নির্ধারণ করে।

**সঠিক উত্তর: B) Optimization search-এ bound ব্যবহার করে এমন branch prune করা যার থেকে incumbent-এর চেয়ে ভালো solution সম্ভব নয়।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Optimization search-এ bound ব্যবহার করে এমন branch prune করা যার থেকে incumbent-এর চেয়ে ভালো solution সম্ভব নয়।
- **A option কেন ভুল:** এই statementটি `Assembly Line Scheduling` ধারণাকে বর্ণনা করে; `Branch and Bound`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `State-space Tree` ধারণাকে বর্ণনা করে; `Branch and Bound`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Feasibility Constraint` ধারণাকে বর্ণনা করে; `Branch and Bound`-কে নয়।
- **Related Concept:** TSP ও assignment problem-এ ব্যবহৃত।
- **মনে রাখার টিপস:** Bound খারাপ branch কাটে।

---

## প্রশ্ন 513 | Topic: Data Structure and Algorithm > Backtracking and Optimization | Difficulty: Medium | Type: Calculation

Q. ৫টি city-এর symmetric TSP-তে একটি fixed starting city ধরে brute-force tour permutation `(n−1)!` হলে candidate tour কত?

A) 120
B) 20
C) 5
D) 24

**সঠিক উত্তর: D) 24**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Fixed start বাদ দিলে বাকি 4 city-এর permutation 4!=24।

#### Step-by-step সমাধান

```text
n = 5
Candidates = (n - 1)!
           = 4!
           = 4 x 3 x 2 x 1
           = 24
```
- **A option কেন ভুল:** 5! করা হয়েছে; starting city fixed ছিল।
- **B option কেন ভুল:** 5×4 করা হয়েছে।
- **C option কেন ভুল:** শুধু city count।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Reverse tour একই ধরা হলে symmetric case-এ আরও 2 দিয়ে ভাগ করা যেতে পারে।
- **মনে রাখার টিপস:** Fixed start → (n−1)!।

---

## প্রশ্ন 514 | Topic: Data Structure and Algorithm > Backtracking and Optimization | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Search problem-এর partial decision-গুলোকে node এবং choice-গুলোকে branch হিসেবে প্রকাশ করা tree।`

A) Travelling Salesperson Problem
B) Feasibility Constraint
C) State-space Tree
D) NP-hard

**সঠিক উত্তর: C) State-space Tree**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Search problem-এর partial decision-গুলোকে node এবং choice-গুলোকে branch হিসেবে প্রকাশ করা tree।
- **A option কেন ভুল:** `Travelling Salesperson Problem` বলতে সব city একবার visit করে শুরুতে ফিরে minimum-cost Hamiltonian cycle খোঁজার NP-hard optimization problem। বোঝায়; প্রশ্নের বর্ণনা `State-space Tree`-এর।
- **B option কেন ভুল:** `Feasibility Constraint` বলতে Partial বা complete candidate problem-এর বাধ্যতামূলক constraint মানছে কি না নির্ধারণ করে। বোঝায়; প্রশ্নের বর্ণনা `State-space Tree`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `NP-hard` বলতে যে optimization problem polynomial time-এ solve করা পরিচিত নয় এবং NP-এর সব problem তার কাছে polynomial reduction করা যায়। বোঝায়; প্রশ্নের বর্ণনা `State-space Tree`-এর।
- **Related Concept:** Backtracking ও Branch-and-Bound analysis-এ ব্যবহৃত।
- **মনে রাখার টিপস:** Node = partial solution।

---

## প্রশ্ন 515 | Topic: Data Structure and Algorithm > Backtracking and Optimization | Difficulty: Hard | Type: Theory

Q. `Feasibility Constraint` সম্পর্কে কোন statement সঠিক?

A) Partial বা complete candidate problem-এর বাধ্যতামূলক constraint মানছে কি না নির্ধারণ করে।
B) সব city একবার visit করে শুরুতে ফিরে minimum-cost Hamiltonian cycle খোঁজার NP-hard optimization problem।
C) যে optimization problem polynomial time-এ solve করা পরিচিত নয় এবং NP-এর সব problem তার কাছে polynomial reduction করা যায়।
D) Polynomial time-এ provable boundসহ optimal-এর কাছাকাছি solution প্রদান করে।

**সঠিক উত্তর: A) Partial বা complete candidate problem-এর বাধ্যতামূলক constraint মানছে কি না নির্ধারণ করে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Partial বা complete candidate problem-এর বাধ্যতামূলক constraint মানছে কি না নির্ধারণ করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Travelling Salesperson Problem` ধারণাকে বর্ণনা করে; `Feasibility Constraint`-কে নয়।
- **C option কেন ভুল:** এই statementটি `NP-hard` ধারণাকে বর্ণনা করে; `Feasibility Constraint`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Approximation Algorithm` ধারণাকে বর্ণনা করে; `Feasibility Constraint`-কে নয়।
- **Related Concept:** Invalid candidate দ্রুত prune করা যায়।
- **মনে রাখার টিপস:** Constraint না মানলে branch বন্ধ।

---

## প্রশ্ন 516 | Topic: Data Structure and Algorithm > Backtracking and Optimization | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `Optimization problem-এ যে numeric value minimize বা maximize করা হয়।`—এখানে কোন concept প্রযোজ্য?

A) Objective Function
B) Assembly Line Scheduling
C) Travelling Salesperson Problem
D) Branch and Bound

**সঠিক উত্তর: A) Objective Function**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Optimization problem-এ যে numeric value minimize বা maximize করা হয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Assembly Line Scheduling` বলতে একাধিক production line ও transfer cost-এর মধ্যে minimum completion time DP দিয়ে নির্ণয় করার problem। বোঝায়; প্রশ্নের বর্ণনা `Objective Function`-এর।
- **C option কেন ভুল:** `Travelling Salesperson Problem` বলতে সব city একবার visit করে শুরুতে ফিরে minimum-cost Hamiltonian cycle খোঁজার NP-hard optimization problem। বোঝায়; প্রশ্নের বর্ণনা `Objective Function`-এর।
- **D option কেন ভুল:** `Branch and Bound` বলতে Optimization search-এ bound ব্যবহার করে এমন branch prune করা যার থেকে incumbent-এর চেয়ে ভালো solution সম্ভব নয়। বোঝায়; প্রশ্নের বর্ণনা `Objective Function`-এর।
- **Related Concept:** TSP-তে total tour cost objective।
- **মনে রাখার টিপস:** Best বলতে objective-এর best value।

---

## প্রশ্ন 517 | Topic: Data Structure and Algorithm > Backtracking and Optimization | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Hidden Markov Model-এ সবচেয়ে probable hidden-state sequence Dynamic Programming দিয়ে নির্ণয় করে।`

A) Backtracking
B) Travelling Salesperson Problem
C) Branch and Bound
D) Viterbi Algorithm

**সঠিক উত্তর: D) Viterbi Algorithm**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Hidden Markov Model-এ সবচেয়ে probable hidden-state sequence Dynamic Programming দিয়ে নির্ণয় করে।
- **A option কেন ভুল:** `Backtracking` বলতে Partial solution constraint ভাঙলে সেই branch ত্যাগ করে আগের decision-এ ফিরে অন্য choice পরীক্ষা করা search technique। বোঝায়; প্রশ্নের বর্ণনা `Viterbi Algorithm`-এর।
- **B option কেন ভুল:** `Travelling Salesperson Problem` বলতে সব city একবার visit করে শুরুতে ফিরে minimum-cost Hamiltonian cycle খোঁজার NP-hard optimization problem। বোঝায়; প্রশ্নের বর্ণনা `Viterbi Algorithm`-এর।
- **C option কেন ভুল:** `Branch and Bound` বলতে Optimization search-এ bound ব্যবহার করে এমন branch prune করা যার থেকে incumbent-এর চেয়ে ভালো solution সম্ভব নয়। বোঝায়; প্রশ্নের বর্ণনা `Viterbi Algorithm`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Speech recognition ও sequence decoding-এ ব্যবহৃত।
- **মনে রাখার টিপস:** Most likely path through states।

---

## প্রশ্ন 518 | Topic: Data Structure and Algorithm > Backtracking and Optimization | Difficulty: Medium | Type: Calculation

Q. Assembly line-এর একটি station-এ একই line-এ থাকলে arrival time 12 এবং অন্য line থেকে transferসহ arrival time 9। DP state কোন value নেবে?

A) 3
B) 9
C) 12
D) 21

**সঠিক উত্তর: B) 9**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Minimum completion time state দুটি candidate-এর minimum নেয়।

#### Step-by-step সমাধান

```text
Candidate 1 = 12
Candidate 2 = 9
DP value    = min(12, 9)
            = 9
```
- **A option কেন ভুল:** দুই candidate-এর difference নেওয়া হয়েছে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** বড় candidate নেওয়া হয়েছে।
- **D option কেন ভুল:** দুইটি যোগ করা হয়েছে।
- **Related Concept:** Assembly Line DP প্রতিটি station-এ stay বনাম transfer তুলনা করে।
- **মনে রাখার টিপস:** দুটি route-এর ছোট arrival time রাখুন।

---

## প্রশ্ন 519 | Topic: Data Structure and Algorithm > Backtracking and Optimization | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `যে optimization problem polynomial time-এ solve করা পরিচিত নয় এবং NP-এর সব problem তার কাছে polynomial reduction করা যায়।`—এখানে কোন concept প্রযোজ্য?

A) Feasibility Constraint
B) Approximation Algorithm
C) Backtracking
D) NP-hard

**সঠিক উত্তর: D) NP-hard**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** যে optimization problem polynomial time-এ solve করা পরিচিত নয় এবং NP-এর সব problem তার কাছে polynomial reduction করা যায়।
- **A option কেন ভুল:** `Feasibility Constraint` বলতে Partial বা complete candidate problem-এর বাধ্যতামূলক constraint মানছে কি না নির্ধারণ করে। বোঝায়; প্রশ্নের বর্ণনা `NP-hard`-এর।
- **B option কেন ভুল:** `Approximation Algorithm` বলতে Polynomial time-এ provable boundসহ optimal-এর কাছাকাছি solution প্রদান করে। বোঝায়; প্রশ্নের বর্ণনা `NP-hard`-এর।
- **C option কেন ভুল:** `Backtracking` বলতে Partial solution constraint ভাঙলে সেই branch ত্যাগ করে আগের decision-এ ফিরে অন্য choice পরীক্ষা করা search technique। বোঝায়; প্রশ্নের বর্ণনা `NP-hard`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** TSP optimization version NP-hard।
- **মনে রাখার টিপস:** Hardness মানে known efficient exact algorithm নেই।

---

## প্রশ্ন 520 | Topic: Data Structure and Algorithm > Backtracking and Optimization | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Polynomial time-এ provable boundসহ optimal-এর কাছাকাছি solution প্রদান করে।`

A) Approximation Algorithm
B) State-space Tree
C) Assembly Line Scheduling
D) NP-hard

**সঠিক উত্তর: A) Approximation Algorithm**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Polynomial time-এ provable boundসহ optimal-এর কাছাকাছি solution প্রদান করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `State-space Tree` বলতে Search problem-এর partial decision-গুলোকে node এবং choice-গুলোকে branch হিসেবে প্রকাশ করা tree। বোঝায়; প্রশ্নের বর্ণনা `Approximation Algorithm`-এর।
- **C option কেন ভুল:** `Assembly Line Scheduling` বলতে একাধিক production line ও transfer cost-এর মধ্যে minimum completion time DP দিয়ে নির্ণয় করার problem। বোঝায়; প্রশ্নের বর্ণনা `Approximation Algorithm`-এর।
- **D option কেন ভুল:** `NP-hard` বলতে যে optimization problem polynomial time-এ solve করা পরিচিত নয় এবং NP-এর সব problem তার কাছে polynomial reduction করা যায়। বোঝায়; প্রশ্নের বর্ণনা `Approximation Algorithm`-এর।
- **Related Concept:** NP-hard optimization-এ কার্যকর।
- **মনে রাখার টিপস:** Fast near-optimal + guarantee।

---


# Chapter Theory 42: Internet, Web এবং HTTP Fundamentals

## বিস্তারিত Theory Note

Internet হলো network-of-networks; Web সেই infrastructure-এর ওপর চলা একটি application service। Browser URL parse করে DNS resolution-এর মাধ্যমে server address পায়, connection স্থাপন করে, HTTP request পাঠায় এবং response body render করে।

HTTPS ব্যবহার করলে TLS handshake-এর মাধ্যমে encrypted channel ও certificate-based server identity যাচাই করা হয়। HTTP stateless হওয়ায় cookie, session token বা application storage দিয়ে state management যোগ করা হয়।

## মূল ধারণার মানচিত্র

- **World Wide Web:** Internet-এর ওপর HTTP/HTTPS ও hyperlink ব্যবহার করে interlinked resource access-এর service।
- **HTTP:** Client–server request-response application protocol, যা web resource transfer করে।
- **HTTPS:** TLS দ্বারা encrypted ও authenticated HTTP communication।
- **URL:** একটি resource-এর scheme, host, optional port, path, query ও fragmentসহ locator।
- **DNS:** Human-readable domain name-কে IP address বা অন্যান্য record-এ resolve করার distributed naming system।
- **Web Browser:** HTML/CSS render, JavaScript execute এবং HTTP client হিসেবে web resource access করা software।
- **Web Server:** HTTP request গ্রহণ করে static file বা generated response প্রদান করা server software।
- **Statelessness:** প্রতিটি HTTP request নিজস্ব প্রয়োজনীয় context বহন করে; protocol নিজে previous request state ধরে না।
- **Status Code:** HTTP response outcome তিন-digit code দিয়ে প্রকাশ করে।
- **Content-Type:** HTTP header যা message body-এর media type যেমন text/html বা application/json জানায়।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Internet, Web এবং HTTP Fundamentals

## প্রশ্ন 521 | Topic: Web Technology > Web Fundamentals | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Internet-এর ওপর HTTP/HTTPS ও hyperlink ব্যবহার করে interlinked resource access-এর service।`

A) URL
B) Statelessness
C) World Wide Web
D) HTTP

**সঠিক উত্তর: C) World Wide Web**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Internet-এর ওপর HTTP/HTTPS ও hyperlink ব্যবহার করে interlinked resource access-এর service।
- **A option কেন ভুল:** `URL` বলতে একটি resource-এর scheme, host, optional port, path, query ও fragmentসহ locator। বোঝায়; প্রশ্নের বর্ণনা `World Wide Web`-এর।
- **B option কেন ভুল:** `Statelessness` বলতে প্রতিটি HTTP request নিজস্ব প্রয়োজনীয় context বহন করে; protocol নিজে previous request state ধরে না। বোঝায়; প্রশ্নের বর্ণনা `World Wide Web`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `HTTP` বলতে Client–server request-response application protocol, যা web resource transfer করে। বোঝায়; প্রশ্নের বর্ণনা `World Wide Web`-এর।
- **Related Concept:** Internet infrastructure; Web তার একটি service।
- **মনে রাখার টিপস:** Internet আর Web এক নয়।

---

## প্রশ্ন 522 | Topic: Web Technology > Web Fundamentals | Difficulty: Easy | Type: Theory

Q. `HTTP` সম্পর্কে কোন statement সঠিক?

A) HTTP request গ্রহণ করে static file বা generated response প্রদান করা server software।
B) Client–server request-response application protocol, যা web resource transfer করে।
C) Human-readable domain name-কে IP address বা অন্যান্য record-এ resolve করার distributed naming system।
D) একটি resource-এর scheme, host, optional port, path, query ও fragmentসহ locator।

**সঠিক উত্তর: B) Client–server request-response application protocol, যা web resource transfer করে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Client–server request-response application protocol, যা web resource transfer করে।
- **A option কেন ভুল:** এই statementটি `Web Server` ধারণাকে বর্ণনা করে; `HTTP`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `DNS` ধারণাকে বর্ণনা করে; `HTTP`-কে নয়।
- **D option কেন ভুল:** এই statementটি `URL` ধারণাকে বর্ণনা করে; `HTTP`-কে নয়।
- **Related Concept:** সাধারণত stateless protocol।
- **মনে রাখার টিপস:** HTTP request, server response।

---

## প্রশ্ন 523 | Topic: Web Technology > Web Fundamentals | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `TLS দ্বারা encrypted ও authenticated HTTP communication।`—এখানে কোন concept প্রযোজ্য?

A) HTTPS
B) DNS
C) World Wide Web
D) Web Browser

**সঠিক উত্তর: A) HTTPS**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** TLS দ্বারা encrypted ও authenticated HTTP communication।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `DNS` বলতে Human-readable domain name-কে IP address বা অন্যান্য record-এ resolve করার distributed naming system। বোঝায়; প্রশ্নের বর্ণনা `HTTPS`-এর।
- **C option কেন ভুল:** `World Wide Web` বলতে Internet-এর ওপর HTTP/HTTPS ও hyperlink ব্যবহার করে interlinked resource access-এর service। বোঝায়; প্রশ্নের বর্ণনা `HTTPS`-এর।
- **D option কেন ভুল:** `Web Browser` বলতে HTML/CSS render, JavaScript execute এবং HTTP client হিসেবে web resource access করা software। বোঝায়; প্রশ্নের বর্ণনা `HTTPS`-এর।
- **Related Concept:** Confidentiality, integrity ও server authentication দেয়।
- **মনে রাখার টিপস:** HTTPS = HTTP over TLS।

---

## প্রশ্ন 524 | Topic: Web Technology > Web Fundamentals | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`একটি resource-এর scheme, host, optional port, path, query ও fragmentসহ locator।`

A) HTTP
B) World Wide Web
C) Web Server
D) URL

**সঠিক উত্তর: D) URL**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একটি resource-এর scheme, host, optional port, path, query ও fragmentসহ locator।
- **A option কেন ভুল:** `HTTP` বলতে Client–server request-response application protocol, যা web resource transfer করে। বোঝায়; প্রশ্নের বর্ণনা `URL`-এর।
- **B option কেন ভুল:** `World Wide Web` বলতে Internet-এর ওপর HTTP/HTTPS ও hyperlink ব্যবহার করে interlinked resource access-এর service। বোঝায়; প্রশ্নের বর্ণনা `URL`-এর।
- **C option কেন ভুল:** `Web Server` বলতে HTTP request গ্রহণ করে static file বা generated response প্রদান করা server software। বোঝায়; প্রশ্নের বর্ণনা `URL`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** URI-এর একটি ধরন।
- **মনে রাখার টিপস:** কোথায় resource—URL।

---

## প্রশ্ন 525 | Topic: Web Technology > Web Fundamentals | Difficulty: Medium | Type: Theory

Q. `DNS` সম্পর্কে কোন statement সঠিক?

A) Human-readable domain name-কে IP address বা অন্যান্য record-এ resolve করার distributed naming system।
B) প্রতিটি HTTP request নিজস্ব প্রয়োজনীয় context বহন করে; protocol নিজে previous request state ধরে না।
C) HTTP request গ্রহণ করে static file বা generated response প্রদান করা server software।
D) Client–server request-response application protocol, যা web resource transfer করে।

**সঠিক উত্তর: A) Human-readable domain name-কে IP address বা অন্যান্য record-এ resolve করার distributed naming system।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Human-readable domain name-কে IP address বা অন্যান্য record-এ resolve করার distributed naming system।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Statelessness` ধারণাকে বর্ণনা করে; `DNS`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Web Server` ধারণাকে বর্ণনা করে; `DNS`-কে নয়।
- **D option কেন ভুল:** এই statementটি `HTTP` ধারণাকে বর্ণনা করে; `DNS`-কে নয়।
- **Related Concept:** A, AAAA, CNAME, MX record প্রচলিত।
- **মনে রাখার টিপস:** Name to address।

---

## প্রশ্ন 526 | Topic: Web Technology > Web Fundamentals | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `HTML/CSS render, JavaScript execute এবং HTTP client হিসেবে web resource access করা software।`—এখানে কোন concept প্রযোজ্য?

A) URL
B) Web Browser
C) HTTPS
D) DNS

**সঠিক উত্তর: B) Web Browser**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** HTML/CSS render, JavaScript execute এবং HTTP client হিসেবে web resource access করা software।
- **A option কেন ভুল:** `URL` বলতে একটি resource-এর scheme, host, optional port, path, query ও fragmentসহ locator। বোঝায়; প্রশ্নের বর্ণনা `Web Browser`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `HTTPS` বলতে TLS দ্বারা encrypted ও authenticated HTTP communication। বোঝায়; প্রশ্নের বর্ণনা `Web Browser`-এর।
- **D option কেন ভুল:** `DNS` বলতে Human-readable domain name-কে IP address বা অন্যান্য record-এ resolve করার distributed naming system। বোঝায়; প্রশ্নের বর্ণনা `Web Browser`-এর।
- **Related Concept:** Rendering engine ও JS engine থাকে।
- **মনে রাখার টিপস:** Browser client-side runtime।

---

## প্রশ্ন 527 | Topic: Web Technology > Web Fundamentals | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`HTTP request গ্রহণ করে static file বা generated response প্রদান করা server software।`

A) DNS
B) World Wide Web
C) Content-Type
D) Web Server

**সঠিক উত্তর: D) Web Server**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** HTTP request গ্রহণ করে static file বা generated response প্রদান করা server software।
- **A option কেন ভুল:** `DNS` বলতে Human-readable domain name-কে IP address বা অন্যান্য record-এ resolve করার distributed naming system। বোঝায়; প্রশ্নের বর্ণনা `Web Server`-এর।
- **B option কেন ভুল:** `World Wide Web` বলতে Internet-এর ওপর HTTP/HTTPS ও hyperlink ব্যবহার করে interlinked resource access-এর service। বোঝায়; প্রশ্নের বর্ণনা `Web Server`-এর।
- **C option কেন ভুল:** `Content-Type` বলতে HTTP header যা message body-এর media type যেমন text/html বা application/json জানায়। বোঝায়; প্রশ্নের বর্ণনা `Web Server`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Apache, Nginx ইত্যাদি।
- **মনে রাখার টিপস:** Server request serve করে।

---

## প্রশ্ন 528 | Topic: Web Technology > Web Fundamentals | Difficulty: Hard | Type: Theory

Q. `Statelessness` সম্পর্কে কোন statement সঠিক?

A) HTTP header যা message body-এর media type যেমন text/html বা application/json জানায়।
B) একটি resource-এর scheme, host, optional port, path, query ও fragmentসহ locator।
C) প্রতিটি HTTP request নিজস্ব প্রয়োজনীয় context বহন করে; protocol নিজে previous request state ধরে না।
D) HTTP request গ্রহণ করে static file বা generated response প্রদান করা server software।

**সঠিক উত্তর: C) প্রতিটি HTTP request নিজস্ব প্রয়োজনীয় context বহন করে; protocol নিজে previous request state ধরে না।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি HTTP request নিজস্ব প্রয়োজনীয় context বহন করে; protocol নিজে previous request state ধরে না।
- **A option কেন ভুল:** এই statementটি `Content-Type` ধারণাকে বর্ণনা করে; `Statelessness`-কে নয়।
- **B option কেন ভুল:** এই statementটি `URL` ধারণাকে বর্ণনা করে; `Statelessness`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Web Server` ধারণাকে বর্ণনা করে; `Statelessness`-কে নয়।
- **Related Concept:** Session layer applicationভাবে যোগ করা হয়।
- **মনে রাখার টিপস:** HTTP নিজে memory রাখে না।

---

## প্রশ্ন 529 | Topic: Web Technology > Web Fundamentals | Difficulty: Medium | Type: Tracing

Q. HTTP response code 404 কোন category ও অর্থ নির্দেশ করে?

A) 2xx Success
B) 3xx Redirection
C) 5xx Server Error
D) 4xx Client Error—Not Found

**সঠিক উত্তর: D) 4xx Client Error—Not Found**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 404-এ প্রথম digit 4 client-error class এবং নির্দিষ্ট অর্থ requested resource not found।

#### Step-by-step সমাধান

```text
Status code = 404
First digit = 4
Category    = Client Error
Specific    = Not Found
```
- **A option কেন ভুল:** Successful response class।
- **B option কেন ভুল:** Resource location/redirect class।
- **C option কেন ভুল:** Server-side failure class।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** HTTP status code category প্রথম digit থেকে বোঝা যায়।
- **মনে রাখার টিপস:** 404 = client requested resource not found।

---

## প্রশ্ন 530 | Topic: Web Technology > Web Fundamentals | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`HTTP header যা message body-এর media type যেমন text/html বা application/json জানায়।`

A) DNS
B) World Wide Web
C) Content-Type
D) HTTPS

**সঠিক উত্তর: C) Content-Type**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** HTTP header যা message body-এর media type যেমন text/html বা application/json জানায়।
- **A option কেন ভুল:** `DNS` বলতে Human-readable domain name-কে IP address বা অন্যান্য record-এ resolve করার distributed naming system। বোঝায়; প্রশ্নের বর্ণনা `Content-Type`-এর।
- **B option কেন ভুল:** `World Wide Web` বলতে Internet-এর ওপর HTTP/HTTPS ও hyperlink ব্যবহার করে interlinked resource access-এর service। বোঝায়; প্রশ্নের বর্ণনা `Content-Type`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `HTTPS` বলতে TLS দ্বারা encrypted ও authenticated HTTP communication। বোঝায়; প্রশ্নের বর্ণনা `Content-Type`-এর।
- **Related Concept:** Correct parsing ও rendering-এর জন্য দরকার।
- **মনে রাখার টিপস:** Body কী format—Content-Type।

---


# Chapter Theory 43: HTML Structure, Forms এবং Accessibility

## বিস্তারিত Theory Note

HTML content-এর meaning ও hierarchy প্রকাশ করে। Heading level, landmark element, label, table header ও alternative text সঠিকভাবে ব্যবহার করলে screen reader ও search engine document ভালোভাবে বুঝতে পারে।

Form submission-এ `name` attribute ছাড়া control-এর value সাধারণত successful form data হিসেবে পাঠানো হয় না। `GET` query URL-এ যায়; `POST` request body-তে যায়। Client-side validation user experience বাড়ালেও server-side validation অপরিহার্য।

## মূল ধারণার মানচিত্র

- **HTML:** Web document-এর semantic structure ও content markup করার language।
- **DOCTYPE:** Document কোন HTML standard অনুযায়ী parse হবে তা browser-কে জানায়।
- **Semantic Element:** Content-এর অর্থ প্রকাশকারী element যেমন header, nav, main, article ও footer।
- **Form:** User input সংগ্রহ ও server endpoint-এ submit করার HTML structure।
- **Label:** Form control-এর accessible name ও click target প্রদান করে।
- **Table:** Tabular data row ও column-এ প্রকাশ করার element; page layout-এর জন্য নয়।
- **Hyperlink:** `a` element-এর `href` দিয়ে অন্য resource বা location-এ navigation।
- **Image Alternative Text:** `alt` attribute image unavailable বা screen reader context-এ অর্থপূর্ণ বিকল্প text দেয়।
- **Block Element:** সাধারণ flow-এ নতুন line/available width দখল করা element category।
- **HTML Validation:** Markup standard-এর syntax ও structural rule পরীক্ষা করা।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: HTML Structure, Forms এবং Accessibility

## প্রশ্ন 531 | Topic: Web Technology > HTML | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Web document-এর semantic structure ও content markup করার language।`

A) HTML
B) Semantic Element
C) Label
D) Table

**সঠিক উত্তর: A) HTML**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Web document-এর semantic structure ও content markup করার language।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Semantic Element` বলতে Content-এর অর্থ প্রকাশকারী element যেমন header, nav, main, article ও footer। বোঝায়; প্রশ্নের বর্ণনা `HTML`-এর।
- **C option কেন ভুল:** `Label` বলতে Form control-এর accessible name ও click target প্রদান করে। বোঝায়; প্রশ্নের বর্ণনা `HTML`-এর।
- **D option কেন ভুল:** `Table` বলতে Tabular data row ও column-এ প্রকাশ করার element; page layout-এর জন্য নয়। বোঝায়; প্রশ্নের বর্ণনা `HTML`-এর।
- **Related Concept:** Programming language নয়; markup language।
- **মনে রাখার টিপস:** HTML structure দেয়।

---

## প্রশ্ন 532 | Topic: Web Technology > HTML | Difficulty: Medium | Type: Theory

Q. `DOCTYPE` সম্পর্কে কোন statement সঠিক?

A) Form control-এর accessible name ও click target প্রদান করে।
B) Document কোন HTML standard অনুযায়ী parse হবে তা browser-কে জানায়।
C) User input সংগ্রহ ও server endpoint-এ submit করার HTML structure।
D) Web document-এর semantic structure ও content markup করার language।

**সঠিক উত্তর: B) Document কোন HTML standard অনুযায়ী parse হবে তা browser-কে জানায়।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Document কোন HTML standard অনুযায়ী parse হবে তা browser-কে জানায়।
- **A option কেন ভুল:** এই statementটি `Label` ধারণাকে বর্ণনা করে; `DOCTYPE`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `Form` ধারণাকে বর্ণনা করে; `DOCTYPE`-কে নয়।
- **D option কেন ভুল:** এই statementটি `HTML` ধারণাকে বর্ণনা করে; `DOCTYPE`-কে নয়।
- **Related Concept:** HTML5 declaration `<!DOCTYPE html>`।
- **মনে রাখার টিপস:** Standards mode trigger।

---

## প্রশ্ন 533 | Topic: Web Technology > HTML | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Content-এর অর্থ প্রকাশকারী element যেমন header, nav, main, article ও footer।`—এখানে কোন concept প্রযোজ্য?

A) Form
B) Semantic Element
C) Block Element
D) Table

**সঠিক উত্তর: B) Semantic Element**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Content-এর অর্থ প্রকাশকারী element যেমন header, nav, main, article ও footer।
- **A option কেন ভুল:** `Form` বলতে User input সংগ্রহ ও server endpoint-এ submit করার HTML structure। বোঝায়; প্রশ্নের বর্ণনা `Semantic Element`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Block Element` বলতে সাধারণ flow-এ নতুন line/available width দখল করা element category। বোঝায়; প্রশ্নের বর্ণনা `Semantic Element`-এর।
- **D option কেন ভুল:** `Table` বলতে Tabular data row ও column-এ প্রকাশ করার element; page layout-এর জন্য নয়। বোঝায়; প্রশ্নের বর্ণনা `Semantic Element`-এর।
- **Related Concept:** Accessibility ও SEO উন্নত করে।
- **মনে রাখার টিপস:** Tag দেখে অর্থ বোঝা যায়।

---

## প্রশ্ন 534 | Topic: Web Technology > HTML | Difficulty: Easy | Type: Code

Q. Form-এর method `GET` এবং input `q=ict` হলে URL query সাধারণত কীভাবে যুক্ত হয়?

A) /search#q=ict
B) /search/q/ict
C) /search?q=ict
D) /search;ict

**সঠিক উত্তর: C) /search?q=ict**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** GET form data URL-এর query string-এ `?name=value` format-এ যায়।

#### Step-by-step সমাধান

```text
Action path = /search
Field name  = q
Field value = ict
Query       = ?q=ict
Final URL   = /search?q=ict
```
- **A option কেন ভুল:** `#` fragment server request query নয়।
- **B option কেন ভুল:** এটি path-style routing, default GET serialization নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Standard query name-value syntax নয়।
- **Related Concept:** Sensitive বা large data-এর জন্য GET query উপযুক্ত নয়।
- **মনে রাখার টিপস:** GET data URL-এ দেখা যায়: ?key=value।

---

## প্রশ্ন 535 | Topic: Web Technology > HTML | Difficulty: Hard | Type: Theory

Q. `Label` সম্পর্কে কোন statement সঠিক?

A) সাধারণ flow-এ নতুন line/available width দখল করা element category।
B) Form control-এর accessible name ও click target প্রদান করে।
C) Content-এর অর্থ প্রকাশকারী element যেমন header, nav, main, article ও footer।
D) `a` element-এর `href` দিয়ে অন্য resource বা location-এ navigation।

**সঠিক উত্তর: B) Form control-এর accessible name ও click target প্রদান করে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Form control-এর accessible name ও click target প্রদান করে।
- **A option কেন ভুল:** এই statementটি `Block Element` ধারণাকে বর্ণনা করে; `Label`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `Semantic Element` ধারণাকে বর্ণনা করে; `Label`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Hyperlink` ধারণাকে বর্ণনা করে; `Label`-কে নয়।
- **Related Concept:** `for` attribute input id-এর সঙ্গে যুক্ত হয়।
- **মনে রাখার টিপস:** Input-এর নাম label।

---

## প্রশ্ন 536 | Topic: Web Technology > HTML | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Tabular data row ও column-এ প্রকাশ করার element; page layout-এর জন্য নয়।`—এখানে কোন concept প্রযোজ্য?

A) Label
B) Table
C) HTML
D) Form

**সঠিক উত্তর: B) Table**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Tabular data row ও column-এ প্রকাশ করার element; page layout-এর জন্য নয়।
- **A option কেন ভুল:** `Label` বলতে Form control-এর accessible name ও click target প্রদান করে। বোঝায়; প্রশ্নের বর্ণনা `Table`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `HTML` বলতে Web document-এর semantic structure ও content markup করার language। বোঝায়; প্রশ্নের বর্ণনা `Table`-এর।
- **D option কেন ভুল:** `Form` বলতে User input সংগ্রহ ও server endpoint-এ submit করার HTML structure। বোঝায়; প্রশ্নের বর্ণনা `Table`-এর।
- **Related Concept:** caption, thead, tbody, th accessibility বাড়ায়।
- **মনে রাখার টিপস:** Data table, layout নয়।

---

## প্রশ্ন 537 | Topic: Web Technology > HTML | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

``a` element-এর `href` দিয়ে অন্য resource বা location-এ navigation।`

A) Label
B) Image Alternative Text
C) Hyperlink
D) DOCTYPE

**সঠিক উত্তর: C) Hyperlink**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `a` element-এর `href` দিয়ে অন্য resource বা location-এ navigation।
- **A option কেন ভুল:** `Label` বলতে Form control-এর accessible name ও click target প্রদান করে। বোঝায়; প্রশ্নের বর্ণনা `Hyperlink`-এর।
- **B option কেন ভুল:** `Image Alternative Text` বলতে `alt` attribute image unavailable বা screen reader context-এ অর্থপূর্ণ বিকল্প text দেয়। বোঝায়; প্রশ্নের বর্ণনা `Hyperlink`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `DOCTYPE` বলতে Document কোন HTML standard অনুযায়ী parse হবে তা browser-কে জানায়। বোঝায়; প্রশ্নের বর্ণনা `Hyperlink`-এর।
- **Related Concept:** Relative ও absolute URL ব্যবহার করা যায়।
- **মনে রাখার টিপস:** Anchor connects resources।

---

## প্রশ্ন 538 | Topic: Web Technology > HTML | Difficulty: Medium | Type: Theory

Q. `Image Alternative Text` সম্পর্কে কোন statement সঠিক?

A) `alt` attribute image unavailable বা screen reader context-এ অর্থপূর্ণ বিকল্প text দেয়।
B) `a` element-এর `href` দিয়ে অন্য resource বা location-এ navigation।
C) Markup standard-এর syntax ও structural rule পরীক্ষা করা।
D) Content-এর অর্থ প্রকাশকারী element যেমন header, nav, main, article ও footer।

**সঠিক উত্তর: A) `alt` attribute image unavailable বা screen reader context-এ অর্থপূর্ণ বিকল্প text দেয়।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `alt` attribute image unavailable বা screen reader context-এ অর্থপূর্ণ বিকল্প text দেয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Hyperlink` ধারণাকে বর্ণনা করে; `Image Alternative Text`-কে নয়।
- **C option কেন ভুল:** এই statementটি `HTML Validation` ধারণাকে বর্ণনা করে; `Image Alternative Text`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Semantic Element` ধারণাকে বর্ণনা করে; `Image Alternative Text`-কে নয়।
- **Related Concept:** Decorative image-এ empty alt হতে পারে।
- **মনে রাখার টিপস:** Image meaning in words।

---

## প্রশ্ন 539 | Topic: Web Technology > HTML | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `সাধারণ flow-এ নতুন line/available width দখল করা element category।`—এখানে কোন concept প্রযোজ্য?

A) Label
B) Hyperlink
C) Table
D) Block Element

**সঠিক উত্তর: D) Block Element**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** সাধারণ flow-এ নতুন line/available width দখল করা element category।
- **A option কেন ভুল:** `Label` বলতে Form control-এর accessible name ও click target প্রদান করে। বোঝায়; প্রশ্নের বর্ণনা `Block Element`-এর।
- **B option কেন ভুল:** `Hyperlink` বলতে `a` element-এর `href` দিয়ে অন্য resource বা location-এ navigation। বোঝায়; প্রশ্নের বর্ণনা `Block Element`-এর।
- **C option কেন ভুল:** `Table` বলতে Tabular data row ও column-এ প্রকাশ করার element; page layout-এর জন্য নয়। বোঝায়; প্রশ্নের বর্ণনা `Block Element`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** CSS display দিয়ে behavior বদলানো যায়।
- **মনে রাখার টিপস:** Block starts new line।

---

## প্রশ্ন 540 | Topic: Web Technology > HTML | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Markup standard-এর syntax ও structural rule পরীক্ষা করা।`

A) Table
B) Label
C) Hyperlink
D) HTML Validation

**সঠিক উত্তর: D) HTML Validation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Markup standard-এর syntax ও structural rule পরীক্ষা করা।
- **A option কেন ভুল:** `Table` বলতে Tabular data row ও column-এ প্রকাশ করার element; page layout-এর জন্য নয়। বোঝায়; প্রশ্নের বর্ণনা `HTML Validation`-এর।
- **B option কেন ভুল:** `Label` বলতে Form control-এর accessible name ও click target প্রদান করে। বোঝায়; প্রশ্নের বর্ণনা `HTML Validation`-এর।
- **C option কেন ভুল:** `Hyperlink` বলতে `a` element-এর `href` দিয়ে অন্য resource বা location-এ navigation। বোঝায়; প্রশ্নের বর্ণনা `HTML Validation`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Browser error recovery করলেও valid markup গুরুত্বপূর্ণ।
- **মনে রাখার টিপস:** Browser দেখালেই valid নয়।

---


# Chapter Theory 44: CSS Cascade, Box Model এবং Layout

## বিস্তারিত Theory Note

CSS presentation layer। Cascade conflicting rule resolve করে; specificity তার একটি অংশ। Layout bug বিশ্লেষণে computed style, containing block, box sizing ও overflow পরীক্ষা করা জরুরি।

Flexbox এক axis-এ distribution, Grid দুই axis-এ track control দেয়। Responsive design-এ relative unit, flexible media ও content-driven breakpoint ব্যবহার করলে interface বিভিন্ন viewport-এ কার্যকর থাকে।

## মূল ধারণার মানচিত্র

- **CSS Cascade:** Origin, importance, layer, specificity ও source order অনুযায়ী competing declaration-এর winner নির্ধারণের process।
- **Specificity:** Selector-এর ID, class/attribute/pseudo-class ও type component-এর weight comparison।
- **Box Model:** Content, padding, border ও margin নিয়ে element-এর rectangular layout model।
- **Flexbox:** এক-dimensional row বা column alignment ও flexible distribution-এর layout model।
- **CSS Grid:** Row ও column—দুই dimension-এ track-based layout system।
- **Media Query:** Viewport বা device feature অনুযায়ী conditional CSS প্রয়োগ করে responsive design তৈরি করে।
- **Pseudo-class:** Element state বা structural condition select করে, যেমন `:hover`, `:focus`, `:nth-child()`।
- **Inheritance:** কিছু CSS property parent-এর computed value থেকে child-এ আসে।
- **Positioning:** static, relative, absolute, fixed ও sticky দিয়ে normal flow ও containing block relation নিয়ন্ত্রণ।
- **Responsive Design:** Flexible layout, media query ও adaptable media দিয়ে বিভিন্ন screen size-এ usable interface।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: CSS Cascade, Box Model এবং Layout

## প্রশ্ন 541 | Topic: Web Technology > CSS | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Origin, importance, layer, specificity ও source order অনুযায়ী competing declaration-এর winner নির্ধারণের process।`

A) CSS Grid
B) Responsive Design
C) CSS Cascade
D) Specificity

**সঠিক উত্তর: C) CSS Cascade**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Origin, importance, layer, specificity ও source order অনুযায়ী competing declaration-এর winner নির্ধারণের process।
- **A option কেন ভুল:** `CSS Grid` বলতে Row ও column—দুই dimension-এ track-based layout system। বোঝায়; প্রশ্নের বর্ণনা `CSS Cascade`-এর।
- **B option কেন ভুল:** `Responsive Design` বলতে Flexible layout, media query ও adaptable media দিয়ে বিভিন্ন screen size-এ usable interface। বোঝায়; প্রশ্নের বর্ণনা `CSS Cascade`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Specificity` বলতে Selector-এর ID, class/attribute/pseudo-class ও type component-এর weight comparison। বোঝায়; প্রশ্নের বর্ণনা `CSS Cascade`-এর।
- **Related Concept:** Cascade শুধু specificity নয়।
- **মনে রাখার টিপস:** Priority chain মনে রাখুন।

---

## প্রশ্ন 542 | Topic: Web Technology > CSS | Difficulty: Hard | Type: Theory

Q. `Specificity` সম্পর্কে কোন statement সঠিক?

A) Viewport বা device feature অনুযায়ী conditional CSS প্রয়োগ করে responsive design তৈরি করে।
B) Element state বা structural condition select করে, যেমন `:hover`, `:focus`, `:nth-child()`।
C) Origin, importance, layer, specificity ও source order অনুযায়ী competing declaration-এর winner নির্ধারণের process।
D) Selector-এর ID, class/attribute/pseudo-class ও type component-এর weight comparison।

**সঠিক উত্তর: D) Selector-এর ID, class/attribute/pseudo-class ও type component-এর weight comparison।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Selector-এর ID, class/attribute/pseudo-class ও type component-এর weight comparison।
- **A option কেন ভুল:** এই statementটি `Media Query` ধারণাকে বর্ণনা করে; `Specificity`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Pseudo-class` ধারণাকে বর্ণনা করে; `Specificity`-কে নয়।
- **C option কেন ভুল:** এই statementটি `CSS Cascade` ধারণাকে বর্ণনা করে; `Specificity`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Inline style ও !important-এর আলাদা cascade ভূমিকা আছে।
- **মনে রাখার টিপস:** ID > class > element।

---

## প্রশ্ন 543 | Topic: Web Technology > CSS | Difficulty: Easy | Type: Calculation

Q. `box-sizing: content-box` অবস্থায় width 200px, দুই পাশে padding 10px এবং border 2px হলে total border-box width কত? Margin বাদ দিন।

A) 200px
B) 224px
C) 212px
D) 244px

**সঠিক উত্তর: B) 224px**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Content width-এর সঙ্গে left/right padding 20px ও border 4px যোগ হয়।

#### Step-by-step সমাধান

```text
Content width = 200
Padding total = 10 + 10 = 20
Border total  = 2 + 2 = 4
Total width   = 200 + 20 + 4 = 224px
```
- **A option কেন ভুল:** শুধু content width।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এক পাশের padding ও borderের মতো অসম্পূর্ণ যোগ।
- **D option কেন ভুল:** Margin বা extra 20px অপ্রয়োজনে যোগ।
- **Related Concept:** `border-box` হলে declared width-এর মধ্যে padding ও border অন্তর্ভুক্ত হয়।
- **মনে রাখার টিপস:** দুই পাশের value দ্বিগুণ করতে ভুলবেন না।

---

## প্রশ্ন 544 | Topic: Web Technology > CSS | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`এক-dimensional row বা column alignment ও flexible distribution-এর layout model।`

A) Inheritance
B) Responsive Design
C) Flexbox
D) Media Query

**সঠিক উত্তর: C) Flexbox**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** এক-dimensional row বা column alignment ও flexible distribution-এর layout model।
- **A option কেন ভুল:** `Inheritance` বলতে কিছু CSS property parent-এর computed value থেকে child-এ আসে। বোঝায়; প্রশ্নের বর্ণনা `Flexbox`-এর।
- **B option কেন ভুল:** `Responsive Design` বলতে Flexible layout, media query ও adaptable media দিয়ে বিভিন্ন screen size-এ usable interface। বোঝায়; প্রশ্নের বর্ণনা `Flexbox`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Media Query` বলতে Viewport বা device feature অনুযায়ী conditional CSS প্রয়োগ করে responsive design তৈরি করে। বোঝায়; প্রশ্নের বর্ণনা `Flexbox`-এর।
- **Related Concept:** Main axis ও cross axis থাকে।
- **মনে রাখার টিপস:** One direction layout।

---

## প্রশ্ন 545 | Topic: Web Technology > CSS | Difficulty: Easy | Type: Theory

Q. `CSS Grid` সম্পর্কে কোন statement সঠিক?

A) Selector-এর ID, class/attribute/pseudo-class ও type component-এর weight comparison।
B) Flexible layout, media query ও adaptable media দিয়ে বিভিন্ন screen size-এ usable interface।
C) কিছু CSS property parent-এর computed value থেকে child-এ আসে।
D) Row ও column—দুই dimension-এ track-based layout system।

**সঠিক উত্তর: D) Row ও column—দুই dimension-এ track-based layout system।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Row ও column—দুই dimension-এ track-based layout system।
- **A option কেন ভুল:** এই statementটি `Specificity` ধারণাকে বর্ণনা করে; `CSS Grid`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Responsive Design` ধারণাকে বর্ণনা করে; `CSS Grid`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Inheritance` ধারণাকে বর্ণনা করে; `CSS Grid`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Complex page layout-এ কার্যকর।
- **মনে রাখার টিপস:** Two-dimensional layout।

---

## প্রশ্ন 546 | Topic: Web Technology > CSS | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Viewport বা device feature অনুযায়ী conditional CSS প্রয়োগ করে responsive design তৈরি করে।`—এখানে কোন concept প্রযোজ্য?

A) Media Query
B) Box Model
C) Flexbox
D) Specificity

**সঠিক উত্তর: A) Media Query**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Viewport বা device feature অনুযায়ী conditional CSS প্রয়োগ করে responsive design তৈরি করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Box Model` বলতে Content, padding, border ও margin নিয়ে element-এর rectangular layout model। বোঝায়; প্রশ্নের বর্ণনা `Media Query`-এর।
- **C option কেন ভুল:** `Flexbox` বলতে এক-dimensional row বা column alignment ও flexible distribution-এর layout model। বোঝায়; প্রশ্নের বর্ণনা `Media Query`-এর।
- **D option কেন ভুল:** `Specificity` বলতে Selector-এর ID, class/attribute/pseudo-class ও type component-এর weight comparison। বোঝায়; প্রশ্নের বর্ণনা `Media Query`-এর।
- **Related Concept:** Mobile-first-এ min-width common।
- **মনে রাখার টিপস:** Screen condition অনুযায়ী style।

---

## প্রশ্ন 547 | Topic: Web Technology > CSS | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Element state বা structural condition select করে, যেমন `:hover`, `:focus`, `:nth-child()`।`

A) CSS Cascade
B) Box Model
C) Pseudo-class
D) CSS Grid

**সঠিক উত্তর: C) Pseudo-class**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Element state বা structural condition select করে, যেমন `:hover`, `:focus`, `:nth-child()`।
- **A option কেন ভুল:** `CSS Cascade` বলতে Origin, importance, layer, specificity ও source order অনুযায়ী competing declaration-এর winner নির্ধারণের process। বোঝায়; প্রশ্নের বর্ণনা `Pseudo-class`-এর।
- **B option কেন ভুল:** `Box Model` বলতে Content, padding, border ও margin নিয়ে element-এর rectangular layout model। বোঝায়; প্রশ্নের বর্ণনা `Pseudo-class`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `CSS Grid` বলতে Row ও column—দুই dimension-এ track-based layout system। বোঝায়; প্রশ্নের বর্ণনা `Pseudo-class`-এর।
- **Related Concept:** Pseudo-element content-এর অংশ select/create করে।
- **মনে রাখার টিপস:** Single colon state।

---

## প্রশ্ন 548 | Topic: Web Technology > CSS | Difficulty: Hard | Type: Theory

Q. `Inheritance` সম্পর্কে কোন statement সঠিক?

A) কিছু CSS property parent-এর computed value থেকে child-এ আসে।
B) static, relative, absolute, fixed ও sticky দিয়ে normal flow ও containing block relation নিয়ন্ত্রণ।
C) Origin, importance, layer, specificity ও source order অনুযায়ী competing declaration-এর winner নির্ধারণের process।
D) Flexible layout, media query ও adaptable media দিয়ে বিভিন্ন screen size-এ usable interface।

**সঠিক উত্তর: A) কিছু CSS property parent-এর computed value থেকে child-এ আসে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** কিছু CSS property parent-এর computed value থেকে child-এ আসে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Positioning` ধারণাকে বর্ণনা করে; `Inheritance`-কে নয়।
- **C option কেন ভুল:** এই statementটি `CSS Cascade` ধারণাকে বর্ণনা করে; `Inheritance`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Responsive Design` ধারণাকে বর্ণনা করে; `Inheritance`-কে নয়।
- **Related Concept:** Color inherits; margin সাধারণত নয়।
- **মনে রাখার টিপস:** সব property inherit করে না।

---

## প্রশ্ন 549 | Topic: Web Technology > CSS | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `static, relative, absolute, fixed ও sticky দিয়ে normal flow ও containing block relation নিয়ন্ত্রণ।`—এখানে কোন concept প্রযোজ্য?

A) Flexbox
B) Positioning
C) CSS Cascade
D) Pseudo-class

**সঠিক উত্তর: B) Positioning**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** static, relative, absolute, fixed ও sticky দিয়ে normal flow ও containing block relation নিয়ন্ত্রণ।
- **A option কেন ভুল:** `Flexbox` বলতে এক-dimensional row বা column alignment ও flexible distribution-এর layout model। বোঝায়; প্রশ্নের বর্ণনা `Positioning`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `CSS Cascade` বলতে Origin, importance, layer, specificity ও source order অনুযায়ী competing declaration-এর winner নির্ধারণের process। বোঝায়; প্রশ্নের বর্ণনা `Positioning`-এর।
- **D option কেন ভুল:** `Pseudo-class` বলতে Element state বা structural condition select করে, যেমন `:hover`, `:focus`, `:nth-child()`। বোঝায়; প্রশ্নের বর্ণনা `Positioning`-এর।
- **Related Concept:** Absolute element সাধারণত normal flow থেকে বের হয়।
- **মনে রাখার টিপস:** Position type containing block বদলায়।

---

## প্রশ্ন 550 | Topic: Web Technology > CSS | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Flexible layout, media query ও adaptable media দিয়ে বিভিন্ন screen size-এ usable interface।`

A) Inheritance
B) Responsive Design
C) Flexbox
D) Positioning

**সঠিক উত্তর: B) Responsive Design**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Flexible layout, media query ও adaptable media দিয়ে বিভিন্ন screen size-এ usable interface।
- **A option কেন ভুল:** `Inheritance` বলতে কিছু CSS property parent-এর computed value থেকে child-এ আসে। বোঝায়; প্রশ্নের বর্ণনা `Responsive Design`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Flexbox` বলতে এক-dimensional row বা column alignment ও flexible distribution-এর layout model। বোঝায়; প্রশ্নের বর্ণনা `Responsive Design`-এর।
- **D option কেন ভুল:** `Positioning` বলতে static, relative, absolute, fixed ও sticky দিয়ে normal flow ও containing block relation নিয়ন্ত্রণ। বোঝায়; প্রশ্নের বর্ণনা `Responsive Design`-এর।
- **Related Concept:** Fixed desktop width-এর বিপরীত।
- **মনে রাখার টিপস:** One site, many screens।

---


# Chapter Theory 45: JavaScript Language Fundamentals

## বিস্তারিত Theory Note

JavaScript execution-এ lexical scope, closure, coercion ও reference semantics গুরুত্বপূর্ণ। Primitive value copy হয়; object variable reference value ধারণ করে। `let` ও `const` block scope দেয়, এবং declaration-এর আগে access করলে TDZ error হতে পারে।

Function first-class হওয়ায় callback, event handler ও asynchronous composition সম্ভব। Equality প্রশ্নে `===` type coercion না করায় অধিক predictable।

## মূল ধারণার মানচিত্র

- **JavaScript:** Browser ও server environment-এ চলা dynamic, prototype-based programming language।
- **let:** Block-scoped reassignable binding ঘোষণা করে এবং temporal dead zone-এর অধীন।
- **const:** Block-scoped binding যা পুনরায় assign করা যায় না; referenced object-এর content mutate হতে পারে।
- **Strict Equality:** `===` type coercion ছাড়াই type ও value তুলনা করে।
- **Closure:** Function তার lexical creation environment-এর variable access ধরে রাখে, outer call শেষ হলেও।
- **Hoisting:** Declaration processing-এর কারণে binding execution-এর আগে scope-এ পরিচিত হয়; initialization rule declaration type অনুযায়ী ভিন্ন।
- **Array:** Ordered, zero-indexed, dynamically sized collection-like object।
- **Object:** Key-value property ও prototype relation ধারণকারী reference value।
- **Function:** Callable first-class object, variable-এ রাখা ও argument হিসেবে পাঠানো যায়।
- **Type Coercion:** Operation-এর সময় value এক type থেকে অন্য type-এ implicit বা explicit conversion।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: JavaScript Language Fundamentals

# Batch 13 — Question 551–600

## প্রশ্ন 551 | Topic: Web Technology > JavaScript | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Browser ও server environment-এ চলা dynamic, prototype-based programming language।`

A) Closure
B) Strict Equality
C) JavaScript
D) Function

**সঠিক উত্তর: C) JavaScript**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Browser ও server environment-এ চলা dynamic, prototype-based programming language।
- **A option কেন ভুল:** `Closure` বলতে Function তার lexical creation environment-এর variable access ধরে রাখে, outer call শেষ হলেও। বোঝায়; প্রশ্নের বর্ণনা `JavaScript`-এর।
- **B option কেন ভুল:** `Strict Equality` বলতে `===` type coercion ছাড়াই type ও value তুলনা করে। বোঝায়; প্রশ্নের বর্ণনা `JavaScript`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Function` বলতে Callable first-class object, variable-এ রাখা ও argument হিসেবে পাঠানো যায়। বোঝায়; প্রশ্নের বর্ণনা `JavaScript`-এর।
- **Related Concept:** ECMAScript standard দ্বারা সংজ্ঞায়িত।
- **মনে রাখার টিপস:** Web behavior-এর ভাষা।

---

## প্রশ্ন 552 | Topic: Web Technology > JavaScript | Difficulty: Easy | Type: Theory

Q. `let` সম্পর্কে কোন statement সঠিক?

A) Function তার lexical creation environment-এর variable access ধরে রাখে, outer call শেষ হলেও।
B) Operation-এর সময় value এক type থেকে অন্য type-এ implicit বা explicit conversion।
C) Callable first-class object, variable-এ রাখা ও argument হিসেবে পাঠানো যায়।
D) Block-scoped reassignable binding ঘোষণা করে এবং temporal dead zone-এর অধীন।

**সঠিক উত্তর: D) Block-scoped reassignable binding ঘোষণা করে এবং temporal dead zone-এর অধীন।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Block-scoped reassignable binding ঘোষণা করে এবং temporal dead zone-এর অধীন।
- **A option কেন ভুল:** এই statementটি `Closure` ধারণাকে বর্ণনা করে; `let`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Type Coercion` ধারণাকে বর্ণনা করে; `let`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Function` ধারণাকে বর্ণনা করে; `let`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `var` function-scoped।
- **মনে রাখার টিপস:** Block scope + reassign।

---

## প্রশ্ন 553 | Topic: Web Technology > JavaScript | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `Block-scoped binding যা পুনরায় assign করা যায় না; referenced object-এর content mutate হতে পারে।`—এখানে কোন concept প্রযোজ্য?

A) Strict Equality
B) const
C) Array
D) Hoisting

**সঠিক উত্তর: B) const**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Block-scoped binding যা পুনরায় assign করা যায় না; referenced object-এর content mutate হতে পারে।
- **A option কেন ভুল:** `Strict Equality` বলতে `===` type coercion ছাড়াই type ও value তুলনা করে। বোঝায়; প্রশ্নের বর্ণনা `const`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Array` বলতে Ordered, zero-indexed, dynamically sized collection-like object। বোঝায়; প্রশ্নের বর্ণনা `const`-এর।
- **D option কেন ভুল:** `Hoisting` বলতে Declaration processing-এর কারণে binding execution-এর আগে scope-এ পরিচিত হয়; initialization rule declaration type অনুযায়ী ভিন্ন। বোঝায়; প্রশ্নের বর্ণনা `const`-এর।
- **Related Concept:** Immutable binding, সবসময় immutable value নয়।
- **মনে রাখার টিপস:** Const address fixed, object necessarily নয়।

---

## প্রশ্ন 554 | Topic: Web Technology > JavaScript | Difficulty: Easy | Type: Code

Q. JavaScript expression `2 + '3'`-এর result কী?

A) 5
B) NaN
C) undefined
D) '23'

**সঠিক উত্তর: D) '23'**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** String operand থাকায় `+` concatenation করে এবং number 2 string-এ coerce হয়।

#### Step-by-step সমাধান

```text
Left operand  = number 2
Right operand = string '3'
Number 2 coerces to '2'
Result = '2' + '3' = '23'
```
- **A option কেন ভুল:** Numeric addition ধরে type coercion উপেক্ষা করা হয়েছে।
- **B option কেন ভুল:** Conversion failure নয়; concatenation valid।
- **C option কেন ভুল:** Expression একটি string value দেয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `-` operator সাধারণত operands-কে number-এ coerce করে; `2-'1'` হয় 1।
- **মনে রাখার টিপস:** `+` string দেখলে concatenation পরীক্ষা করুন।

---

## প্রশ্ন 555 | Topic: Web Technology > JavaScript | Difficulty: Medium | Type: Theory

Q. `Closure` সম্পর্কে কোন statement সঠিক?

A) Operation-এর সময় value এক type থেকে অন্য type-এ implicit বা explicit conversion।
B) Block-scoped binding যা পুনরায় assign করা যায় না; referenced object-এর content mutate হতে পারে।
C) `===` type coercion ছাড়াই type ও value তুলনা করে।
D) Function তার lexical creation environment-এর variable access ধরে রাখে, outer call শেষ হলেও।

**সঠিক উত্তর: D) Function তার lexical creation environment-এর variable access ধরে রাখে, outer call শেষ হলেও।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Function তার lexical creation environment-এর variable access ধরে রাখে, outer call শেষ হলেও।
- **A option কেন ভুল:** এই statementটি `Type Coercion` ধারণাকে বর্ণনা করে; `Closure`-কে নয়।
- **B option কেন ভুল:** এই statementটি `const` ধারণাকে বর্ণনা করে; `Closure`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Strict Equality` ধারণাকে বর্ণনা করে; `Closure`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Private state ও callback-এ ব্যবহৃত।
- **মনে রাখার টিপস:** Function remembers outer scope।

---

## প্রশ্ন 556 | Topic: Web Technology > JavaScript | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Declaration processing-এর কারণে binding execution-এর আগে scope-এ পরিচিত হয়; initialization rule declaration type অনুযায়ী ভিন্ন।`—এখানে কোন concept প্রযোজ্য?

A) Function
B) Hoisting
C) Strict Equality
D) Closure

**সঠিক উত্তর: B) Hoisting**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Declaration processing-এর কারণে binding execution-এর আগে scope-এ পরিচিত হয়; initialization rule declaration type অনুযায়ী ভিন্ন।
- **A option কেন ভুল:** `Function` বলতে Callable first-class object, variable-এ রাখা ও argument হিসেবে পাঠানো যায়। বোঝায়; প্রশ্নের বর্ণনা `Hoisting`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Strict Equality` বলতে `===` type coercion ছাড়াই type ও value তুলনা করে। বোঝায়; প্রশ্নের বর্ণনা `Hoisting`-এর।
- **D option কেন ভুল:** `Closure` বলতে Function তার lexical creation environment-এর variable access ধরে রাখে, outer call শেষ হলেও। বোঝায়; প্রশ্নের বর্ণনা `Hoisting`-এর।
- **Related Concept:** `let/const` TDZ-এ থাকে।
- **মনে রাখার টিপস:** Hoisted মানে usable সবসময় নয়।

---

## প্রশ্ন 557 | Topic: Web Technology > JavaScript | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Ordered, zero-indexed, dynamically sized collection-like object।`

A) Object
B) Array
C) Hoisting
D) Type Coercion

**সঠিক উত্তর: B) Array**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Ordered, zero-indexed, dynamically sized collection-like object।
- **A option কেন ভুল:** `Object` বলতে Key-value property ও prototype relation ধারণকারী reference value। বোঝায়; প্রশ্নের বর্ণনা `Array`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Hoisting` বলতে Declaration processing-এর কারণে binding execution-এর আগে scope-এ পরিচিত হয়; initialization rule declaration type অনুযায়ী ভিন্ন। বোঝায়; প্রশ্নের বর্ণনা `Array`-এর।
- **D option কেন ভুল:** `Type Coercion` বলতে Operation-এর সময় value এক type থেকে অন্য type-এ implicit বা explicit conversion। বোঝায়; প্রশ্নের বর্ণনা `Array`-এর।
- **Related Concept:** Sparse slot থাকতে পারে।
- **মনে রাখার টিপস:** Index starts zero।

---

## প্রশ্ন 558 | Topic: Web Technology > JavaScript | Difficulty: Hard | Type: Theory

Q. `Object` সম্পর্কে কোন statement সঠিক?

A) Operation-এর সময় value এক type থেকে অন্য type-এ implicit বা explicit conversion।
B) Browser ও server environment-এ চলা dynamic, prototype-based programming language।
C) Key-value property ও prototype relation ধারণকারী reference value।
D) Function তার lexical creation environment-এর variable access ধরে রাখে, outer call শেষ হলেও।

**সঠিক উত্তর: C) Key-value property ও prototype relation ধারণকারী reference value।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Key-value property ও prototype relation ধারণকারী reference value।
- **A option কেন ভুল:** এই statementটি `Type Coercion` ধারণাকে বর্ণনা করে; `Object`-কে নয়।
- **B option কেন ভুল:** এই statementটি `JavaScript` ধারণাকে বর্ণনা করে; `Object`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Closure` ধারণাকে বর্ণনা করে; `Object`-কে নয়।
- **Related Concept:** Property string বা symbol key হতে পারে।
- **মনে রাখার টিপস:** Named properties।

---

## প্রশ্ন 559 | Topic: Web Technology > JavaScript | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Callable first-class object, variable-এ রাখা ও argument হিসেবে পাঠানো যায়।`—এখানে কোন concept প্রযোজ্য?

A) Function
B) Type Coercion
C) Strict Equality
D) JavaScript

**সঠিক উত্তর: A) Function**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Callable first-class object, variable-এ রাখা ও argument হিসেবে পাঠানো যায়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Type Coercion` বলতে Operation-এর সময় value এক type থেকে অন্য type-এ implicit বা explicit conversion। বোঝায়; প্রশ্নের বর্ণনা `Function`-এর।
- **C option কেন ভুল:** `Strict Equality` বলতে `===` type coercion ছাড়াই type ও value তুলনা করে। বোঝায়; প্রশ্নের বর্ণনা `Function`-এর।
- **D option কেন ভুল:** `JavaScript` বলতে Browser ও server environment-এ চলা dynamic, prototype-based programming language। বোঝায়; প্রশ্নের বর্ণনা `Function`-এর।
- **Related Concept:** Higher-order programming সম্ভব।
- **মনে রাখার টিপস:** Function is a value।

---

## প্রশ্ন 560 | Topic: Web Technology > JavaScript | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Operation-এর সময় value এক type থেকে অন্য type-এ implicit বা explicit conversion।`

A) Hoisting
B) Strict Equality
C) JavaScript
D) Type Coercion

**সঠিক উত্তর: D) Type Coercion**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Operation-এর সময় value এক type থেকে অন্য type-এ implicit বা explicit conversion।
- **A option কেন ভুল:** `Hoisting` বলতে Declaration processing-এর কারণে binding execution-এর আগে scope-এ পরিচিত হয়; initialization rule declaration type অনুযায়ী ভিন্ন। বোঝায়; প্রশ্নের বর্ণনা `Type Coercion`-এর।
- **B option কেন ভুল:** `Strict Equality` বলতে `===` type coercion ছাড়াই type ও value তুলনা করে। বোঝায়; প্রশ্নের বর্ণনা `Type Coercion`-এর।
- **C option কেন ভুল:** `JavaScript` বলতে Browser ও server environment-এ চলা dynamic, prototype-based programming language। বোঝায়; প্রশ্নের বর্ণনা `Type Coercion`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Unexpected `+` behavior ঘটাতে পারে।
- **মনে রাখার টিপস:** Type conversion আগে ভাবুন।

---


# Chapter Theory 46: DOM, Events এবং Asynchronous JavaScript

## বিস্তারিত Theory Note

DOM browser-এর document API। Event তিনটি পর্যায়ে ভাবা যায়: capture, target ও bubble। Event delegation bubbling ব্যবহার করে listener সংখ্যা কমায় এবং dynamically added child handle করতে পারে।

JavaScript concurrency model event loop-নির্ভর। Current call stack শেষ না হওয়া পর্যন্ত callback চলে না। Promise reaction microtask queue-তে এবং timer callback task queue-তে যায়; সাধারণত microtask আগে drain হয়।

## মূল ধারণার মানচিত্র

- **DOM:** HTML document-কে node tree ও programming interface হিসেবে প্রকাশ করে।
- **Event Bubbling:** Event target থেকে ancestor-এর দিকে propagation phase।
- **Event Capturing:** Root/ancestor থেকে target-এর দিকে event propagation phase।
- **Event Delegation:** Ancestor-এ listener বসিয়ে bubbling ব্যবহার করে বহু child-এর event handle করা।
- **Promise:** Asynchronous operation-এর pending, fulfilled বা rejected eventual result representation।
- **async/await:** Promise-based asynchronous flow-কে synchronous-looking syntax-এ লেখা।
- **Event Loop:** Call stack, task queue ও microtask queue coordinate করে asynchronous callback চালায়।
- **Microtask:** Promise reaction-এর মতো high-priority queued job যা current stack শেষ হলে task-এর আগে চলে।
- **DOM Query:** `querySelector` CSS selector অনুযায়ী প্রথম matching element দেয়।
- **preventDefault:** Event-এর browser default action cancel করে, propagation নয়।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: DOM, Events এবং Asynchronous JavaScript

## প্রশ্ন 561 | Topic: Web Technology > DOM and Async | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`HTML document-কে node tree ও programming interface হিসেবে প্রকাশ করে।`

A) Event Loop
B) Event Capturing
C) DOM
D) Event Bubbling

**সঠিক উত্তর: C) DOM**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** HTML document-কে node tree ও programming interface হিসেবে প্রকাশ করে।
- **A option কেন ভুল:** `Event Loop` বলতে Call stack, task queue ও microtask queue coordinate করে asynchronous callback চালায়। বোঝায়; প্রশ্নের বর্ণনা `DOM`-এর।
- **B option কেন ভুল:** `Event Capturing` বলতে Root/ancestor থেকে target-এর দিকে event propagation phase। বোঝায়; প্রশ্নের বর্ণনা `DOM`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Event Bubbling` বলতে Event target থেকে ancestor-এর দিকে propagation phase। বোঝায়; প্রশ্নের বর্ণনা `DOM`-এর।
- **Related Concept:** JavaScript node query ও পরিবর্তন করতে পারে।
- **মনে রাখার টিপস:** Document as object tree।

---

## প্রশ্ন 562 | Topic: Web Technology > DOM and Async | Difficulty: Medium | Type: Theory

Q. `Event Bubbling` সম্পর্কে কোন statement সঠিক?

A) `querySelector` CSS selector অনুযায়ী প্রথম matching element দেয়।
B) Promise reaction-এর মতো high-priority queued job যা current stack শেষ হলে task-এর আগে চলে।
C) HTML document-কে node tree ও programming interface হিসেবে প্রকাশ করে।
D) Event target থেকে ancestor-এর দিকে propagation phase।

**সঠিক উত্তর: D) Event target থেকে ancestor-এর দিকে propagation phase।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Event target থেকে ancestor-এর দিকে propagation phase।
- **A option কেন ভুল:** এই statementটি `DOM Query` ধারণাকে বর্ণনা করে; `Event Bubbling`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Microtask` ধারণাকে বর্ণনা করে; `Event Bubbling`-কে নয়।
- **C option কেন ভুল:** এই statementটি `DOM` ধারণাকে বর্ণনা করে; `Event Bubbling`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Delegation-এ ব্যবহৃত।
- **মনে রাখার টিপস:** Target থেকে উপরে।

---

## প্রশ্ন 563 | Topic: Web Technology > DOM and Async | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Root/ancestor থেকে target-এর দিকে event propagation phase।`—এখানে কোন concept প্রযোজ্য?

A) Event Capturing
B) preventDefault
C) Event Delegation
D) DOM

**সঠিক উত্তর: A) Event Capturing**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Root/ancestor থেকে target-এর দিকে event propagation phase।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `preventDefault` বলতে Event-এর browser default action cancel করে, propagation নয়। বোঝায়; প্রশ্নের বর্ণনা `Event Capturing`-এর।
- **C option কেন ভুল:** `Event Delegation` বলতে Ancestor-এ listener বসিয়ে bubbling ব্যবহার করে বহু child-এর event handle করা। বোঝায়; প্রশ্নের বর্ণনা `Event Capturing`-এর।
- **D option কেন ভুল:** `DOM` বলতে HTML document-কে node tree ও programming interface হিসেবে প্রকাশ করে। বোঝায়; প্রশ্নের বর্ণনা `Event Capturing`-এর।
- **Related Concept:** Listener capture option দিয়ে সক্রিয় করা যায়।
- **মনে রাখার টিপস:** উপরে থেকে target।

---

## প্রশ্ন 564 | Topic: Web Technology > DOM and Async | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Ancestor-এ listener বসিয়ে bubbling ব্যবহার করে বহু child-এর event handle করা।`

A) Event Bubbling
B) async/await
C) DOM Query
D) Event Delegation

**সঠিক উত্তর: D) Event Delegation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Ancestor-এ listener বসিয়ে bubbling ব্যবহার করে বহু child-এর event handle করা।
- **A option কেন ভুল:** `Event Bubbling` বলতে Event target থেকে ancestor-এর দিকে propagation phase। বোঝায়; প্রশ্নের বর্ণনা `Event Delegation`-এর।
- **B option কেন ভুল:** `async/await` বলতে Promise-based asynchronous flow-কে synchronous-looking syntax-এ লেখা। বোঝায়; প্রশ্নের বর্ণনা `Event Delegation`-এর।
- **C option কেন ভুল:** `DOM Query` বলতে `querySelector` CSS selector অনুযায়ী প্রথম matching element দেয়। বোঝায়; প্রশ্নের বর্ণনা `Event Delegation`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Dynamic child-এর জন্য কার্যকর।
- **মনে রাখার টিপস:** One parent listener, many children।

---

## প্রশ্ন 565 | Topic: Web Technology > DOM and Async | Difficulty: Medium | Type: Theory

Q. `Promise` সম্পর্কে কোন statement সঠিক?

A) Event-এর browser default action cancel করে, propagation নয়।
B) `querySelector` CSS selector অনুযায়ী প্রথম matching element দেয়।
C) Promise-based asynchronous flow-কে synchronous-looking syntax-এ লেখা।
D) Asynchronous operation-এর pending, fulfilled বা rejected eventual result representation।

**সঠিক উত্তর: D) Asynchronous operation-এর pending, fulfilled বা rejected eventual result representation।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Asynchronous operation-এর pending, fulfilled বা rejected eventual result representation।
- **A option কেন ভুল:** এই statementটি `preventDefault` ধারণাকে বর্ণনা করে; `Promise`-কে নয়।
- **B option কেন ভুল:** এই statementটি `DOM Query` ধারণাকে বর্ণনা করে; `Promise`-কে নয়।
- **C option কেন ভুল:** এই statementটি `async/await` ধারণাকে বর্ণনা করে; `Promise`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** then/catch/finally ব্যবহার করা যায়।
- **মনে রাখার টিপস:** Future value container।

---

## প্রশ্ন 566 | Topic: Web Technology > DOM and Async | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Promise-based asynchronous flow-কে synchronous-looking syntax-এ লেখা।`—এখানে কোন concept প্রযোজ্য?

A) Event Delegation
B) async/await
C) Event Capturing
D) preventDefault

**সঠিক উত্তর: B) async/await**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Promise-based asynchronous flow-কে synchronous-looking syntax-এ লেখা।
- **A option কেন ভুল:** `Event Delegation` বলতে Ancestor-এ listener বসিয়ে bubbling ব্যবহার করে বহু child-এর event handle করা। বোঝায়; প্রশ্নের বর্ণনা `async/await`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Event Capturing` বলতে Root/ancestor থেকে target-এর দিকে event propagation phase। বোঝায়; প্রশ্নের বর্ণনা `async/await`-এর।
- **D option কেন ভুল:** `preventDefault` বলতে Event-এর browser default action cancel করে, propagation নয়। বোঝায়; প্রশ্নের বর্ণনা `async/await`-এর।
- **Related Concept:** await async function pause করে, thread block নয়।
- **মনে রাখার টিপস:** Promise syntax সহজ করে।

---

## প্রশ্ন 567 | Topic: Web Technology > DOM and Async | Difficulty: Medium | Type: Code

Q. নিচের JavaScript code-এর output order কী?

```js
console.log('A');
Promise.resolve().then(()=>console.log('B'));
console.log('C');
```

A) A, C, B
B) A, B, C
C) B, A, C
D) C, A, B

**সঠিক উত্তর: A) A, C, B**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Synchronous A ও C আগে; Promise callback microtask হিসেবে current stack শেষ হওয়ার পরে চলে।

#### Step-by-step সমাধান

```text
1. console.log('A') -> A
2. Promise callback queued as microtask
3. console.log('C') -> C
4. Current stack empty
5. Microtask runs -> B
Output: A, C, B
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Microtask synchronous C-এর আগে চলে না।
- **C option কেন ভুল:** Promise callback immediate নয়।
- **D option কেন ভুল:** Source order-এর synchronous log উল্টো হয়েছে।
- **Related Concept:** Microtask queue current script শেষ হলে drain হয়।
- **মনে রাখার টিপস:** Sync first, then Promise microtask।

---

## প্রশ্ন 568 | Topic: Web Technology > DOM and Async | Difficulty: Hard | Type: Theory

Q. `Microtask` সম্পর্কে কোন statement সঠিক?

A) Event-এর browser default action cancel করে, propagation নয়।
B) Promise reaction-এর মতো high-priority queued job যা current stack শেষ হলে task-এর আগে চলে।
C) HTML document-কে node tree ও programming interface হিসেবে প্রকাশ করে।
D) Promise-based asynchronous flow-কে synchronous-looking syntax-এ লেখা।

**সঠিক উত্তর: B) Promise reaction-এর মতো high-priority queued job যা current stack শেষ হলে task-এর আগে চলে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Promise reaction-এর মতো high-priority queued job যা current stack শেষ হলে task-এর আগে চলে।
- **A option কেন ভুল:** এই statementটি `preventDefault` ধারণাকে বর্ণনা করে; `Microtask`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `DOM` ধারণাকে বর্ণনা করে; `Microtask`-কে নয়।
- **D option কেন ভুল:** এই statementটি `async/await` ধারণাকে বর্ণনা করে; `Microtask`-কে নয়।
- **Related Concept:** Infinite microtask UI starve করতে পারে।
- **মনে রাখার টিপস:** Promise callback queue।

---

## প্রশ্ন 569 | Topic: Web Technology > DOM and Async | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে ``querySelector` CSS selector অনুযায়ী প্রথম matching element দেয়।`—এখানে কোন concept প্রযোজ্য?

A) Event Bubbling
B) Event Capturing
C) DOM Query
D) preventDefault

**সঠিক উত্তর: C) DOM Query**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `querySelector` CSS selector অনুযায়ী প্রথম matching element দেয়।
- **A option কেন ভুল:** `Event Bubbling` বলতে Event target থেকে ancestor-এর দিকে propagation phase। বোঝায়; প্রশ্নের বর্ণনা `DOM Query`-এর।
- **B option কেন ভুল:** `Event Capturing` বলতে Root/ancestor থেকে target-এর দিকে event propagation phase। বোঝায়; প্রশ্নের বর্ণনা `DOM Query`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `preventDefault` বলতে Event-এর browser default action cancel করে, propagation নয়। বোঝায়; প্রশ্নের বর্ণনা `DOM Query`-এর।
- **Related Concept:** `querySelectorAll` static NodeList দেয়।
- **মনে রাখার টিপস:** CSS selector দিয়ে node খুঁজুন।

---

## প্রশ্ন 570 | Topic: Web Technology > DOM and Async | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Event-এর browser default action cancel করে, propagation নয়।`

A) DOM
B) Event Loop
C) Event Delegation
D) preventDefault

**সঠিক উত্তর: D) preventDefault**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Event-এর browser default action cancel করে, propagation নয়।
- **A option কেন ভুল:** `DOM` বলতে HTML document-কে node tree ও programming interface হিসেবে প্রকাশ করে। বোঝায়; প্রশ্নের বর্ণনা `preventDefault`-এর।
- **B option কেন ভুল:** `Event Loop` বলতে Call stack, task queue ও microtask queue coordinate করে asynchronous callback চালায়। বোঝায়; প্রশ্নের বর্ণনা `preventDefault`-এর।
- **C option কেন ভুল:** `Event Delegation` বলতে Ancestor-এ listener বসিয়ে bubbling ব্যবহার করে বহু child-এর event handle করা। বোঝায়; প্রশ্নের বর্ণনা `preventDefault`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `stopPropagation` propagation থামায়।
- **মনে রাখার টিপস:** Default action বনাম bubbling আলাদা।

---


# Chapter Theory 47: Client State, CORS এবং Real-time Communication

## বিস্তারিত Theory Note

HTTP stateless হলেও web application authentication ও personalization-এর জন্য state রাখে। Cookie request-এর সঙ্গে যায়; localStorage যায় না। Sensitive session identifier-এ `HttpOnly`, `Secure` ও উপযুক্ত `SameSite` attribute গুরুত্বপূর্ণ।

Same-Origin Policy cross-origin read সীমিত করে। CORS server-এর explicit permission প্রকাশ করে; এটি input validation বা user authorization-এর বিকল্প নয়। WebSocket two-way real-time channel, SSE server-to-client stream।

## মূল ধারণার মানচিত্র

- **Cookie:** Browser থেকে matching request-এ স্বয়ংক্রিয়ভাবে পাঠানো ছোট name-value state, attribute দ্বারা scope ও security নিয়ন্ত্রিত।
- **Session:** Server-side user state, client সাধারণত session identifier বহন করে।
- **localStorage:** Origin-scoped persistent key-value browser storage, request-এর সঙ্গে স্বয়ংক্রিয়ভাবে যায় না।
- **sessionStorage:** Origin ও browser tab/session-scoped storage, tab lifetime পর্যন্ত থাকে।
- **Same-Origin Policy:** এক origin-এর script-কে অন্য origin-এর sensitive resource access সীমিত করা browser security policy।
- **CORS:** Server response header দিয়ে নির্দিষ্ট cross-origin browser access অনুমতি দেওয়ার mechanism।
- **Cache:** Response পুনর্ব্যবহার করে latency ও bandwidth কমানোর storage mechanism।
- **CDN:** Geographically distributed edge server দিয়ে content user-এর কাছাকাছি serve করে।
- **WebSocket:** একটি persistent connection-এর ওপর bidirectional full-duplex communication protocol।
- **SSE:** HTTP-based server-to-client one-way event stream।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Client State, CORS এবং Real-time Communication

## প্রশ্ন 571 | Topic: Web Technology > Client-Server State | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Browser থেকে matching request-এ স্বয়ংক্রিয়ভাবে পাঠানো ছোট name-value state, attribute দ্বারা scope ও security নিয়ন্ত্রিত।`

A) Cookie
B) Cache
C) Same-Origin Policy
D) CORS

**সঠিক উত্তর: A) Cookie**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Browser থেকে matching request-এ স্বয়ংক্রিয়ভাবে পাঠানো ছোট name-value state, attribute দ্বারা scope ও security নিয়ন্ত্রিত।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Cache` বলতে Response পুনর্ব্যবহার করে latency ও bandwidth কমানোর storage mechanism। বোঝায়; প্রশ্নের বর্ণনা `Cookie`-এর।
- **C option কেন ভুল:** `Same-Origin Policy` বলতে এক origin-এর script-কে অন্য origin-এর sensitive resource access সীমিত করা browser security policy। বোঝায়; প্রশ্নের বর্ণনা `Cookie`-এর।
- **D option কেন ভুল:** `CORS` বলতে Server response header দিয়ে নির্দিষ্ট cross-origin browser access অনুমতি দেওয়ার mechanism। বোঝায়; প্রশ্নের বর্ণনা `Cookie`-এর।
- **Related Concept:** HttpOnly, Secure, SameSite গুরুত্বপূর্ণ।
- **মনে রাখার টিপস:** Request-এর সঙ্গে যায়।

---

## প্রশ্ন 572 | Topic: Web Technology > Client-Server State | Difficulty: Medium | Type: Theory

Q. `Session` সম্পর্কে কোন statement সঠিক?

A) Server-side user state, client সাধারণত session identifier বহন করে।
B) একটি persistent connection-এর ওপর bidirectional full-duplex communication protocol।
C) Origin-scoped persistent key-value browser storage, request-এর সঙ্গে স্বয়ংক্রিয়ভাবে যায় না।
D) Response পুনর্ব্যবহার করে latency ও bandwidth কমানোর storage mechanism।

**সঠিক উত্তর: A) Server-side user state, client সাধারণত session identifier বহন করে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Server-side user state, client সাধারণত session identifier বহন করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `WebSocket` ধারণাকে বর্ণনা করে; `Session`-কে নয়।
- **C option কেন ভুল:** এই statementটি `localStorage` ধারণাকে বর্ণনা করে; `Session`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Cache` ধারণাকে বর্ণনা করে; `Session`-কে নয়।
- **Related Concept:** Logout/expiry ও storage management দরকার।
- **মনে রাখার টিপস:** State server-এ, ID client-এ।

---

## প্রশ্ন 573 | Topic: Web Technology > Client-Server State | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Origin-scoped persistent key-value browser storage, request-এর সঙ্গে স্বয়ংক্রিয়ভাবে যায় না।`—এখানে কোন concept প্রযোজ্য?

A) localStorage
B) Cookie
C) Cache
D) SSE

**সঠিক উত্তর: A) localStorage**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Origin-scoped persistent key-value browser storage, request-এর সঙ্গে স্বয়ংক্রিয়ভাবে যায় না।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Cookie` বলতে Browser থেকে matching request-এ স্বয়ংক্রিয়ভাবে পাঠানো ছোট name-value state, attribute দ্বারা scope ও security নিয়ন্ত্রিত। বোঝায়; প্রশ্নের বর্ণনা `localStorage`-এর।
- **C option কেন ভুল:** `Cache` বলতে Response পুনর্ব্যবহার করে latency ও bandwidth কমানোর storage mechanism। বোঝায়; প্রশ্নের বর্ণনা `localStorage`-এর।
- **D option কেন ভুল:** `SSE` বলতে HTTP-based server-to-client one-way event stream। বোঝায়; প্রশ্নের বর্ণনা `localStorage`-এর।
- **Related Concept:** Synchronous API এবং JavaScript-readable।
- **মনে রাখার টিপস:** Persistent local key-value।

---

## প্রশ্ন 574 | Topic: Web Technology > Client-Server State | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Origin ও browser tab/session-scoped storage, tab lifetime পর্যন্ত থাকে।`

A) WebSocket
B) sessionStorage
C) Cache
D) Session

**সঠিক উত্তর: B) sessionStorage**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Origin ও browser tab/session-scoped storage, tab lifetime পর্যন্ত থাকে।
- **A option কেন ভুল:** `WebSocket` বলতে একটি persistent connection-এর ওপর bidirectional full-duplex communication protocol। বোঝায়; প্রশ্নের বর্ণনা `sessionStorage`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Cache` বলতে Response পুনর্ব্যবহার করে latency ও bandwidth কমানোর storage mechanism। বোঝায়; প্রশ্নের বর্ণনা `sessionStorage`-এর।
- **D option কেন ভুল:** `Session` বলতে Server-side user state, client সাধারণত session identifier বহন করে। বোঝায়; প্রশ্নের বর্ণনা `sessionStorage`-এর।
- **Related Concept:** Request-এর সঙ্গে যায় না।
- **মনে রাখার টিপস:** Per-tab temporary storage।

---

## প্রশ্ন 575 | Topic: Web Technology > Client-Server State | Difficulty: Medium | Type: Tracing

Q. Origin নির্ধারণে কোন তিনটি অংশ তুলনা করা হয়?

A) path, query, fragment
B) method, status, body
C) scheme, host, port
D) cookie, session, cache

**সঠিক উত্তর: C) scheme, host, port**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Same origin হতে scheme, hostname ও effective port একই হতে হয়।

#### Step-by-step সমাধান

```text
Origin tuple:
1. Scheme
2. Host
3. Port
All three must match.
```
- **A option কেন ভুল:** এগুলো URL অংশ হলেও origin identity নির্ধারণ করে না।
- **B option কেন ভুল:** HTTP message property।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** State/storage concept।
- **Related Concept:** https://a.com এবং http://a.com ভিন্ন origin।
- **মনে রাখার টিপস:** Origin = protocol + domain + port।

---

## প্রশ্ন 576 | Topic: Web Technology > Client-Server State | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Server response header দিয়ে নির্দিষ্ট cross-origin browser access অনুমতি দেওয়ার mechanism।`—এখানে কোন concept প্রযোজ্য?

A) Same-Origin Policy
B) Cookie
C) localStorage
D) CORS

**সঠিক উত্তর: D) CORS**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Server response header দিয়ে নির্দিষ্ট cross-origin browser access অনুমতি দেওয়ার mechanism।
- **A option কেন ভুল:** `Same-Origin Policy` বলতে এক origin-এর script-কে অন্য origin-এর sensitive resource access সীমিত করা browser security policy। বোঝায়; প্রশ্নের বর্ণনা `CORS`-এর।
- **B option কেন ভুল:** `Cookie` বলতে Browser থেকে matching request-এ স্বয়ংক্রিয়ভাবে পাঠানো ছোট name-value state, attribute দ্বারা scope ও security নিয়ন্ত্রিত। বোঝায়; প্রশ্নের বর্ণনা `CORS`-এর।
- **C option কেন ভুল:** `localStorage` বলতে Origin-scoped persistent key-value browser storage, request-এর সঙ্গে স্বয়ংক্রিয়ভাবে যায় না। বোঝায়; প্রশ্নের বর্ণনা `CORS`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Browser enforcement; authentication mechanism নয়।
- **মনে রাখার টিপস:** Server grants origin access।

---

## প্রশ্ন 577 | Topic: Web Technology > Client-Server State | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Response পুনর্ব্যবহার করে latency ও bandwidth কমানোর storage mechanism।`

A) Cache
B) SSE
C) CDN
D) localStorage

**সঠিক উত্তর: A) Cache**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Response পুনর্ব্যবহার করে latency ও bandwidth কমানোর storage mechanism।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `SSE` বলতে HTTP-based server-to-client one-way event stream। বোঝায়; প্রশ্নের বর্ণনা `Cache`-এর।
- **C option কেন ভুল:** `CDN` বলতে Geographically distributed edge server দিয়ে content user-এর কাছাকাছি serve করে। বোঝায়; প্রশ্নের বর্ণনা `Cache`-এর।
- **D option কেন ভুল:** `localStorage` বলতে Origin-scoped persistent key-value browser storage, request-এর সঙ্গে স্বয়ংক্রিয়ভাবে যায় না। বোঝায়; প্রশ্নের বর্ণনা `Cache`-এর।
- **Related Concept:** Cache-Control, ETag ও validation ব্যবহৃত।
- **মনে রাখার টিপস:** Reuse response safely।

---

## প্রশ্ন 578 | Topic: Web Technology > Client-Server State | Difficulty: Medium | Type: Theory

Q. `CDN` সম্পর্কে কোন statement সঠিক?

A) Server-side user state, client সাধারণত session identifier বহন করে।
B) Geographically distributed edge server দিয়ে content user-এর কাছাকাছি serve করে।
C) Browser থেকে matching request-এ স্বয়ংক্রিয়ভাবে পাঠানো ছোট name-value state, attribute দ্বারা scope ও security নিয়ন্ত্রিত।
D) Server response header দিয়ে নির্দিষ্ট cross-origin browser access অনুমতি দেওয়ার mechanism।

**সঠিক উত্তর: B) Geographically distributed edge server দিয়ে content user-এর কাছাকাছি serve করে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Geographically distributed edge server দিয়ে content user-এর কাছাকাছি serve করে।
- **A option কেন ভুল:** এই statementটি `Session` ধারণাকে বর্ণনা করে; `CDN`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `Cookie` ধারণাকে বর্ণনা করে; `CDN`-কে নয়।
- **D option কেন ভুল:** এই statementটি `CORS` ধারণাকে বর্ণনা করে; `CDN`-কে নয়।
- **Related Concept:** Latency ও origin load কমায়।
- **মনে রাখার টিপস:** Content near users।

---

## প্রশ্ন 579 | Topic: Web Technology > Client-Server State | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `একটি persistent connection-এর ওপর bidirectional full-duplex communication protocol।`—এখানে কোন concept প্রযোজ্য?

A) Session
B) WebSocket
C) SSE
D) localStorage

**সঠিক উত্তর: B) WebSocket**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একটি persistent connection-এর ওপর bidirectional full-duplex communication protocol।
- **A option কেন ভুল:** `Session` বলতে Server-side user state, client সাধারণত session identifier বহন করে। বোঝায়; প্রশ্নের বর্ণনা `WebSocket`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `SSE` বলতে HTTP-based server-to-client one-way event stream। বোঝায়; প্রশ্নের বর্ণনা `WebSocket`-এর।
- **D option কেন ভুল:** `localStorage` বলতে Origin-scoped persistent key-value browser storage, request-এর সঙ্গে স্বয়ংক্রিয়ভাবে যায় না। বোঝায়; প্রশ্নের বর্ণনা `WebSocket`-এর।
- **Related Concept:** Real-time chat ও live updates-এ উপযোগী।
- **মনে রাখার টিপস:** Both sides push।

---

## প্রশ্ন 580 | Topic: Web Technology > Client-Server State | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`HTTP-based server-to-client one-way event stream।`

A) SSE
B) Cookie
C) localStorage
D) Same-Origin Policy

**সঠিক উত্তর: A) SSE**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** HTTP-based server-to-client one-way event stream।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Cookie` বলতে Browser থেকে matching request-এ স্বয়ংক্রিয়ভাবে পাঠানো ছোট name-value state, attribute দ্বারা scope ও security নিয়ন্ত্রিত। বোঝায়; প্রশ্নের বর্ণনা `SSE`-এর।
- **C option কেন ভুল:** `localStorage` বলতে Origin-scoped persistent key-value browser storage, request-এর সঙ্গে স্বয়ংক্রিয়ভাবে যায় না। বোঝায়; প্রশ্নের বর্ণনা `SSE`-এর।
- **D option কেন ভুল:** `Same-Origin Policy` বলতে এক origin-এর script-কে অন্য origin-এর sensitive resource access সীমিত করা browser security policy। বোঝায়; প্রশ্নের বর্ণনা `SSE`-এর।
- **Related Concept:** Browser auto-reconnect support করতে পারে।
- **মনে রাখার টিপস:** Server pushes one direction।

---


# Chapter Theory 48: Web Security Fundamentals

## বিস্তারিত Theory Note

Web security-তে data-flow boundary চিনতে হয়। XSS browser execution context, SQL Injection database query context এবং command injection OS command context-এর সমস্যা। Context-specific encoding ও parameterization অত্যন্ত গুরুত্বপূর্ণ।

Authentication পরিচয়, authorization permission। Session token চুরি হলে identity impersonation সম্ভব, তাই TLS, secure cookie ও expiration দরকার। Defense-in-depth-এ CSP, least privilege, logging এবং secure headers যোগ হয়।

## মূল ধারণার মানচিত্র

- **XSS:** Untrusted content browser-এ executable script হিসেবে inject ও execute হওয়া vulnerability।
- **CSRF:** Authenticated browser-কে user-এর ইচ্ছা ছাড়া target site-এ state-changing request পাঠাতে বাধ্য করা attack।
- **SQL Injection:** Untrusted input SQL syntax-এর অংশ হয়ে query meaning পরিবর্তন করে।
- **Content Security Policy:** Allowed script, style, image ও অন্যান্য resource source policy header দিয়ে সীমিত করে।
- **Authentication:** User বা entity কে তা যাচাই করার process।
- **Authorization:** Authenticated identity কোন resource/action access করতে পারবে তা নির্ধারণ।
- **Hashing Password:** Password-কে saltসহ slow one-way password hash দিয়ে store করা।
- **TLS:** Transport communication-এর confidentiality, integrity ও peer authentication প্রদানকারী protocol suite।
- **Clickjacking:** অদৃশ্য/প্রচ্ছন্ন frame overlay দিয়ে user-কে অনিচ্ছাকৃত click করানো attack।
- **Least Privilege:** User/process-কে প্রয়োজনের সর্বনিম্ন permission দেওয়া security principle।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Web Security Fundamentals

## প্রশ্ন 581 | Topic: Web Technology > Web Security | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Untrusted content browser-এ executable script হিসেবে inject ও execute হওয়া vulnerability।`

A) CSRF
B) Least Privilege
C) XSS
D) Content Security Policy

**সঠিক উত্তর: C) XSS**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Untrusted content browser-এ executable script হিসেবে inject ও execute হওয়া vulnerability।
- **A option কেন ভুল:** `CSRF` বলতে Authenticated browser-কে user-এর ইচ্ছা ছাড়া target site-এ state-changing request পাঠাতে বাধ্য করা attack। বোঝায়; প্রশ্নের বর্ণনা `XSS`-এর।
- **B option কেন ভুল:** `Least Privilege` বলতে User/process-কে প্রয়োজনের সর্বনিম্ন permission দেওয়া security principle। বোঝায়; প্রশ্নের বর্ণনা `XSS`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Content Security Policy` বলতে Allowed script, style, image ও অন্যান্য resource source policy header দিয়ে সীমিত করে। বোঝায়; প্রশ্নের বর্ণনা `XSS`-এর।
- **Related Concept:** Output encoding ও CSP mitigation।
- **মনে রাখার টিপস:** Input becomes script।

---

## প্রশ্ন 582 | Topic: Web Technology > Web Security | Difficulty: Easy | Type: Theory

Q. `CSRF` সম্পর্কে কোন statement সঠিক?

A) Untrusted input SQL syntax-এর অংশ হয়ে query meaning পরিবর্তন করে।
B) Untrusted content browser-এ executable script হিসেবে inject ও execute হওয়া vulnerability।
C) Authenticated browser-কে user-এর ইচ্ছা ছাড়া target site-এ state-changing request পাঠাতে বাধ্য করা attack।
D) Authenticated identity কোন resource/action access করতে পারবে তা নির্ধারণ।

**সঠিক উত্তর: C) Authenticated browser-কে user-এর ইচ্ছা ছাড়া target site-এ state-changing request পাঠাতে বাধ্য করা attack।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Authenticated browser-কে user-এর ইচ্ছা ছাড়া target site-এ state-changing request পাঠাতে বাধ্য করা attack।
- **A option কেন ভুল:** এই statementটি `SQL Injection` ধারণাকে বর্ণনা করে; `CSRF`-কে নয়।
- **B option কেন ভুল:** এই statementটি `XSS` ধারণাকে বর্ণনা করে; `CSRF`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Authorization` ধারণাকে বর্ণনা করে; `CSRF`-কে নয়।
- **Related Concept:** CSRF token ও SameSite cookie mitigation।
- **মনে রাখার টিপস:** Victim browser sends trusted cookie।

---

## প্রশ্ন 583 | Topic: Web Technology > Web Security | Difficulty: Medium | Type: Code

Q. নিচের server-side query pattern-এর নিরাপদ বিকল্প কোনটি?

```text
"SELECT * FROM users WHERE name='" + input + "'"
```

A) Input string শুধু lowercase করা
B) Query browser-এ লুকানো
C) Error message বন্ধ করা
D) Parameterized query ব্যবহার

**সঠিক উত্তর: D) Parameterized query ব্যবহার**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Prepared/parameterized query SQL structure ও data আলাদা রাখে, ফলে input syntax query পরিবর্তন করতে পারে না।

#### Step-by-step সমাধান

```text
Unsafe: SQL text + input concatenation
Safe  : SELECT ... WHERE name = ?
Bind  : parameter value separately
```
- **A option কেন ভুল:** Attack payload lowercase-এও সম্ভব।
- **B option কেন ভুল:** Server query visibility attack প্রতিরোধ করে না।
- **C option কেন ভুল:** Information leakage কমায়, injection root cause নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Validation সহায়ক, কিন্তু SQL injection-এর primary defense parameter binding।
- **মনে রাখার টিপস:** SQL code ও user data আলাদা করুন।

---

## প্রশ্ন 584 | Topic: Web Technology > Web Security | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Allowed script, style, image ও অন্যান্য resource source policy header দিয়ে সীমিত করে।`

A) Content Security Policy
B) SQL Injection
C) XSS
D) Authorization

**সঠিক উত্তর: A) Content Security Policy**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Allowed script, style, image ও অন্যান্য resource source policy header দিয়ে সীমিত করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `SQL Injection` বলতে Untrusted input SQL syntax-এর অংশ হয়ে query meaning পরিবর্তন করে। বোঝায়; প্রশ্নের বর্ণনা `Content Security Policy`-এর।
- **C option কেন ভুল:** `XSS` বলতে Untrusted content browser-এ executable script হিসেবে inject ও execute হওয়া vulnerability। বোঝায়; প্রশ্নের বর্ণনা `Content Security Policy`-এর।
- **D option কেন ভুল:** `Authorization` বলতে Authenticated identity কোন resource/action access করতে পারবে তা নির্ধারণ। বোঝায়; প্রশ্নের বর্ণনা `Content Security Policy`-এর।
- **Related Concept:** XSS impact কমাতে defense-in-depth।
- **মনে রাখার টিপস:** Browser resource allowlist।

---

## প্রশ্ন 585 | Topic: Web Technology > Web Security | Difficulty: Medium | Type: Theory

Q. `Authentication` সম্পর্কে কোন statement সঠিক?

A) Untrusted content browser-এ executable script হিসেবে inject ও execute হওয়া vulnerability।
B) Password-কে saltসহ slow one-way password hash দিয়ে store করা।
C) User বা entity কে তা যাচাই করার process।
D) Allowed script, style, image ও অন্যান্য resource source policy header দিয়ে সীমিত করে।

**সঠিক উত্তর: C) User বা entity কে তা যাচাই করার process।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** User বা entity কে তা যাচাই করার process।
- **A option কেন ভুল:** এই statementটি `XSS` ধারণাকে বর্ণনা করে; `Authentication`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Hashing Password` ধারণাকে বর্ণনা করে; `Authentication`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Content Security Policy` ধারণাকে বর্ণনা করে; `Authentication`-কে নয়।
- **Related Concept:** Password, token, MFA ব্যবহার করা যায়।
- **মনে রাখার টিপস:** Who are you?

---

## প্রশ্ন 586 | Topic: Web Technology > Web Security | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Authenticated identity কোন resource/action access করতে পারবে তা নির্ধারণ।`—এখানে কোন concept প্রযোজ্য?

A) TLS
B) Authentication
C) Authorization
D) Clickjacking

**সঠিক উত্তর: C) Authorization**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Authenticated identity কোন resource/action access করতে পারবে তা নির্ধারণ।
- **A option কেন ভুল:** `TLS` বলতে Transport communication-এর confidentiality, integrity ও peer authentication প্রদানকারী protocol suite। বোঝায়; প্রশ্নের বর্ণনা `Authorization`-এর।
- **B option কেন ভুল:** `Authentication` বলতে User বা entity কে তা যাচাই করার process। বোঝায়; প্রশ্নের বর্ণনা `Authorization`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Clickjacking` বলতে অদৃশ্য/প্রচ্ছন্ন frame overlay দিয়ে user-কে অনিচ্ছাকৃত click করানো attack। বোঝায়; প্রশ্নের বর্ণনা `Authorization`-এর।
- **Related Concept:** Least privilege গুরুত্বপূর্ণ।
- **মনে রাখার টিপস:** What may you do?

---

## প্রশ্ন 587 | Topic: Web Technology > Web Security | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Password-কে saltসহ slow one-way password hash দিয়ে store করা।`

A) Authorization
B) Authentication
C) TLS
D) Hashing Password

**সঠিক উত্তর: D) Hashing Password**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Password-কে saltসহ slow one-way password hash দিয়ে store করা।
- **A option কেন ভুল:** `Authorization` বলতে Authenticated identity কোন resource/action access করতে পারবে তা নির্ধারণ। বোঝায়; প্রশ্নের বর্ণনা `Hashing Password`-এর।
- **B option কেন ভুল:** `Authentication` বলতে User বা entity কে তা যাচাই করার process। বোঝায়; প্রশ্নের বর্ণনা `Hashing Password`-এর।
- **C option কেন ভুল:** `TLS` বলতে Transport communication-এর confidentiality, integrity ও peer authentication প্রদানকারী protocol suite। বোঝায়; প্রশ্নের বর্ণনা `Hashing Password`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Argon2, bcrypt, scrypt উপযোগী।
- **মনে রাখার টিপস:** Password encrypt নয়; salted hash।

---

## প্রশ্ন 588 | Topic: Web Technology > Web Security | Difficulty: Hard | Type: Theory

Q. `TLS` সম্পর্কে কোন statement সঠিক?

A) Transport communication-এর confidentiality, integrity ও peer authentication প্রদানকারী protocol suite।
B) অদৃশ্য/প্রচ্ছন্ন frame overlay দিয়ে user-কে অনিচ্ছাকৃত click করানো attack।
C) Authenticated identity কোন resource/action access করতে পারবে তা নির্ধারণ।
D) Untrusted input SQL syntax-এর অংশ হয়ে query meaning পরিবর্তন করে।

**সঠিক উত্তর: A) Transport communication-এর confidentiality, integrity ও peer authentication প্রদানকারী protocol suite।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Transport communication-এর confidentiality, integrity ও peer authentication প্রদানকারী protocol suite।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Clickjacking` ধারণাকে বর্ণনা করে; `TLS`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Authorization` ধারণাকে বর্ণনা করে; `TLS`-কে নয়।
- **D option কেন ভুল:** এই statementটি `SQL Injection` ধারণাকে বর্ণনা করে; `TLS`-কে নয়।
- **Related Concept:** HTTPS-এর security layer।
- **মনে রাখার টিপস:** Secure channel।

---

## প্রশ্ন 589 | Topic: Web Technology > Web Security | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `অদৃশ্য/প্রচ্ছন্ন frame overlay দিয়ে user-কে অনিচ্ছাকৃত click করানো attack।`—এখানে কোন concept প্রযোজ্য?

A) Hashing Password
B) Authentication
C) Clickjacking
D) SQL Injection

**সঠিক উত্তর: C) Clickjacking**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** অদৃশ্য/প্রচ্ছন্ন frame overlay দিয়ে user-কে অনিচ্ছাকৃত click করানো attack।
- **A option কেন ভুল:** `Hashing Password` বলতে Password-কে saltসহ slow one-way password hash দিয়ে store করা। বোঝায়; প্রশ্নের বর্ণনা `Clickjacking`-এর।
- **B option কেন ভুল:** `Authentication` বলতে User বা entity কে তা যাচাই করার process। বোঝায়; প্রশ্নের বর্ণনা `Clickjacking`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `SQL Injection` বলতে Untrusted input SQL syntax-এর অংশ হয়ে query meaning পরিবর্তন করে। বোঝায়; প্রশ্নের বর্ণনা `Clickjacking`-এর।
- **Related Concept:** frame-ancestors বা X-Frame-Options mitigation।
- **মনে রাখার টিপস:** User clicks hidden target।

---

## প্রশ্ন 590 | Topic: Web Technology > Web Security | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`User/process-কে প্রয়োজনের সর্বনিম্ন permission দেওয়া security principle।`

A) Authorization
B) Hashing Password
C) Least Privilege
D) TLS

**সঠিক উত্তর: C) Least Privilege**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** User/process-কে প্রয়োজনের সর্বনিম্ন permission দেওয়া security principle।
- **A option কেন ভুল:** `Authorization` বলতে Authenticated identity কোন resource/action access করতে পারবে তা নির্ধারণ। বোঝায়; প্রশ্নের বর্ণনা `Least Privilege`-এর।
- **B option কেন ভুল:** `Hashing Password` বলতে Password-কে saltসহ slow one-way password hash দিয়ে store করা। বোঝায়; প্রশ্নের বর্ণনা `Least Privilege`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `TLS` বলতে Transport communication-এর confidentiality, integrity ও peer authentication প্রদানকারী protocol suite। বোঝায়; প্রশ্নের বর্ণনা `Least Privilege`-এর।
- **Related Concept:** Compromise impact সীমিত করে।
- **মনে রাখার টিপস:** Only necessary access।

---


# Chapter Theory 49: XML, JSON এবং Data Interchange

## বিস্তারিত Theory Note

XML document-centric ও extensible markup-এর জন্য শক্তিশালী; JSON compact application data exchange-এ জনপ্রিয়। XML-এ well-formed syntax এবং schema-valid structure আলাদা ধারণা।

Parser untrusted input handle করলে entity expansion, oversized payload ও type assumption সতর্কভাবে নিয়ন্ত্রণ করতে হয়। JSON-এ comment standard নয় এবং key double-quoted string হওয়া উচিত।

## মূল ধারণার মানচিত্র

- **XML:** Custom element ও attribute-ভিত্তিক hierarchical text data format।
- **JSON:** Object, array, string, number, boolean ও null-ভিত্তিক lightweight data interchange format।
- **Well-formed XML:** একটি root, proper nesting, matching tag ও quoted attributeসহ XML syntax rule মানা document।
- **Valid XML:** Well-formed হওয়ার পাশাপাশি DTD বা XML Schema-এর declared structure মানে।
- **DTD:** XML document-এর allowed element ও structure ঘোষণার পুরোনো schema language।
- **XML Schema:** XML namespace-aware typed schema language, element structure ও datatype constraint প্রকাশ করে।
- **XPath:** XML tree-এর node select ও navigate করার expression language।
- **Namespace:** URI-qualified name দিয়ে বিভিন্ন XML vocabulary-এর একই local name conflict এড়ায়।
- **Serialization:** In-memory data structure-কে transferable বা storable representation-এ রূপান্তর।
- **Parsing:** Serialized text থেকে syntax অনুযায়ী structured in-memory representation তৈরি।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: XML, JSON এবং Data Interchange

## প্রশ্ন 591 | Topic: Web Technology > XML and JSON | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Custom element ও attribute-ভিত্তিক hierarchical text data format।`

A) JSON
B) XML Schema
C) XML
D) DTD

**সঠিক উত্তর: C) XML**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Custom element ও attribute-ভিত্তিক hierarchical text data format।
- **A option কেন ভুল:** `JSON` বলতে Object, array, string, number, boolean ও null-ভিত্তিক lightweight data interchange format। বোঝায়; প্রশ্নের বর্ণনা `XML`-এর।
- **B option কেন ভুল:** `XML Schema` বলতে XML namespace-aware typed schema language, element structure ও datatype constraint প্রকাশ করে। বোঝায়; প্রশ্নের বর্ণনা `XML`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `DTD` বলতে XML document-এর allowed element ও structure ঘোষণার পুরোনো schema language। বোঝায়; প্রশ্নের বর্ণনা `XML`-এর।
- **Related Concept:** Well-formedness এবং optional schema validation আছে।
- **মনে রাখার টিপস:** Extensible markup data।

---

## প্রশ্ন 592 | Topic: Web Technology > XML and JSON | Difficulty: Hard | Type: Tracing

Q. JSON text `{"a":2,"b":[3,4]}`-এ array `b`-এর দ্বিতীয় element কত?

A) 2
B) 4
C) 3
D) b

**সঠিক উত্তর: B) 4**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** JSON array zero-based access করলে b[0]=3 এবং b[1]=4।

#### Step-by-step সমাধান

```text
Object:
a = 2
b = [3, 4]

b[0] = 3
b[1] = 4
Answer = 4
```
- **A option কেন ভুল:** এটি property a-এর value।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Array-এর প্রথম element।
- **D option কেন ভুল:** এটি property name, numeric element নয়।
- **Related Concept:** JSON object property value array হতে পারে।
- **মনে রাখার টিপস:** Array-এর দ্বিতীয় element index 1।

---

## প্রশ্ন 593 | Topic: Web Technology > XML and JSON | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `একটি root, proper nesting, matching tag ও quoted attributeসহ XML syntax rule মানা document।`—এখানে কোন concept প্রযোজ্য?

A) XML
B) Well-formed XML
C) XML Schema
D) XPath

**সঠিক উত্তর: B) Well-formed XML**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একটি root, proper nesting, matching tag ও quoted attributeসহ XML syntax rule মানা document।
- **A option কেন ভুল:** `XML` বলতে Custom element ও attribute-ভিত্তিক hierarchical text data format। বোঝায়; প্রশ্নের বর্ণনা `Well-formed XML`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `XML Schema` বলতে XML namespace-aware typed schema language, element structure ও datatype constraint প্রকাশ করে। বোঝায়; প্রশ্নের বর্ণনা `Well-formed XML`-এর।
- **D option কেন ভুল:** `XPath` বলতে XML tree-এর node select ও navigate করার expression language। বোঝায়; প্রশ্নের বর্ণনা `Well-formed XML`-এর।
- **Related Concept:** Valid হওয়া আলাদা বিষয়।
- **মনে রাখার টিপস:** Syntax ঠিক = well-formed।

---

## প্রশ্ন 594 | Topic: Web Technology > XML and JSON | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Well-formed হওয়ার পাশাপাশি DTD বা XML Schema-এর declared structure মানে।`

A) Valid XML
B) Well-formed XML
C) Parsing
D) DTD

**সঠিক উত্তর: A) Valid XML**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Well-formed হওয়ার পাশাপাশি DTD বা XML Schema-এর declared structure মানে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Well-formed XML` বলতে একটি root, proper nesting, matching tag ও quoted attributeসহ XML syntax rule মানা document। বোঝায়; প্রশ্নের বর্ণনা `Valid XML`-এর।
- **C option কেন ভুল:** `Parsing` বলতে Serialized text থেকে syntax অনুযায়ী structured in-memory representation তৈরি। বোঝায়; প্রশ্নের বর্ণনা `Valid XML`-এর।
- **D option কেন ভুল:** `DTD` বলতে XML document-এর allowed element ও structure ঘোষণার পুরোনো schema language। বোঝায়; প্রশ্নের বর্ণনা `Valid XML`-এর।
- **Related Concept:** Schema ছাড়া valid claim context-dependent।
- **মনে রাখার টিপস:** Syntax + schema।

---

## প্রশ্ন 595 | Topic: Web Technology > XML and JSON | Difficulty: Medium | Type: Theory

Q. `DTD` সম্পর্কে কোন statement সঠিক?

A) URI-qualified name দিয়ে বিভিন্ন XML vocabulary-এর একই local name conflict এড়ায়।
B) Well-formed হওয়ার পাশাপাশি DTD বা XML Schema-এর declared structure মানে।
C) In-memory data structure-কে transferable বা storable representation-এ রূপান্তর।
D) XML document-এর allowed element ও structure ঘোষণার পুরোনো schema language।

**সঠিক উত্তর: D) XML document-এর allowed element ও structure ঘোষণার পুরোনো schema language।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** XML document-এর allowed element ও structure ঘোষণার পুরোনো schema language।
- **A option কেন ভুল:** এই statementটি `Namespace` ধারণাকে বর্ণনা করে; `DTD`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Valid XML` ধারণাকে বর্ণনা করে; `DTD`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Serialization` ধারণাকে বর্ণনা করে; `DTD`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** XML Schema-এর type system বেশি সমৃদ্ধ।
- **মনে রাখার টিপস:** Document type rules।

---

## প্রশ্ন 596 | Topic: Web Technology > XML and JSON | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `XML namespace-aware typed schema language, element structure ও datatype constraint প্রকাশ করে।`—এখানে কোন concept প্রযোজ্য?

A) Parsing
B) XML Schema
C) XML
D) Serialization

**সঠিক উত্তর: B) XML Schema**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** XML namespace-aware typed schema language, element structure ও datatype constraint প্রকাশ করে।
- **A option কেন ভুল:** `Parsing` বলতে Serialized text থেকে syntax অনুযায়ী structured in-memory representation তৈরি। বোঝায়; প্রশ্নের বর্ণনা `XML Schema`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `XML` বলতে Custom element ও attribute-ভিত্তিক hierarchical text data format। বোঝায়; প্রশ্নের বর্ণনা `XML Schema`-এর।
- **D option কেন ভুল:** `Serialization` বলতে In-memory data structure-কে transferable বা storable representation-এ রূপান্তর। বোঝায়; প্রশ্নের বর্ণনা `XML Schema`-এর।
- **Related Concept:** XSD নামেও পরিচিত।
- **মনে রাখার টিপস:** Typed XML validation।

---

## প্রশ্ন 597 | Topic: Web Technology > XML and JSON | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`XML tree-এর node select ও navigate করার expression language।`

A) Well-formed XML
B) XPath
C) Parsing
D) Valid XML

**সঠিক উত্তর: B) XPath**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** XML tree-এর node select ও navigate করার expression language।
- **A option কেন ভুল:** `Well-formed XML` বলতে একটি root, proper nesting, matching tag ও quoted attributeসহ XML syntax rule মানা document। বোঝায়; প্রশ্নের বর্ণনা `XPath`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Parsing` বলতে Serialized text থেকে syntax অনুযায়ী structured in-memory representation তৈরি। বোঝায়; প্রশ্নের বর্ণনা `XPath`-এর।
- **D option কেন ভুল:** `Valid XML` বলতে Well-formed হওয়ার পাশাপাশি DTD বা XML Schema-এর declared structure মানে। বোঝায়; প্রশ্নের বর্ণনা `XPath`-এর।
- **Related Concept:** XSLT ও XML query-তে ব্যবহৃত।
- **মনে রাখার টিপস:** Path through XML tree।

---

## প্রশ্ন 598 | Topic: Web Technology > XML and JSON | Difficulty: Medium | Type: Theory

Q. `Namespace` সম্পর্কে কোন statement সঠিক?

A) URI-qualified name দিয়ে বিভিন্ন XML vocabulary-এর একই local name conflict এড়ায়।
B) XML document-এর allowed element ও structure ঘোষণার পুরোনো schema language।
C) In-memory data structure-কে transferable বা storable representation-এ রূপান্তর।
D) Object, array, string, number, boolean ও null-ভিত্তিক lightweight data interchange format।

**সঠিক উত্তর: A) URI-qualified name দিয়ে বিভিন্ন XML vocabulary-এর একই local name conflict এড়ায়।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** URI-qualified name দিয়ে বিভিন্ন XML vocabulary-এর একই local name conflict এড়ায়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `DTD` ধারণাকে বর্ণনা করে; `Namespace`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Serialization` ধারণাকে বর্ণনা করে; `Namespace`-কে নয়।
- **D option কেন ভুল:** এই statementটি `JSON` ধারণাকে বর্ণনা করে; `Namespace`-কে নয়।
- **Related Concept:** Prefix URI-এর alias।
- **মনে রাখার টিপস:** Name collision prevention।

---

## প্রশ্ন 599 | Topic: Web Technology > XML and JSON | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `In-memory data structure-কে transferable বা storable representation-এ রূপান্তর।`—এখানে কোন concept প্রযোজ্য?

A) Serialization
B) DTD
C) XPath
D) XML Schema

**সঠিক উত্তর: A) Serialization**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** In-memory data structure-কে transferable বা storable representation-এ রূপান্তর।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `DTD` বলতে XML document-এর allowed element ও structure ঘোষণার পুরোনো schema language। বোঝায়; প্রশ্নের বর্ণনা `Serialization`-এর।
- **C option কেন ভুল:** `XPath` বলতে XML tree-এর node select ও navigate করার expression language। বোঝায়; প্রশ্নের বর্ণনা `Serialization`-এর।
- **D option কেন ভুল:** `XML Schema` বলতে XML namespace-aware typed schema language, element structure ও datatype constraint প্রকাশ করে। বোঝায়; প্রশ্নের বর্ণনা `Serialization`-এর।
- **Related Concept:** JSON/XML encode এর উদাহরণ।
- **মনে রাখার টিপস:** Object to bytes/text।

---

## প্রশ্ন 600 | Topic: Web Technology > XML and JSON | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Serialized text থেকে syntax অনুযায়ী structured in-memory representation তৈরি।`

A) XPath
B) Parsing
C) Serialization
D) XML

**সঠিক উত্তর: B) Parsing**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Serialized text থেকে syntax অনুযায়ী structured in-memory representation তৈরি।
- **A option কেন ভুল:** `XPath` বলতে XML tree-এর node select ও navigate করার expression language। বোঝায়; প্রশ্নের বর্ণনা `Parsing`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Serialization` বলতে In-memory data structure-কে transferable বা storable representation-এ রূপান্তর। বোঝায়; প্রশ্নের বর্ণনা `Parsing`-এর।
- **D option কেন ভুল:** `XML` বলতে Custom element ও attribute-ভিত্তিক hierarchical text data format। বোঝায়; প্রশ্নের বর্ণনা `Parsing`-এর।
- **Related Concept:** Untrusted parser input security-sensitive।
- **মনে রাখার টিপস:** Text to structure।

---


# Chapter Theory 50: Server-side Development এবং MVC

## বিস্তারিত Theory Note

Server-side layer request validate করে, authentication/authorization প্রয়োগ করে, business logic চালায় এবং data store-এর সঙ্গে কাজ করে। Browser-side validation bypass করা যায়, তাই server সব untrusted input পুনরায় validate করে।

MVC responsibility separation করে; routing request destination নির্ধারণ করে এবং middleware shared policy প্রয়োগ করে। Secret ও environment-specific configuration source code-এ hard-code করা উচিত নয়।

## মূল ধারণার মানচিত্র

- **Server-side Scripting:** Request server-এ process করে database/business logic অনুযায়ী dynamic response তৈরি করা।
- **PHP:** Web-oriented server-side scripting language যা HTML-এর সঙ্গে integrate করতে পারে।
- **GET Parameter:** URL query string থেকে প্রাপ্ত request data।
- **POST Body:** Request body-তে পাঠানো form/API data।
- **Server Session:** User-specific state server-side storage-এ রাখা এবং session ID দিয়ে associate করা।
- **Template Engine:** Data ও presentation template combine করে HTML বা text response তৈরি করে।
- **MVC:** Model data/business rule, View presentation এবং Controller request coordination আলাদা করে।
- **Routing:** Request method ও path-কে নির্দিষ্ট handler/controller-এর সঙ্গে map করা।
- **Middleware:** Request-response pipeline-এ authentication, logging বা parsing-এর মতো cross-cutting কাজ করা component।
- **Environment Variable:** Deployment-specific configuration process environment থেকে নেওয়া value।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Server-side Development এবং MVC

# Batch 14 — Question 601–650

## প্রশ্ন 601 | Topic: Web Technology > Server-side Web | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Request server-এ process করে database/business logic অনুযায়ী dynamic response তৈরি করা।`

A) Routing
B) Server Session
C) Server-side Scripting
D) Middleware

**সঠিক উত্তর: C) Server-side Scripting**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Request server-এ process করে database/business logic অনুযায়ী dynamic response তৈরি করা।
- **A option কেন ভুল:** `Routing` বলতে Request method ও path-কে নির্দিষ্ট handler/controller-এর সঙ্গে map করা। বোঝায়; প্রশ্নের বর্ণনা `Server-side Scripting`-এর।
- **B option কেন ভুল:** `Server Session` বলতে User-specific state server-side storage-এ রাখা এবং session ID দিয়ে associate করা। বোঝায়; প্রশ্নের বর্ণনা `Server-side Scripting`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Middleware` বলতে Request-response pipeline-এ authentication, logging বা parsing-এর মতো cross-cutting কাজ করা component। বোঝায়; প্রশ্নের বর্ণনা `Server-side Scripting`-এর।
- **Related Concept:** PHP, Python, Java, Node.js ব্যবহার করা যায়।
- **মনে রাখার টিপস:** Code runs on server।

---

## প্রশ্ন 602 | Topic: Web Technology > Server-side Web | Difficulty: Medium | Type: Theory

Q. `PHP` সম্পর্কে কোন statement সঠিক?

A) Model data/business rule, View presentation এবং Controller request coordination আলাদা করে।
B) Request server-এ process করে database/business logic অনুযায়ী dynamic response তৈরি করা।
C) Web-oriented server-side scripting language যা HTML-এর সঙ্গে integrate করতে পারে।
D) Request-response pipeline-এ authentication, logging বা parsing-এর মতো cross-cutting কাজ করা component।

**সঠিক উত্তর: C) Web-oriented server-side scripting language যা HTML-এর সঙ্গে integrate করতে পারে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Web-oriented server-side scripting language যা HTML-এর সঙ্গে integrate করতে পারে।
- **A option কেন ভুল:** এই statementটি `MVC` ধারণাকে বর্ণনা করে; `PHP`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Server-side Scripting` ধারণাকে বর্ণনা করে; `PHP`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Middleware` ধারণাকে বর্ণনা করে; `PHP`-কে নয়।
- **Related Concept:** Request lifecycle-এ script execute হয়।
- **মনে রাখার টিপস:** PHP server generates output।

---

## প্রশ্ন 603 | Topic: Web Technology > Server-side Web | Difficulty: Hard | Type: Tracing

Q. URL `/search?q=database&page=2`-এ query parameter `page`-এর value কী?

A) search
B) q
C) 2
D) database

**সঠিক উত্তর: C) 2**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Query string-এ `page=2`, তাই page parameter-এর value 2।

#### Step-by-step সমাধান

```text
Path  = /search
Query = q=database&page=2
q     = database
page  = 2
```
- **A option কেন ভুল:** এটি path segment।
- **B option কেন ভুল:** এটি অন্য parameter-এর name।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এটি q parameter-এর value।
- **Related Concept:** Query parameter `&` দিয়ে আলাদা হয়।
- **মনে রাখার টিপস:** name=value pair খুঁজুন।

---

## প্রশ্ন 604 | Topic: Web Technology > Server-side Web | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Request body-তে পাঠানো form/API data।`

A) Server-side Scripting
B) POST Body
C) Middleware
D) Routing

**সঠিক উত্তর: B) POST Body**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Request body-তে পাঠানো form/API data।
- **A option কেন ভুল:** `Server-side Scripting` বলতে Request server-এ process করে database/business logic অনুযায়ী dynamic response তৈরি করা। বোঝায়; প্রশ্নের বর্ণনা `POST Body`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Middleware` বলতে Request-response pipeline-এ authentication, logging বা parsing-এর মতো cross-cutting কাজ করা component। বোঝায়; প্রশ্নের বর্ণনা `POST Body`-এর।
- **D option কেন ভুল:** `Routing` বলতে Request method ও path-কে নির্দিষ্ট handler/controller-এর সঙ্গে map করা। বোঝায়; প্রশ্নের বর্ণনা `POST Body`-এর।
- **Related Concept:** HTTPS ছাড়া encrypted নয়।
- **মনে রাখার টিপস:** Body data, not automatically secure।

---

## প্রশ্ন 605 | Topic: Web Technology > Server-side Web | Difficulty: Easy | Type: Theory

Q. `Server Session` সম্পর্কে কোন statement সঠিক?

A) Deployment-specific configuration process environment থেকে নেওয়া value।
B) User-specific state server-side storage-এ রাখা এবং session ID দিয়ে associate করা।
C) Request method ও path-কে নির্দিষ্ট handler/controller-এর সঙ্গে map করা।
D) Request-response pipeline-এ authentication, logging বা parsing-এর মতো cross-cutting কাজ করা component।

**সঠিক উত্তর: B) User-specific state server-side storage-এ রাখা এবং session ID দিয়ে associate করা।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** User-specific state server-side storage-এ রাখা এবং session ID দিয়ে associate করা।
- **A option কেন ভুল:** এই statementটি `Environment Variable` ধারণাকে বর্ণনা করে; `Server Session`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `Routing` ধারণাকে বর্ণনা করে; `Server Session`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Middleware` ধারণাকে বর্ণনা করে; `Server Session`-কে নয়।
- **Related Concept:** Session fixation ও hijacking প্রতিরোধ দরকার।
- **মনে রাখার টিপস:** State on server।

---

## প্রশ্ন 606 | Topic: Web Technology > Server-side Web | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `Data ও presentation template combine করে HTML বা text response তৈরি করে।`—এখানে কোন concept প্রযোজ্য?

A) GET Parameter
B) PHP
C) MVC
D) Template Engine

**সঠিক উত্তর: D) Template Engine**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Data ও presentation template combine করে HTML বা text response তৈরি করে।
- **A option কেন ভুল:** `GET Parameter` বলতে URL query string থেকে প্রাপ্ত request data। বোঝায়; প্রশ্নের বর্ণনা `Template Engine`-এর।
- **B option কেন ভুল:** `PHP` বলতে Web-oriented server-side scripting language যা HTML-এর সঙ্গে integrate করতে পারে। বোঝায়; প্রশ্নের বর্ণনা `Template Engine`-এর।
- **C option কেন ভুল:** `MVC` বলতে Model data/business rule, View presentation এবং Controller request coordination আলাদা করে। বোঝায়; প্রশ্নের বর্ণনা `Template Engine`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Auto-escaping XSS কমাতে পারে।
- **মনে রাখার টিপস:** Template + data = view।

---

## প্রশ্ন 607 | Topic: Web Technology > Server-side Web | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Model data/business rule, View presentation এবং Controller request coordination আলাদা করে।`

A) Environment Variable
B) Routing
C) MVC
D) Server Session

**সঠিক উত্তর: C) MVC**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Model data/business rule, View presentation এবং Controller request coordination আলাদা করে।
- **A option কেন ভুল:** `Environment Variable` বলতে Deployment-specific configuration process environment থেকে নেওয়া value। বোঝায়; প্রশ্নের বর্ণনা `MVC`-এর।
- **B option কেন ভুল:** `Routing` বলতে Request method ও path-কে নির্দিষ্ট handler/controller-এর সঙ্গে map করা। বোঝায়; প্রশ্নের বর্ণনা `MVC`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Server Session` বলতে User-specific state server-side storage-এ রাখা এবং session ID দিয়ে associate করা। বোঝায়; প্রশ্নের বর্ণনা `MVC`-এর।
- **Related Concept:** Separation of concerns উন্নত করে।
- **মনে রাখার টিপস:** M-V-C দায়িত্ব ভাগ।

---

## প্রশ্ন 608 | Topic: Web Technology > Server-side Web | Difficulty: Easy | Type: Theory

Q. `Routing` সম্পর্কে কোন statement সঠিক?

A) Request-response pipeline-এ authentication, logging বা parsing-এর মতো cross-cutting কাজ করা component।
B) Request method ও path-কে নির্দিষ্ট handler/controller-এর সঙ্গে map করা।
C) URL query string থেকে প্রাপ্ত request data।
D) Data ও presentation template combine করে HTML বা text response তৈরি করে।

**সঠিক উত্তর: B) Request method ও path-কে নির্দিষ্ট handler/controller-এর সঙ্গে map করা।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Request method ও path-কে নির্দিষ্ট handler/controller-এর সঙ্গে map করা।
- **A option কেন ভুল:** এই statementটি `Middleware` ধারণাকে বর্ণনা করে; `Routing`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `GET Parameter` ধারণাকে বর্ণনা করে; `Routing`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Template Engine` ধারণাকে বর্ণনা করে; `Routing`-কে নয়।
- **Related Concept:** REST endpoint dispatch-এর ভিত্তি।
- **মনে রাখার টিপস:** URL to handler।

---

## প্রশ্ন 609 | Topic: Web Technology > Server-side Web | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Request-response pipeline-এ authentication, logging বা parsing-এর মতো cross-cutting কাজ করা component।`—এখানে কোন concept প্রযোজ্য?

A) Server Session
B) Middleware
C) PHP
D) Server-side Scripting

**সঠিক উত্তর: B) Middleware**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Request-response pipeline-এ authentication, logging বা parsing-এর মতো cross-cutting কাজ করা component।
- **A option কেন ভুল:** `Server Session` বলতে User-specific state server-side storage-এ রাখা এবং session ID দিয়ে associate করা। বোঝায়; প্রশ্নের বর্ণনা `Middleware`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `PHP` বলতে Web-oriented server-side scripting language যা HTML-এর সঙ্গে integrate করতে পারে। বোঝায়; প্রশ্নের বর্ণনা `Middleware`-এর।
- **D option কেন ভুল:** `Server-side Scripting` বলতে Request server-এ process করে database/business logic অনুযায়ী dynamic response তৈরি করা। বোঝায়; প্রশ্নের বর্ণনা `Middleware`-এর।
- **Related Concept:** Order গুরুত্বপূর্ণ।
- **মনে রাখার টিপস:** Pipeline processing layer।

---

## প্রশ্ন 610 | Topic: Web Technology > Server-side Web | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Deployment-specific configuration process environment থেকে নেওয়া value।`

A) Middleware
B) PHP
C) Environment Variable
D) Server-side Scripting

**সঠিক উত্তর: C) Environment Variable**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Deployment-specific configuration process environment থেকে নেওয়া value।
- **A option কেন ভুল:** `Middleware` বলতে Request-response pipeline-এ authentication, logging বা parsing-এর মতো cross-cutting কাজ করা component। বোঝায়; প্রশ্নের বর্ণনা `Environment Variable`-এর।
- **B option কেন ভুল:** `PHP` বলতে Web-oriented server-side scripting language যা HTML-এর সঙ্গে integrate করতে পারে। বোঝায়; প্রশ্নের বর্ণনা `Environment Variable`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Server-side Scripting` বলতে Request server-এ process করে database/business logic অনুযায়ী dynamic response তৈরি করা। বোঝায়; প্রশ্নের বর্ণনা `Environment Variable`-এর।
- **Related Concept:** Secret handling-এ source control এড়াতে সহায়ক, কিন্তু secure management দরকার।
- **মনে রাখার টিপস:** Config outside code।

---


# Chapter Theory 51: REST API, Deployment এবং Scaling

## বিস্তারিত Theory Note

REST resource representation ও uniform HTTP semantics ব্যবহার করে। Method-এর safety ও idempotence retry, caching ও client behavior নির্ধারণে গুরুত্বপূর্ণ। Status code ও error body consistent হলে API client robust হয়।

Deployment layer-এ reverse proxy TLS termination, caching ও routing করতে পারে; load balancer healthy backend-এ traffic ভাগ করে। Horizontal scaling-এর জন্য stateless application instance ও shared/external state store সহায়ক।

## মূল ধারণার মানচিত্র

- **REST:** Resource-oriented architectural style যা uniform interface, stateless communication ও cacheability-এর মতো constraint অনুসরণ করে।
- **GET Method:** Resource representation retrieve করার safe ও idempotent HTTP method।
- **POST Method:** Server-কে representation process বা subordinate resource create করতে পাঠানো non-idempotent হতে পারে এমন method।
- **PUT Method:** Target resource-কে supplied representation দিয়ে create/replace করার idempotent method।
- **DELETE Method:** Target resource remove করার idempotent semantics-যুক্ত HTTP method।
- **Idempotence:** একই request একবার বা বহুবার করলে intended server state effect একই থাকা property।
- **API Versioning:** Breaking interface change আলাদা version contract দিয়ে manage করা।
- **Rate Limiting:** নির্দিষ্ট সময় window-তে client request সংখ্যা সীমিত করা।
- **Reverse Proxy:** Client request গ্রহণ করে upstream server-এ forward, TLS termination, caching বা load balancing করতে পারে।
- **Load Balancer:** Incoming request একাধিক backend instance-এ distribute করে availability ও scale বাড়ায়।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: REST API, Deployment এবং Scaling

## প্রশ্ন 611 | Topic: Web Technology > Web API and Hosting | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Resource-oriented architectural style যা uniform interface, stateless communication ও cacheability-এর মতো constraint অনুসরণ করে।`

A) POST Method
B) Load Balancer
C) REST
D) PUT Method

**সঠিক উত্তর: C) REST**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Resource-oriented architectural style যা uniform interface, stateless communication ও cacheability-এর মতো constraint অনুসরণ করে।
- **A option কেন ভুল:** `POST Method` বলতে Server-কে representation process বা subordinate resource create করতে পাঠানো non-idempotent হতে পারে এমন method। বোঝায়; প্রশ্নের বর্ণনা `REST`-এর।
- **B option কেন ভুল:** `Load Balancer` বলতে Incoming request একাধিক backend instance-এ distribute করে availability ও scale বাড়ায়। বোঝায়; প্রশ্নের বর্ণনা `REST`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `PUT Method` বলতে Target resource-কে supplied representation দিয়ে create/replace করার idempotent method। বোঝায়; প্রশ্নের বর্ণনা `REST`-এর।
- **Related Concept:** HTTP ব্যবহার প্রচলিত, কিন্তু REST শুধু URL naming নয়।
- **মনে রাখার টিপস:** Resource + representation।

---

## প্রশ্ন 612 | Topic: Web Technology > Web API and Hosting | Difficulty: Hard | Type: Theory

Q. `GET Method` সম্পর্কে কোন statement সঠিক?

A) Resource representation retrieve করার safe ও idempotent HTTP method।
B) Breaking interface change আলাদা version contract দিয়ে manage করা।
C) একই request একবার বা বহুবার করলে intended server state effect একই থাকা property।
D) Client request গ্রহণ করে upstream server-এ forward, TLS termination, caching বা load balancing করতে পারে।

**সঠিক উত্তর: A) Resource representation retrieve করার safe ও idempotent HTTP method।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Resource representation retrieve করার safe ও idempotent HTTP method।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `API Versioning` ধারণাকে বর্ণনা করে; `GET Method`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Idempotence` ধারণাকে বর্ণনা করে; `GET Method`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Reverse Proxy` ধারণাকে বর্ণনা করে; `GET Method`-কে নয়।
- **Related Concept:** State change উদ্দেশ্য নয়।
- **মনে রাখার টিপস:** Read operation।

---

## প্রশ্ন 613 | Topic: Web Technology > Web API and Hosting | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Server-কে representation process বা subordinate resource create করতে পাঠানো non-idempotent হতে পারে এমন method।`—এখানে কোন concept প্রযোজ্য?

A) DELETE Method
B) POST Method
C) Idempotence
D) Rate Limiting

**সঠিক উত্তর: B) POST Method**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Server-কে representation process বা subordinate resource create করতে পাঠানো non-idempotent হতে পারে এমন method।
- **A option কেন ভুল:** `DELETE Method` বলতে Target resource remove করার idempotent semantics-যুক্ত HTTP method। বোঝায়; প্রশ্নের বর্ণনা `POST Method`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Idempotence` বলতে একই request একবার বা বহুবার করলে intended server state effect একই থাকা property। বোঝায়; প্রশ্নের বর্ণনা `POST Method`-এর।
- **D option কেন ভুল:** `Rate Limiting` বলতে নির্দিষ্ট সময় window-তে client request সংখ্যা সীমিত করা। বোঝায়; প্রশ্নের বর্ণনা `POST Method`-এর।
- **Related Concept:** Repeat করলে duplicate effect হতে পারে।
- **মনে রাখার টিপস:** Submit/create processing।

---

## প্রশ্ন 614 | Topic: Web Technology > Web API and Hosting | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Target resource-কে supplied representation দিয়ে create/replace করার idempotent method।`

A) REST
B) Idempotence
C) POST Method
D) PUT Method

**সঠিক উত্তর: D) PUT Method**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Target resource-কে supplied representation দিয়ে create/replace করার idempotent method।
- **A option কেন ভুল:** `REST` বলতে Resource-oriented architectural style যা uniform interface, stateless communication ও cacheability-এর মতো constraint অনুসরণ করে। বোঝায়; প্রশ্নের বর্ণনা `PUT Method`-এর।
- **B option কেন ভুল:** `Idempotence` বলতে একই request একবার বা বহুবার করলে intended server state effect একই থাকা property। বোঝায়; প্রশ্নের বর্ণনা `PUT Method`-এর।
- **C option কেন ভুল:** `POST Method` বলতে Server-কে representation process বা subordinate resource create করতে পাঠানো non-idempotent হতে পারে এমন method। বোঝায়; প্রশ্নের বর্ণনা `PUT Method`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Repeated identical request same intended state।
- **মনে রাখার টিপস:** Replace at known URI।

---

## প্রশ্ন 615 | Topic: Web Technology > Web API and Hosting | Difficulty: Medium | Type: Theory

Q. `DELETE Method` সম্পর্কে কোন statement সঠিক?

A) Incoming request একাধিক backend instance-এ distribute করে availability ও scale বাড়ায়।
B) Target resource remove করার idempotent semantics-যুক্ত HTTP method।
C) একই request একবার বা বহুবার করলে intended server state effect একই থাকা property।
D) Server-কে representation process বা subordinate resource create করতে পাঠানো non-idempotent হতে পারে এমন method।

**সঠিক উত্তর: B) Target resource remove করার idempotent semantics-যুক্ত HTTP method।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Target resource remove করার idempotent semantics-যুক্ত HTTP method।
- **A option কেন ভুল:** এই statementটি `Load Balancer` ধারণাকে বর্ণনা করে; `DELETE Method`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `Idempotence` ধারণাকে বর্ণনা করে; `DELETE Method`-কে নয়।
- **D option কেন ভুল:** এই statementটি `POST Method` ধারণাকে বর্ণনা করে; `DELETE Method`-কে নয়।
- **Related Concept:** Repeated response code ভিন্ন হতে পারে, intended state same।
- **মনে রাখার টিপস:** Remove resource।

---

## প্রশ্ন 616 | Topic: Web Technology > Web API and Hosting | Difficulty: Medium | Type: Tracing

Q. একই `PUT /users/7` request একই bodyসহ তিনবার পাঠালে idempotent semantics অনুযায়ী intended final resource state কী হবে?

A) তিনটি আলাদা user তৈরি হবে
B) প্রথম request-এর পরের একই state থাকবে
C) Resource বাধ্যতামূলক delete হবে
D) প্রতি request-এ random state

**সঠিক উত্তর: B) প্রথম request-এর পরের একই state থাকবে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** PUT-এর intended effect repeated identical execution-এ একই target representation।

#### Step-by-step সমাধান

```text
Request 1 -> resource 7 becomes representation X
Request 2 -> resource 7 remains X
Request 3 -> resource 7 remains X
Final intended state = X
```
- **A option কেন ভুল:** Known target URI replacement; POST create behavior-এর সঙ্গে গুলিয়েছে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** DELETE semantics নয়।
- **D option কেন ভুল:** Idempotence deterministic intended state চায়।
- **Related Concept:** Network retry-এর জন্য idempotent method গুরুত্বপূর্ণ।
- **মনে রাখার টিপস:** Repeat করলে state multiply না হলে idempotent।

---

## প্রশ্ন 617 | Topic: Web Technology > Web API and Hosting | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Breaking interface change আলাদা version contract দিয়ে manage করা।`

A) PUT Method
B) API Versioning
C) Idempotence
D) POST Method

**সঠিক উত্তর: B) API Versioning**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Breaking interface change আলাদা version contract দিয়ে manage করা।
- **A option কেন ভুল:** `PUT Method` বলতে Target resource-কে supplied representation দিয়ে create/replace করার idempotent method। বোঝায়; প্রশ্নের বর্ণনা `API Versioning`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Idempotence` বলতে একই request একবার বা বহুবার করলে intended server state effect একই থাকা property। বোঝায়; প্রশ্নের বর্ণনা `API Versioning`-এর।
- **D option কেন ভুল:** `POST Method` বলতে Server-কে representation process বা subordinate resource create করতে পাঠানো non-idempotent হতে পারে এমন method। বোঝায়; প্রশ্নের বর্ণনা `API Versioning`-এর।
- **Related Concept:** URL, header বা media type strategy হতে পারে।
- **মনে রাখার টিপস:** Clients need stable contract।

---

## প্রশ্ন 618 | Topic: Web Technology > Web API and Hosting | Difficulty: Hard | Type: Theory

Q. `Rate Limiting` সম্পর্কে কোন statement সঠিক?

A) Target resource-কে supplied representation দিয়ে create/replace করার idempotent method।
B) Resource-oriented architectural style যা uniform interface, stateless communication ও cacheability-এর মতো constraint অনুসরণ করে।
C) নির্দিষ্ট সময় window-তে client request সংখ্যা সীমিত করা।
D) Server-কে representation process বা subordinate resource create করতে পাঠানো non-idempotent হতে পারে এমন method।

**সঠিক উত্তর: C) নির্দিষ্ট সময় window-তে client request সংখ্যা সীমিত করা।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** নির্দিষ্ট সময় window-তে client request সংখ্যা সীমিত করা।
- **A option কেন ভুল:** এই statementটি `PUT Method` ধারণাকে বর্ণনা করে; `Rate Limiting`-কে নয়।
- **B option কেন ভুল:** এই statementটি `REST` ধারণাকে বর্ণনা করে; `Rate Limiting`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `POST Method` ধারণাকে বর্ণনা করে; `Rate Limiting`-কে নয়।
- **Related Concept:** Abuse ও resource exhaustion কমায়।
- **মনে রাখার টিপস:** Requests per time সীমা।

---

## প্রশ্ন 619 | Topic: Web Technology > Web API and Hosting | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Client request গ্রহণ করে upstream server-এ forward, TLS termination, caching বা load balancing করতে পারে।`—এখানে কোন concept প্রযোজ্য?

A) Rate Limiting
B) API Versioning
C) Load Balancer
D) Reverse Proxy

**সঠিক উত্তর: D) Reverse Proxy**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Client request গ্রহণ করে upstream server-এ forward, TLS termination, caching বা load balancing করতে পারে।
- **A option কেন ভুল:** `Rate Limiting` বলতে নির্দিষ্ট সময় window-তে client request সংখ্যা সীমিত করা। বোঝায়; প্রশ্নের বর্ণনা `Reverse Proxy`-এর।
- **B option কেন ভুল:** `API Versioning` বলতে Breaking interface change আলাদা version contract দিয়ে manage করা। বোঝায়; প্রশ্নের বর্ণনা `Reverse Proxy`-এর।
- **C option কেন ভুল:** `Load Balancer` বলতে Incoming request একাধিক backend instance-এ distribute করে availability ও scale বাড়ায়। বোঝায়; প্রশ্নের বর্ণনা `Reverse Proxy`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Nginx প্রচলিত।
- **মনে রাখার টিপস:** Front door to backends।

---

## প্রশ্ন 620 | Topic: Web Technology > Web API and Hosting | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Incoming request একাধিক backend instance-এ distribute করে availability ও scale বাড়ায়।`

A) Rate Limiting
B) REST
C) Load Balancer
D) DELETE Method

**সঠিক উত্তর: C) Load Balancer**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Incoming request একাধিক backend instance-এ distribute করে availability ও scale বাড়ায়।
- **A option কেন ভুল:** `Rate Limiting` বলতে নির্দিষ্ট সময় window-তে client request সংখ্যা সীমিত করা। বোঝায়; প্রশ্নের বর্ণনা `Load Balancer`-এর।
- **B option কেন ভুল:** `REST` বলতে Resource-oriented architectural style যা uniform interface, stateless communication ও cacheability-এর মতো constraint অনুসরণ করে। বোঝায়; প্রশ্নের বর্ণনা `Load Balancer`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `DELETE Method` বলতে Target resource remove করার idempotent semantics-যুক্ত HTTP method। বোঝায়; প্রশ্নের বর্ণনা `Load Balancer`-এর।
- **Related Concept:** Health check ও algorithm ব্যবহার করে।
- **মনে রাখার টিপস:** Traffic distribution।

---

# Chapter Theory 52: Operating System Fundamentals

## বিস্তারিত Theory Note

Operating System application ও hardware-এর মধ্যে controlled layer। CPU, memory, storage, I/O device ও protection domain manage করে। Privilege separation user error বা malicious code-কে সরাসরি hardware control থেকে আটকায়।

System call synchronous request; hardware interrupt সাধারণত asynchronous event। Trap, exception ও interrupt terminology architecture অনুযায়ী সূক্ষ্মভাবে ভিন্ন হতে পারে।

## মূল ধারণার মানচিত্র

- **Operating System:** Hardware resource manage করে এবং application/user-এর জন্য service ও abstraction প্রদানকারী system software।
- **Kernel:** Privileged core যা process, memory, device ও interrupt management করে।
- **System Call:** User program-এর controlled request যা kernel service গ্রহণ করে।
- **User Mode:** Restricted execution mode যেখানে privileged instruction চালানো যায় না।
- **Kernel Mode:** Privileged mode যেখানে hardware ও protected resource access করা যায়।
- **Interrupt:** Hardware বা software event যা CPU-কে current flow suspend করে handler চালাতে বলে।
- **Batch OS:** Job interaction ছাড়া batch-এ collect ও execute করে throughput বাড়ানোর model।
- **Time-sharing OS:** CPU time slice দিয়ে বহু interactive user/process-কে responsive service দেয়।
- **Multiprogramming:** Memory-তে একাধিক job রেখে একটি I/O wait করলে অন্যটি CPU পায়।
- **Real-time OS:** Deadline ও predictable response constraint পূরণে deterministic scheduling ও latency control করে।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Operating System Fundamentals

## প্রশ্ন 621 | Topic: Operating System > OS Basics | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Hardware resource manage করে এবং application/user-এর জন্য service ও abstraction প্রদানকারী system software।`

A) Operating System
B) Time-sharing OS
C) Kernel Mode
D) User Mode

**সঠিক উত্তর: A) Operating System**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Hardware resource manage করে এবং application/user-এর জন্য service ও abstraction প্রদানকারী system software।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Time-sharing OS` বলতে CPU time slice দিয়ে বহু interactive user/process-কে responsive service দেয়। বোঝায়; প্রশ্নের বর্ণনা `Operating System`-এর।
- **C option কেন ভুল:** `Kernel Mode` বলতে Privileged mode যেখানে hardware ও protected resource access করা যায়। বোঝায়; প্রশ্নের বর্ণনা `Operating System`-এর।
- **D option কেন ভুল:** `User Mode` বলতে Restricted execution mode যেখানে privileged instruction চালানো যায় না। বোঝায়; প্রশ্নের বর্ণনা `Operating System`-এর।
- **Related Concept:** Kernel, system call ও resource management এর অংশ।
- **মনে রাখার টিপস:** OS হলো resource manager ও abstraction provider।

---

## প্রশ্ন 622 | Topic: Operating System > OS Basics | Difficulty: Easy | Type: Theory

Q. `Kernel` সম্পর্কে কোন statement সঠিক?

A) Hardware বা software event যা CPU-কে current flow suspend করে handler চালাতে বলে।
B) User program-এর controlled request যা kernel service গ্রহণ করে।
C) Privileged mode যেখানে hardware ও protected resource access করা যায়।
D) Privileged core যা process, memory, device ও interrupt management করে।

**সঠিক উত্তর: D) Privileged core যা process, memory, device ও interrupt management করে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Privileged core যা process, memory, device ও interrupt management করে।
- **A option কেন ভুল:** এই statementটি `Interrupt` ধারণাকে বর্ণনা করে; `Kernel`-কে নয়।
- **B option কেন ভুল:** এই statementটি `System Call` ধারণাকে বর্ণনা করে; `Kernel`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Kernel Mode` ধারণাকে বর্ণনা করে; `Kernel`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Monolithic, microkernel ও hybrid design আছে।
- **মনে রাখার টিপস:** Kernel runs with high privilege।

---

## প্রশ্ন 623 | Topic: Operating System > OS Basics | Difficulty: Hard | Type: Tracing

Q. User program file পড়তে kernel service চাইলে সাধারণ flow কোনটি?

A) System call/trap → kernel handler → return
B) Directly privileged disk instruction
C) Browser redirect
D) Compiler macro only

**সঠিক উত্তর: A) System call/trap → kernel handler → return**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** User mode থেকে controlled trap system call handler-এ যায়; kernel operation শেষে resultসহ user mode-এ ফেরে।

#### Step-by-step সমাধান

```text
1. User code invokes read()
2. Wrapper places syscall number/arguments
3. Trap enters kernel mode
4. Kernel validates and performs service
5. Return value supplied
6. CPU returns to user mode
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** User mode privileged device instruction চালাতে পারে না।
- **C option কেন ভুল:** Web navigation OS service transition নয়।
- **D option কেন ভুল:** Macro kernel privilege অর্জন করে না।
- **Related Concept:** Mode switch ও context switch এক নয়; system call-এ process একই থাকতে পারে।
- **মনে রাখার টিপস:** Trap দিয়ে kernel-এ, return দিয়ে user mode।

---

## প্রশ্ন 624 | Topic: Operating System > OS Basics | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Restricted execution mode যেখানে privileged instruction চালানো যায় না।`

A) User Mode
B) Kernel Mode
C) Kernel
D) Multiprogramming

**সঠিক উত্তর: A) User Mode**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Restricted execution mode যেখানে privileged instruction চালানো যায় না।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Kernel Mode` বলতে Privileged mode যেখানে hardware ও protected resource access করা যায়। বোঝায়; প্রশ্নের বর্ণনা `User Mode`-এর।
- **C option কেন ভুল:** `Kernel` বলতে Privileged core যা process, memory, device ও interrupt management করে। বোঝায়; প্রশ্নের বর্ণনা `User Mode`-এর।
- **D option কেন ভুল:** `Multiprogramming` বলতে Memory-তে একাধিক job রেখে একটি I/O wait করলে অন্যটি CPU পায়। বোঝায়; প্রশ্নের বর্ণনা `User Mode`-এর।
- **Related Concept:** System call/trap kernel mode-এ transition ঘটায়।
- **মনে রাখার টিপস:** Application restricted mode।

---

## প্রশ্ন 625 | Topic: Operating System > OS Basics | Difficulty: Medium | Type: Theory

Q. `Kernel Mode` সম্পর্কে কোন statement সঠিক?

A) Memory-তে একাধিক job রেখে একটি I/O wait করলে অন্যটি CPU পায়।
B) CPU time slice দিয়ে বহু interactive user/process-কে responsive service দেয়।
C) Privileged core যা process, memory, device ও interrupt management করে।
D) Privileged mode যেখানে hardware ও protected resource access করা যায়।

**সঠিক উত্তর: D) Privileged mode যেখানে hardware ও protected resource access করা যায়।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Privileged mode যেখানে hardware ও protected resource access করা যায়।
- **A option কেন ভুল:** এই statementটি `Multiprogramming` ধারণাকে বর্ণনা করে; `Kernel Mode`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Time-sharing OS` ধারণাকে বর্ণনা করে; `Kernel Mode`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Kernel` ধারণাকে বর্ণনা করে; `Kernel Mode`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Bug পুরো system crash করতে পারে।
- **মনে রাখার টিপস:** Full privilege।

---

## প্রশ্ন 626 | Topic: Operating System > OS Basics | Difficulty: Medium | Type: Calculation

Q. Timer প্রতি 10 ms-এ interrupt দেয়। 100 ms সময়ে সর্বোচ্চ কতটি periodic timer interrupt হবে?

A) 5
B) 20
C) 100
D) 10

**সঠিক উত্তর: D) 10**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 100/10 = 10 interval।

#### Step-by-step সমাধান

```text
Total time = 100 ms
Period     = 10 ms
Interrupts = 100 / 10
           = 10
```
- **A option কেন ভুল:** 20 ms interval ধরে নেওয়া হয়েছে।
- **B option কেন ভুল:** 5 ms interval ধরা হয়েছে।
- **C option কেন ভুল:** Millisecond count-কে interrupt count ধরা হয়েছে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Timer interrupt preemptive scheduling trigger করতে পারে।
- **মনে রাখার টিপস:** Total time ÷ period।

---

## প্রশ্ন 627 | Topic: Operating System > OS Basics | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Job interaction ছাড়া batch-এ collect ও execute করে throughput বাড়ানোর model।`

A) System Call
B) Batch OS
C) Operating System
D) Time-sharing OS

**সঠিক উত্তর: B) Batch OS**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Job interaction ছাড়া batch-এ collect ও execute করে throughput বাড়ানোর model।
- **A option কেন ভুল:** `System Call` বলতে User program-এর controlled request যা kernel service গ্রহণ করে। বোঝায়; প্রশ্নের বর্ণনা `Batch OS`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Operating System` বলতে Hardware resource manage করে এবং application/user-এর জন্য service ও abstraction প্রদানকারী system software। বোঝায়; প্রশ্নের বর্ণনা `Batch OS`-এর।
- **D option কেন ভুল:** `Time-sharing OS` বলতে CPU time slice দিয়ে বহু interactive user/process-কে responsive service দেয়। বোঝায়; প্রশ্নের বর্ণনা `Batch OS`-এর।
- **Related Concept:** Early mainframe system-এ প্রচলিত।
- **মনে রাখার টিপস:** Jobs in batches।

---

## প্রশ্ন 628 | Topic: Operating System > OS Basics | Difficulty: Medium | Type: Theory

Q. `Time-sharing OS` সম্পর্কে কোন statement সঠিক?

A) CPU time slice দিয়ে বহু interactive user/process-কে responsive service দেয়।
B) Memory-তে একাধিক job রেখে একটি I/O wait করলে অন্যটি CPU পায়।
C) Hardware বা software event যা CPU-কে current flow suspend করে handler চালাতে বলে।
D) Job interaction ছাড়া batch-এ collect ও execute করে throughput বাড়ানোর model।

**সঠিক উত্তর: A) CPU time slice দিয়ে বহু interactive user/process-কে responsive service দেয়।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** CPU time slice দিয়ে বহু interactive user/process-কে responsive service দেয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Multiprogramming` ধারণাকে বর্ণনা করে; `Time-sharing OS`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Interrupt` ধারণাকে বর্ণনা করে; `Time-sharing OS`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Batch OS` ধারণাকে বর্ণনা করে; `Time-sharing OS`-কে নয়।
- **Related Concept:** Preemptive scheduling গুরুত্বপূর্ণ।
- **মনে রাখার টিপস:** Many users, short slices।

---

## প্রশ্ন 629 | Topic: Operating System > OS Basics | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `Memory-তে একাধিক job রেখে একটি I/O wait করলে অন্যটি CPU পায়।`—এখানে কোন concept প্রযোজ্য?

A) Multiprogramming
B) Kernel Mode
C) Kernel
D) Interrupt

**সঠিক উত্তর: A) Multiprogramming**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Memory-তে একাধিক job রেখে একটি I/O wait করলে অন্যটি CPU পায়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Kernel Mode` বলতে Privileged mode যেখানে hardware ও protected resource access করা যায়। বোঝায়; প্রশ্নের বর্ণনা `Multiprogramming`-এর।
- **C option কেন ভুল:** `Kernel` বলতে Privileged core যা process, memory, device ও interrupt management করে। বোঝায়; প্রশ্নের বর্ণনা `Multiprogramming`-এর।
- **D option কেন ভুল:** `Interrupt` বলতে Hardware বা software event যা CPU-কে current flow suspend করে handler চালাতে বলে। বোঝায়; প্রশ্নের বর্ণনা `Multiprogramming`-এর।
- **Related Concept:** CPU utilization বাড়ায়।
- **মনে রাখার টিপস:** One waits, another runs।

---

## প্রশ্ন 630 | Topic: Operating System > OS Basics | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Deadline ও predictable response constraint পূরণে deterministic scheduling ও latency control করে।`

A) Real-time OS
B) Multiprogramming
C) Interrupt
D) System Call

**সঠিক উত্তর: A) Real-time OS**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Deadline ও predictable response constraint পূরণে deterministic scheduling ও latency control করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Multiprogramming` বলতে Memory-তে একাধিক job রেখে একটি I/O wait করলে অন্যটি CPU পায়। বোঝায়; প্রশ্নের বর্ণনা `Real-time OS`-এর।
- **C option কেন ভুল:** `Interrupt` বলতে Hardware বা software event যা CPU-কে current flow suspend করে handler চালাতে বলে। বোঝায়; প্রশ্নের বর্ণনা `Real-time OS`-এর।
- **D option কেন ভুল:** `System Call` বলতে User program-এর controlled request যা kernel service গ্রহণ করে। বোঝায়; প্রশ্নের বর্ণনা `Real-time OS`-এর।
- **Related Concept:** Hard ও soft real-time আছে।
- **মনে রাখার টিপস:** Correct time-এ correct result।

---


# Chapter Theory 53: Process, State এবং PCB

## বিস্তারিত Theory Note

Process lifecycle scheduling ও event-এর কারণে state বদলায়। Ready process শুধু CPU-এর অপেক্ষায়; Blocked process event complete না হওয়া পর্যন্ত CPU পেলেও চলতে পারে না।

Context switch state save/restore, address-space switch ও cache/TLB effect তৈরি করতে পারে। Scheduler নির্বাচন করে; dispatcher বাস্তবে selected entity চালায়।

## মূল ধারণার মানচিত্র

- **Process:** Execution-এ থাকা program, যার address space, registers, resources ও execution state আছে।
- **PCB:** Process ID, state, program counter, registers, scheduling ও resource metadata ধারণকারী kernel structure।
- **Ready State:** Process CPU পাওয়ার অপেক্ষায় ready queue-তে আছে।
- **Running State:** CPU বর্তমানে process-এর instruction execute করছে।
- **Blocked State:** Process I/O বা event-এর জন্য অপেক্ষা করছে এবং CPU পেলেও এগোতে পারবে না।
- **Context Switch:** CPU এক process/thread-এর execution context save করে অন্যটির context restore করে।
- **Process Creation:** Parent নতুন process তৈরি করে; OS PID, address space ও PCB allocate করে।
- **Zombie Process:** Terminated child যার exit status parent এখনও collect করেনি।
- **Orphan Process:** Parent আগে terminate হওয়া live child process।
- **Dispatcher:** Scheduler-selected process-কে CPU control দেওয়া, mode switch ও context restore করা component।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Process, State এবং PCB

## প্রশ্ন 631 | Topic: Operating System > Process Management | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Execution-এ থাকা program, যার address space, registers, resources ও execution state আছে।`

A) Process
B) Process Creation
C) Running State
D) Context Switch

**সঠিক উত্তর: A) Process**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Execution-এ থাকা program, যার address space, registers, resources ও execution state আছে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Process Creation` বলতে Parent নতুন process তৈরি করে; OS PID, address space ও PCB allocate করে। বোঝায়; প্রশ্নের বর্ণনা `Process`-এর।
- **C option কেন ভুল:** `Running State` বলতে CPU বর্তমানে process-এর instruction execute করছে। বোঝায়; প্রশ্নের বর্ণনা `Process`-এর।
- **D option কেন ভুল:** `Context Switch` বলতে CPU এক process/thread-এর execution context save করে অন্যটির context restore করে। বোঝায়; প্রশ্নের বর্ণনা `Process`-এর।
- **Related Concept:** Program passive; process active instance।
- **মনে রাখার টিপস:** Running program instance।

---

## প্রশ্ন 632 | Topic: Operating System > Process Management | Difficulty: Medium | Type: Tracing

Q. একটি PCB-তে নিচের কোন combination context switch-এর জন্য সবচেয়ে প্রয়োজনীয়?

A) HTML ও CSS
B) DNS ও URL
C) Program counter ও CPU registers
D) Database table rows

**সঠিক উত্তর: C) Program counter ও CPU registers**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Execution পরে ঠিক জায়গা থেকে চালাতে instruction pointer ও register state save করতে হয়।

#### Step-by-step সমাধান

```text
Outgoing process:
- Save program counter
- Save general registers
- Save stack pointer/status
Incoming process:
- Restore saved values
- Resume execution
```
- **A option কেন ভুল:** Web presentation data।
- **B option কেন ভুল:** Networking/web concepts।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Application data, CPU context নয়।
- **Related Concept:** PCB scheduling/accounting data-ও রাখে।
- **মনে রাখার টিপস:** Resume করতে PC + registers দরকার।

---

## প্রশ্ন 633 | Topic: Operating System > Process Management | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Process CPU পাওয়ার অপেক্ষায় ready queue-তে আছে।`—এখানে কোন concept প্রযোজ্য?

A) Process Creation
B) Orphan Process
C) Ready State
D) Process

**সঠিক উত্তর: C) Ready State**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Process CPU পাওয়ার অপেক্ষায় ready queue-তে আছে।
- **A option কেন ভুল:** `Process Creation` বলতে Parent নতুন process তৈরি করে; OS PID, address space ও PCB allocate করে। বোঝায়; প্রশ্নের বর্ণনা `Ready State`-এর।
- **B option কেন ভুল:** `Orphan Process` বলতে Parent আগে terminate হওয়া live child process। বোঝায়; প্রশ্নের বর্ণনা `Ready State`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Process` বলতে Execution-এ থাকা program, যার address space, registers, resources ও execution state আছে। বোঝায়; প্রশ্নের বর্ণনা `Ready State`-এর।
- **Related Concept:** I/O-এর জন্য অপেক্ষা নয়।
- **মনে রাখার টিপস:** Ready to run, waiting CPU।

---

## প্রশ্ন 634 | Topic: Operating System > Process Management | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`CPU বর্তমানে process-এর instruction execute করছে।`

A) Running State
B) Process
C) Context Switch
D) Zombie Process

**সঠিক উত্তর: A) Running State**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** CPU বর্তমানে process-এর instruction execute করছে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Process` বলতে Execution-এ থাকা program, যার address space, registers, resources ও execution state আছে। বোঝায়; প্রশ্নের বর্ণনা `Running State`-এর।
- **C option কেন ভুল:** `Context Switch` বলতে CPU এক process/thread-এর execution context save করে অন্যটির context restore করে। বোঝায়; প্রশ্নের বর্ণনা `Running State`-এর।
- **D option কেন ভুল:** `Zombie Process` বলতে Terminated child যার exit status parent এখনও collect করেনি। বোঝায়; প্রশ্নের বর্ণনা `Running State`-এর।
- **Related Concept:** Single-core-এ এক সময়ে একটি running process per core।
- **মনে রাখার টিপস:** Currently on CPU।

---

## প্রশ্ন 635 | Topic: Operating System > Process Management | Difficulty: Medium | Type: Tracing

Q. একটি process I/O request করার আগে Running এবং request-এর পরে completion-এর অপেক্ষায় থাকে। State transition কোনটি?

A) Running → Ready
B) Running → Blocked
C) Ready → Running
D) Blocked → Terminated

**সঠিক উত্তর: B) Running → Blocked**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** I/O completion না হওয়া পর্যন্ত process CPU ব্যবহার করে এগোতে পারে না।

#### Step-by-step সমাধান

```text
Before request: Running
I/O issued    : process cannot continue
After request : Blocked/Waiting
On completion : Ready
```
- **A option কেন ভুল:** Preemption/time slice expiry-তে হতে পারে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Dispatch transition।
- **D option কেন ভুল:** সাধারণ I/O request transition নয়।
- **Related Concept:** I/O complete হলে Blocked → Ready।
- **মনে রাখার টিপস:** Event wait = Blocked।

---

## প্রশ্ন 636 | Topic: Operating System > Process Management | Difficulty: Hard | Type: Calculation

Q. Context switch 0.2 ms এবং প্রতি second-এ 50টি switch হলে মোট overhead time কত ms?

A) 10 ms
B) 2 ms
C) 5 ms
D) 25 ms

**সঠিক উত্তর: A) 10 ms**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 50×0.2 = 10 ms।

#### Step-by-step সমাধান

```text
Switch count = 50
Cost/switch  = 0.2 ms
Total        = 50 x 0.2
             = 10 ms
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** শুধু 10 switch ধরা হয়েছে।
- **C option কেন ভুল:** 0.1 ms cost ধরা হয়েছে।
- **D option কেন ভুল:** 0.5 ms cost ধরা হয়েছে।
- **Related Concept:** Frequent short quantum context-switch overhead বাড়ায়।
- **মনে রাখার টিপস:** Count × cost।

---

## প্রশ্ন 637 | Topic: Operating System > Process Management | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Parent নতুন process তৈরি করে; OS PID, address space ও PCB allocate করে।`

A) Running State
B) Blocked State
C) Ready State
D) Process Creation

**সঠিক উত্তর: D) Process Creation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Parent নতুন process তৈরি করে; OS PID, address space ও PCB allocate করে।
- **A option কেন ভুল:** `Running State` বলতে CPU বর্তমানে process-এর instruction execute করছে। বোঝায়; প্রশ্নের বর্ণনা `Process Creation`-এর।
- **B option কেন ভুল:** `Blocked State` বলতে Process I/O বা event-এর জন্য অপেক্ষা করছে এবং CPU পেলেও এগোতে পারবে না। বোঝায়; প্রশ্নের বর্ণনা `Process Creation`-এর।
- **C option কেন ভুল:** `Ready State` বলতে Process CPU পাওয়ার অপেক্ষায় ready queue-তে আছে। বোঝায়; প্রশ্নের বর্ণনা `Process Creation`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** fork/exec Unix model উদাহরণ।
- **মনে রাখার টিপস:** New execution entity।

---

## প্রশ্ন 638 | Topic: Operating System > Process Management | Difficulty: Hard | Type: Theory

Q. `Zombie Process` সম্পর্কে কোন statement সঠিক?

A) CPU এক process/thread-এর execution context save করে অন্যটির context restore করে।
B) Terminated child যার exit status parent এখনও collect করেনি।
C) Execution-এ থাকা program, যার address space, registers, resources ও execution state আছে।
D) Parent নতুন process তৈরি করে; OS PID, address space ও PCB allocate করে।

**সঠিক উত্তর: B) Terminated child যার exit status parent এখনও collect করেনি।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Terminated child যার exit status parent এখনও collect করেনি।
- **A option কেন ভুল:** এই statementটি `Context Switch` ধারণাকে বর্ণনা করে; `Zombie Process`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `Process` ধারণাকে বর্ণনা করে; `Zombie Process`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Process Creation` ধারণাকে বর্ণনা করে; `Zombie Process`-কে নয়।
- **Related Concept:** CPU execute করে না; process-table entry থাকে।
- **মনে রাখার টিপস:** Dead but uncollected status।

---

## প্রশ্ন 639 | Topic: Operating System > Process Management | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Parent আগে terminate হওয়া live child process।`—এখানে কোন concept প্রযোজ্য?

A) Blocked State
B) Dispatcher
C) Zombie Process
D) Orphan Process

**সঠিক উত্তর: D) Orphan Process**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Parent আগে terminate হওয়া live child process।
- **A option কেন ভুল:** `Blocked State` বলতে Process I/O বা event-এর জন্য অপেক্ষা করছে এবং CPU পেলেও এগোতে পারবে না। বোঝায়; প্রশ্নের বর্ণনা `Orphan Process`-এর।
- **B option কেন ভুল:** `Dispatcher` বলতে Scheduler-selected process-কে CPU control দেওয়া, mode switch ও context restore করা component। বোঝায়; প্রশ্নের বর্ণনা `Orphan Process`-এর।
- **C option কেন ভুল:** `Zombie Process` বলতে Terminated child যার exit status parent এখনও collect করেনি। বোঝায়; প্রশ্নের বর্ণনা `Orphan Process`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** System process adopt করতে পারে।
- **মনে রাখার টিপস:** Child alive, parent gone।

---

## প্রশ্ন 640 | Topic: Operating System > Process Management | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Scheduler-selected process-কে CPU control দেওয়া, mode switch ও context restore করা component।`

A) Dispatcher
B) Process Creation
C) PCB
D) Blocked State

**সঠিক উত্তর: A) Dispatcher**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Scheduler-selected process-কে CPU control দেওয়া, mode switch ও context restore করা component।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Process Creation` বলতে Parent নতুন process তৈরি করে; OS PID, address space ও PCB allocate করে। বোঝায়; প্রশ্নের বর্ণনা `Dispatcher`-এর।
- **C option কেন ভুল:** `PCB` বলতে Process ID, state, program counter, registers, scheduling ও resource metadata ধারণকারী kernel structure। বোঝায়; প্রশ্নের বর্ণনা `Dispatcher`-এর।
- **D option কেন ভুল:** `Blocked State` বলতে Process I/O বা event-এর জন্য অপেক্ষা করছে এবং CPU পেলেও এগোতে পারবে না। বোঝায়; প্রশ্নের বর্ণনা `Dispatcher`-এর।
- **Related Concept:** Dispatch latency গুরুত্বপূর্ণ।
- **মনে রাখার টিপস:** Selectionকে CPU-তে চালায়।

---


# Chapter Theory 54: Threads, Concurrency এবং Parallelism

## বিস্তারিত Theory Note

Threads process resource share করায় communication সহজ, কিন্তু shared writable state race condition তৈরি করে। Stack ও register আলাদা হওয়ায় প্রত্যেক thread নিজস্ব call flow ধরে রাখে।

Concurrency scheduling concept; parallelism hardware simultaneity। Thread pool creation cost ও unbounded thread growth কমায়, তবে pool size workload ও blocking behavior অনুযায়ী tune করতে হয়।

## মূল ধারণার মানচিত্র

- **Thread:** Process-এর ভিতরের execution stream; একই process-এর code, data ও open resource share করে।
- **User-level Thread:** User library manage করে; kernel প্রতিটি thread আলাদাভাবে জানে না এমন model।
- **Kernel-level Thread:** Kernel schedulable entity হিসেবে thread manage করে।
- **Concurrency:** একাধিক task overlapping time interval-এ progress করে।
- **Parallelism:** একাধিক task বাস্তবে একই সময়ে বিভিন্ন core/processor-এ execute করে।
- **Race Condition:** Shared state outcome thread interleaving/timing-এর ওপর অনির্ধারিতভাবে নির্ভর করা bug।
- **Thread-safe:** Multiple thread থেকে documentedভাবে সঠিক operation বজায় রাখা code/component।
- **Thread Pool:** পূর্বনির্মিত worker thread task queue থেকে কাজ নেয়, creation overhead সীমিত করে।
- **Many-to-One Model:** অনেক user thread এক kernel thread-এর ওপর map হয়।
- **One-to-One Model:** প্রতিটি user thread একটি kernel thread-এর সঙ্গে map।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Threads, Concurrency এবং Parallelism

## প্রশ্ন 641 | Topic: Operating System > Thread Management | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Process-এর ভিতরের execution stream; একই process-এর code, data ও open resource share করে।`

A) Kernel-level Thread
B) Thread
C) Concurrency
D) Thread-safe

**সঠিক উত্তর: B) Thread**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Process-এর ভিতরের execution stream; একই process-এর code, data ও open resource share করে।
- **A option কেন ভুল:** `Kernel-level Thread` বলতে Kernel schedulable entity হিসেবে thread manage করে। বোঝায়; প্রশ্নের বর্ণনা `Thread`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Concurrency` বলতে একাধিক task overlapping time interval-এ progress করে। বোঝায়; প্রশ্নের বর্ণনা `Thread`-এর।
- **D option কেন ভুল:** `Thread-safe` বলতে Multiple thread থেকে documentedভাবে সঠিক operation বজায় রাখা code/component। বোঝায়; প্রশ্নের বর্ণনা `Thread`-এর।
- **Related Concept:** প্রতি thread-এর নিজস্ব stack ও registers থাকে।
- **মনে রাখার টিপস:** Lightweight execution path।

---

## প্রশ্ন 642 | Topic: Operating System > Thread Management | Difficulty: Medium | Type: Theory

Q. `User-level Thread` সম্পর্কে কোন statement সঠিক?

A) User library manage করে; kernel প্রতিটি thread আলাদাভাবে জানে না এমন model।
B) পূর্বনির্মিত worker thread task queue থেকে কাজ নেয়, creation overhead সীমিত করে।
C) Kernel schedulable entity হিসেবে thread manage করে।
D) একাধিক task বাস্তবে একই সময়ে বিভিন্ন core/processor-এ execute করে।

**সঠিক উত্তর: A) User library manage করে; kernel প্রতিটি thread আলাদাভাবে জানে না এমন model।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** User library manage করে; kernel প্রতিটি thread আলাদাভাবে জানে না এমন model।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Thread Pool` ধারণাকে বর্ণনা করে; `User-level Thread`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Kernel-level Thread` ধারণাকে বর্ণনা করে; `User-level Thread`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Parallelism` ধারণাকে বর্ণনা করে; `User-level Thread`-কে নয়।
- **Related Concept:** Switch দ্রুত, blocking syscall issue হতে পারে।
- **মনে রাখার টিপস:** Thread management in user space।

---

## প্রশ্ন 643 | Topic: Operating System > Thread Management | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Kernel schedulable entity হিসেবে thread manage করে।`—এখানে কোন concept প্রযোজ্য?

A) Thread-safe
B) Many-to-One Model
C) Thread Pool
D) Kernel-level Thread

**সঠিক উত্তর: D) Kernel-level Thread**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Kernel schedulable entity হিসেবে thread manage করে।
- **A option কেন ভুল:** `Thread-safe` বলতে Multiple thread থেকে documentedভাবে সঠিক operation বজায় রাখা code/component। বোঝায়; প্রশ্নের বর্ণনা `Kernel-level Thread`-এর।
- **B option কেন ভুল:** `Many-to-One Model` বলতে অনেক user thread এক kernel thread-এর ওপর map হয়। বোঝায়; প্রশ্নের বর্ণনা `Kernel-level Thread`-এর।
- **C option কেন ভুল:** `Thread Pool` বলতে পূর্বনির্মিত worker thread task queue থেকে কাজ নেয়, creation overhead সীমিত করে। বোঝায়; প্রশ্নের বর্ণনা `Kernel-level Thread`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** True multicore parallelism support।
- **মনে রাখার টিপস:** Kernel knows each thread।

---

## প্রশ্ন 644 | Topic: Operating System > Thread Management | Difficulty: Medium | Type: Tracing

Q. এক core CPU-তে দুই thread time-slice interleave করে, কিন্তু একই instant-এ একটিই চলে। এটি কী?

A) Parallelism only
B) Deadlock
C) Concurrency without parallelism
D) No multitasking

**সঠিক উত্তর: C) Concurrency without parallelism**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** দুই task overlapping period-এ progress করছে, কিন্তু simultaneous hardware execution নেই।

#### Step-by-step সমাধান

```text
Time 0-2: Thread A
Time 2-4: Thread B
Time 4-6: Thread A
Both progress in same interval
Only one runs at each instant
```
- **A option কেন ভুল:** Parallelism একই সময়ে execution চায়।
- **B option কেন ভুল:** দুই thread progress করছে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Interleaving নিজেই multitasking।
- **Related Concept:** Multicore-এ concurrency parallel executionও হতে পারে।
- **মনে রাখার টিপস:** Overlap ≠ simultaneous।

---

## প্রশ্ন 645 | Topic: Operating System > Thread Management | Difficulty: Medium | Type: Theory

Q. `Parallelism` সম্পর্কে কোন statement সঠিক?

A) একাধিক task বাস্তবে একই সময়ে বিভিন্ন core/processor-এ execute করে।
B) Kernel schedulable entity হিসেবে thread manage করে।
C) অনেক user thread এক kernel thread-এর ওপর map হয়।
D) Shared state outcome thread interleaving/timing-এর ওপর অনির্ধারিতভাবে নির্ভর করা bug।

**সঠিক উত্তর: A) একাধিক task বাস্তবে একই সময়ে বিভিন্ন core/processor-এ execute করে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একাধিক task বাস্তবে একই সময়ে বিভিন্ন core/processor-এ execute করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Kernel-level Thread` ধারণাকে বর্ণনা করে; `Parallelism`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Many-to-One Model` ধারণাকে বর্ণনা করে; `Parallelism`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Race Condition` ধারণাকে বর্ণনা করে; `Parallelism`-কে নয়।
- **Related Concept:** Concurrency ছাড়া parallelism নয়।
- **মনে রাখার টিপস:** Simultaneous execution।

---

## প্রশ্ন 646 | Topic: Operating System > Thread Management | Difficulty: Medium | Type: Calculation

Q. দুই thread shared counter 0 থেকে প্রত্যেকে একবার `counter=counter+1` করে, operation atomic নয়। Lost update হলে final value কত হতে পারে?

A) 0 only
B) 2 only
C) 3
D) 1

**সঠিক উত্তর: D) 1**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** দুই thread একই পুরোনো 0 পড়ে উভয়েই 1 লিখলে একটি increment হারায়।

#### Step-by-step সমাধান

```text
Initial counter = 0
T1 reads 0
T2 reads 0
T1 computes/writes 1
T2 computes/writes 1
Final counter = 1
```
- **A option কেন ভুল:** কমপক্ষে write 1 হয়।
- **B option কেন ভুল:** Proper serialization-এ 2, কিন্তু race-এ 1 সম্ভব।
- **C option কেন ভুল:** দুই incrementে 3 সম্ভব নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Read-modify-write atomic না হলে race।
- **মনে রাখার টিপস:** Read0, Read0, Write1, Write1।

---

## প্রশ্ন 647 | Topic: Operating System > Thread Management | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Multiple thread থেকে documentedভাবে সঠিক operation বজায় রাখা code/component।`

A) Thread Pool
B) Many-to-One Model
C) Parallelism
D) Thread-safe

**সঠিক উত্তর: D) Thread-safe**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Multiple thread থেকে documentedভাবে সঠিক operation বজায় রাখা code/component।
- **A option কেন ভুল:** `Thread Pool` বলতে পূর্বনির্মিত worker thread task queue থেকে কাজ নেয়, creation overhead সীমিত করে। বোঝায়; প্রশ্নের বর্ণনা `Thread-safe`-এর।
- **B option কেন ভুল:** `Many-to-One Model` বলতে অনেক user thread এক kernel thread-এর ওপর map হয়। বোঝায়; প্রশ্নের বর্ণনা `Thread-safe`-এর।
- **C option কেন ভুল:** `Parallelism` বলতে একাধিক task বাস্তবে একই সময়ে বিভিন্ন core/processor-এ execute করে। বোঝায়; প্রশ্নের বর্ণনা `Thread-safe`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Immutable data ও locks সহায়ক।
- **মনে রাখার টিপস:** Correct under concurrency।

---

## প্রশ্ন 648 | Topic: Operating System > Thread Management | Difficulty: Medium | Type: Calculation

Q. ২০টি task, প্রতিটি 5 ms CPU কাজ; 4 worker thread আদর্শ parallelism এবং overhead শূন্য হলে minimum makespan কত?

A) 20 ms
B) 25 ms
C) 50 ms
D) 100 ms

**সঠিক উত্তর: B) 25 ms**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতি worker 5টি task পায়; 5×5=25 ms।

#### Step-by-step সমাধান

```text
Total work = 20 x 5 = 100 ms
Workers    = 4
Makespan   = 100 / 4
           = 25 ms
```
- **A option কেন ভুল:** Task count নয়, load per worker বিবেচনা দরকার।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** শুধু 2 worker-এর মতো।
- **D option কেন ভুল:** Sequential total।
- **Related Concept:** Ideal lower bound total work/worker count।
- **মনে রাখার টিপস:** (Tasks × time)/workers।

---

## প্রশ্ন 649 | Topic: Operating System > Thread Management | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `অনেক user thread এক kernel thread-এর ওপর map হয়।`—এখানে কোন concept প্রযোজ্য?

A) One-to-One Model
B) Thread
C) Parallelism
D) Many-to-One Model

**সঠিক উত্তর: D) Many-to-One Model**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** অনেক user thread এক kernel thread-এর ওপর map হয়।
- **A option কেন ভুল:** `One-to-One Model` বলতে প্রতিটি user thread একটি kernel thread-এর সঙ্গে map। বোঝায়; প্রশ্নের বর্ণনা `Many-to-One Model`-এর।
- **B option কেন ভুল:** `Thread` বলতে Process-এর ভিতরের execution stream; একই process-এর code, data ও open resource share করে। বোঝায়; প্রশ্নের বর্ণনা `Many-to-One Model`-এর।
- **C option কেন ভুল:** `Parallelism` বলতে একাধিক task বাস্তবে একই সময়ে বিভিন্ন core/processor-এ execute করে। বোঝায়; প্রশ্নের বর্ণনা `Many-to-One Model`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** এক blocking call সব block করতে পারে; multicore parallelism সীমিত।
- **মনে রাখার টিপস:** Many users, one kernel।

---

## প্রশ্ন 650 | Topic: Operating System > Thread Management | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`প্রতিটি user thread একটি kernel thread-এর সঙ্গে map।`

A) User-level Thread
B) Concurrency
C) One-to-One Model
D) Thread-safe

**সঠিক উত্তর: C) One-to-One Model**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি user thread একটি kernel thread-এর সঙ্গে map।
- **A option কেন ভুল:** `User-level Thread` বলতে User library manage করে; kernel প্রতিটি thread আলাদাভাবে জানে না এমন model। বোঝায়; প্রশ্নের বর্ণনা `One-to-One Model`-এর।
- **B option কেন ভুল:** `Concurrency` বলতে একাধিক task overlapping time interval-এ progress করে। বোঝায়; প্রশ্নের বর্ণনা `One-to-One Model`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Thread-safe` বলতে Multiple thread থেকে documentedভাবে সঠিক operation বজায় রাখা code/component। বোঝায়; প্রশ্নের বর্ণনা `One-to-One Model`-এর।
- **Related Concept:** Parallelism ভালো, kernel overhead বেশি।
- **মনে রাখার টিপস:** One user, one kernel thread।

---


# Chapter Theory 55: CPU Scheduling: FCFS এবং SJF

## বিস্তারিত Theory Note

Scheduling metric হিসাবের আগে Gantt chart এবং arrival availability নির্ধারণ করুন। Turnaround completion পর্যন্ত total time; waiting ready queue time; response প্রথম CPU allocation পর্যন্ত delay।

FCFS simple কিন্তু convoy effect তৈরি করতে পারে। SJF average waiting কমায়, তবে future burst estimate প্রয়োজন এবং long job starvation হতে পারে।

## মূল ধারণার মানচিত্র

- **CPU Burst:** Process ধারাবাহিকভাবে CPU ব্যবহার করার সময় interval।
- **Arrival Time:** Process ready queue-তে প্রবেশের সময়।
- **Completion Time:** Process execution সম্পূর্ণ হওয়ার clock time।
- **Turnaround Time:** Completion time minus arrival time।
- **Waiting Time:** Ready queue-তে মোট অপেক্ষার সময়; CPU burst time বাদ।
- **Response Time:** Arrival থেকে process প্রথমবার CPU পাওয়ার আগ পর্যন্ত সময়।
- **FCFS:** Arrival order অনুযায়ী non-preemptive scheduling।
- **SJF:** Available process-এর মধ্যে smallest next CPU burst non-preemptively নির্বাচন।
- **Convoy Effect:** Long CPU-bound process-এর পেছনে অনেক short process আটকে throughput/response ক্ষতি।
- **Throughput:** Unit time-এ complete হওয়া process/job সংখ্যা।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: CPU Scheduling: FCFS এবং SJF

# Batch 15 — Question 651–700

## প্রশ্ন 651 | Topic: Operating System > CPU Scheduling I | Difficulty: Hard | Type: Calculation

Q. Process burst time যথাক্রমে 6, 4, 2 ms। Total CPU burst কত?

A) 12 ms
B) 8 ms
C) 10 ms
D) 14 ms

**সঠিক উত্তর: A) 12 ms**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** সব burst যোগ করলে 12 ms।

#### Step-by-step সমাধান

```text
Total = 6 + 4 + 2
      = 12 ms
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** একটি burst বাদ গেছে।
- **C option কেন ভুল:** 6+4, 2 বাদ।
- **D option কেন ভুল:** অতিরিক্ত 2 যোগ।
- **Related Concept:** Total busy time context-switch overhead ছাড়া burst sum।
- **মনে রাখার টিপস:** সব CPU burst যোগ করুন।

---

## প্রশ্ন 652 | Topic: Operating System > CPU Scheduling I | Difficulty: Medium | Type: Theory

Q. `Arrival Time` সম্পর্কে কোন statement সঠিক?

A) Process ready queue-তে প্রবেশের সময়।
B) Completion time minus arrival time।
C) Process execution সম্পূর্ণ হওয়ার clock time।
D) Available process-এর মধ্যে smallest next CPU burst non-preemptively নির্বাচন।

**সঠিক উত্তর: A) Process ready queue-তে প্রবেশের সময়।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Process ready queue-তে প্রবেশের সময়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Turnaround Time` ধারণাকে বর্ণনা করে; `Arrival Time`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Completion Time` ধারণাকে বর্ণনা করে; `Arrival Time`-কে নয়।
- **D option কেন ভুল:** এই statementটি `SJF` ধারণাকে বর্ণনা করে; `Arrival Time`-কে নয়।
- **Related Concept:** Scheduling calculation-এর input।
- **মনে রাখার টিপস:** When process arrives।

---

## প্রশ্ন 653 | Topic: Operating System > CPU Scheduling I | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Process execution সম্পূর্ণ হওয়ার clock time।`—এখানে কোন concept প্রযোজ্য?

A) Response Time
B) CPU Burst
C) Completion Time
D) FCFS

**সঠিক উত্তর: C) Completion Time**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Process execution সম্পূর্ণ হওয়ার clock time।
- **A option কেন ভুল:** `Response Time` বলতে Arrival থেকে process প্রথমবার CPU পাওয়ার আগ পর্যন্ত সময়। বোঝায়; প্রশ্নের বর্ণনা `Completion Time`-এর।
- **B option কেন ভুল:** `CPU Burst` বলতে Process ধারাবাহিকভাবে CPU ব্যবহার করার সময় interval। বোঝায়; প্রশ্নের বর্ণনা `Completion Time`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `FCFS` বলতে Arrival order অনুযায়ী non-preemptive scheduling। বোঝায়; প্রশ্নের বর্ণনা `Completion Time`-এর।
- **Related Concept:** Turnaround calculationে ব্যবহৃত।
- **মনে রাখার টিপস:** When process finishes।

---

## প্রশ্ন 654 | Topic: Operating System > CPU Scheduling I | Difficulty: Easy | Type: Calculation

Q. এক process arrival 3 ms, completion 18 ms। Turnaround time কত?

A) 18 ms
B) 21 ms
C) 6 ms
D) 15 ms

**সঠিক উত্তর: D) 15 ms**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** TAT=CT−AT=18−3=15।

#### Step-by-step সমাধান

```text
AT = 3
CT = 18
TAT = 18 - 3 = 15 ms
```
- **A option কেন ভুল:** Completion time সরাসরি নেওয়া হয়েছে।
- **B option কেন ভুল:** যোগ করা হয়েছে।
- **C option কেন ভুল:** অপ্রাসঙ্গিক difference।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Turnaround submission থেকে finish।
- **মনে রাখার টিপস:** CT−AT।

---

## প্রশ্ন 655 | Topic: Operating System > CPU Scheduling I | Difficulty: Medium | Type: Calculation

Q. এক process-এর turnaround 20 ms এবং CPU burst 7 ms। Waiting time কত?

A) 27 ms
B) 7 ms
C) 20 ms
D) 13 ms

**সঠিক উত্তর: D) 13 ms**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** WT=TAT−BT=20−7=13।

#### Step-by-step সমাধান

```text
TAT = 20
BT  = 7
WT  = 20 - 7 = 13 ms
```
- **A option কেন ভুল:** যোগ করা হয়েছে।
- **B option কেন ভুল:** Burst time।
- **C option কেন ভুল:** Turnaround সরাসরি।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** I/O time থাকলে simple formula assumptions প্রশ্নে দেখুন।
- **মনে রাখার টিপস:** TAT−CPU burst।

---

## প্রশ্ন 656 | Topic: Operating System > CPU Scheduling I | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Arrival থেকে process প্রথমবার CPU পাওয়ার আগ পর্যন্ত সময়।`—এখানে কোন concept প্রযোজ্য?

A) Throughput
B) Waiting Time
C) Response Time
D) Turnaround Time

**সঠিক উত্তর: C) Response Time**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Arrival থেকে process প্রথমবার CPU পাওয়ার আগ পর্যন্ত সময়।
- **A option কেন ভুল:** `Throughput` বলতে Unit time-এ complete হওয়া process/job সংখ্যা। বোঝায়; প্রশ্নের বর্ণনা `Response Time`-এর।
- **B option কেন ভুল:** `Waiting Time` বলতে Ready queue-তে মোট অপেক্ষার সময়; CPU burst time বাদ। বোঝায়; প্রশ্নের বর্ণনা `Response Time`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Turnaround Time` বলতে Completion time minus arrival time। বোঝায়; প্রশ্নের বর্ণনা `Response Time`-এর।
- **Related Concept:** Interactive responsiveness metric।
- **মনে রাখার টিপস:** First start − arrival।

---

## প্রশ্ন 657 | Topic: Operating System > CPU Scheduling I | Difficulty: Hard | Type: Calculation

Q. সব process arrival 0। FCFS order P1=5, P2=3, P3=2। Average waiting time কত?

A) 3.0 ms
B) 5.0 ms
C) 6.0 ms
D) 4.33 ms

**সঠিক উত্তর: D) 4.33 ms**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Wait: P1=0, P2=5, P3=8; average 13/3=4.33।

#### Step-by-step সমাধান

```text
Order: P1(5) P2(3) P3(2)
P1 wait = 0
P2 wait = 5
P3 wait = 5+3 = 8
Average = (0+5+8)/3 = 13/3 = 4.33 ms
```
- **A option কেন ভুল:** Incorrect averaging।
- **B option কেন ভুল:** P2 wait-কে average ধরা।
- **C option কেন ভুল:** Wait sum/ভুল count।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** FCFS wait হলো আগের burst sum।
- **মনে রাখার টিপস:** Gantt chart লিখুন।

---

## প্রশ্ন 658 | Topic: Operating System > CPU Scheduling I | Difficulty: Hard | Type: Tracing

Q. সব process arrival 0। Burst: P1=7, P2=2, P3=4। Non-preemptive SJF order কী?

A) P1,P2,P3
B) P3,P2,P1
C) P2,P3,P1
D) P2,P1,P3

**সঠিক উত্তর: C) P2,P3,P1**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Shortest 2, তারপর 4, তারপর 7।

#### Step-by-step সমাধান

```text
Burst list:
P1=7
P2=2
P3=4
Ascending: 2,4,7
Order: P2,P3,P1
```
- **A option কেন ভুল:** FCFS input order।
- **B option কেন ভুল:** 4-এর আগে 2 হওয়া উচিত।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** 7-এর আগে 4 হওয়া উচিত।
- **Related Concept:** SJF available shortest burst নেয়।
- **মনে রাখার টিপস:** Burst ascending order।

---

## প্রশ্ন 659 | Topic: Operating System > CPU Scheduling I | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Long CPU-bound process-এর পেছনে অনেক short process আটকে throughput/response ক্ষতি।`—এখানে কোন concept প্রযোজ্য?

A) Convoy Effect
B) SJF
C) Arrival Time
D) Response Time

**সঠিক উত্তর: A) Convoy Effect**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Long CPU-bound process-এর পেছনে অনেক short process আটকে throughput/response ক্ষতি।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `SJF` বলতে Available process-এর মধ্যে smallest next CPU burst non-preemptively নির্বাচন। বোঝায়; প্রশ্নের বর্ণনা `Convoy Effect`-এর।
- **C option কেন ভুল:** `Arrival Time` বলতে Process ready queue-তে প্রবেশের সময়। বোঝায়; প্রশ্নের বর্ণনা `Convoy Effect`-এর।
- **D option কেন ভুল:** `Response Time` বলতে Arrival থেকে process প্রথমবার CPU পাওয়ার আগ পর্যন্ত সময়। বোঝায়; প্রশ্নের বর্ণনা `Convoy Effect`-এর।
- **Related Concept:** FCFS-এ দেখা যায়।
- **মনে রাখার টিপস:** Long job leads convoy।

---

## প্রশ্ন 660 | Topic: Operating System > CPU Scheduling I | Difficulty: Medium | Type: Calculation

Q. 40 ms interval-এ 8টি process complete হলে throughput কত process/ms?

A) 5
B) 0.2
C) 8
D) 40

**সঠিক উত্তর: B) 0.2**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Throughput=8/40=0.2 process/ms।

#### Step-by-step সমাধান

```text
Throughput = 8 / 40
           = 0.2 process/ms
```
- **A option কেন ভুল:** Time/process latency 40/8, throughput নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Completion count, rate নয়।
- **D option কেন ভুল:** Time interval।
- **Related Concept:** Throughput jobs per unit time।
- **মনে রাখার টিপস:** Completed ÷ time।

---


# Chapter Theory 56: CPU Scheduling: Round Robin, Priority এবং SRTF

## বিস্তারিত Theory Note

Round Robin responsiveness ও fairness দিতে quantum ব্যবহার করে। Quantum খুব বড় হলে FCFS-এর মতো; খুব ছোট হলে context-switch overhead বেশি। Priority scheduling-এ convention ও preemption rule স্পষ্টভাবে পড়তে হবে।

SRTF remaining burst estimate-এর ওপর চলে এবং short job response ভালো করলেও long process starvation ঘটাতে পারে। Aging priority ধীরে উন্নত করে starvation কমায়।

## মূল ধারণার মানচিত্র

- **Preemptive Scheduling:** OS running process-এর CPU কেড়ে অন্য process চালাতে পারে।
- **Round Robin:** Ready queue FIFO এবং fixed time quantum দিয়ে preemptive time-sharing scheduling।
- **Time Quantum:** Round Robin-এ এক turn-এ process-এর সর্বোচ্চ continuous CPU time।
- **Priority Scheduling:** Priority value অনুযায়ী process নির্বাচন; convention-এ ছোট বা বড় value high হতে পারে।
- **Aging:** Waiting process-এর priority সময়ের সঙ্গে বাড়িয়ে starvation কমানো।
- **SRTF:** Shortest Remaining Time First; নতুন shorter process এলে current process preempt হয়।
- **Starvation:** একটি process দীর্ঘ/অনির্দিষ্ট সময় CPU/resource না পাওয়া।
- **Dispatch Latency:** Scheduler decision-এর পর selected process বাস্তবে run শুরু করতে delay।
- **Preemption:** Running entity-কে involuntarily stop করে ready state-এ ফেরানো।
- **Fairness:** Comparable process-কে reasonable CPU opportunity দেওয়া scheduling goal।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: CPU Scheduling: Round Robin, Priority এবং SRTF

## প্রশ্ন 661 | Topic: Operating System > CPU Scheduling II | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`OS running process-এর CPU কেড়ে অন্য process চালাতে পারে।`

A) Preemption
B) Preemptive Scheduling
C) Aging
D) Priority Scheduling

**সঠিক উত্তর: B) Preemptive Scheduling**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** OS running process-এর CPU কেড়ে অন্য process চালাতে পারে।
- **A option কেন ভুল:** `Preemption` বলতে Running entity-কে involuntarily stop করে ready state-এ ফেরানো। বোঝায়; প্রশ্নের বর্ণনা `Preemptive Scheduling`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Aging` বলতে Waiting process-এর priority সময়ের সঙ্গে বাড়িয়ে starvation কমানো। বোঝায়; প্রশ্নের বর্ণনা `Preemptive Scheduling`-এর।
- **D option কেন ভুল:** `Priority Scheduling` বলতে Priority value অনুযায়ী process নির্বাচন; convention-এ ছোট বা বড় value high হতে পারে। বোঝায়; প্রশ্নের বর্ণনা `Preemptive Scheduling`-এর।
- **Related Concept:** Timer interrupt ও priority event trigger।
- **মনে রাখার টিপস:** OS may interrupt running task।

---

## প্রশ্ন 662 | Topic: Operating System > CPU Scheduling II | Difficulty: Medium | Type: Tracing

Q. সব arrival 0; burst P1=5, P2=3; quantum=2। প্রথম চার CPU slices-এর sequence কী?

A) P1,P1,P2,P2
B) P1,P2,P1,P2
C) P2,P1,P2,P1
D) P1,P2,P2,P1

**সঠিক উত্তর: B) P1,P2,P1,P2**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** RR queue rotate করে: P1 2, P2 2, P1 আরও2, P2 remaining1।

#### Step-by-step সমাধান

```text
Initial queue [P1(5),P2(3)]
Slice1 P1 uses2 rem3 -> queue [P2,P1]
Slice2 P2 uses2 rem1 -> queue [P1,P2]
Slice3 P1 uses2 rem1 -> queue [P2,P1]
Slice4 P2 uses1 done
```
- **A option কেন ভুল:** এক process consecutive quantum পাবে না যখন অন্য ready।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Initial queue P1 আগে।
- **D option কেন ভুল:** P2 প্রথম slice-এর পরে queue-এর পেছনে যায়।
- **Related Concept:** Remaining burst ও queue state trace করুন।
- **মনে রাখার টিপস:** Quantum শেষে unfinished process rear-এ।

---

## প্রশ্ন 663 | Topic: Operating System > CPU Scheduling II | Difficulty: Hard | Type: Calculation

Q. Quantum 1 ms, context switch 0.1 ms। 10টি full quantum-এর পর 10টি switch হলে overhead percentage (CPU quantum+switch total) কত?

A) 5%
B) 9.09%
C) 10%
D) 11%

**সঠিক উত্তর: B) 9.09%**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Useful=10 ms, overhead=1 ms, total=11 ms; 1/11×100=9.09%।

#### Step-by-step সমাধান

```text
Useful time   = 10 x 1   = 10 ms
Switch overhead= 10 x 0.1 = 1 ms
Total time     = 11 ms
Overhead %     = 1/11 x100 = 9.09%
```
- **A option কেন ভুল:** Overhead অর্ধেক।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Overhead/useful ratio, total denominator নয়।
- **D option কেন ভুল:** Total time-কে percent ধরা।
- **Related Concept:** Quantum ছোট হলে switch fraction বাড়ে।
- **মনে রাখার টিপস:** Overhead% = overhead/(useful+overhead)।

---

## প্রশ্ন 664 | Topic: Operating System > CPU Scheduling II | Difficulty: Medium | Type: Tracing

Q. Priority convention: smaller number = higher priority। Ready process priority P1=3, P2=1, P3=2। প্রথমে কে চলবে?

A) P1
B) P3
C) P2
D) Tie

**সঠিক উত্তর: C) P2**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** সবচেয়ে ছোট priority number 1, তাই P2।

#### Step-by-step সমাধান

```text
P1 priority=3
P2 priority=1 <- minimum
P3 priority=2
Selected=P2
```
- **A option কেন ভুল:** Priority 3 lowest in given convention।
- **B option কেন ভুল:** Priority 2, কিন্তু P2-এর 1 বেশি অগ্রাধিকার।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** মান distinct।
- **Related Concept:** Priority direction question থেকে পড়ুন।
- **মনে রাখার টিপস:** Smaller-is-higher convention ভুলবেন না।

---

## প্রশ্ন 665 | Topic: Operating System > CPU Scheduling II | Difficulty: Medium | Type: Calculation

Q. এক process priority 10 থেকে প্রতি 5 second wait-এ 1 করে উন্নত হয়; smaller number higher। 20 second পরে priority কত?

A) 6
B) 8
C) 10
D) 14

**সঠিক উত্তর: A) 6**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 20/5=4 improvement; 10−4=6।

#### Step-by-step সমাধান

```text
Intervals = 20/5 = 4
Old priority=10
New priority=10-4=6
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** দুই interval ধরা।
- **C option কেন ভুল:** Aging প্রয়োগ হয়নি।
- **D option কেন ভুল:** Wrong direction; smaller better।
- **Related Concept:** Aging direction priority convention-এর ওপর নির্ভরশীল।
- **মনে রাখার টিপস:** Intervals count করে priority improve করুন।

---

## প্রশ্ন 666 | Topic: Operating System > CPU Scheduling II | Difficulty: Easy | Type: Tracing

Q. t=0-এ P1 burst 8 চলে; t=1-এ P2 burst 3 আসে। SRTF-এ t=1-এ কী হবে?

A) P2 P1-কে preempt করবে
B) P1 চলবে; remaining7 >3 হলেও
C) দুইটি একই core-এ parallel
D) সব process block

**সঠিক উত্তর: A) P2 P1-কে preempt করবে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** t=1-এ P1 remaining 7, P2 burst 3; smallest remaining P2।

#### Step-by-step সমাধান

```text
t=0..1: P1 executes 1
P1 remaining=7
At t=1 P2 arrives, remaining=3
3 < 7 -> select P2
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** SRTF preemptive।
- **C option কেন ভুল:** Single-core scheduling assumption।
- **D option কেন ভুল:** CPU burst available।
- **Related Concept:** SRTF arrival event-এ remaining time পুনরায় তুলনা করে।
- **মনে রাখার টিপস:** New job shorter হলে preempt।

---

## প্রশ্ন 667 | Topic: Operating System > CPU Scheduling II | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`একটি process দীর্ঘ/অনির্দিষ্ট সময় CPU/resource না পাওয়া।`

A) Priority Scheduling
B) Preemptive Scheduling
C) Time Quantum
D) Starvation

**সঠিক উত্তর: D) Starvation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একটি process দীর্ঘ/অনির্দিষ্ট সময় CPU/resource না পাওয়া।
- **A option কেন ভুল:** `Priority Scheduling` বলতে Priority value অনুযায়ী process নির্বাচন; convention-এ ছোট বা বড় value high হতে পারে। বোঝায়; প্রশ্নের বর্ণনা `Starvation`-এর।
- **B option কেন ভুল:** `Preemptive Scheduling` বলতে OS running process-এর CPU কেড়ে অন্য process চালাতে পারে। বোঝায়; প্রশ্নের বর্ণনা `Starvation`-এর।
- **C option কেন ভুল:** `Time Quantum` বলতে Round Robin-এ এক turn-এ process-এর সর্বোচ্চ continuous CPU time। বোঝায়; প্রশ্নের বর্ণনা `Starvation`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Unfair priority policy-এ হতে পারে।
- **মনে রাখার টিপস:** Waits indefinitely।

---

## প্রশ্ন 668 | Topic: Operating System > CPU Scheduling II | Difficulty: Medium | Type: Theory

Q. `Dispatch Latency` সম্পর্কে কোন statement সঠিক?

A) Scheduler decision-এর পর selected process বাস্তবে run শুরু করতে delay।
B) OS running process-এর CPU কেড়ে অন্য process চালাতে পারে।
C) Comparable process-কে reasonable CPU opportunity দেওয়া scheduling goal।
D) Ready queue FIFO এবং fixed time quantum দিয়ে preemptive time-sharing scheduling।

**সঠিক উত্তর: A) Scheduler decision-এর পর selected process বাস্তবে run শুরু করতে delay।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Scheduler decision-এর পর selected process বাস্তবে run শুরু করতে delay।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Preemptive Scheduling` ধারণাকে বর্ণনা করে; `Dispatch Latency`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Fairness` ধারণাকে বর্ণনা করে; `Dispatch Latency`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Round Robin` ধারণাকে বর্ণনা করে; `Dispatch Latency`-কে নয়।
- **Related Concept:** Real-time system-এ গুরুত্বপূর্ণ।
- **মনে রাখার টিপস:** Decision-to-run delay।

---

## প্রশ্ন 669 | Topic: Operating System > CPU Scheduling II | Difficulty: Medium | Type: Tracing

Q. Running P1 time slice expiry-তে ready queue-তে ফেরে। State transition কী?

A) Running→Blocked
B) Ready→Running
C) Running→Ready
D) Blocked→Ready

**সঠিক উত্তর: C) Running→Ready**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Preemption process-কে CPU থেকে সরিয়ে ready রাখে; event wait নয়।

#### Step-by-step সমাধান

```text
Before timer: Running
Timer expires: context saved
Process can still execute
After preemption: Ready
```
- **A option কেন ভুল:** I/O/event wait হলে।
- **B option কেন ভুল:** Dispatch।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Event completion।
- **Related Concept:** Preemption ও blocking আলাদা।
- **মনে রাখার টিপস:** CPU কেড়ে নিলে Ready।

---

## প্রশ্ন 670 | Topic: Operating System > CPU Scheduling II | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Comparable process-কে reasonable CPU opportunity দেওয়া scheduling goal।`

A) Time Quantum
B) Fairness
C) Aging
D) Dispatch Latency

**সঠিক উত্তর: B) Fairness**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Comparable process-কে reasonable CPU opportunity দেওয়া scheduling goal।
- **A option কেন ভুল:** `Time Quantum` বলতে Round Robin-এ এক turn-এ process-এর সর্বোচ্চ continuous CPU time। বোঝায়; প্রশ্নের বর্ণনা `Fairness`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Aging` বলতে Waiting process-এর priority সময়ের সঙ্গে বাড়িয়ে starvation কমানো। বোঝায়; প্রশ্নের বর্ণনা `Fairness`-এর।
- **D option কেন ভুল:** `Dispatch Latency` বলতে Scheduler decision-এর পর selected process বাস্তবে run শুরু করতে delay। বোঝায়; প্রশ্নের বর্ণনা `Fairness`-এর।
- **Related Concept:** Performance metric-এর সঙ্গে trade-off।
- **মনে রাখার টিপস:** No unfair neglect।

---


# Chapter Theory 57: Critical Section, Mutex এবং Atomicity

## বিস্তারিত Theory Note

Synchronization solution-এ mutual exclusion safety দেয়; progress ও bounded waiting liveness/fairness দেয়। Atomic hardware primitive দিয়ে lock তৈরি করা যায়, কিন্তু memory ordering ও fairnessও গুরুত্বপূর্ণ।

Spinlock wait-এর সময় CPU consume করে। Expected wait খুব ছোট ও thread অন্য core-এ lock release করবে হলে কার্যকর; long wait-এ blocking lock ভালো।

## মূল ধারণার মানচিত্র

- **Critical Section:** Shared data/resource access করা code region যা race এড়াতে controlledভাবে execute করতে হয়।
- **Mutual Exclusion:** এক সময়ে সর্বোচ্চ একটি process/thread critical section-এ থাকার property।
- **Progress:** Critical section খালি হলে interested process-এর মধ্যে selection অনির্দিষ্টভাবে postpone না করা condition।
- **Bounded Waiting:** Request-এর পরে অন্যরা কতবার আগে ঢুকতে পারবে তার finite bound থাকা।
- **Atomic Operation:** অন্য thread-এর দৃষ্টিতে indivisibleভাবে সম্পন্ন operation।
- **Mutex:** Ownership-based lock; holder unlock করে mutual exclusion দেয়।
- **Spinlock:** Waiting thread sleep না গিয়ে repeatedly lock পরীক্ষা করে।
- **Race Condition:** Interleaving-dependent incorrect shared-state outcome।
- **Test-and-Set:** Atomic read-modify-write hardware primitive যা lock implementation-এ ব্যবহৃত হয়।
- **Compare-and-Swap:** Memory value expected হলে atomically new value বসায় এবং success জানায়।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Critical Section, Mutex এবং Atomicity

## প্রশ্ন 671 | Topic: Operating System > Process Synchronization I | Difficulty: Hard | Type: Tracing

Q. দুই thread একই critical section-এ একই সময়ে থাকলে কোন correctness condition ভাঙে?

A) Progress
B) Mutual Exclusion
C) Bounded Waiting
D) Liveness only

**সঠিক উত্তর: B) Mutual Exclusion**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একাধিক thread একসঙ্গে critical section-এ প্রবেশ করেছে।

#### Step-by-step সমাধান

```text
Time t:
Thread A inside critical section
Thread B inside critical section
Count inside = 2
Required maximum = 1
```
- **A option কেন ভুল:** Selection delay condition।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Wait bound condition।
- **D option কেন ভুল:** Specific violated safety property mutual exclusion।
- **Related Concept:** Critical-section solution-এ safety ও liveness দুটোই দরকার।
- **মনে রাখার টিপস:** Two inside → mutual exclusion broken।

---

## প্রশ্ন 672 | Topic: Operating System > Process Synchronization I | Difficulty: Medium | Type: Theory

Q. `Mutual Exclusion` সম্পর্কে কোন statement সঠিক?

A) এক সময়ে সর্বোচ্চ একটি process/thread critical section-এ থাকার property।
B) Atomic read-modify-write hardware primitive যা lock implementation-এ ব্যবহৃত হয়।
C) Waiting thread sleep না গিয়ে repeatedly lock পরীক্ষা করে।
D) অন্য thread-এর দৃষ্টিতে indivisibleভাবে সম্পন্ন operation।

**সঠিক উত্তর: A) এক সময়ে সর্বোচ্চ একটি process/thread critical section-এ থাকার property।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** এক সময়ে সর্বোচ্চ একটি process/thread critical section-এ থাকার property।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Test-and-Set` ধারণাকে বর্ণনা করে; `Mutual Exclusion`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Spinlock` ধারণাকে বর্ণনা করে; `Mutual Exclusion`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Atomic Operation` ধারণাকে বর্ণনা করে; `Mutual Exclusion`-কে নয়।
- **Related Concept:** Safety condition।
- **মনে রাখার টিপস:** Only one inside।

---

## প্রশ্ন 673 | Topic: Operating System > Process Synchronization I | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Critical section খালি হলে interested process-এর মধ্যে selection অনির্দিষ্টভাবে postpone না করা condition।`—এখানে কোন concept প্রযোজ্য?

A) Mutex
B) Progress
C) Atomic Operation
D) Compare-and-Swap

**সঠিক উত্তর: B) Progress**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Critical section খালি হলে interested process-এর মধ্যে selection অনির্দিষ্টভাবে postpone না করা condition।
- **A option কেন ভুল:** `Mutex` বলতে Ownership-based lock; holder unlock করে mutual exclusion দেয়। বোঝায়; প্রশ্নের বর্ণনা `Progress`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Atomic Operation` বলতে অন্য thread-এর দৃষ্টিতে indivisibleভাবে সম্পন্ন operation। বোঝায়; প্রশ্নের বর্ণনা `Progress`-এর।
- **D option কেন ভুল:** `Compare-and-Swap` বলতে Memory value expected হলে atomically new value বসায় এবং success জানায়। বোঝায়; প্রশ্নের বর্ণনা `Progress`-এর।
- **Related Concept:** Correct critical-section solution requirement।
- **মনে রাখার টিপস:** Someone should proceed।

---

## প্রশ্ন 674 | Topic: Operating System > Process Synchronization I | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Request-এর পরে অন্যরা কতবার আগে ঢুকতে পারবে তার finite bound থাকা।`

A) Mutual Exclusion
B) Mutex
C) Critical Section
D) Bounded Waiting

**সঠিক উত্তর: D) Bounded Waiting**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Request-এর পরে অন্যরা কতবার আগে ঢুকতে পারবে তার finite bound থাকা।
- **A option কেন ভুল:** `Mutual Exclusion` বলতে এক সময়ে সর্বোচ্চ একটি process/thread critical section-এ থাকার property। বোঝায়; প্রশ্নের বর্ণনা `Bounded Waiting`-এর।
- **B option কেন ভুল:** `Mutex` বলতে Ownership-based lock; holder unlock করে mutual exclusion দেয়। বোঝায়; প্রশ্নের বর্ণনা `Bounded Waiting`-এর।
- **C option কেন ভুল:** `Critical Section` বলতে Shared data/resource access করা code region যা race এড়াতে controlledভাবে execute করতে হয়। বোঝায়; প্রশ্নের বর্ণনা `Bounded Waiting`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Starvation prevention।
- **মনে রাখার টিপস:** Finite turn wait।

---

## প্রশ্ন 675 | Topic: Operating System > Process Synchronization I | Difficulty: Medium | Type: Calculation

Q. Atomic increment ছাড়া 100 thread প্রত্যেকে counter একবার বাড়ালে expected serial result কত?

A) 1
B) 99
C) 101
D) 100

**সঠিক উত্তর: D) 100**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি increment exactly once serial হলে 0+100=100।

#### Step-by-step সমাধান

```text
Initial counter=0
Operations=100 increments
Correct result=0+100=100
```
- **A option কেন ভুল:** Maximum lost-update extreme হিসেবে হতে পারে, expected correct result নয়।
- **B option কেন ভুল:** এক increment কম।
- **C option কেন ভুল:** এক increment বেশি।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Race হলে actual result 100-এর কম হতে পারে।
- **মনে রাখার টিপস:** Initial 0 + number of increments।

---

## প্রশ্ন 676 | Topic: Operating System > Process Synchronization I | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `Ownership-based lock; holder unlock করে mutual exclusion দেয়।`—এখানে কোন concept প্রযোজ্য?

A) Progress
B) Race Condition
C) Mutex
D) Compare-and-Swap

**সঠিক উত্তর: C) Mutex**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Ownership-based lock; holder unlock করে mutual exclusion দেয়।
- **A option কেন ভুল:** `Progress` বলতে Critical section খালি হলে interested process-এর মধ্যে selection অনির্দিষ্টভাবে postpone না করা condition। বোঝায়; প্রশ্নের বর্ণনা `Mutex`-এর।
- **B option কেন ভুল:** `Race Condition` বলতে Interleaving-dependent incorrect shared-state outcome। বোঝায়; প্রশ্নের বর্ণনা `Mutex`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Compare-and-Swap` বলতে Memory value expected হলে atomically new value বসায় এবং success জানায়। বোঝায়; প্রশ্নের বর্ণনা `Mutex`-এর।
- **Related Concept:** Binary state হলেও semaphore semantics এক নয়।
- **মনে রাখার টিপস:** Lock with owner।

---

## প্রশ্ন 677 | Topic: Operating System > Process Synchronization I | Difficulty: Hard | Type: Calculation

Q. Spinlock 2 microsecond অপেক্ষায় এবং sleep/wakeup overhead 20 microsecond হলে short wait-এর জন্য কোনটি যুক্তিযুক্ত?

A) Spinlock
B) Always blocking mutex
C) Disk semaphore
D) No synchronization

**সঠিক উত্তর: A) Spinlock**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Expected wait sleep/wakeup overhead-এর চেয়ে অনেক কম, তাই busy wait সস্তা হতে পারে।

#### Step-by-step সমাধান

```text
Expected spin cost = 2 us
Sleep/wakeup cost  = 20 us
2 < 20 -> spin can be cheaper
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** 20 µs overhead 2 µs wait-এর চেয়ে বেশি।
- **C option কেন ভুল:** এমন standard choice নয়।
- **D option কেন ভুল:** Shared critical section unsafe।
- **Related Concept:** Single-core বা long wait-এ spin wasteful।
- **মনে রাখার টিপস:** Wait খুব short হলে spin।

---

## প্রশ্ন 678 | Topic: Operating System > Process Synchronization I | Difficulty: Easy | Type: Theory

Q. `Race Condition` সম্পর্কে কোন statement সঠিক?

A) Interleaving-dependent incorrect shared-state outcome।
B) অন্য thread-এর দৃষ্টিতে indivisibleভাবে সম্পন্ন operation।
C) Waiting thread sleep না গিয়ে repeatedly lock পরীক্ষা করে।
D) Memory value expected হলে atomically new value বসায় এবং success জানায়।

**সঠিক উত্তর: A) Interleaving-dependent incorrect shared-state outcome।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Interleaving-dependent incorrect shared-state outcome।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Atomic Operation` ধারণাকে বর্ণনা করে; `Race Condition`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Spinlock` ধারণাকে বর্ণনা করে; `Race Condition`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Compare-and-Swap` ধারণাকে বর্ণনা করে; `Race Condition`-কে নয়।
- **Related Concept:** Critical section synchronization প্রয়োজন।
- **মনে রাখার টিপস:** Timing-dependent bug।

---

## প্রশ্ন 679 | Topic: Operating System > Process Synchronization I | Difficulty: Easy | Type: Tracing

Q. Test-and-Set lock-এ lock value initially 0। প্রথম thread atomic operation করলে old value 0 পায় ও lock 1 হয়। দ্বিতীয় thread সঙ্গে সঙ্গে কী old value পাবে?

A) 0
B) 1
C) -1
D) undefined

**সঠিক উত্তর: B) 1**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রথম thread lock 1 করেছে; দ্বিতীয় atomic exchange old locked state 1 দেখে।

#### Step-by-step সমাধান

```text
Initial lock=0
T1 test-and-set: returns0, lock=1
T2 test-and-set: returns1, lock remains1
```
- **A option কেন ভুল:** Lock এখনও free হলে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Binary lock value নয়।
- **D option কেন ভুল:** Atomic primitive defined old value দেয়।
- **Related Concept:** Old 0 পাওয়া thread lock acquire করে।
- **মনে রাখার টিপস:** 0=free, 1=locked।

---

## প্রশ্ন 680 | Topic: Operating System > Process Synchronization I | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Memory value expected হলে atomically new value বসায় এবং success জানায়।`

A) Critical Section
B) Compare-and-Swap
C) Spinlock
D) Mutex

**সঠিক উত্তর: B) Compare-and-Swap**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Memory value expected হলে atomically new value বসায় এবং success জানায়।
- **A option কেন ভুল:** `Critical Section` বলতে Shared data/resource access করা code region যা race এড়াতে controlledভাবে execute করতে হয়। বোঝায়; প্রশ্নের বর্ণনা `Compare-and-Swap`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Spinlock` বলতে Waiting thread sleep না গিয়ে repeatedly lock পরীক্ষা করে। বোঝায়; প্রশ্নের বর্ণনা `Compare-and-Swap`-এর।
- **D option কেন ভুল:** `Mutex` বলতে Ownership-based lock; holder unlock করে mutual exclusion দেয়। বোঝায়; প্রশ্নের বর্ণনা `Compare-and-Swap`-এর।
- **Related Concept:** Lock-free algorithm-এ ব্যবহৃত।
- **মনে রাখার টিপস:** Update if expected matches।

---


# Chapter Theory 58: Semaphore, Monitor এবং Classic Synchronization

## বিস্তারিত Theory Note

Semaphore operation atomic হতে হয়। Counting semaphore resource permits track করে; binary semaphore event বা exclusion দিতে পারে। Mutex ownership rule থাকায় যে thread lock নেয় সাধারণত সেটিই unlock করে।

Producer–Consumer-এ buffer metadata protect করার জন্য mutex এবং available slot/item count-এর জন্য separate semaphore লাগে। Condition variable wait lock atomically release করে, নইলে missed progress/deadlock হতে পারে।

## মূল ধারণার মানচিত্র

- **Semaphore:** Atomic wait/P ও signal/V operationসহ integer synchronization primitive।
- **Binary Semaphore:** Value সাধারণত 0/1; mutual exclusion বা event signaling-এ ব্যবহার।
- **Counting Semaphore:** একাধিক identical resource-এর available count track করে।
- **wait Operation:** Resource count decrement করে; unavailable হলে caller block/wait করতে পারে।
- **signal Operation:** Count increment করে এবং waiting entity wake করতে পারে।
- **Monitor:** Shared data ও procedure encapsulate করে implicit mutual exclusion এবং condition variable দেয় high-level construct।
- **Condition Variable:** Monitor/lock context-এ condition wait ও signal করার mechanism।
- **Producer-Consumer:** Producer buffer-এ item রাখে, consumer নেয়; empty/full ও mutual exclusion coordinate করতে হয়।
- **Readers-Writers:** Multiple reader concurrent হতে পারে, writer exclusive access চায়।
- **Dining Philosophers:** Multiple process resource acquisition থেকে deadlock/starvation illustrate করা classic problem।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Semaphore, Monitor এবং Classic Synchronization

## প্রশ্ন 681 | Topic: Operating System > Process Synchronization II | Difficulty: Easy | Type: Calculation

Q. Counting semaphore initial 4। দুই successful wait এবং এক signal-এর পরে value কত?

A) 1
B) 3
C) 2
D) 5

**সঠিক উত্তর: B) 3**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 4−2+1=3।

#### Step-by-step সমাধান

```text
Initial=4
After wait=3
After wait=2
After signal=3
```
- **A option কেন ভুল:** Signal বাদ/extra decrement।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Signal প্রয়োগ হয়নি।
- **D option কেন ভুল:** Wait-এর direction ভুল।
- **Related Concept:** Blocked waiter semantics implementationভেদে internal negative count হতে পারে; এখানে simple permit count।
- **মনে রাখার টিপস:** wait −1, signal +1।

---

## প্রশ্ন 682 | Topic: Operating System > Process Synchronization II | Difficulty: Medium | Type: Theory

Q. `Binary Semaphore` সম্পর্কে কোন statement সঠিক?

A) একাধিক identical resource-এর available count track করে।
B) Value সাধারণত 0/1; mutual exclusion বা event signaling-এ ব্যবহার।
C) Multiple process resource acquisition থেকে deadlock/starvation illustrate করা classic problem।
D) Atomic wait/P ও signal/V operationসহ integer synchronization primitive।

**সঠিক উত্তর: B) Value সাধারণত 0/1; mutual exclusion বা event signaling-এ ব্যবহার।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Value সাধারণত 0/1; mutual exclusion বা event signaling-এ ব্যবহার।
- **A option কেন ভুল:** এই statementটি `Counting Semaphore` ধারণাকে বর্ণনা করে; `Binary Semaphore`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `Dining Philosophers` ধারণাকে বর্ণনা করে; `Binary Semaphore`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Semaphore` ধারণাকে বর্ণনা করে; `Binary Semaphore`-কে নয়।
- **Related Concept:** Mutex-এর ownership semantics নাও থাকে।
- **মনে রাখার টিপস:** Two-state semaphore।

---

## প্রশ্ন 683 | Topic: Operating System > Process Synchronization II | Difficulty: Hard | Type: Calculation

Q. ৫টি identical printer resource control করতে counting semaphore-এর initial value কত হওয়া উচিত?

A) 0
B) 1
C) 4
D) 5

**সঠিক উত্তর: D) 5**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি available printer একটি permit।
- **A option কেন ভুল:** কোনো resource available দেখাবে না।
- **B option কেন ভুল:** শুধু একটি resource allow।
- **C option কেন ভুল:** এক printer কম।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Resource pool size = initial count।
- **মনে রাখার টিপস:** যত resource, তত permit।

---

## প্রশ্ন 684 | Topic: Operating System > Process Synchronization II | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Resource count decrement করে; unavailable হলে caller block/wait করতে পারে।`

A) wait Operation
B) Monitor
C) Condition Variable
D) Binary Semaphore

**সঠিক উত্তর: A) wait Operation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Resource count decrement করে; unavailable হলে caller block/wait করতে পারে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Monitor` বলতে Shared data ও procedure encapsulate করে implicit mutual exclusion এবং condition variable দেয় high-level construct। বোঝায়; প্রশ্নের বর্ণনা `wait Operation`-এর।
- **C option কেন ভুল:** `Condition Variable` বলতে Monitor/lock context-এ condition wait ও signal করার mechanism। বোঝায়; প্রশ্নের বর্ণনা `wait Operation`-এর।
- **D option কেন ভুল:** `Binary Semaphore` বলতে Value সাধারণত 0/1; mutual exclusion বা event signaling-এ ব্যবহার। বোঝায়; প্রশ্নের বর্ণনা `wait Operation`-এর।
- **Related Concept:** Atomic operation।
- **মনে রাখার টিপস:** Acquire one permit।

---

## প্রশ্ন 685 | Topic: Operating System > Process Synchronization II | Difficulty: Easy | Type: Theory

Q. `signal Operation` সম্পর্কে কোন statement সঠিক?

A) Multiple process resource acquisition থেকে deadlock/starvation illustrate করা classic problem।
B) Value সাধারণত 0/1; mutual exclusion বা event signaling-এ ব্যবহার।
C) Count increment করে এবং waiting entity wake করতে পারে।
D) একাধিক identical resource-এর available count track করে।

**সঠিক উত্তর: C) Count increment করে এবং waiting entity wake করতে পারে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Count increment করে এবং waiting entity wake করতে পারে।
- **A option কেন ভুল:** এই statementটি `Dining Philosophers` ধারণাকে বর্ণনা করে; `signal Operation`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Binary Semaphore` ধারণাকে বর্ণনা করে; `signal Operation`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Counting Semaphore` ধারণাকে বর্ণনা করে; `signal Operation`-কে নয়।
- **Related Concept:** Release/notify semantics।
- **মনে রাখার টিপস:** Return one permit।

---

## প্রশ্ন 686 | Topic: Operating System > Process Synchronization II | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Shared data ও procedure encapsulate করে implicit mutual exclusion এবং condition variable দেয় high-level construct।`—এখানে কোন concept প্রযোজ্য?

A) Readers-Writers
B) Semaphore
C) Monitor
D) Binary Semaphore

**সঠিক উত্তর: C) Monitor**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Shared data ও procedure encapsulate করে implicit mutual exclusion এবং condition variable দেয় high-level construct।
- **A option কেন ভুল:** `Readers-Writers` বলতে Multiple reader concurrent হতে পারে, writer exclusive access চায়। বোঝায়; প্রশ্নের বর্ণনা `Monitor`-এর।
- **B option কেন ভুল:** `Semaphore` বলতে Atomic wait/P ও signal/V operationসহ integer synchronization primitive। বোঝায়; প্রশ্নের বর্ণনা `Monitor`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Binary Semaphore` বলতে Value সাধারণত 0/1; mutual exclusion বা event signaling-এ ব্যবহার। বোঝায়; প্রশ্নের বর্ণনা `Monitor`-এর।
- **Related Concept:** Language/runtime support হতে পারে।
- **মনে রাখার টিপস:** Synchronized object abstraction।

---

## প্রশ্ন 687 | Topic: Operating System > Process Synchronization II | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Monitor/lock context-এ condition wait ও signal করার mechanism।`

A) signal Operation
B) Readers-Writers
C) Counting Semaphore
D) Condition Variable

**সঠিক উত্তর: D) Condition Variable**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Monitor/lock context-এ condition wait ও signal করার mechanism।
- **A option কেন ভুল:** `signal Operation` বলতে Count increment করে এবং waiting entity wake করতে পারে। বোঝায়; প্রশ্নের বর্ণনা `Condition Variable`-এর।
- **B option কেন ভুল:** `Readers-Writers` বলতে Multiple reader concurrent হতে পারে, writer exclusive access চায়। বোঝায়; প্রশ্নের বর্ণনা `Condition Variable`-এর।
- **C option কেন ভুল:** `Counting Semaphore` বলতে একাধিক identical resource-এর available count track করে। বোঝায়; প্রশ্নের বর্ণনা `Condition Variable`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Wait lock atomically release করে।
- **মনে রাখার টিপস:** Sleep until condition।

---

## প্রশ্ন 688 | Topic: Operating System > Process Synchronization II | Difficulty: Medium | Type: Calculation

Q. Bounded buffer size 8, বর্তমানে 3 item। `full` ও `empty` semaphore value যথাক্রমে কত?

A) 5 ও 3
B) 8 ও 0
C) 3 ও 5
D) 3 ও 8

**সঠিক উত্তর: C) 3 ও 5**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** full=item count=3; empty=8−3=5।

#### Step-by-step সমাধান

```text
Capacity=8
Items=3
full=3
empty=8-3=5
```
- **A option কেন ভুল:** দুই value উল্টো।
- **B option কেন ভুল:** Buffer full ধরে নেওয়া।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Empty slot capacity থেকে item বাদ দেওয়া হয়নি।
- **Related Concept:** Producer waits empty; consumer waits full।
- **মনে রাখার টিপস:** full+empty=capacity।

---

## প্রশ্ন 689 | Topic: Operating System > Process Synchronization II | Difficulty: Hard | Type: Calculation

Q. Readers-Writers lock-এ বর্তমানে 4 reader active। নতুন reader policy অনুযায়ী allowed এবং writer waiting নেই। Active reader count কত হবে?

A) 1
B) 4
C) Blocked
D) 5

**সঠিক উত্তর: D) 5**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Compatible reader আরও যোগ হলে count 4+1=5।

#### Step-by-step সমাধান

```text
Current readers=4
New allowed reader=1
Total=5
```
- **A option কেন ভুল:** Count reset হয় না।
- **B option কেন ভুল:** নতুন reader যোগ করা হয়নি।
- **C option কেন ভুল:** Writer active/writer-preference condition দেওয়া নেই।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Writer active হলে reader block।
- **মনে রাখার টিপস:** Reader count increment।

---

## প্রশ্ন 690 | Topic: Operating System > Process Synchronization II | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Multiple process resource acquisition থেকে deadlock/starvation illustrate করা classic problem।`

A) Semaphore
B) Condition Variable
C) Dining Philosophers
D) Readers-Writers

**সঠিক উত্তর: C) Dining Philosophers**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Multiple process resource acquisition থেকে deadlock/starvation illustrate করা classic problem।
- **A option কেন ভুল:** `Semaphore` বলতে Atomic wait/P ও signal/V operationসহ integer synchronization primitive। বোঝায়; প্রশ্নের বর্ণনা `Dining Philosophers`-এর।
- **B option কেন ভুল:** `Condition Variable` বলতে Monitor/lock context-এ condition wait ও signal করার mechanism। বোঝায়; প্রশ্নের বর্ণনা `Dining Philosophers`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Readers-Writers` বলতে Multiple reader concurrent হতে পারে, writer exclusive access চায়। বোঝায়; প্রশ্নের বর্ণনা `Dining Philosophers`-এর।
- **Related Concept:** Ordering বা waiter solution।
- **মনে রাখার টিপস:** Fork competition problem।

---


# Chapter Theory 59: Deadlock, Safety এবং Banker’s Algorithm

## বিস্তারিত Theory Note

Deadlock-এর চারটি necessary condition একসঙ্গে থাকলে deadlock সম্ভব; নিশ্চিত নয়। Prevention একটি condition ভাঙে, avoidance future safe sequence যাচাই করে, detection ঘটার পরে খুঁজে।

Safe state-এ অন্তত একটি completion sequence আছে। Unsafe state অবিলম্বে deadlock নয়, কিন্তু future allocation pattern deadlock ঘটাতে পারে।

## মূল ধারণার মানচিত্র

- **Deadlock:** Process set এমনভাবে resource-এর অপেক্ষায় যেখানে প্রত্যেকে অন্যের held resource চায় এবং কেউ progress করতে পারে না।
- **Mutual Exclusion Condition:** কমপক্ষে একটি resource non-shareable।
- **Hold and Wait:** Process অন্তত একটি resource ধরে অন্য resource-এর অপেক্ষা করে।
- **No Preemption Condition:** Resource process থেকে জোর করে কেড়ে নেওয়া যায় না; voluntary release প্রয়োজন।
- **Circular Wait:** Process-resource waiting cycle থাকে।
- **Deadlock Prevention:** কমপক্ষে একটি necessary condition structurally অসম্ভব করা।
- **Deadlock Avoidance:** প্রতিটি allocation-এর আগে system safe state-এ থাকবে কি না যাচাই করা।
- **Deadlock Detection:** Deadlock ঘটতে দেওয়া, পরে wait-for/resource graph algorithm দিয়ে শনাক্ত।
- **Safe State:** এমন state যেখানে সব process complete করার অন্তত একটি safe sequence আছে।
- **Banker’s Algorithm:** Available, Allocation, Max/Need ব্যবহার করে tentative grant-এর safety পরীক্ষা।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Deadlock, Safety এবং Banker’s Algorithm

## প্রশ্ন 691 | Topic: Operating System > Deadlock | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Process set এমনভাবে resource-এর অপেক্ষায় যেখানে প্রত্যেকে অন্যের held resource চায় এবং কেউ progress করতে পারে না।`

A) Deadlock
B) Hold and Wait
C) Circular Wait
D) Mutual Exclusion Condition

**সঠিক উত্তর: A) Deadlock**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Process set এমনভাবে resource-এর অপেক্ষায় যেখানে প্রত্যেকে অন্যের held resource চায় এবং কেউ progress করতে পারে না।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Hold and Wait` বলতে Process অন্তত একটি resource ধরে অন্য resource-এর অপেক্ষা করে। বোঝায়; প্রশ্নের বর্ণনা `Deadlock`-এর।
- **C option কেন ভুল:** `Circular Wait` বলতে Process-resource waiting cycle থাকে। বোঝায়; প্রশ্নের বর্ণনা `Deadlock`-এর।
- **D option কেন ভুল:** `Mutual Exclusion Condition` বলতে কমপক্ষে একটি resource non-shareable। বোঝায়; প্রশ্নের বর্ণনা `Deadlock`-এর।
- **Related Concept:** Four Coffman conditions প্রয়োজন।
- **মনে রাখার টিপস:** Circular permanent waiting।

---

## প্রশ্ন 692 | Topic: Operating System > Deadlock | Difficulty: Medium | Type: Theory

Q. `Mutual Exclusion Condition` সম্পর্কে কোন statement সঠিক?

A) কমপক্ষে একটি necessary condition structurally অসম্ভব করা।
B) Available, Allocation, Max/Need ব্যবহার করে tentative grant-এর safety পরীক্ষা।
C) প্রতিটি allocation-এর আগে system safe state-এ থাকবে কি না যাচাই করা।
D) কমপক্ষে একটি resource non-shareable।

**সঠিক উত্তর: D) কমপক্ষে একটি resource non-shareable।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** কমপক্ষে একটি resource non-shareable।
- **A option কেন ভুল:** এই statementটি `Deadlock Prevention` ধারণাকে বর্ণনা করে; `Mutual Exclusion Condition`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Banker’s Algorithm` ধারণাকে বর্ণনা করে; `Mutual Exclusion Condition`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Deadlock Avoidance` ধারণাকে বর্ণনা করে; `Mutual Exclusion Condition`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Deadlock necessary condition।
- **মনে রাখার টিপস:** One holder only।

---

## প্রশ্ন 693 | Topic: Operating System > Deadlock | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `Process অন্তত একটি resource ধরে অন্য resource-এর অপেক্ষা করে।`—এখানে কোন concept প্রযোজ্য?

A) No Preemption Condition
B) Circular Wait
C) Deadlock Avoidance
D) Hold and Wait

**সঠিক উত্তর: D) Hold and Wait**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Process অন্তত একটি resource ধরে অন্য resource-এর অপেক্ষা করে।
- **A option কেন ভুল:** `No Preemption Condition` বলতে Resource process থেকে জোর করে কেড়ে নেওয়া যায় না; voluntary release প্রয়োজন। বোঝায়; প্রশ্নের বর্ণনা `Hold and Wait`-এর।
- **B option কেন ভুল:** `Circular Wait` বলতে Process-resource waiting cycle থাকে। বোঝায়; প্রশ্নের বর্ণনা `Hold and Wait`-এর।
- **C option কেন ভুল:** `Deadlock Avoidance` বলতে প্রতিটি allocation-এর আগে system safe state-এ থাকবে কি না যাচাই করা। বোঝায়; প্রশ্নের বর্ণনা `Hold and Wait`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Deadlock necessary condition।
- **মনে রাখার টিপস:** Hold one, wait another।

---

## প্রশ্ন 694 | Topic: Operating System > Deadlock | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Resource process থেকে জোর করে কেড়ে নেওয়া যায় না; voluntary release প্রয়োজন।`

A) Deadlock Prevention
B) Deadlock Detection
C) Deadlock Avoidance
D) No Preemption Condition

**সঠিক উত্তর: D) No Preemption Condition**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Resource process থেকে জোর করে কেড়ে নেওয়া যায় না; voluntary release প্রয়োজন।
- **A option কেন ভুল:** `Deadlock Prevention` বলতে কমপক্ষে একটি necessary condition structurally অসম্ভব করা। বোঝায়; প্রশ্নের বর্ণনা `No Preemption Condition`-এর।
- **B option কেন ভুল:** `Deadlock Detection` বলতে Deadlock ঘটতে দেওয়া, পরে wait-for/resource graph algorithm দিয়ে শনাক্ত। বোঝায়; প্রশ্নের বর্ণনা `No Preemption Condition`-এর।
- **C option কেন ভুল:** `Deadlock Avoidance` বলতে প্রতিটি allocation-এর আগে system safe state-এ থাকবে কি না যাচাই করা। বোঝায়; প্রশ্নের বর্ণনা `No Preemption Condition`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Deadlock necessary condition।
- **মনে রাখার টিপস:** Cannot forcibly take।

---

## প্রশ্ন 695 | Topic: Operating System > Deadlock | Difficulty: Medium | Type: Tracing

Q. P1 R2-এর অপেক্ষায়, R2 P2 ধরে; P2 R1-এর অপেক্ষায়, R1 P1 ধরে। কোন condition স্পষ্ট?

A) No mutual exclusion
B) Safe sequence
C) Circular Wait
D) Preemption

**সঠিক উত্তর: C) Circular Wait**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** P1→R2→P2→R1→P1 cycle।

#### Step-by-step সমাধান

```text
P1 waits R2
R2 held by P2
P2 waits R1
R1 held by P1
Cycle: P1 -> R2 -> P2 -> R1 -> P1
```
- **A option কেন ভুল:** Resources exclusiveভাবে held।
- **B option কেন ভুল:** দুজনেই পরস্পরের জন্য অপেক্ষা করছে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Resource কেড়ে নেওয়ার তথ্য নেই।
- **Related Concept:** Single-instance resource graph cycle deadlock নির্দেশ করে।
- **মনে রাখার টিপস:** Wait cycle আঁকুন।

---

## প্রশ্ন 696 | Topic: Operating System > Deadlock | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `কমপক্ষে একটি necessary condition structurally অসম্ভব করা।`—এখানে কোন concept প্রযোজ্য?

A) Deadlock Prevention
B) Mutual Exclusion Condition
C) Deadlock
D) Circular Wait

**সঠিক উত্তর: A) Deadlock Prevention**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** কমপক্ষে একটি necessary condition structurally অসম্ভব করা।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Mutual Exclusion Condition` বলতে কমপক্ষে একটি resource non-shareable। বোঝায়; প্রশ্নের বর্ণনা `Deadlock Prevention`-এর।
- **C option কেন ভুল:** `Deadlock` বলতে Process set এমনভাবে resource-এর অপেক্ষায় যেখানে প্রত্যেকে অন্যের held resource চায় এবং কেউ progress করতে পারে না। বোঝায়; প্রশ্নের বর্ণনা `Deadlock Prevention`-এর।
- **D option কেন ভুল:** `Circular Wait` বলতে Process-resource waiting cycle থাকে। বোঝায়; প্রশ্নের বর্ণনা `Deadlock Prevention`-এর।
- **Related Concept:** Resource ordering circular wait ভাঙে।
- **মনে রাখার টিপস:** Break a Coffman condition।

---

## প্রশ্ন 697 | Topic: Operating System > Deadlock | Difficulty: Easy | Type: Tracing

Q. Available resource=3। P1 remaining Need=2, P2 Need=4; safety check-এ প্রথমে কোন process complete হতে পারে?

A) P2
B) P1
C) দুজনই নয়
D) শুধু নতুন P3

**সঠিক উত্তর: B) P1**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** P1 need 2≤available3; P2 need4>3।

#### Step-by-step সমাধান

```text
Work=3
P1 Need=2 <=3 -> can finish
P2 Need=4 >3 -> cannot finish first
```
- **A option কেন ভুল:** বর্তমান available যথেষ্ট নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** P1 feasible।
- **D option কেন ভুল:** P3 তথ্য নেই।
- **Related Concept:** Complete process allocation release করলে available বাড়ে।
- **মনে রাখার টিপস:** Need≤Work process খুঁজুন।

---

## প্রশ্ন 698 | Topic: Operating System > Deadlock | Difficulty: Medium | Type: Theory

Q. `Deadlock Detection` সম্পর্কে কোন statement সঠিক?

A) Process-resource waiting cycle থাকে।
B) Deadlock ঘটতে দেওয়া, পরে wait-for/resource graph algorithm দিয়ে শনাক্ত।
C) কমপক্ষে একটি resource non-shareable।
D) কমপক্ষে একটি necessary condition structurally অসম্ভব করা।

**সঠিক উত্তর: B) Deadlock ঘটতে দেওয়া, পরে wait-for/resource graph algorithm দিয়ে শনাক্ত।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Deadlock ঘটতে দেওয়া, পরে wait-for/resource graph algorithm দিয়ে শনাক্ত।
- **A option কেন ভুল:** এই statementটি `Circular Wait` ধারণাকে বর্ণনা করে; `Deadlock Detection`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `Mutual Exclusion Condition` ধারণাকে বর্ণনা করে; `Deadlock Detection`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Deadlock Prevention` ধারণাকে বর্ণনা করে; `Deadlock Detection`-কে নয়।
- **Related Concept:** Recovery দরকার।
- **মনে রাখার টিপস:** Find after occurrence।

---

## প্রশ্ন 699 | Topic: Operating System > Deadlock | Difficulty: Medium | Type: Calculation

Q. এক safe sequence-এ 4টি process থাকলে sequence-এ process entry কতটি?

A) 4
B) 3
C) 8
D) 16

**সঠিক উত্তর: A) 4**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Safe sequence প্রতিটি process একবার completion order-এ রাখে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এক process বাদ।
- **C option কেন ভুল:** দ্বিগুণ।
- **D option কেন ভুল:** Square।
- **Related Concept:** একাধিক safe sequence থাকতে পারে।
- **মনে রাখার টিপস:** n process → n positions।

---

## প্রশ্ন 700 | Topic: Operating System > Deadlock | Difficulty: Medium | Type: Calculation

Q. Total resource instances 10, currently allocated 7 হলে available কত?

A) 17
B) 7
C) 3
D) 10

**সঠিক উত্তর: C) 3**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Available=Total−Allocated=3।

#### Step-by-step সমাধান

```text
Total=10
Allocated=7
Available=10-7=3
```
- **A option কেন ভুল:** যোগ।
- **B option কেন ভুল:** Allocated value।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Total value।
- **Related Concept:** Banker state-এ available vector component-wise subtract।
- **মনে রাখার টিপস:** Total−allocated।

---


# Chapter Theory 60: Contiguous Memory Allocation এবং Fragmentation

## বিস্তারিত Theory Note

Contiguous allocation সহজ address translation দিলেও free-space management কঠিন। Internal fragmentation allocated unit-এর ভিতরে; external fragmentation free space-এর মধ্যে ছড়িয়ে থাকা hole।

First/Best/Worst Fit selection semantics প্রশ্নে hole order গুরুত্বপূর্ণ। Compaction external fragmentation কমায়, কিন্তু running process relocate করা ও large memory copy expensive।

## মূল ধারণার মানচিত্র

- **Logical Address:** CPU/process যে virtual address তৈরি করে।
- **Physical Address:** Main memory hardware-এ actual location address।
- **Contiguous Allocation:** Process-কে একটানা physical memory block দেওয়া।
- **Internal Fragmentation:** Allocated block-এর ভিতরে unused space।
- **External Fragmentation:** মোট free memory যথেষ্ট হলেও ছোট বিচ্ছিন্ন hole-এ ভাগ হওয়া।
- **First Fit:** প্রথম যথেষ্ট বড় free hole allocate করে।
- **Best Fit:** সবচেয়ে ছোট যথেষ্ট বড় hole বেছে।
- **Worst Fit:** সবচেয়ে বড় hole থেকে allocate।
- **Compaction:** Allocated block সরিয়ে free hole একত্র করে external fragmentation কমানো।
- **Swapping:** Process/address-space memory ও backing store-এর মধ্যে সাময়িক স্থানান্তর।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Contiguous Memory Allocation এবং Fragmentation

# Batch 16 — Question 701–750

## প্রশ্ন 701 | Topic: Operating System > Memory Management I | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`CPU/process যে virtual address তৈরি করে।`

A) Logical Address
B) Compaction
C) Worst Fit
D) Physical Address

**সঠিক উত্তর: A) Logical Address**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** CPU/process যে virtual address তৈরি করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Compaction` বলতে Allocated block সরিয়ে free hole একত্র করে external fragmentation কমানো। বোঝায়; প্রশ্নের বর্ণনা `Logical Address`-এর।
- **C option কেন ভুল:** `Worst Fit` বলতে সবচেয়ে বড় hole থেকে allocate। বোঝায়; প্রশ্নের বর্ণনা `Logical Address`-এর।
- **D option কেন ভুল:** `Physical Address` বলতে Main memory hardware-এ actual location address। বোঝায়; প্রশ্নের বর্ণনা `Logical Address`-এর।
- **Related Concept:** MMU physical address-এ translate করে।
- **মনে রাখার টিপস:** Process-visible address।

---

## প্রশ্ন 702 | Topic: Operating System > Memory Management I | Difficulty: Medium | Type: Theory

Q. `Physical Address` সম্পর্কে কোন statement সঠিক?

A) Allocated block সরিয়ে free hole একত্র করে external fragmentation কমানো।
B) মোট free memory যথেষ্ট হলেও ছোট বিচ্ছিন্ন hole-এ ভাগ হওয়া।
C) Process-কে একটানা physical memory block দেওয়া।
D) Main memory hardware-এ actual location address।

**সঠিক উত্তর: D) Main memory hardware-এ actual location address।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Main memory hardware-এ actual location address।
- **A option কেন ভুল:** এই statementটি `Compaction` ধারণাকে বর্ণনা করে; `Physical Address`-কে নয়।
- **B option কেন ভুল:** এই statementটি `External Fragmentation` ধারণাকে বর্ণনা করে; `Physical Address`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Contiguous Allocation` ধারণাকে বর্ণনা করে; `Physical Address`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Address bus/DRAM location।
- **মনে রাখার টিপস:** RAM location।

---

## প্রশ্ন 703 | Topic: Operating System > Memory Management I | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Process-কে একটানা physical memory block দেওয়া।`—এখানে কোন concept প্রযোজ্য?

A) Internal Fragmentation
B) Worst Fit
C) Best Fit
D) Contiguous Allocation

**সঠিক উত্তর: D) Contiguous Allocation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Process-কে একটানা physical memory block দেওয়া।
- **A option কেন ভুল:** `Internal Fragmentation` বলতে Allocated block-এর ভিতরে unused space। বোঝায়; প্রশ্নের বর্ণনা `Contiguous Allocation`-এর।
- **B option কেন ভুল:** `Worst Fit` বলতে সবচেয়ে বড় hole থেকে allocate। বোঝায়; প্রশ্নের বর্ণনা `Contiguous Allocation`-এর।
- **C option কেন ভুল:** `Best Fit` বলতে সবচেয়ে ছোট যথেষ্ট বড় hole বেছে। বোঝায়; প্রশ্নের বর্ণনা `Contiguous Allocation`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** External fragmentation হতে পারে।
- **মনে রাখার টিপস:** One continuous region।

---

## প্রশ্ন 704 | Topic: Operating System > Memory Management I | Difficulty: Medium | Type: Calculation

Q. Fixed partition 16 KB-তে 13 KB process রাখা হলে internal fragmentation কত?

A) 3 KB
B) 13 KB
C) 16 KB
D) 29 KB

**সঠিক উত্তর: A) 3 KB**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Allocated block−used size=16−13=3 KB।

#### Step-by-step সমাধান

```text
Partition=16 KB
Process=13 KB
Internal waste=16-13=3 KB
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Used size।
- **C option কেন ভুল:** Whole partition।
- **D option কেন ভুল:** যোগ।
- **Related Concept:** Fixed allocation leftover inside block internal fragmentation।
- **মনে রাখার টিপস:** Block−request।

---

## প্রশ্ন 705 | Topic: Operating System > Memory Management I | Difficulty: Hard | Type: Tracing

Q. Free holes 10 KB, 6 KB, 12 KB; request 7 KB। First Fit কোন hole নেবে?

A) 6 KB
B) 12 KB
C) কোনোটিই নয়
D) 10 KB

**সঠিক উত্তর: D) 10 KB**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** List order-এ প্রথম adequate hole 10 KB।

#### Step-by-step সমাধান

```text
Request=7
Hole1=10 >=7 -> select immediately
```
- **A option কেন ভুল:** Request-এর চেয়ে ছোট।
- **B option কেন ভুল:** Adequate হলেও প্রথম নয়।
- **C option কেন ভুল:** 10 ও12 adequate।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** First Fit size-minimum নয়, order-first।
- **মনে রাখার টিপস:** বাম থেকে প্রথম fitting hole।

---

## প্রশ্ন 706 | Topic: Operating System > Memory Management I | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `প্রথম যথেষ্ট বড় free hole allocate করে।`—এখানে কোন concept প্রযোজ্য?

A) Swapping
B) Best Fit
C) First Fit
D) Worst Fit

**সঠিক উত্তর: C) First Fit**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রথম যথেষ্ট বড় free hole allocate করে।
- **A option কেন ভুল:** `Swapping` বলতে Process/address-space memory ও backing store-এর মধ্যে সাময়িক স্থানান্তর। বোঝায়; প্রশ্নের বর্ণনা `First Fit`-এর।
- **B option কেন ভুল:** `Best Fit` বলতে সবচেয়ে ছোট যথেষ্ট বড় hole বেছে। বোঝায়; প্রশ্নের বর্ণনা `First Fit`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Worst Fit` বলতে সবচেয়ে বড় hole থেকে allocate। বোঝায়; প্রশ্নের বর্ণনা `First Fit`-এর।
- **Related Concept:** Fast search, fragmentation pattern নির্ভর।
- **মনে রাখার টিপস:** First adequate hole।

---

## প্রশ্ন 707 | Topic: Operating System > Memory Management I | Difficulty: Medium | Type: Tracing

Q. একই holes 10, 6, 12 KB এবং request 7 KB। Best Fit কোনটি?

A) 6 KB
B) 12 KB
C) 10 KB
D) 28 KB

**সঠিক উত্তর: C) 10 KB**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Adequate holes 10 ও12; smallest adequate 10।

#### Step-by-step সমাধান

```text
Adequate={10,12}
min=10 KB
```
- **A option কেন ভুল:** Fit করে না।
- **B option কেন ভুল:** Larger adequate, best নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Total free, single hole নয়।
- **Related Concept:** Best Fit candidate filter তারপর minimum।
- **মনে রাখার টিপস:** যেটি fit করে তাদের মধ্যে smallest।

---

## প্রশ্ন 708 | Topic: Operating System > Memory Management I | Difficulty: Easy | Type: Calculation

Q. Holes 10, 6, 12 KB এবং request 7 KB। Worst Fit কোন hole নেবে?

A) 6 KB
B) 10 KB
C) 12 KB
D) 7 KB

**সঠিক উত্তর: C) 12 KB**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Largest adequate hole 12।
- **A option কেন ভুল:** Fit নয়।
- **B option কেন ভুল:** Largest নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এমন hole নেই।
- **Related Concept:** Worst Fit largest free block ব্যবহার করে।
- **মনে রাখার টিপস:** Adequate maximum।

---

## প্রশ্ন 709 | Topic: Operating System > Memory Management I | Difficulty: Medium | Type: Calculation

Q. Free holes 4+5+7 KB, কিন্তু largest request 10 KB fit করে না। Total free 16 KB। সমস্যাটি কী?

A) External fragmentation
B) Internal fragmentation
C) No free memory
D) Deadlock

**সঠিক উত্তর: A) External fragmentation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Total free যথেষ্ট, কিন্তু contiguous 10 KB hole নেই।

#### Step-by-step সমাধান

```text
Total free=4+5+7=16 KB
Largest hole=7 KB
Request=10 KB
16>=10 but 7<10 -> external fragmentation
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Allocated block-এর ভিতরের waste নয়।
- **C option কেন ভুল:** 16 KB free আছে।
- **D option কেন ভুল:** Resource waiting cycle নয়।
- **Related Concept:** Compaction hole একত্র করতে পারে।
- **মনে রাখার টিপস:** Enough total, no large block = external।

---

## প্রশ্ন 710 | Topic: Operating System > Memory Management I | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Process/address-space memory ও backing store-এর মধ্যে সাময়িক স্থানান্তর।`

A) First Fit
B) Swapping
C) Contiguous Allocation
D) Compaction

**সঠিক উত্তর: B) Swapping**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Process/address-space memory ও backing store-এর মধ্যে সাময়িক স্থানান্তর।
- **A option কেন ভুল:** `First Fit` বলতে প্রথম যথেষ্ট বড় free hole allocate করে। বোঝায়; প্রশ্নের বর্ণনা `Swapping`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Contiguous Allocation` বলতে Process-কে একটানা physical memory block দেওয়া। বোঝায়; প্রশ্নের বর্ণনা `Swapping`-এর।
- **D option কেন ভুল:** `Compaction` বলতে Allocated block সরিয়ে free hole একত্র করে external fragmentation কমানো। বোঝায়; প্রশ্নের বর্ণনা `Swapping`-এর।
- **Related Concept:** I/O expensive।
- **মনে রাখার টিপস:** Move process out/in।

---


# Chapter Theory 61: Paging এবং Address Translation

## বিস্তারিত Theory Note

Paging virtual page-কে arbitrary physical frame-এ map করে। Offset unchanged থাকে; page number page table lookup-এর মাধ্যমে frame number হয়। Page size power of two হওয়ায় address bit field সহজে ভাগ করা যায়।

Page-table memory বড় হতে পারে, তাই multi-level, hashed বা inverted structure ব্যবহৃত হয়। Protection, dirty ও reference bit replacement এবং access control-এ গুরুত্বপূর্ণ।

## মূল ধারণার মানচিত্র

- **Paging:** Logical memory fixed-size page এবং physical memory same-size frame-এ ভাগ করে non-contiguous allocation।
- **Page:** Virtual/logical address space-এর fixed-size unit।
- **Frame:** Physical memory-এর page-size fixed block।
- **Page Table:** Virtual page number-কে physical frame number ও permission/status bit-এ map করে।
- **Page Offset:** Page-এর ভিতরের byte position, translation-এ অপরিবর্তিত থাকে।
- **Page Table Entry:** Frame number, valid, protection, dirty, referenced ইত্যাদি bit ধারণ করে।
- **Valid Bit:** Page mapping process address space/physical presence policy অনুযায়ী valid কি না জানায়।
- **Dirty Bit:** Page memory-তে পরিবর্তিত হয়েছে কি না; eviction-এ disk write দরকার হতে পারে।
- **Multi-level Page Table:** Sparse virtual space-এর unused page-table অংশ allocate না করে hierarchy ব্যবহার।
- **Inverted Page Table:** প্রতি virtual page নয়, প্রতি physical frame-এর জন্য mapping entry রাখে।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Paging এবং Address Translation

## প্রশ্ন 711 | Topic: Operating System > Memory Management II | Difficulty: Hard | Type: Calculation

Q. Logical address space 16 KB এবং page size 1 KB হলে page সংখ্যা কত?

A) 8
B) 16
C) 32
D) 1024

**সঠিক উত্তর: B) 16**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 16/1=16 page।

#### Step-by-step সমাধান

```text
Pages=16 KB/1 KB=16
```
- **A option কেন ভুল:** 2 KB page ধরে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** 0.5 KB page।
- **D option কেন ভুল:** Bytes per KB-এর সঙ্গে গুলিয়েছে।
- **Related Concept:** Address space/page size।
- **মনে রাখার টিপস:** একই unit-এ ভাগ।

---

## প্রশ্ন 712 | Topic: Operating System > Memory Management II | Difficulty: Medium | Type: Calculation

Q. Page size 4 KB হলে 32-bit byte address-এর offset bit কত?

A) 10
B) 12
C) 16
D) 20

**সঠিক উত্তর: B) 12**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 4 KB=4096=2^12 byte।

#### Step-by-step সমাধান

```text
4 KB=4x1024=4096=2^12
Offset bits=12
```
- **A option কেন ভুল:** 1 KB-এর offset।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** 64 KB page।
- **D option কেন ভুল:** Page number bit-এর সঙ্গে গুলিয়েছে।
- **Related Concept:** Power-of-two page size-এর log₂।
- **মনে রাখার টিপস:** 4 KB = 2¹²।

---

## প্রশ্ন 713 | Topic: Operating System > Memory Management II | Difficulty: Easy | Type: Calculation

Q. Physical memory 64 KB, frame size 4 KB। Frame সংখ্যা কত?

A) 8
B) 32
C) 64
D) 16

**সঠিক উত্তর: D) 16**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 64/4=16।

#### Step-by-step সমাধান

```text
Frames=64/4=16
```
- **A option কেন ভুল:** 8 KB frame ধরে।
- **B option কেন ভুল:** 2 KB frame ধরে।
- **C option কেন ভুল:** KB count।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Physical/frame size।
- **মনে রাখার টিপস:** Memory ভাগ frame size।

---

## প্রশ্ন 714 | Topic: Operating System > Memory Management II | Difficulty: Easy | Type: Calculation

Q. Page 5 frame 9-এ map; page size 1024 byte; logical offset 100। Physical address কত?

A) 5220
B) 9316
C) 9216
D) 10240

**সঠিক উত্তর: B) 9316**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Frame base=9×1024=9216; +100=9316।

#### Step-by-step সমাধান

```text
Frame base=9x1024=9216
Offset=100
Physical=9216+100=9316
```
- **A option কেন ভুল:** Page number ব্যবহার করে physical base।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Offset যোগ হয়নি।
- **D option কেন ভুল:** Frame10 base।
- **Related Concept:** Physical=frame×page size+offset।
- **মনে রাখার টিপস:** Frame number ব্যবহার করুন, page নয়।

---

## প্রশ্ন 715 | Topic: Operating System > Memory Management II | Difficulty: Easy | Type: Calculation

Q. Logical address 3500, page size 1000 byte। Page number ও offset কত?

A) page3, offset500
B) page4, offset500
C) page3, offset0
D) page2, offset1500

**সঠিক উত্তর: A) page3, offset500**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Integer quotient 3, remainder 500 (zero-based page)।

#### Step-by-step সমাধান

```text
3500/1000 -> quotient3 remainder500
Page=3
Offset=500
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Page numbering one-based ধরা।
- **C option কেন ভুল:** Remainder বাদ।
- **D option কেন ভুল:** Offset page size-এর চেয়ে বড় হতে পারে না।
- **Related Concept:** Page=floor(addr/size), offset=mod।
- **মনে রাখার টিপস:** Quotient ও remainder।

---

## প্রশ্ন 716 | Topic: Operating System > Memory Management II | Difficulty: Hard | Type: Calculation

Q. এক-level page table-এ 2^20 entry, প্রতি entry 4 byte। Table size কত MB?

A) 2 MB
B) 4 MB
C) 8 MB
D) 20 MB

**সঠিক উত্তর: B) 4 MB**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 2^20×4=2^22 byte=4 MB।

#### Step-by-step সমাধান

```text
Entries=2^20
PTE=4=2^2 byte
Size=2^22 byte=4 MB
```
- **A option কেন ভুল:** Entry 2 byte ধরে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Entry 8 byte ধরে।
- **D option কেন ভুল:** Exponent/MB conversion ভুল।
- **Related Concept:** Page table size=entries×PTE size।
- **মনে রাখার টিপস:** 2²⁰ byte=1 MB।

---

## প্রশ্ন 717 | Topic: Operating System > Memory Management II | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Page mapping process address space/physical presence policy অনুযায়ী valid কি না জানায়।`

A) Valid Bit
B) Dirty Bit
C) Frame
D) Page Table

**সঠিক উত্তর: A) Valid Bit**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Page mapping process address space/physical presence policy অনুযায়ী valid কি না জানায়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Dirty Bit` বলতে Page memory-তে পরিবর্তিত হয়েছে কি না; eviction-এ disk write দরকার হতে পারে। বোঝায়; প্রশ্নের বর্ণনা `Valid Bit`-এর।
- **C option কেন ভুল:** `Frame` বলতে Physical memory-এর page-size fixed block। বোঝায়; প্রশ্নের বর্ণনা `Valid Bit`-এর।
- **D option কেন ভুল:** `Page Table` বলতে Virtual page number-কে physical frame number ও permission/status bit-এ map করে। বোঝায়; প্রশ্নের বর্ণনা `Valid Bit`-এর।
- **Related Concept:** Invalid access fault ঘটাতে পারে।
- **মনে রাখার টিপস:** Mapping usable?

---

## প্রশ্ন 718 | Topic: Operating System > Memory Management II | Difficulty: Medium | Type: Theory

Q. `Dirty Bit` সম্পর্কে কোন statement সঠিক?

A) Page memory-তে পরিবর্তিত হয়েছে কি না; eviction-এ disk write দরকার হতে পারে।
B) Virtual/logical address space-এর fixed-size unit।
C) Sparse virtual space-এর unused page-table অংশ allocate না করে hierarchy ব্যবহার।
D) প্রতি virtual page নয়, প্রতি physical frame-এর জন্য mapping entry রাখে।

**সঠিক উত্তর: A) Page memory-তে পরিবর্তিত হয়েছে কি না; eviction-এ disk write দরকার হতে পারে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Page memory-তে পরিবর্তিত হয়েছে কি না; eviction-এ disk write দরকার হতে পারে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Page` ধারণাকে বর্ণনা করে; `Dirty Bit`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Multi-level Page Table` ধারণাকে বর্ণনা করে; `Dirty Bit`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Inverted Page Table` ধারণাকে বর্ণনা করে; `Dirty Bit`-কে নয়।
- **Related Concept:** Write-back optimization।
- **মনে রাখার টিপস:** Modified page marker।

---

## প্রশ্ন 719 | Topic: Operating System > Memory Management II | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Sparse virtual space-এর unused page-table অংশ allocate না করে hierarchy ব্যবহার।`—এখানে কোন concept প্রযোজ্য?

A) Multi-level Page Table
B) Page Table Entry
C) Dirty Bit
D) Inverted Page Table

**সঠিক উত্তর: A) Multi-level Page Table**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Sparse virtual space-এর unused page-table অংশ allocate না করে hierarchy ব্যবহার।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Page Table Entry` বলতে Frame number, valid, protection, dirty, referenced ইত্যাদি bit ধারণ করে। বোঝায়; প্রশ্নের বর্ণনা `Multi-level Page Table`-এর।
- **C option কেন ভুল:** `Dirty Bit` বলতে Page memory-তে পরিবর্তিত হয়েছে কি না; eviction-এ disk write দরকার হতে পারে। বোঝায়; প্রশ্নের বর্ণনা `Multi-level Page Table`-এর।
- **D option কেন ভুল:** `Inverted Page Table` বলতে প্রতি virtual page নয়, প্রতি physical frame-এর জন্য mapping entry রাখে। বোঝায়; প্রশ্নের বর্ণনা `Multi-level Page Table`-এর।
- **Related Concept:** Page-table memory কমায়।
- **মনে রাখার টিপস:** Page table of page tables।

---

## প্রশ্ন 720 | Topic: Operating System > Memory Management II | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`প্রতি virtual page নয়, প্রতি physical frame-এর জন্য mapping entry রাখে।`

A) Dirty Bit
B) Inverted Page Table
C) Valid Bit
D) Page

**সঠিক উত্তর: B) Inverted Page Table**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতি virtual page নয়, প্রতি physical frame-এর জন্য mapping entry রাখে।
- **A option কেন ভুল:** `Dirty Bit` বলতে Page memory-তে পরিবর্তিত হয়েছে কি না; eviction-এ disk write দরকার হতে পারে। বোঝায়; প্রশ্নের বর্ণনা `Inverted Page Table`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Valid Bit` বলতে Page mapping process address space/physical presence policy অনুযায়ী valid কি না জানায়। বোঝায়; প্রশ্নের বর্ণনা `Inverted Page Table`-এর।
- **D option কেন ভুল:** `Page` বলতে Virtual/logical address space-এর fixed-size unit। বোঝায়; প্রশ্নের বর্ণনা `Inverted Page Table`-এর।
- **Related Concept:** Large virtual address space-এ table size কমাতে পারে।
- **মনে রাখার টিপস:** One entry per frame।

---


# Chapter Theory 62: Segmentation, TLB এবং Effective Access Time

## বিস্তারিত Theory Note

Segmentation programmer-visible logical unit ও protection sharing সহজ করে, কিন্তু variable-size allocation external fragmentation সৃষ্টি করতে পারে। Base-limit check invalid offset আটকায়।

TLB page-table translation cache। TLB miss page-table walk; page fault page absent। Effective access time hit/miss path-এর probability-weighted average।

## মূল ধারণার মানচিত্র

- **Segmentation:** Program-এর logical variable-size unit যেমন code, data, stack অনুযায়ী memory ভাগ।
- **Segment Table:** প্রতি segment-এর base ও limit রাখে।
- **Segmentation Fault:** Invalid/protected memory reference-এর ফলে OS signal/exception।
- **TLB:** সাম্প্রতিক page-table translation cache করা associative hardware।
- **TLB Hit:** Requested virtual page mapping TLB-তে পাওয়া।
- **TLB Miss:** Mapping TLB-তে নেই; page table walk প্রয়োজন।
- **Effective Access Time:** TLB hit/miss probability ও memory access latency মিলিয়ে expected translation+data access সময়।
- **Base Register:** Segment/relocation-এর starting physical address রাখে।
- **Limit Register:** Valid logical offset range/segment size bound রাখে।
- **Segmentation with Paging:** প্রথমে segment select, segment-এর page table দিয়ে page-to-frame map।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Segmentation, TLB এবং Effective Access Time

## প্রশ্ন 721 | Topic: Operating System > Memory Management III | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Program-এর logical variable-size unit যেমন code, data, stack অনুযায়ী memory ভাগ।`

A) Segmentation
B) Segmentation Fault
C) Base Register
D) TLB

**সঠিক উত্তর: A) Segmentation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Program-এর logical variable-size unit যেমন code, data, stack অনুযায়ী memory ভাগ।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Segmentation Fault` বলতে Invalid/protected memory reference-এর ফলে OS signal/exception। বোঝায়; প্রশ্নের বর্ণনা `Segmentation`-এর।
- **C option কেন ভুল:** `Base Register` বলতে Segment/relocation-এর starting physical address রাখে। বোঝায়; প্রশ্নের বর্ণনা `Segmentation`-এর।
- **D option কেন ভুল:** `TLB` বলতে সাম্প্রতিক page-table translation cache করা associative hardware। বোঝায়; প্রশ্নের বর্ণনা `Segmentation`-এর।
- **Related Concept:** Segment number + offset।
- **মনে রাখার টিপস:** Logical variable regions।

---

## প্রশ্ন 722 | Topic: Operating System > Memory Management III | Difficulty: Easy | Type: Calculation

Q. Segment base=4000, limit=1000; offset=700। Physical address কত?

A) 3300
B) 5000
C) Invalid
D) 4700

**সঠিক উত্তর: D) 4700**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 700<1000 valid; base+offset=4700।

#### Step-by-step সমাধান

```text
700<1000 -> valid
Physical=4000+700=4700
```
- **A option কেন ভুল:** Offset subtract।
- **B option কেন ভুল:** Limit যোগ।
- **C option কেন ভুল:** Offset limit-এর মধ্যে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Bounds check আগে, তারপর base যোগ।
- **মনে রাখার টিপস:** offset<limit।

---

## প্রশ্ন 723 | Topic: Operating System > Memory Management III | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Invalid/protected memory reference-এর ফলে OS signal/exception।`—এখানে কোন concept প্রযোজ্য?

A) Base Register
B) Segmentation with Paging
C) Segmentation
D) Segmentation Fault

**সঠিক উত্তর: D) Segmentation Fault**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Invalid/protected memory reference-এর ফলে OS signal/exception।
- **A option কেন ভুল:** `Base Register` বলতে Segment/relocation-এর starting physical address রাখে। বোঝায়; প্রশ্নের বর্ণনা `Segmentation Fault`-এর।
- **B option কেন ভুল:** `Segmentation with Paging` বলতে প্রথমে segment select, segment-এর page table দিয়ে page-to-frame map। বোঝায়; প্রশ্নের বর্ণনা `Segmentation Fault`-এর।
- **C option কেন ভুল:** `Segmentation` বলতে Program-এর logical variable-size unit যেমন code, data, stack অনুযায়ী memory ভাগ। বোঝায়; প্রশ্নের বর্ণনা `Segmentation Fault`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** শুধু segmentation scheme-এর মধ্যে সীমিত term নয়।
- **মনে রাখার টিপস:** Invalid memory access fault।

---

## প্রশ্ন 724 | Topic: Operating System > Memory Management III | Difficulty: Medium | Type: Calculation

Q. TLB hit timeসহ lookup 10 ns এবং memory access 100 ns; hit-এ total 110 ns। Hit ratio 80%; miss-এ page-table+data total 210 ns। EAT কত?

A) 130 ns
B) 110 ns
C) 190 ns
D) 210 ns

**সঠিক উত্তর: A) 130 ns**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 0.8×110+0.2×210=88+42=130।

#### Step-by-step সমাধান

```text
Hit ratio=0.8
Miss ratio=0.2
EAT=0.8x110+0.2x210
   =88+42
   =130 ns
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** সব access hit ধরা।
- **C option কেন ভুল:** Weighted average ভুল।
- **D option কেন ভুল:** সব miss ধরা।
- **Related Concept:** EAT probability-weighted latency।
- **মনে রাখার টিপস:** Hit ratio ও miss ratio যোগ 1।

---

## প্রশ্ন 725 | Topic: Operating System > Memory Management III | Difficulty: Medium | Type: Calculation

Q. 1000 memory reference-এর TLB hit ratio 90% হলে expected hit count কত?

A) 900
B) 90
C) 100
D) 910

**সঠিক উত্তর: A) 900**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 1000×0.9=900।

#### Step-by-step সমাধান

```text
Hits=1000x0.90=900
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Percent count হিসেবে।
- **C option কেন ভুল:** Miss count।
- **D option কেন ভুল:** অতিরিক্ত 10।
- **Related Concept:** Expected count=total×probability।
- **মনে রাখার টিপস:** 90% of 1000।

---

## প্রশ্ন 726 | Topic: Operating System > Memory Management III | Difficulty: Medium | Type: Tracing

Q. TLB miss হলে কিন্তু page memory-তে present থাকলে কী প্রয়োজন?

A) Disk page-in বাধ্যতামূলক
B) Process termination
C) Cache flush only
D) Page-table walk, disk নয়

**সঠিক উত্তর: D) Page-table walk, disk নয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** TLB cache miss mapping page table থেকে পাওয়া যায়; valid present page হলে disk access নেই।

#### Step-by-step সমাধান

```text
TLB lookup: miss
Page table: valid + present
Action: obtain frame, refill TLB
Disk I/O: none
```
- **A option কেন ভুল:** এটি page fault হলে।
- **B option কেন ভুল:** Valid mapping পাওয়া যায়।
- **C option কেন ভুল:** Mapping lookup দরকার।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** TLB miss ≠ page fault।
- **মনে রাখার টিপস:** Cache miss আর absence আলাদা।

---

## প্রশ্ন 727 | Topic: Operating System > Memory Management III | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`TLB hit/miss probability ও memory access latency মিলিয়ে expected translation+data access সময়।`

A) Segmentation with Paging
B) Effective Access Time
C) Segmentation Fault
D) TLB

**সঠিক উত্তর: B) Effective Access Time**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** TLB hit/miss probability ও memory access latency মিলিয়ে expected translation+data access সময়।
- **A option কেন ভুল:** `Segmentation with Paging` বলতে প্রথমে segment select, segment-এর page table দিয়ে page-to-frame map। বোঝায়; প্রশ্নের বর্ণনা `Effective Access Time`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Segmentation Fault` বলতে Invalid/protected memory reference-এর ফলে OS signal/exception। বোঝায়; প্রশ্নের বর্ণনা `Effective Access Time`-এর।
- **D option কেন ভুল:** `TLB` বলতে সাম্প্রতিক page-table translation cache করা associative hardware। বোঝায়; প্রশ্নের বর্ণনা `Effective Access Time`-এর।
- **Related Concept:** EAT formula।
- **মনে রাখার টিপস:** Weighted average latency।

---

## প্রশ্ন 728 | Topic: Operating System > Memory Management III | Difficulty: Medium | Type: Theory

Q. `Base Register` সম্পর্কে কোন statement সঠিক?

A) TLB hit/miss probability ও memory access latency মিলিয়ে expected translation+data access সময়।
B) প্রথমে segment select, segment-এর page table দিয়ে page-to-frame map।
C) Segment/relocation-এর starting physical address রাখে।
D) Program-এর logical variable-size unit যেমন code, data, stack অনুযায়ী memory ভাগ।

**সঠিক উত্তর: C) Segment/relocation-এর starting physical address রাখে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Segment/relocation-এর starting physical address রাখে।
- **A option কেন ভুল:** এই statementটি `Effective Access Time` ধারণাকে বর্ণনা করে; `Base Register`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Segmentation with Paging` ধারণাকে বর্ণনা করে; `Base Register`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Segmentation` ধারণাকে বর্ণনা করে; `Base Register`-কে নয়।
- **Related Concept:** Limit-এর সঙ্গে protection।
- **মনে রাখার টিপস:** Start address।

---

## প্রশ্ন 729 | Topic: Operating System > Memory Management III | Difficulty: Medium | Type: Calculation

Q. Base=10000, limit=500; offset=500। Valid condition `offset < limit` হলে result কী?

A) Physical10500
B) Invalid
C) Physical10000
D) Physical9500

**সঠিক উত্তর: B) Invalid**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 500<500 false; maximum valid offset 499।

#### Step-by-step সমাধান

```text
Condition: 500 < 500
Result: false
Access: invalid
```
- **A option কেন ভুল:** Bounds check উপেক্ষা।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Offset বাদ।
- **D option কেন ভুল:** Subtract।
- **Related Concept:** Limit size হলে valid offsets 0..limit−1।
- **মনে রাখার টিপস:** Strict less-than।

---

## প্রশ্ন 730 | Topic: Operating System > Memory Management III | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`প্রথমে segment select, segment-এর page table দিয়ে page-to-frame map।`

A) TLB
B) Segment Table
C) Effective Access Time
D) Segmentation with Paging

**সঠিক উত্তর: D) Segmentation with Paging**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রথমে segment select, segment-এর page table দিয়ে page-to-frame map।
- **A option কেন ভুল:** `TLB` বলতে সাম্প্রতিক page-table translation cache করা associative hardware। বোঝায়; প্রশ্নের বর্ণনা `Segmentation with Paging`-এর।
- **B option কেন ভুল:** `Segment Table` বলতে প্রতি segment-এর base ও limit রাখে। বোঝায়; প্রশ্নের বর্ণনা `Segmentation with Paging`-এর।
- **C option কেন ভুল:** `Effective Access Time` বলতে TLB hit/miss probability ও memory access latency মিলিয়ে expected translation+data access সময়। বোঝায়; প্রশ্নের বর্ণনা `Segmentation with Paging`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Logical view ও paging allocation combine।
- **মনে রাখার টিপস:** Segment then page।

---


# Chapter Theory 63: Virtual Memory, Demand Paging এবং Thrashing

## বিস্তারিত Theory Note

Virtual memory isolation ও large address space দেয়। Demand paging locality ব্যবহার করে প্রয়োজনীয় page load করে; page fault hardware trap থেকে OS handler, disk I/O ও instruction restart ঘটায়।

Working set-এর তুলনায় frames কম হলে page repeatedly evict/reload হয়ে thrashing। Copy-on-Write read sharing বজায় রেখে write-এর সময় copy তৈরি করে।

## মূল ধারণার মানচিত্র

- **Virtual Memory:** Process-কে physical RAM-এর চেয়ে বড় ও isolated logical address space দেওয়ার abstraction।
- **Demand Paging:** Page প্রথম reference না হওয়া পর্যন্ত memory-তে load না করা।
- **Page Fault:** Referenced page present না থাকলে hardware trap ও OS page-in handling।
- **Locality of Reference:** Program কাছাকাছি সময়/ঠিকানার data পুনরায় access করার প্রবণতা।
- **Working Set:** Recent window-তে process যে page set সক্রিয়ভাবে ব্যবহার করে।
- **Thrashing:** Page fault এত বেশি যে CPU useful execution-এর বদলে paging-এ সময় ব্যয় করে।
- **Copy-on-Write:** Shared page write না হওয়া পর্যন্ত copy না করে share; write-এ private copy।
- **Memory-mapped File:** File content virtual address range-এ map করে load/store access।
- **Page Fault Service Time:** Trap, victim selection, write-back, page read ও restartসহ page fault handling latency।
- **Resident Set:** এক process-এর বর্তমানে physical memory-তে থাকা page set।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Virtual Memory, Demand Paging এবং Thrashing

## প্রশ্ন 731 | Topic: Operating System > Virtual Memory | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Process-কে physical RAM-এর চেয়ে বড় ও isolated logical address space দেওয়ার abstraction।`

A) Memory-mapped File
B) Virtual Memory
C) Page Fault
D) Copy-on-Write

**সঠিক উত্তর: B) Virtual Memory**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Process-কে physical RAM-এর চেয়ে বড় ও isolated logical address space দেওয়ার abstraction।
- **A option কেন ভুল:** `Memory-mapped File` বলতে File content virtual address range-এ map করে load/store access। বোঝায়; প্রশ্নের বর্ণনা `Virtual Memory`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Page Fault` বলতে Referenced page present না থাকলে hardware trap ও OS page-in handling। বোঝায়; প্রশ্নের বর্ণনা `Virtual Memory`-এর।
- **D option কেন ভুল:** `Copy-on-Write` বলতে Shared page write না হওয়া পর্যন্ত copy না করে share; write-এ private copy। বোঝায়; প্রশ্নের বর্ণনা `Virtual Memory`-এর।
- **Related Concept:** Demand paging ও backing store ব্যবহার।
- **মনে রাখার টিপস:** Large logical memory illusion।

---

## প্রশ্ন 732 | Topic: Operating System > Virtual Memory | Difficulty: Easy | Type: Theory

Q. `Demand Paging` সম্পর্কে কোন statement সঠিক?

A) Page fault এত বেশি যে CPU useful execution-এর বদলে paging-এ সময় ব্যয় করে।
B) Page প্রথম reference না হওয়া পর্যন্ত memory-তে load না করা।
C) File content virtual address range-এ map করে load/store access।
D) Program কাছাকাছি সময়/ঠিকানার data পুনরায় access করার প্রবণতা।

**সঠিক উত্তর: B) Page প্রথম reference না হওয়া পর্যন্ত memory-তে load না করা।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Page প্রথম reference না হওয়া পর্যন্ত memory-তে load না করা।
- **A option কেন ভুল:** এই statementটি `Thrashing` ধারণাকে বর্ণনা করে; `Demand Paging`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `Memory-mapped File` ধারণাকে বর্ণনা করে; `Demand Paging`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Locality of Reference` ধারণাকে বর্ণনা করে; `Demand Paging`-কে নয়।
- **Related Concept:** Locality exploit করে।
- **মনে রাখার টিপস:** Load on demand।

---

## প্রশ্ন 733 | Topic: Operating System > Virtual Memory | Difficulty: Medium | Type: Calculation

Q. 10,000 memory reference-এ 20টি page fault হলে page-fault rate কত?

A) 0.0002
B) 0.02
C) 0.002
D) 0.2

**সঠিক উত্তর: C) 0.002**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 20/10000=0.002।

#### Step-by-step সমাধান

```text
Rate=20/10000=0.002
Percent=0.002x100=0.2%
```
- **A option কেন ভুল:** 2 fault ধরে।
- **B option কেন ভুল:** 200 fault-এর ratio।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** 2000 fault-এর ratio।
- **Related Concept:** Percent হিসেবে 0.2%।
- **মনে রাখার টিপস:** Fault count/total reference।

---

## প্রশ্ন 734 | Topic: Operating System > Virtual Memory | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Program কাছাকাছি সময়/ঠিকানার data পুনরায় access করার প্রবণতা।`

A) Copy-on-Write
B) Thrashing
C) Locality of Reference
D) Memory-mapped File

**সঠিক উত্তর: C) Locality of Reference**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Program কাছাকাছি সময়/ঠিকানার data পুনরায় access করার প্রবণতা।
- **A option কেন ভুল:** `Copy-on-Write` বলতে Shared page write না হওয়া পর্যন্ত copy না করে share; write-এ private copy। বোঝায়; প্রশ্নের বর্ণনা `Locality of Reference`-এর।
- **B option কেন ভুল:** `Thrashing` বলতে Page fault এত বেশি যে CPU useful execution-এর বদলে paging-এ সময় ব্যয় করে। বোঝায়; প্রশ্নের বর্ণনা `Locality of Reference`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Memory-mapped File` বলতে File content virtual address range-এ map করে load/store access। বোঝায়; প্রশ্নের বর্ণনা `Locality of Reference`-এর।
- **Related Concept:** Temporal ও spatial locality।
- **মনে রাখার টিপস:** Programs reuse nearby things।

---

## প্রশ্ন 735 | Topic: Operating System > Virtual Memory | Difficulty: Hard | Type: Tracing

Q. Working-set window-তে reference `1,2,1,3,2,4`। Distinct page set size কত?

A) 3
B) 6
C) 2
D) 4

**সঠিক উত্তর: D) 4**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Distinct={1,2,3,4}, size4।

#### Step-by-step সমাধান

```text
References=1,2,1,3,2,4
Unique={1,2,3,4}
Size=4
```
- **A option কেন ভুল:** এক distinct page বাদ।
- **B option কেন ভুল:** Reference count, distinct নয়।
- **C option কেন ভুল:** Repeated popular page count।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Working set repeated page একবার count।
- **মনে রাখার টিপস:** Unique page গুনুন।

---

## প্রশ্ন 736 | Topic: Operating System > Virtual Memory | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `Page fault এত বেশি যে CPU useful execution-এর বদলে paging-এ সময় ব্যয় করে।`—এখানে কোন concept প্রযোজ্য?

A) Page Fault
B) Resident Set
C) Thrashing
D) Copy-on-Write

**সঠিক উত্তর: C) Thrashing**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Page fault এত বেশি যে CPU useful execution-এর বদলে paging-এ সময় ব্যয় করে।
- **A option কেন ভুল:** `Page Fault` বলতে Referenced page present না থাকলে hardware trap ও OS page-in handling। বোঝায়; প্রশ্নের বর্ণনা `Thrashing`-এর।
- **B option কেন ভুল:** `Resident Set` বলতে এক process-এর বর্তমানে physical memory-তে থাকা page set। বোঝায়; প্রশ্নের বর্ণনা `Thrashing`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Copy-on-Write` বলতে Shared page write না হওয়া পর্যন্ত copy না করে share; write-এ private copy। বোঝায়; প্রশ্নের বর্ণনা `Thrashing`-এর।
- **Related Concept:** Insufficient frames/overcommit।
- **মনে রাখার টিপস:** Mostly swapping pages।

---

## প্রশ্ন 737 | Topic: Operating System > Virtual Memory | Difficulty: Medium | Type: Tracing

Q. Copy-on-Write-এ parent ও child shared page শুধু read করলে physical copy সংখ্যা কত থাকে?

A) 1
B) 2
C) 0
D) প্রতি read-এ বাড়ে

**সঠিক উত্তর: A) 1**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Write না হওয়া পর্যন্ত একই physical page share করে।

#### Step-by-step সমাধান

```text
After fork: shared physical page=1
Parent read: no copy
Child read : no copy
Copies remain=1
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Immediate eager copy ধরে।
- **C option কেন ভুল:** Page থাকা প্রয়োজন।
- **D option কেন ভুল:** Read copy trigger করে না।
- **Related Concept:** প্রথম write-এ writer-এর private copy।
- **মনে রাখার টিপস:** COW—W মানে Write।

---

## প্রশ্ন 738 | Topic: Operating System > Virtual Memory | Difficulty: Medium | Type: Theory

Q. `Memory-mapped File` সম্পর্কে কোন statement সঠিক?

A) File content virtual address range-এ map করে load/store access।
B) Page fault এত বেশি যে CPU useful execution-এর বদলে paging-এ সময় ব্যয় করে।
C) Page প্রথম reference না হওয়া পর্যন্ত memory-তে load না করা।
D) Recent window-তে process যে page set সক্রিয়ভাবে ব্যবহার করে।

**সঠিক উত্তর: A) File content virtual address range-এ map করে load/store access।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** File content virtual address range-এ map করে load/store access।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Thrashing` ধারণাকে বর্ণনা করে; `Memory-mapped File`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Demand Paging` ধারণাকে বর্ণনা করে; `Memory-mapped File`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Working Set` ধারণাকে বর্ণনা করে; `Memory-mapped File`-কে নয়।
- **Related Concept:** Demand paging ও shared mapping সম্ভব।
- **মনে রাখার টিপস:** File as memory pages।

---

## প্রশ্ন 739 | Topic: Operating System > Virtual Memory | Difficulty: Hard | Type: Calculation

Q. Normal memory access 100 ns, page fault service 10 ms। এক page fault প্রায় কত normal access time-এর সমান? `10 ms = 10,000,000 ns`।

A) 10,000
B) 1,000,000
C) 100,000
D) 100

**সঠিক উত্তর: C) 100,000**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 10,000,000/100=100,000।

#### Step-by-step সমাধান

```text
Fault=10,000,000 ns
Memory=100 ns
Ratio=10,000,000/100=100,000
```
- **A option কেন ভুল:** এক zero কম।
- **B option কেন ভুল:** এক zero বেশি।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Unit conversion বাদ।
- **Related Concept:** অতি ক্ষুদ্র fault rateও EAT-এ বড় প্রভাব ফেলে।
- **মনে রাখার টিপস:** একই unit-এ convert।

---

## প্রশ্ন 740 | Topic: Operating System > Virtual Memory | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`এক process-এর বর্তমানে physical memory-তে থাকা page set।`

A) Page Fault Service Time
B) Copy-on-Write
C) Thrashing
D) Resident Set

**সঠিক উত্তর: D) Resident Set**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** এক process-এর বর্তমানে physical memory-তে থাকা page set।
- **A option কেন ভুল:** `Page Fault Service Time` বলতে Trap, victim selection, write-back, page read ও restartসহ page fault handling latency। বোঝায়; প্রশ্নের বর্ণনা `Resident Set`-এর।
- **B option কেন ভুল:** `Copy-on-Write` বলতে Shared page write না হওয়া পর্যন্ত copy না করে share; write-এ private copy। বোঝায়; প্রশ্নের বর্ণনা `Resident Set`-এর।
- **C option কেন ভুল:** `Thrashing` বলতে Page fault এত বেশি যে CPU useful execution-এর বদলে paging-এ সময় ব্যয় করে। বোঝায়; প্রশ্নের বর্ণনা `Resident Set`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Frame allocation policy নির্ধারণ করে।
- **মনে রাখার টিপস:** Pages in RAM now।

---


# Chapter Theory 64: Page Replacement Algorithms

## বিস্তারিত Theory Note

Page replacement fault-এর সময় free frame না থাকলে victim নির্বাচন করে। Optimal benchmark, LRU locality approximation, FIFO implementation সহজ কিন্তু anomaly-prone। Clock/Second Chance reference bit দিয়ে LRU approximate করে।

Fault count calculation-এ initial frame empty, replacement order ও hit-এর সময় recency update স্পষ্টভাবে trace করতে হবে।

## মূল ধারণার মানচিত্র

- **FIFO Replacement:** Memory-তে সবচেয়ে আগে load হওয়া page evict করে।
- **Optimal Replacement:** ভবিষ্যতে সবচেয়ে দেরিতে ব্যবহৃত হবে এমন page evict করে; theoretical minimum fault।
- **LRU Replacement:** অতীতে সবচেয়ে দীর্ঘ সময় ব্যবহার না হওয়া page evict করে।
- **Second Chance:** FIFO order-এর সঙ্গে reference bit ব্যবহার করে recently used page-কে আরেক সুযোগ দেয়।
- **Belady Anomaly:** কিছু algorithm-এ frame বাড়ালেও page fault বাড়া।
- **Stack Algorithm:** n-frame resident set সবসময় n+1-frame set-এর subset; Belady anomaly হয় না।
- **Reference Bit:** Page সাম্প্রতিক access হয়েছে কি না approximate করে।
- **Dirty Page:** Memory-তে modified page, eviction-এ backing store write প্রয়োজন।
- **Frame Allocation:** Process-গুলোর মধ্যে available physical frames ভাগ করার policy।
- **Local Replacement:** Victim frame একই process-এর resident set থেকে নেয়।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Page Replacement Algorithms

## প্রশ্ন 741 | Topic: Operating System > Page Replacement | Difficulty: Medium | Type: Tracing

Q. 3 frame FIFO; reference `1,2,3,4`। প্রথম তিন load-এর পর 4 এলে কোন page evict?

A) 2
B) 3
C) 1
D) 4

**সঠিক উত্তর: C) 1**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** FIFO oldest loaded page 1।

#### Step-by-step সমাধান

```text
Load1 [1]
Load2 [1,2]
Load3 [1,2,3]
Reference4 -> evict oldest1
```
- **A option কেন ভুল:** দ্বিতীয় oldest।
- **B option কেন ভুল:** Newest resident।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Incoming page।
- **Related Concept:** Queue arrival order track করুন।
- **মনে রাখার টিপস:** First in first out।

---

## প্রশ্ন 742 | Topic: Operating System > Page Replacement | Difficulty: Hard | Type: Tracing

Q. Frames contain 1,2,3। Future references: `2,1,4,2,3`। Optimal কোন page evict করবে নতুন 4-এর জন্য?

A) 1
B) 2
C) 3
D) 4

**সঠিক উত্তর: C) 3**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Future-এ 2 earliest, 1 next, 3 latest; তাই 3।

#### Step-by-step সমাধান

```text
Next use:
page2 -> position1
page1 -> position2
page3 -> position5
Farthest=3
```
- **A option কেন ভুল:** 1, 3-এর আগে ব্যবহৃত হবে।
- **B option কেন ভুল:** Immediate next use।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Incoming page victim নয়।
- **Related Concept:** Optimal future next-use দূরত্ব দেখে।
- **মনে রাখার টিপস:** যেটি সবচেয়ে পরে দরকার।

---

## প্রশ্ন 743 | Topic: Operating System > Page Replacement | Difficulty: Easy | Type: Calculation

Q. Frames 1,2,3; last-use time: page1=20, page2=5, page3=12। LRU victim কোনটি?

A) 1
B) 2
C) 3
D) সব

**সঠিক উত্তর: B) 2**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** সবচেয়ে পুরোনো last-use time 5।

#### Step-by-step সমাধান

```text
Last use:
1:20
2:5 <- oldest
3:12
Victim=2
```
- **A option কেন ভুল:** Most recent20।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** 12, page2-এর চেয়ে recent।
- **D option কেন ভুল:** এক victim দরকার।
- **Related Concept:** Smallest last-use timestamp = least recent।
- **মনে রাখার টিপস:** Oldest timestamp।

---

## প্রশ্ন 744 | Topic: Operating System > Page Replacement | Difficulty: Hard | Type: Tracing

Q. Reference string `1,2,1,3` এবং initially empty 2 frame LRU। Page fault কত?

A) 2
B) 3
C) 4
D) 1

**সঠিক উত্তর: B) 3**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 1 fault,2 fault,1 hit,3 fault=3।

#### Step-by-step সমাধান

```text
1 -> fault [1]
2 -> fault [1,2]
1 -> hit  [1,2]
3 -> fault, evict2 [1,3]
Faults=3
```
- **A option কেন ভুল:** শেষ replacement fault বাদ।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Hit-কে fault ধরা।
- **D option কেন ভুল:** শুধু first reference।
- **Related Concept:** প্রতি reference resident set trace।
- **মনে রাখার টিপস:** Hit/fault আলাদা লিখুন।

---

## প্রশ্ন 745 | Topic: Operating System > Page Replacement | Difficulty: Easy | Type: Calculation

Q. Frame 3 থেকে 4 বাড়িয়ে FIFO fault 9 থেকে 10 হলে phenomenon কী?

A) Thrashing only
B) LRU property
C) Deadlock
D) Belady Anomaly

**সঠিক উত্তর: D) Belady Anomaly**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Frame বাড়িয়েও fault বেড়েছে।

#### Step-by-step সমাধান

```text
Old frames=3, faults=9
New frames=4, faults=10
Frames increased and faults increased
```
- **A option কেন ভুল:** High fault হতে পারে, কিন্তু specific counterintuitive property Belady।
- **B option কেন ভুল:** LRU stack algorithm; anomaly হয় না।
- **C option কেন ভুল:** Memory replacement relation নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** FIFO classic anomaly sequence আছে।
- **মনে রাখার টিপস:** More frame, more fault = Belady।

---

## প্রশ্ন 746 | Topic: Operating System > Page Replacement | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `n-frame resident set সবসময় n+1-frame set-এর subset; Belady anomaly হয় না।`—এখানে কোন concept প্রযোজ্য?

A) Reference Bit
B) LRU Replacement
C) Stack Algorithm
D) FIFO Replacement

**সঠিক উত্তর: C) Stack Algorithm**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** n-frame resident set সবসময় n+1-frame set-এর subset; Belady anomaly হয় না।
- **A option কেন ভুল:** `Reference Bit` বলতে Page সাম্প্রতিক access হয়েছে কি না approximate করে। বোঝায়; প্রশ্নের বর্ণনা `Stack Algorithm`-এর।
- **B option কেন ভুল:** `LRU Replacement` বলতে অতীতে সবচেয়ে দীর্ঘ সময় ব্যবহার না হওয়া page evict করে। বোঝায়; প্রশ্নের বর্ণনা `Stack Algorithm`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `FIFO Replacement` বলতে Memory-তে সবচেয়ে আগে load হওয়া page evict করে। বোঝায়; প্রশ্নের বর্ণনা `Stack Algorithm`-এর।
- **Related Concept:** LRU ও Optimal উদাহরণ।
- **মনে রাখার টিপস:** Nested resident sets।

---

## প্রশ্ন 747 | Topic: Operating System > Page Replacement | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Page সাম্প্রতিক access হয়েছে কি না approximate করে।`

A) Stack Algorithm
B) Dirty Page
C) Reference Bit
D) LRU Replacement

**সঠিক উত্তর: C) Reference Bit**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Page সাম্প্রতিক access হয়েছে কি না approximate করে।
- **A option কেন ভুল:** `Stack Algorithm` বলতে n-frame resident set সবসময় n+1-frame set-এর subset; Belady anomaly হয় না। বোঝায়; প্রশ্নের বর্ণনা `Reference Bit`-এর।
- **B option কেন ভুল:** `Dirty Page` বলতে Memory-তে modified page, eviction-এ backing store write প্রয়োজন। বোঝায়; প্রশ্নের বর্ণনা `Reference Bit`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `LRU Replacement` বলতে অতীতে সবচেয়ে দীর্ঘ সময় ব্যবহার না হওয়া page evict করে। বোঝায়; প্রশ্নের বর্ণনা `Reference Bit`-এর।
- **Related Concept:** Hardware set, OS clear।
- **মনে রাখার টিপস:** Recently touched flag।

---

## প্রশ্ন 748 | Topic: Operating System > Page Replacement | Difficulty: Hard | Type: Calculation

Q. Eviction-এ clean page write time 0 ms, dirty page write 4 ms। 3 dirty eviction-এর extra write time কত?

A) 4 ms
B) 12 ms
C) 7 ms
D) 0 ms

**সঠিক উত্তর: B) 12 ms**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 3×4=12 ms।

#### Step-by-step সমাধান

```text
3 x 4 ms=12 ms
```
- **A option কেন ভুল:** এক eviction।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** যোগ ভুল।
- **D option কেন ভুল:** Dirty write প্রয়োজন।
- **Related Concept:** Dirty eviction replacement latency বাড়ায়।
- **মনে রাখার টিপস:** Count×write time।

---

## প্রশ্ন 749 | Topic: Operating System > Page Replacement | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Process-গুলোর মধ্যে available physical frames ভাগ করার policy।`—এখানে কোন concept প্রযোজ্য?

A) Reference Bit
B) Stack Algorithm
C) Dirty Page
D) Frame Allocation

**সঠিক উত্তর: D) Frame Allocation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Process-গুলোর মধ্যে available physical frames ভাগ করার policy।
- **A option কেন ভুল:** `Reference Bit` বলতে Page সাম্প্রতিক access হয়েছে কি না approximate করে। বোঝায়; প্রশ্নের বর্ণনা `Frame Allocation`-এর।
- **B option কেন ভুল:** `Stack Algorithm` বলতে n-frame resident set সবসময় n+1-frame set-এর subset; Belady anomaly হয় না। বোঝায়; প্রশ্নের বর্ণনা `Frame Allocation`-এর।
- **C option কেন ভুল:** `Dirty Page` বলতে Memory-তে modified page, eviction-এ backing store write প্রয়োজন। বোঝায়; প্রশ্নের বর্ণনা `Frame Allocation`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Equal, proportional, priority-based।
- **মনে রাখার টিপস:** Who gets how many frames।

---

## প্রশ্ন 750 | Topic: Operating System > Page Replacement | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Victim frame একই process-এর resident set থেকে নেয়।`

A) Local Replacement
B) Dirty Page
C) Stack Algorithm
D) Reference Bit

**সঠিক উত্তর: A) Local Replacement**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Victim frame একই process-এর resident set থেকে নেয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Dirty Page` বলতে Memory-তে modified page, eviction-এ backing store write প্রয়োজন। বোঝায়; প্রশ্নের বর্ণনা `Local Replacement`-এর।
- **C option কেন ভুল:** `Stack Algorithm` বলতে n-frame resident set সবসময় n+1-frame set-এর subset; Belady anomaly হয় না। বোঝায়; প্রশ্নের বর্ণনা `Local Replacement`-এর।
- **D option কেন ভুল:** `Reference Bit` বলতে Page সাম্প্রতিক access হয়েছে কি না approximate করে। বোঝায়; প্রশ্নের বর্ণনা `Local Replacement`-এর।
- **Related Concept:** Global replacement অন্য process-এর frame নিতে পারে।
- **মনে রাখার টিপস:** Replace within self।

---


# Chapter Theory 65: File System, Allocation এবং Links

## বিস্তারিত Theory Note

File system persistent data, namespace, allocation ও crash consistency manage করে। Directory filename রাখে; inode-like object metadata ও block mapping রাখে।

Allocation strategy sequential/random access, growth ও fragmentation trade-off করে। Hard link একই object; symbolic link path-based পৃথক object। Journaling incomplete update recovery সহজ করে।

## মূল ধারণার মানচিত্র

- **File:** Named persistent byte বা record collection, metadataসহ storage abstraction।
- **Directory:** File name-কে metadata/inode reference-এ map ও namespace organize করে।
- **Inode:** Unix-like file-এর metadata ও data-block pointer রাখে; filename directory entry-তে।
- **Contiguous Allocation:** File consecutive disk block-এ; fast sequential/random access কিন্তু growth ও external fragmentation সমস্যা।
- **Linked Allocation:** প্রতিটি file block next block pointer রাখে; growth সহজ, random access দুর্বল।
- **Indexed Allocation:** Index block file-এর data block address রাখে; direct access সমর্থন।
- **File Descriptor:** Process-local integer handle যা open-file table entry নির্দেশ করে।
- **Hard Link:** একই inode/file object-এর আরেক directory entry।
- **Symbolic Link:** Pathname ধারণকারী পৃথক file যা target-এ resolve হয়।
- **Journaling:** Metadata/data update log আগে লিখে crash recovery consistency উন্নত করা।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: File System, Allocation এবং Links

# Batch 17 — Question 751–800

## প্রশ্ন 751 | Topic: Operating System > File Systems | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Named persistent byte বা record collection, metadataসহ storage abstraction।`

A) File
B) Hard Link
C) Symbolic Link
D) Contiguous Allocation

**সঠিক উত্তর: A) File**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Named persistent byte বা record collection, metadataসহ storage abstraction।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Hard Link` বলতে একই inode/file object-এর আরেক directory entry। বোঝায়; প্রশ্নের বর্ণনা `File`-এর।
- **C option কেন ভুল:** `Symbolic Link` বলতে Pathname ধারণকারী পৃথক file যা target-এ resolve হয়। বোঝায়; প্রশ্নের বর্ণনা `File`-এর।
- **D option কেন ভুল:** `Contiguous Allocation` বলতে File consecutive disk block-এ; fast sequential/random access কিন্তু growth ও external fragmentation সমস্যা। বোঝায়; প্রশ্নের বর্ণনা `File`-এর।
- **Related Concept:** Type/structure OS অনুযায়ী।
- **মনে রাখার টিপস:** Persistent named data।

---

## প্রশ্ন 752 | Topic: Operating System > File Systems | Difficulty: Easy | Type: Theory

Q. `Directory` সম্পর্কে কোন statement সঠিক?

A) Process-local integer handle যা open-file table entry নির্দেশ করে।
B) File name-কে metadata/inode reference-এ map ও namespace organize করে।
C) একই inode/file object-এর আরেক directory entry।
D) প্রতিটি file block next block pointer রাখে; growth সহজ, random access দুর্বল।

**সঠিক উত্তর: B) File name-কে metadata/inode reference-এ map ও namespace organize করে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** File name-কে metadata/inode reference-এ map ও namespace organize করে।
- **A option কেন ভুল:** এই statementটি `File Descriptor` ধারণাকে বর্ণনা করে; `Directory`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `Hard Link` ধারণাকে বর্ণনা করে; `Directory`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Linked Allocation` ধারণাকে বর্ণনা করে; `Directory`-কে নয়।
- **Related Concept:** Hierarchical tree common।
- **মনে রাখার টিপস:** Names organized।

---

## প্রশ্ন 753 | Topic: Operating System > File Systems | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Unix-like file-এর metadata ও data-block pointer রাখে; filename directory entry-তে।`—এখানে কোন concept প্রযোজ্য?

A) File
B) Symbolic Link
C) Inode
D) Indexed Allocation

**সঠিক উত্তর: C) Inode**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Unix-like file-এর metadata ও data-block pointer রাখে; filename directory entry-তে।
- **A option কেন ভুল:** `File` বলতে Named persistent byte বা record collection, metadataসহ storage abstraction। বোঝায়; প্রশ্নের বর্ণনা `Inode`-এর।
- **B option কেন ভুল:** `Symbolic Link` বলতে Pathname ধারণকারী পৃথক file যা target-এ resolve হয়। বোঝায়; প্রশ্নের বর্ণনা `Inode`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Indexed Allocation` বলতে Index block file-এর data block address রাখে; direct access সমর্থন। বোঝায়; প্রশ্নের বর্ণনা `Inode`-এর।
- **Related Concept:** Permission,size,timestamps।
- **মনে রাখার টিপস:** File metadata object।

---

## প্রশ্ন 754 | Topic: Operating System > File Systems | Difficulty: Hard | Type: Calculation

Q. File 5টি contiguous block নেয়, starting block 20। Last block number কত?

A) 24
B) 25
C) 15
D) 100

**সঠিক উত্তর: A) 24**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Blocks 20,21,22,23,24।

#### Step-by-step সমাধান

```text
Last=20+5-1=24
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Start+count, off-by-one।
- **C option কেন ভুল:** Subtract।
- **D option কেন ভুল:** Multiply।
- **Related Concept:** Last=start+count−1।
- **মনে রাখার টিপস:** Inclusive counting।

---

## প্রশ্ন 755 | Topic: Operating System > File Systems | Difficulty: Medium | Type: Theory

Q. `Linked Allocation` সম্পর্কে কোন statement সঠিক?

A) Index block file-এর data block address রাখে; direct access সমর্থন।
B) Named persistent byte বা record collection, metadataসহ storage abstraction।
C) প্রতিটি file block next block pointer রাখে; growth সহজ, random access দুর্বল।
D) File consecutive disk block-এ; fast sequential/random access কিন্তু growth ও external fragmentation সমস্যা।

**সঠিক উত্তর: C) প্রতিটি file block next block pointer রাখে; growth সহজ, random access দুর্বল।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি file block next block pointer রাখে; growth সহজ, random access দুর্বল।
- **A option কেন ভুল:** এই statementটি `Indexed Allocation` ধারণাকে বর্ণনা করে; `Linked Allocation`-কে নয়।
- **B option কেন ভুল:** এই statementটি `File` ধারণাকে বর্ণনা করে; `Linked Allocation`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Contiguous Allocation` ধারণাকে বর্ণনা করে; `Linked Allocation`-কে নয়।
- **Related Concept:** FAT table variant।
- **মনে রাখার টিপস:** Block chain।

---

## প্রশ্ন 756 | Topic: Operating System > File Systems | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Index block file-এর data block address রাখে; direct access সমর্থন।`—এখানে কোন concept প্রযোজ্য?

A) Indexed Allocation
B) File Descriptor
C) Directory
D) Hard Link

**সঠিক উত্তর: A) Indexed Allocation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Index block file-এর data block address রাখে; direct access সমর্থন।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `File Descriptor` বলতে Process-local integer handle যা open-file table entry নির্দেশ করে। বোঝায়; প্রশ্নের বর্ণনা `Indexed Allocation`-এর।
- **C option কেন ভুল:** `Directory` বলতে File name-কে metadata/inode reference-এ map ও namespace organize করে। বোঝায়; প্রশ্নের বর্ণনা `Indexed Allocation`-এর।
- **D option কেন ভুল:** `Hard Link` বলতে একই inode/file object-এর আরেক directory entry। বোঝায়; প্রশ্নের বর্ণনা `Indexed Allocation`-এর।
- **Related Concept:** Index overhead।
- **মনে রাখার টিপস:** Block pointer table।

---

## প্রশ্ন 757 | Topic: Operating System > File Systems | Difficulty: Medium | Type: Tracing

Q. Process open করলে file descriptor 3 পাওয়া গেল। এটি সাধারণত কী?

A) Physical block3
B) Process-local open-file handle
C) File size3
D) Permission level3

**সঠিক উত্তর: B) Process-local open-file handle**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** FD open-file table reference, disk block নয়।

#### Step-by-step সমাধান

```text
open(path) -> kernel open-file entry
process table slot -> integer 3
read(3,...) uses that handle
```
- **A option কেন ভুল:** Storage address নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Size metadata অন্যত্র।
- **D option কেন ভুল:** Permission bits নয়।
- **Related Concept:** 0,1,2 সাধারণত stdin/stdout/stderr Unix convention।
- **মনে রাখার টিপস:** FD is handle।

---

## প্রশ্ন 758 | Topic: Operating System > File Systems | Difficulty: Easy | Type: Calculation

Q. এক inode-এ original name ও 2টি additional hard link থাকলে link count কত?

A) 1
B) 2
C) 4
D) 3

**সঠিক উত্তর: D) 3**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Total directory entries pointing inode=1+2=3।

#### Step-by-step সমাধান

```text
Original=1
Additional=2
Link count=3
```
- **A option কেন ভুল:** Additional links বাদ।
- **B option কেন ভুল:** শুধু additional count।
- **C option কেন ভুল:** এক বেশি।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Delete name link count কমায়; zero হলে data reclaim হতে পারে।
- **মনে রাখার টিপস:** সব names count।

---

## প্রশ্ন 759 | Topic: Operating System > File Systems | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Pathname ধারণকারী পৃথক file যা target-এ resolve হয়।`—এখানে কোন concept প্রযোজ্য?

A) Inode
B) Linked Allocation
C) Symbolic Link
D) Journaling

**সঠিক উত্তর: C) Symbolic Link**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Pathname ধারণকারী পৃথক file যা target-এ resolve হয়।
- **A option কেন ভুল:** `Inode` বলতে Unix-like file-এর metadata ও data-block pointer রাখে; filename directory entry-তে। বোঝায়; প্রশ্নের বর্ণনা `Symbolic Link`-এর।
- **B option কেন ভুল:** `Linked Allocation` বলতে প্রতিটি file block next block pointer রাখে; growth সহজ, random access দুর্বল। বোঝায়; প্রশ্নের বর্ণনা `Symbolic Link`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Journaling` বলতে Metadata/data update log আগে লিখে crash recovery consistency উন্নত করা। বোঝায়; প্রশ্নের বর্ণনা `Symbolic Link`-এর।
- **Related Concept:** Dangling হতে পারে।
- **মনে রাখার টিপস:** Pointer by path।

---

## প্রশ্ন 760 | Topic: Operating System > File Systems | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Metadata/data update log আগে লিখে crash recovery consistency উন্নত করা।`

A) File
B) File Descriptor
C) Journaling
D) Linked Allocation

**সঠিক উত্তর: C) Journaling**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Metadata/data update log আগে লিখে crash recovery consistency উন্নত করা।
- **A option কেন ভুল:** `File` বলতে Named persistent byte বা record collection, metadataসহ storage abstraction। বোঝায়; প্রশ্নের বর্ণনা `Journaling`-এর।
- **B option কেন ভুল:** `File Descriptor` বলতে Process-local integer handle যা open-file table entry নির্দেশ করে। বোঝায়; প্রশ্নের বর্ণনা `Journaling`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Linked Allocation` বলতে প্রতিটি file block next block pointer রাখে; growth সহজ, random access দুর্বল। বোঝায়; প্রশ্নের বর্ণনা `Journaling`-এর।
- **Related Concept:** Write ordering গুরুত্বপূর্ণ।
- **মনে রাখার টিপস:** Log before commit।

---


# Chapter Theory 66: Disk Scheduling Algorithms

## বিস্তারিত Theory Note

HDD access time seek, rotation ও transfer নিয়ে গঠিত। Disk scheduling head movement কমিয়ে throughput বাড়াতে চায়; fairness ও starvation trade-off থাকে।

FCFS arrival order, SSTF nearest request, SCAN direction-reversing elevator, C-SCAN same-direction circular service এবং LOOK last pending request-এ reverse করে।

## মূল ধারণার মানচিত্র

- **Seek Time:** Disk head target track/cylinder-এ সরানোর সময়।
- **Rotational Latency:** Desired sector head-এর নিচে ঘুরে আসার অপেক্ষা।
- **Transfer Time:** Sector head-এর নিচে এলে data read/write করার সময়।
- **FCFS Disk Scheduling:** Request arrival order-এ serve।
- **SSTF:** Current head থেকে closest cylinder request আগে serve।
- **SCAN:** Elevator-এর মতো এক direction-এ requests serve করে end/limit-এ direction reverse।
- **C-SCAN:** এক direction-এ serve, end থেকে শুরুতে দ্রুত ফিরে আবার same direction।
- **LOOK:** SCAN-এর মতো, কিন্তু physical end নয়; সেই direction-এর last pending request-এ reverse।
- **Disk Queue:** Pending block I/O request-এর collection।
- **SSD Scheduling:** Mechanical seek নেই; HDD-specific head movement policy-এর গুরুত্ব কম।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Disk Scheduling Algorithms

## প্রশ্ন 761 | Topic: Operating System > Disk Scheduling | Difficulty: Hard | Type: Calculation

Q. Head cylinder 40 থেকে 65-এ গেলে head movement কত cylinder?

A) 105
B) 15
C) 25
D) 65

**সঠিক উত্তর: C) 25**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** |65−40|=25।

#### Step-by-step সমাধান

```text
|65-40|=25
```
- **A option কেন ভুল:** যোগ।
- **B option কেন ভুল:** Difference ভুল।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Target position।
- **Related Concept:** Movement absolute difference।
- **মনে রাখার টিপস:** |new−old|।

---

## প্রশ্ন 762 | Topic: Operating System > Disk Scheduling | Difficulty: Hard | Type: Theory

Q. `Rotational Latency` সম্পর্কে কোন statement সঠিক?

A) Disk head target track/cylinder-এ সরানোর সময়।
B) Desired sector head-এর নিচে ঘুরে আসার অপেক্ষা।
C) Mechanical seek নেই; HDD-specific head movement policy-এর গুরুত্ব কম।
D) Request arrival order-এ serve।

**সঠিক উত্তর: B) Desired sector head-এর নিচে ঘুরে আসার অপেক্ষা।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Desired sector head-এর নিচে ঘুরে আসার অপেক্ষা।
- **A option কেন ভুল:** এই statementটি `Seek Time` ধারণাকে বর্ণনা করে; `Rotational Latency`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `SSD Scheduling` ধারণাকে বর্ণনা করে; `Rotational Latency`-কে নয়।
- **D option কেন ভুল:** এই statementটি `FCFS Disk Scheduling` ধারণাকে বর্ণনা করে; `Rotational Latency`-কে নয়।
- **Related Concept:** RPM-এর ওপর নির্ভর।
- **মনে রাখার টিপস:** Wait for platter rotation।

---

## প্রশ্ন 763 | Topic: Operating System > Disk Scheduling | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Sector head-এর নিচে এলে data read/write করার সময়।`—এখানে কোন concept প্রযোজ্য?

A) SSTF
B) Transfer Time
C) C-SCAN
D) SCAN

**সঠিক উত্তর: B) Transfer Time**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Sector head-এর নিচে এলে data read/write করার সময়।
- **A option কেন ভুল:** `SSTF` বলতে Current head থেকে closest cylinder request আগে serve। বোঝায়; প্রশ্নের বর্ণনা `Transfer Time`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `C-SCAN` বলতে এক direction-এ serve, end থেকে শুরুতে দ্রুত ফিরে আবার same direction। বোঝায়; প্রশ্নের বর্ণনা `Transfer Time`-এর।
- **D option কেন ভুল:** `SCAN` বলতে Elevator-এর মতো এক direction-এ requests serve করে end/limit-এ direction reverse। বোঝায়; প্রশ্নের বর্ণনা `Transfer Time`-এর।
- **Related Concept:** Data size ও transfer rate নির্ভর।
- **মনে রাখার টিপস:** Move bytes time।

---

## প্রশ্ন 764 | Topic: Operating System > Disk Scheduling | Difficulty: Easy | Type: Calculation

Q. Head start 50; FCFS requests 82,43,140। Total head movement কত?

A) 168
B) 132
C) 187
D) 230

**সঠিক উত্তর: A) 168**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** FCFS arrival order-এ consecutive absolute movement 32+39+97=168।

#### Step-by-step সমাধান

```text
50 -> 82  = |82-50|  = 32
82 -> 43  = |43-82|  = 39
43 -> 140 = |140-43| = 97
Total = 32+39+97 = 168
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** শেষ movement undercount।
- **C option কেন ভুল:** Arithmetic ভুল।
- **D option কেন ভুল:** অতিরিক্ত movement।
- **Related Concept:** FCFS queue order পরিবর্তন করে না।
- **মনে রাখার টিপস:** Absolute differences যোগ।

---

## প্রশ্ন 765 | Topic: Operating System > Disk Scheduling | Difficulty: Medium | Type: Tracing

Q. Head 50; pending 45,58,90। SSTF প্রথম কোন request নেবে?

A) 58
B) 45
C) 90
D) Tie

**সঠিক উত্তর: B) 45**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Distance:5,8,40; nearest45।

#### Step-by-step সমাধান

```text
|45-50|=5
|58-50|=8
|90-50|=40
Select45
```
- **A option কেন ভুল:** Distance8।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Distance40।
- **D option কেন ভুল:** Distances distinct।
- **Related Concept:** SSTF absolute distance compare।
- **মনে রাখার টিপস:** Closest cylinder।

---

## প্রশ্ন 766 | Topic: Operating System > Disk Scheduling | Difficulty: Hard | Type: Tracing

Q. SCAN upward; head 40; requests 10,30,60,80; upper limit 99। Service order কী?

A) 30,10,60,80
B) 60,80,10,30
C) 10,30,60,80
D) 60,80,30,10

**সঠিক উত্তর: D) 60,80,30,10**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Upward requests ascending 60,80; limit/reverse পরে lower requests descending30,10।

#### Step-by-step সমাধান

```text
Upward pending:60,80
Serve:60,80
Reverse after upper end
Downward pending:30,10
Serve:30,10
```
- **A option কেন ভুল:** Initially downward।
- **B option কেন ভুল:** Reverse-এ nearest lower first হওয়া উচিত30।
- **C option কেন ভুল:** FCFS/sorted without direction।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** SCAN direction fixed first।
- **মনে রাখার টিপস:** Up side then reverse down।

---

## প্রশ্ন 767 | Topic: Operating System > Disk Scheduling | Difficulty: Hard | Type: Tracing

Q. C-SCAN upward; head 40; requests 10,30,60,80। Service order কী? Wrap movementে service হয় না।

A) 60,80,30,10
B) 60,80,10,30
C) 30,10,60,80
D) 10,30,60,80

**সঠিক উত্তর: B) 60,80,10,30**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Up 60,80; wrap to low end; same upward order10,30।

#### Step-by-step সমাধান

```text
Serve upward >40:60,80
Wrap to beginning
Serve upward <40:10,30
```
- **A option কেন ভুল:** এটি reverse direction SCAN।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Initial direction wrong।
- **D option কেন ভুল:** Head-এর নিচের request আগে নয়।
- **Related Concept:** C-SCAN one-direction service।
- **মনে রাখার টিপস:** End থেকে wrap, direction same।

---

## প্রশ্ন 768 | Topic: Operating System > Disk Scheduling | Difficulty: Hard | Type: Tracing

Q. LOOK upward; head 40; highest pending request 80, disk max199। কোথায় reverse করবে?

A) 80
B) 199
C) 40
D) 0

**সঠিক উত্তর: A) 80**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** LOOK physical end নয়, last request-এ reverse।

#### Step-by-step সমাধান

```text
Direction=up
Pending highest=80
No request 81..199
Reverse at80
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** SCAN physical limit।
- **C option কেন ভুল:** Starting head।
- **D option কেন ভুল:** Lower limit।
- **Related Concept:** LOOK pending request-এর বাইরে যায় না।
- **মনে রাখার টিপস:** Look ahead to last request।

---

## প্রশ্ন 769 | Topic: Operating System > Disk Scheduling | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Pending block I/O request-এর collection।`—এখানে কোন concept প্রযোজ্য?

A) Disk Queue
B) FCFS Disk Scheduling
C) LOOK
D) Seek Time

**সঠিক উত্তর: A) Disk Queue**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Pending block I/O request-এর collection।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `FCFS Disk Scheduling` বলতে Request arrival order-এ serve। বোঝায়; প্রশ্নের বর্ণনা `Disk Queue`-এর।
- **C option কেন ভুল:** `LOOK` বলতে SCAN-এর মতো, কিন্তু physical end নয়; সেই direction-এর last pending request-এ reverse। বোঝায়; প্রশ্নের বর্ণনা `Disk Queue`-এর।
- **D option কেন ভুল:** `Seek Time` বলতে Disk head target track/cylinder-এ সরানোর সময়। বোঝায়; প্রশ্নের বর্ণনা `Disk Queue`-এর।
- **Related Concept:** Scheduler order নির্ধারণ করে।
- **মনে রাখার টিপস:** Waiting I/O requests।

---

## প্রশ্ন 770 | Topic: Operating System > Disk Scheduling | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Mechanical seek নেই; HDD-specific head movement policy-এর গুরুত্ব কম।`

A) SSTF
B) SSD Scheduling
C) FCFS Disk Scheduling
D) Transfer Time

**সঠিক উত্তর: B) SSD Scheduling**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Mechanical seek নেই; HDD-specific head movement policy-এর গুরুত্ব কম।
- **A option কেন ভুল:** `SSTF` বলতে Current head থেকে closest cylinder request আগে serve। বোঝায়; প্রশ্নের বর্ণনা `SSD Scheduling`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `FCFS Disk Scheduling` বলতে Request arrival order-এ serve। বোঝায়; প্রশ্নের বর্ণনা `SSD Scheduling`-এর।
- **D option কেন ভুল:** `Transfer Time` বলতে Sector head-এর নিচে এলে data read/write করার সময়। বোঝায়; প্রশ্নের বর্ণনা `SSD Scheduling`-এর।
- **Related Concept:** Controller parallelism/wear অন্য concern।
- **মনে রাখার টিপস:** No moving head।

---


# Chapter Theory 67: I/O Management এবং Protection

## বিস্তারিত Theory Note

Device-independent I/O layer common interface দেয়; driver hardware-specific operation করে। DMA block transfer-এর সময় CPU overhead কমায়, আর buffering/spooling rate mismatch ও exclusive device sharing সামলায়।

Protection policy subject, object ও right-এর relation নিয়ন্ত্রণ করে। ACL object-centric; capability subject-held authority token। Least privilege unnecessary access কমায়।

## মূল ধারণার মানচিত্র

- **Device Driver:** OS generic I/O request-কে device-specific command-এ translate করা software।
- **DMA:** Device controller CPU প্রতি byte না সরিয়ে memory-এর সঙ্গে block transfer করে।
- **Buffering:** Producer/consumer speed mismatch সামলাতে temporary memory region।
- **Spooling:** Disk queue-এ job জমিয়ে exclusive slow device sequentially serve করা।
- **Access Control List:** Object-এর সঙ্গে subject/user ও permission list সংরক্ষণ।
- **Capability:** Subject-এর কাছে unforgeable token/reference যা object permission দেয়।
- **Protection Domain:** Process/user-এর accessible object ও allowed operation set।
- **Malware:** System confidentiality, integrity বা availability ক্ষতি করা malicious software।
- **Secure Boot:** Boot component cryptographic verification করে trusted chain থেকে system শুরু।
- **Principle of Least Privilege:** কাজের জন্য প্রয়োজনীয় minimum permission দেওয়া।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: I/O Management এবং Protection

## প্রশ্ন 771 | Topic: Operating System > I/O and Protection | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`OS generic I/O request-কে device-specific command-এ translate করা software।`

A) Protection Domain
B) Principle of Least Privilege
C) Capability
D) Device Driver

**সঠিক উত্তর: D) Device Driver**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** OS generic I/O request-কে device-specific command-এ translate করা software।
- **A option কেন ভুল:** `Protection Domain` বলতে Process/user-এর accessible object ও allowed operation set। বোঝায়; প্রশ্নের বর্ণনা `Device Driver`-এর।
- **B option কেন ভুল:** `Principle of Least Privilege` বলতে কাজের জন্য প্রয়োজনীয় minimum permission দেওয়া। বোঝায়; প্রশ্নের বর্ণনা `Device Driver`-এর।
- **C option কেন ভুল:** `Capability` বলতে Subject-এর কাছে unforgeable token/reference যা object permission দেয়। বোঝায়; প্রশ্নের বর্ণনা `Device Driver`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Kernel module হতে পারে।
- **মনে রাখার টিপস:** Hardware-specific control।

---

## প্রশ্ন 772 | Topic: Operating System > I/O and Protection | Difficulty: Medium | Type: Calculation

Q. DMA transfer 4096 byte block; CPU setup 20 microsecond এবং completion handling 10 microsecond। Per-byte CPU copy লাগছে না। Total CPU involvement কত?

A) 10 us
B) 20 us
C) 4096 us
D) 30 us

**সঠিক উত্তর: D) 30 us**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** CPU শুধু setup ও completion 20+10=30 microsecond।

#### Step-by-step সমাধান

```text
Setup=20 us
Completion=10 us
CPU involvement=30 us
```
- **A option কেন ভুল:** শুধু completion।
- **B option কেন ভুল:** শুধু setup।
- **C option কেন ভুল:** প্রতি byte 1 us ধরে DMA সুবিধা উপেক্ষা।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** DMA data transfer controller করে, CPU concurrent কাজ করতে পারে।
- **মনে রাখার টিপস:** Setup + completion।

---

## প্রশ্ন 773 | Topic: Operating System > I/O and Protection | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Producer/consumer speed mismatch সামলাতে temporary memory region।`—এখানে কোন concept প্রযোজ্য?

A) Buffering
B) DMA
C) Capability
D) Access Control List

**সঠিক উত্তর: A) Buffering**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Producer/consumer speed mismatch সামলাতে temporary memory region।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `DMA` বলতে Device controller CPU প্রতি byte না সরিয়ে memory-এর সঙ্গে block transfer করে। বোঝায়; প্রশ্নের বর্ণনা `Buffering`-এর।
- **C option কেন ভুল:** `Capability` বলতে Subject-এর কাছে unforgeable token/reference যা object permission দেয়। বোঝায়; প্রশ্নের বর্ণনা `Buffering`-এর।
- **D option কেন ভুল:** `Access Control List` বলতে Object-এর সঙ্গে subject/user ও permission list সংরক্ষণ। বোঝায়; প্রশ্নের বর্ণনা `Buffering`-এর।
- **Related Concept:** Single/double/circular buffer।
- **মনে রাখার টিপস:** Temporary data holding।

---

## প্রশ্ন 774 | Topic: Operating System > I/O and Protection | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Disk queue-এ job জমিয়ে exclusive slow device sequentially serve করা।`

A) DMA
B) Secure Boot
C) Device Driver
D) Spooling

**সঠিক উত্তর: D) Spooling**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Disk queue-এ job জমিয়ে exclusive slow device sequentially serve করা।
- **A option কেন ভুল:** `DMA` বলতে Device controller CPU প্রতি byte না সরিয়ে memory-এর সঙ্গে block transfer করে। বোঝায়; প্রশ্নের বর্ণনা `Spooling`-এর।
- **B option কেন ভুল:** `Secure Boot` বলতে Boot component cryptographic verification করে trusted chain থেকে system শুরু। বোঝায়; প্রশ্নের বর্ণনা `Spooling`-এর।
- **C option কেন ভুল:** `Device Driver` বলতে OS generic I/O request-কে device-specific command-এ translate করা software। বোঝায়; প্রশ্নের বর্ণনা `Spooling`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Printer classic example।
- **মনে রাখার টিপস:** Queue work for device।

---

## প্রশ্ন 775 | Topic: Operating System > I/O and Protection | Difficulty: Easy | Type: Theory

Q. `Access Control List` সম্পর্কে কোন statement সঠিক?

A) Disk queue-এ job জমিয়ে exclusive slow device sequentially serve করা।
B) Producer/consumer speed mismatch সামলাতে temporary memory region।
C) OS generic I/O request-কে device-specific command-এ translate করা software।
D) Object-এর সঙ্গে subject/user ও permission list সংরক্ষণ।

**সঠিক উত্তর: D) Object-এর সঙ্গে subject/user ও permission list সংরক্ষণ।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Object-এর সঙ্গে subject/user ও permission list সংরক্ষণ।
- **A option কেন ভুল:** এই statementটি `Spooling` ধারণাকে বর্ণনা করে; `Access Control List`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Buffering` ধারণাকে বর্ণনা করে; `Access Control List`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Device Driver` ধারণাকে বর্ণনা করে; `Access Control List`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Object-centric access control।
- **মনে রাখার টিপস:** Who may do what to object।

---

## প্রশ্ন 776 | Topic: Operating System > I/O and Protection | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Subject-এর কাছে unforgeable token/reference যা object permission দেয়।`—এখানে কোন concept প্রযোজ্য?

A) Capability
B) Malware
C) Access Control List
D) Spooling

**সঠিক উত্তর: A) Capability**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Subject-এর কাছে unforgeable token/reference যা object permission দেয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Malware` বলতে System confidentiality, integrity বা availability ক্ষতি করা malicious software। বোঝায়; প্রশ্নের বর্ণনা `Capability`-এর।
- **C option কেন ভুল:** `Access Control List` বলতে Object-এর সঙ্গে subject/user ও permission list সংরক্ষণ। বোঝায়; প্রশ্নের বর্ণনা `Capability`-এর।
- **D option কেন ভুল:** `Spooling` বলতে Disk queue-এ job জমিয়ে exclusive slow device sequentially serve করা। বোঝায়; প্রশ্নের বর্ণনা `Capability`-এর।
- **Related Concept:** Subject-centric delegation।
- **মনে রাখার টিপস:** Possession grants authority।

---

## প্রশ্ন 777 | Topic: Operating System > I/O and Protection | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Process/user-এর accessible object ও allowed operation set।`

A) Principle of Least Privilege
B) Spooling
C) Capability
D) Protection Domain

**সঠিক উত্তর: D) Protection Domain**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Process/user-এর accessible object ও allowed operation set।
- **A option কেন ভুল:** `Principle of Least Privilege` বলতে কাজের জন্য প্রয়োজনীয় minimum permission দেওয়া। বোঝায়; প্রশ্নের বর্ণনা `Protection Domain`-এর।
- **B option কেন ভুল:** `Spooling` বলতে Disk queue-এ job জমিয়ে exclusive slow device sequentially serve করা। বোঝায়; প্রশ্নের বর্ণনা `Protection Domain`-এর।
- **C option কেন ভুল:** `Capability` বলতে Subject-এর কাছে unforgeable token/reference যা object permission দেয়। বোঝায়; প্রশ্নের বর্ণনা `Protection Domain`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Domain switch controlled।
- **মনে রাখার টিপস:** Current rights set।

---

## প্রশ্ন 778 | Topic: Operating System > I/O and Protection | Difficulty: Medium | Type: Theory

Q. `Malware` সম্পর্কে কোন statement সঠিক?

A) System confidentiality, integrity বা availability ক্ষতি করা malicious software।
B) Producer/consumer speed mismatch সামলাতে temporary memory region।
C) Device controller CPU প্রতি byte না সরিয়ে memory-এর সঙ্গে block transfer করে।
D) Process/user-এর accessible object ও allowed operation set।

**সঠিক উত্তর: A) System confidentiality, integrity বা availability ক্ষতি করা malicious software।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** System confidentiality, integrity বা availability ক্ষতি করা malicious software।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Buffering` ধারণাকে বর্ণনা করে; `Malware`-কে নয়।
- **C option কেন ভুল:** এই statementটি `DMA` ধারণাকে বর্ণনা করে; `Malware`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Protection Domain` ধারণাকে বর্ণনা করে; `Malware`-কে নয়।
- **Related Concept:** Virus,worm,trojan,ransomware।
- **মনে রাখার টিপস:** Malicious code।

---

## প্রশ্ন 779 | Topic: Operating System > I/O and Protection | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Boot component cryptographic verification করে trusted chain থেকে system শুরু।`—এখানে কোন concept প্রযোজ্য?

A) Secure Boot
B) Access Control List
C) Device Driver
D) DMA

**সঠিক উত্তর: A) Secure Boot**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Boot component cryptographic verification করে trusted chain থেকে system শুরু।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Access Control List` বলতে Object-এর সঙ্গে subject/user ও permission list সংরক্ষণ। বোঝায়; প্রশ্নের বর্ণনা `Secure Boot`-এর।
- **C option কেন ভুল:** `Device Driver` বলতে OS generic I/O request-কে device-specific command-এ translate করা software। বোঝায়; প্রশ্নের বর্ণনা `Secure Boot`-এর।
- **D option কেন ভুল:** `DMA` বলতে Device controller CPU প্রতি byte না সরিয়ে memory-এর সঙ্গে block transfer করে। বোঝায়; প্রশ্নের বর্ণনা `Secure Boot`-এর।
- **Related Concept:** Firmware root of trust।
- **মনে রাখার টিপস:** Verify before execute।

---

## প্রশ্ন 780 | Topic: Operating System > I/O and Protection | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`কাজের জন্য প্রয়োজনীয় minimum permission দেওয়া।`

A) Secure Boot
B) Principle of Least Privilege
C) Buffering
D) Spooling

**সঠিক উত্তর: B) Principle of Least Privilege**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** কাজের জন্য প্রয়োজনীয় minimum permission দেওয়া।
- **A option কেন ভুল:** `Secure Boot` বলতে Boot component cryptographic verification করে trusted chain থেকে system শুরু। বোঝায়; প্রশ্নের বর্ণনা `Principle of Least Privilege`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Buffering` বলতে Producer/consumer speed mismatch সামলাতে temporary memory region। বোঝায়; প্রশ্নের বর্ণনা `Principle of Least Privilege`-এর।
- **D option কেন ভুল:** `Spooling` বলতে Disk queue-এ job জমিয়ে exclusive slow device sequentially serve করা। বোঝায়; প্রশ্নের বর্ণনা `Principle of Least Privilege`-এর।
- **Related Concept:** Attack impact কমায়।
- **মনে রাখার টিপস:** Minimum rights।

---


# Chapter Theory 68: Linux/Unix, Real-time এবং Distributed OS

## বিস্তারিত Theory Note

Unix process model-এ `fork` process তৈরি করে এবং `exec` program image replace করে। Shell pipeline process ও file descriptor connect করে।

Real-time correctness value ও timing দুটির ওপর নির্ভরশীল। Distributed system partial failure, network delay ও unsynchronized clock handle করে; transparency complexity পুরোপুরি দূর করে না।

## মূল ধারণার মানচিত্র

- **Shell:** Command parse, expansion, pipeline ও program launch করা user interface।
- **Pipe:** এক process-এর output অন্য process-এর input-এ byte stream হিসেবে যুক্ত করে।
- **fork:** Unix process system call যা caller-এর child process তৈরি করে; return value parent/child আলাদা।
- **exec:** Current process image নতুন program দিয়ে replace করে।
- **Hard Real-time:** Deadline miss unacceptable system।
- **Soft Real-time:** Deadline গুরুত্বপূর্ণ কিন্তু occasional miss quality কমায়, catastrophic নয়।
- **Distributed OS:** Networked machines-এর resource ও computationকে integratedভাবে manage করার system concept।
- **Transparency:** Distribution detail user/program থেকে লুকানো property।
- **Remote Procedure Call:** Remote service invocation-কে local procedure call-এর মতো interface দেয়।
- **Clock Synchronization:** Distributed node clock-এর difference সীমিত/estimate করার mechanism।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Linux/Unix, Real-time এবং Distributed OS

## প্রশ্ন 781 | Topic: Operating System > OS Environments | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Command parse, expansion, pipeline ও program launch করা user interface।`

A) Distributed OS
B) Shell
C) fork
D) Soft Real-time

**সঠিক উত্তর: B) Shell**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Command parse, expansion, pipeline ও program launch করা user interface।
- **A option কেন ভুল:** `Distributed OS` বলতে Networked machines-এর resource ও computationকে integratedভাবে manage করার system concept। বোঝায়; প্রশ্নের বর্ণনা `Shell`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `fork` বলতে Unix process system call যা caller-এর child process তৈরি করে; return value parent/child আলাদা। বোঝায়; প্রশ্নের বর্ণনা `Shell`-এর।
- **D option কেন ভুল:** `Soft Real-time` বলতে Deadline গুরুত্বপূর্ণ কিন্তু occasional miss quality কমায়, catastrophic নয়। বোঝায়; প্রশ্নের বর্ণনা `Shell`-এর।
- **Related Concept:** bash, zsh উদাহরণ।
- **মনে রাখার টিপস:** Command interpreter।

---

## প্রশ্ন 782 | Topic: Operating System > OS Environments | Difficulty: Medium | Type: Theory

Q. `Pipe` সম্পর্কে কোন statement সঠিক?

A) Networked machines-এর resource ও computationকে integratedভাবে manage করার system concept।
B) Command parse, expansion, pipeline ও program launch করা user interface।
C) Deadline miss unacceptable system।
D) এক process-এর output অন্য process-এর input-এ byte stream হিসেবে যুক্ত করে।

**সঠিক উত্তর: D) এক process-এর output অন্য process-এর input-এ byte stream হিসেবে যুক্ত করে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** এক process-এর output অন্য process-এর input-এ byte stream হিসেবে যুক্ত করে।
- **A option কেন ভুল:** এই statementটি `Distributed OS` ধারণাকে বর্ণনা করে; `Pipe`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Shell` ধারণাকে বর্ণনা করে; `Pipe`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Hard Real-time` ধারণাকে বর্ণনা করে; `Pipe`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `|` shell syntax।
- **মনে রাখার টিপস:** Output-to-input channel।

---

## প্রশ্ন 783 | Topic: Operating System > OS Environments | Difficulty: Medium | Type: Calculation

Q. এক process `fork()` একবার সফলভাবে call করলে মোট process সংখ্যা কত হয়, initial parentসহ?

A) 1
B) 2
C) 3
D) 4

**সঠিক উত্তর: B) 2**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Parent থাকে এবং একটি child তৈরি হয়।

#### Step-by-step সমাধান

```text
Before fork:1 parent
After fork: parent + child=2
```
- **A option কেন ভুল:** Child বাদ।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** দুই child ধরে।
- **D option কেন ভুল:** দুইবার fork-এর মতো।
- **Related Concept:** পরপর n unconditional fork আদর্শভাবে 2^n process।
- **মনে রাখার টিপস:** এক fork count দ্বিগুণ।

---

## প্রশ্ন 784 | Topic: Operating System > OS Environments | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Current process image নতুন program দিয়ে replace করে।`

A) Clock Synchronization
B) Pipe
C) exec
D) Hard Real-time

**সঠিক উত্তর: C) exec**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Current process image নতুন program দিয়ে replace করে।
- **A option কেন ভুল:** `Clock Synchronization` বলতে Distributed node clock-এর difference সীমিত/estimate করার mechanism। বোঝায়; প্রশ্নের বর্ণনা `exec`-এর।
- **B option কেন ভুল:** `Pipe` বলতে এক process-এর output অন্য process-এর input-এ byte stream হিসেবে যুক্ত করে। বোঝায়; প্রশ্নের বর্ণনা `exec`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Hard Real-time` বলতে Deadline miss unacceptable system। বোঝায়; প্রশ্নের বর্ণনা `exec`-এর।
- **Related Concept:** Successful হলে old code-এ ফেরে না।
- **মনে রাখার টিপস:** Replace program image।

---

## প্রশ্ন 785 | Topic: Operating System > OS Environments | Difficulty: Medium | Type: Calculation

Q. Periodic hard real-time task period 20 ms হলে প্রতি second-এ release count কত?

A) 20
B) 100
C) 50
D) 200

**সঠিক উত্তর: C) 50**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 1000 ms/20=50।

#### Step-by-step সমাধান

```text
Releases=1000/20=50 per second
```
- **A option কেন ভুল:** Period value।
- **B option কেন ভুল:** 10ms period।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** 5ms period।
- **Related Concept:** Frequency=1/period।
- **মনে রাখার টিপস:** এক second 1000 ms।

---

## প্রশ্ন 786 | Topic: Operating System > OS Environments | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Deadline গুরুত্বপূর্ণ কিন্তু occasional miss quality কমায়, catastrophic নয়।`—এখানে কোন concept প্রযোজ্য?

A) Distributed OS
B) fork
C) Soft Real-time
D) Remote Procedure Call

**সঠিক উত্তর: C) Soft Real-time**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Deadline গুরুত্বপূর্ণ কিন্তু occasional miss quality কমায়, catastrophic নয়।
- **A option কেন ভুল:** `Distributed OS` বলতে Networked machines-এর resource ও computationকে integratedভাবে manage করার system concept। বোঝায়; প্রশ্নের বর্ণনা `Soft Real-time`-এর।
- **B option কেন ভুল:** `fork` বলতে Unix process system call যা caller-এর child process তৈরি করে; return value parent/child আলাদা। বোঝায়; প্রশ্নের বর্ণনা `Soft Real-time`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Remote Procedure Call` বলতে Remote service invocation-কে local procedure call-এর মতো interface দেয়। বোঝায়; প্রশ্নের বর্ণনা `Soft Real-time`-এর।
- **Related Concept:** Multimedia উদাহরণ।
- **মনে রাখার টিপস:** Late result still useful somewhat।

---

## প্রশ্ন 787 | Topic: Operating System > OS Environments | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Networked machines-এর resource ও computationকে integratedভাবে manage করার system concept।`

A) Clock Synchronization
B) Transparency
C) Distributed OS
D) Hard Real-time

**সঠিক উত্তর: C) Distributed OS**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Networked machines-এর resource ও computationকে integratedভাবে manage করার system concept।
- **A option কেন ভুল:** `Clock Synchronization` বলতে Distributed node clock-এর difference সীমিত/estimate করার mechanism। বোঝায়; প্রশ্নের বর্ণনা `Distributed OS`-এর।
- **B option কেন ভুল:** `Transparency` বলতে Distribution detail user/program থেকে লুকানো property। বোঝায়; প্রশ্নের বর্ণনা `Distributed OS`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Hard Real-time` বলতে Deadline miss unacceptable system। বোঝায়; প্রশ্নের বর্ণনা `Distributed OS`-এর।
- **Related Concept:** Transparency goal।
- **মনে রাখার টিপস:** Many machines, unified view।

---

## প্রশ্ন 788 | Topic: Operating System > OS Environments | Difficulty: Medium | Type: Theory

Q. `Transparency` সম্পর্কে কোন statement সঠিক?

A) Distribution detail user/program থেকে লুকানো property।
B) Networked machines-এর resource ও computationকে integratedভাবে manage করার system concept।
C) Command parse, expansion, pipeline ও program launch করা user interface।
D) Deadline গুরুত্বপূর্ণ কিন্তু occasional miss quality কমায়, catastrophic নয়।

**সঠিক উত্তর: A) Distribution detail user/program থেকে লুকানো property।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Distribution detail user/program থেকে লুকানো property।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Distributed OS` ধারণাকে বর্ণনা করে; `Transparency`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Shell` ধারণাকে বর্ণনা করে; `Transparency`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Soft Real-time` ধারণাকে বর্ণনা করে; `Transparency`-কে নয়।
- **Related Concept:** Location, migration, replication transparency।
- **মনে রাখার টিপস:** Looks unified।

---

## প্রশ্ন 789 | Topic: Operating System > OS Environments | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Remote service invocation-কে local procedure call-এর মতো interface দেয়।`—এখানে কোন concept প্রযোজ্য?

A) Shell
B) Soft Real-time
C) Remote Procedure Call
D) Transparency

**সঠিক উত্তর: C) Remote Procedure Call**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Remote service invocation-কে local procedure call-এর মতো interface দেয়।
- **A option কেন ভুল:** `Shell` বলতে Command parse, expansion, pipeline ও program launch করা user interface। বোঝায়; প্রশ্নের বর্ণনা `Remote Procedure Call`-এর।
- **B option কেন ভুল:** `Soft Real-time` বলতে Deadline গুরুত্বপূর্ণ কিন্তু occasional miss quality কমায়, catastrophic নয়। বোঝায়; প্রশ্নের বর্ণনা `Remote Procedure Call`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Transparency` বলতে Distribution detail user/program থেকে লুকানো property। বোঝায়; প্রশ্নের বর্ণনা `Remote Procedure Call`-এর।
- **Related Concept:** Marshalling ও network failure handle।
- **মনে রাখার টিপস:** Call across network।

---

## প্রশ্ন 790 | Topic: Operating System > OS Environments | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Distributed node clock-এর difference সীমিত/estimate করার mechanism।`

A) Soft Real-time
B) Transparency
C) Remote Procedure Call
D) Clock Synchronization

**সঠিক উত্তর: D) Clock Synchronization**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Distributed node clock-এর difference সীমিত/estimate করার mechanism।
- **A option কেন ভুল:** `Soft Real-time` বলতে Deadline গুরুত্বপূর্ণ কিন্তু occasional miss quality কমায়, catastrophic নয়। বোঝায়; প্রশ্নের বর্ণনা `Clock Synchronization`-এর।
- **B option কেন ভুল:** `Transparency` বলতে Distribution detail user/program থেকে লুকানো property। বোঝায়; প্রশ্নের বর্ণনা `Clock Synchronization`-এর।
- **C option কেন ভুল:** `Remote Procedure Call` বলতে Remote service invocation-কে local procedure call-এর মতো interface দেয়। বোঝায়; প্রশ্নের বর্ণনা `Clock Synchronization`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** No perfect global clock।
- **মনে রাখার টিপস:** Coordinate time across nodes।

---

# Chapter Theory 69: Database এবং DBMS Fundamentals

## বিস্তারিত Theory Note

Database শুধু file collection নয়; shared meaning, constraint ও controlled operation থাকে। DBMS logical query-কে storage operation-এ রূপান্তর করে, concurrent user isolate করে, failure recovery ও authorization দেয়।

Schema structure, instance current state। Metadata catalog schema, index ও privilege বর্ণনা করে। Redundancy সবসময় খারাপ নয়, তবে uncontrolled duplication inconsistency তৈরি করে।

## মূল ধারণার মানচিত্র

- **Database:** Related data-এর organized persistent collection, যা controlled access ও update সমর্থন করে।
- **DBMS:** Database define, store, query, secure, recover ও concurrently manage করা software system।
- **Metadata:** Data-এর structure, type, constraint ও origin সম্পর্কিত data।
- **Schema:** Database-এর logical structure ও constraint-এর comparatively stable definition।
- **Instance:** নির্দিষ্ট সময়ে database-এ থাকা actual data state।
- **Data Redundancy:** একই fact অপ্রয়োজনীয়ভাবে বহু স্থানে সংরক্ষণ।
- **Data Integrity:** Data accurate, valid ও consistent রাখার property।
- **Data Dictionary:** Schema object, column, constraint, privilege ইত্যাদির system catalog।
- **Database Administrator:** Security, backup, tuning, availability ও lifecycle manage করা role।
- **Data Model:** Data structure, relationship, constraint ও operation প্রকাশের conceptual framework।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Database এবং DBMS Fundamentals

## প্রশ্ন 791 | Topic: Database Management System > DBMS Basics | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Related data-এর organized persistent collection, যা controlled access ও update সমর্থন করে।`

A) Database
B) Instance
C) Metadata
D) Data Integrity

**সঠিক উত্তর: A) Database**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Related data-এর organized persistent collection, যা controlled access ও update সমর্থন করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Instance` বলতে নির্দিষ্ট সময়ে database-এ থাকা actual data state। বোঝায়; প্রশ্নের বর্ণনা `Database`-এর।
- **C option কেন ভুল:** `Metadata` বলতে Data-এর structure, type, constraint ও origin সম্পর্কিত data। বোঝায়; প্রশ্নের বর্ণনা `Database`-এর।
- **D option কেন ভুল:** `Data Integrity` বলতে Data accurate, valid ও consistent রাখার property। বোঝায়; প্রশ্নের বর্ণনা `Database`-এর।
- **Related Concept:** Schema data structure নির্ধারণ করে।
- **মনে রাখার টিপস:** Persistent organized data।

---

## প্রশ্ন 792 | Topic: Database Management System > DBMS Basics | Difficulty: Easy | Type: Theory

Q. `DBMS` সম্পর্কে কোন statement সঠিক?

A) Data accurate, valid ও consistent রাখার property।
B) Schema object, column, constraint, privilege ইত্যাদির system catalog।
C) Database-এর logical structure ও constraint-এর comparatively stable definition।
D) Database define, store, query, secure, recover ও concurrently manage করা software system।

**সঠিক উত্তর: D) Database define, store, query, secure, recover ও concurrently manage করা software system।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Database define, store, query, secure, recover ও concurrently manage করা software system।
- **A option কেন ভুল:** এই statementটি `Data Integrity` ধারণাকে বর্ণনা করে; `DBMS`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Data Dictionary` ধারণাকে বর্ণনা করে; `DBMS`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Schema` ধারণাকে বর্ণনা করে; `DBMS`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Applications ও storage-এর মধ্যবর্তী layer।
- **মনে রাখার টিপস:** Database manager।

---

## প্রশ্ন 793 | Topic: Database Management System > DBMS Basics | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Data-এর structure, type, constraint ও origin সম্পর্কিত data।`—এখানে কোন concept প্রযোজ্য?

A) Data Redundancy
B) Database Administrator
C) Instance
D) Metadata

**সঠিক উত্তর: D) Metadata**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Data-এর structure, type, constraint ও origin সম্পর্কিত data।
- **A option কেন ভুল:** `Data Redundancy` বলতে একই fact অপ্রয়োজনীয়ভাবে বহু স্থানে সংরক্ষণ। বোঝায়; প্রশ্নের বর্ণনা `Metadata`-এর।
- **B option কেন ভুল:** `Database Administrator` বলতে Security, backup, tuning, availability ও lifecycle manage করা role। বোঝায়; প্রশ্নের বর্ণনা `Metadata`-এর।
- **C option কেন ভুল:** `Instance` বলতে নির্দিষ্ট সময়ে database-এ থাকা actual data state। বোঝায়; প্রশ্নের বর্ণনা `Metadata`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Catalog/data dictionary-তে থাকে।
- **মনে রাখার টিপস:** Data about data।

---

## প্রশ্ন 794 | Topic: Database Management System > DBMS Basics | Difficulty: Medium | Type: Tracing

Q. Schema-তে `Student(id INT, name TEXT)` আছে এবং বর্তমানে 500 row। Schema ও instance-এর মধ্যে কোনটি 500 নির্দেশ করে?

A) Instance
B) Schema
C) Metadata only
D) Data model

**সঠিক উত্তর: A) Instance**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 500 row নির্দিষ্ট সময়ের actual database content; schema table shape।

#### Step-by-step সমাধান

```text
Schema: Student(id,name)
Instance: 500 current tuples
Therefore 500 belongs to instance
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Column/type definition।
- **C option কেন ভুল:** Count actual state, শুধু structural metadata নয়।
- **D option কেন ভুল:** Relational abstraction, current row count নয়।
- **Related Concept:** Schema তুলনামূলক স্থিতিশীল; instance ঘন ঘন বদলায়।
- **মনে রাখার টিপস:** Blueprint বনাম current data।

---

## প্রশ্ন 795 | Topic: Database Management System > DBMS Basics | Difficulty: Easy | Type: Theory

Q. `Instance` সম্পর্কে কোন statement সঠিক?

A) Data structure, relationship, constraint ও operation প্রকাশের conceptual framework।
B) Schema object, column, constraint, privilege ইত্যাদির system catalog।
C) নির্দিষ্ট সময়ে database-এ থাকা actual data state।
D) Database-এর logical structure ও constraint-এর comparatively stable definition।

**সঠিক উত্তর: C) নির্দিষ্ট সময়ে database-এ থাকা actual data state।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** নির্দিষ্ট সময়ে database-এ থাকা actual data state।
- **A option কেন ভুল:** এই statementটি `Data Model` ধারণাকে বর্ণনা করে; `Instance`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Data Dictionary` ধারণাকে বর্ণনা করে; `Instance`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Schema` ধারণাকে বর্ণনা করে; `Instance`-কে নয়।
- **Related Concept:** State পরিবর্তিত হয়।
- **মনে রাখার টিপস:** Current contents।

---

## প্রশ্ন 796 | Topic: Database Management System > DBMS Basics | Difficulty: Hard | Type: Calculation

Q. এক customer address 4টি order row-তে duplicate রাখা হলে একই address fact-এর storage occurrence কত?

A) 1
B) 4
C) 3
D) 5

**সঠিক উত্তর: B) 4**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি order row-তে address copy থাকলে চার occurrence।

#### Step-by-step সমাধান

```text
Order rows=4
Address copied in each row
Occurrences=4
```
- **A option কেন ভুল:** Normalized separate customer table হলে হতে পারত।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** একটি row বাদ।
- **D option কেন ভুল:** এক বেশি।
- **Related Concept:** Redundancy update anomaly তৈরি করে।
- **মনে রাখার টিপস:** যত duplicate row, তত occurrence।

---

## প্রশ্ন 797 | Topic: Database Management System > DBMS Basics | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Data accurate, valid ও consistent রাখার property।`

A) Schema
B) Data Redundancy
C) Data Integrity
D) Data Dictionary

**সঠিক উত্তর: C) Data Integrity**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Data accurate, valid ও consistent রাখার property।
- **A option কেন ভুল:** `Schema` বলতে Database-এর logical structure ও constraint-এর comparatively stable definition। বোঝায়; প্রশ্নের বর্ণনা `Data Integrity`-এর।
- **B option কেন ভুল:** `Data Redundancy` বলতে একই fact অপ্রয়োজনীয়ভাবে বহু স্থানে সংরক্ষণ। বোঝায়; প্রশ্নের বর্ণনা `Data Integrity`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Data Dictionary` বলতে Schema object, column, constraint, privilege ইত্যাদির system catalog। বোঝায়; প্রশ্নের বর্ণনা `Data Integrity`-এর।
- **Related Concept:** Constraint ও transaction সহায়ক।
- **মনে রাখার টিপস:** Correct and consistent data।

---

## প্রশ্ন 798 | Topic: Database Management System > DBMS Basics | Difficulty: Medium | Type: Theory

Q. `Data Dictionary` সম্পর্কে কোন statement সঠিক?

A) Database define, store, query, secure, recover ও concurrently manage করা software system।
B) Schema object, column, constraint, privilege ইত্যাদির system catalog।
C) Data-এর structure, type, constraint ও origin সম্পর্কিত data।
D) Data structure, relationship, constraint ও operation প্রকাশের conceptual framework।

**সঠিক উত্তর: B) Schema object, column, constraint, privilege ইত্যাদির system catalog।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Schema object, column, constraint, privilege ইত্যাদির system catalog।
- **A option কেন ভুল:** এই statementটি `DBMS` ধারণাকে বর্ণনা করে; `Data Dictionary`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `Metadata` ধারণাকে বর্ণনা করে; `Data Dictionary`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Data Model` ধারণাকে বর্ণনা করে; `Data Dictionary`-কে নয়।
- **Related Concept:** DBMS নিজেও query করতে পারে।
- **মনে রাখার টিপস:** Catalog of metadata।

---

## প্রশ্ন 799 | Topic: Database Management System > DBMS Basics | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Security, backup, tuning, availability ও lifecycle manage করা role।`—এখানে কোন concept প্রযোজ্য?

A) Data Integrity
B) Data Dictionary
C) Instance
D) Database Administrator

**সঠিক উত্তর: D) Database Administrator**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Security, backup, tuning, availability ও lifecycle manage করা role।
- **A option কেন ভুল:** `Data Integrity` বলতে Data accurate, valid ও consistent রাখার property। বোঝায়; প্রশ্নের বর্ণনা `Database Administrator`-এর।
- **B option কেন ভুল:** `Data Dictionary` বলতে Schema object, column, constraint, privilege ইত্যাদির system catalog। বোঝায়; প্রশ্নের বর্ণনা `Database Administrator`-এর।
- **C option কেন ভুল:** `Instance` বলতে নির্দিষ্ট সময়ে database-এ থাকা actual data state। বোঝায়; প্রশ্নের বর্ণনা `Database Administrator`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Policy ও operation দুইই।
- **মনে রাখার টিপস:** DB operational owner।

---

## প্রশ্ন 800 | Topic: Database Management System > DBMS Basics | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Data structure, relationship, constraint ও operation প্রকাশের conceptual framework।`

A) Data Integrity
B) Data Model
C) Data Dictionary
D) Database Administrator

**সঠিক উত্তর: B) Data Model**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Data structure, relationship, constraint ও operation প্রকাশের conceptual framework।
- **A option কেন ভুল:** `Data Integrity` বলতে Data accurate, valid ও consistent রাখার property। বোঝায়; প্রশ্নের বর্ণনা `Data Model`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Data Dictionary` বলতে Schema object, column, constraint, privilege ইত্যাদির system catalog। বোঝায়; প্রশ্নের বর্ণনা `Data Model`-এর।
- **D option কেন ভুল:** `Database Administrator` বলতে Security, backup, tuning, availability ও lifecycle manage করা role। বোঝায়; প্রশ্নের বর্ণনা `Data Model`-এর।
- **Related Concept:** Relational, document, graph ইত্যাদি।
- **মনে রাখার টিপস:** How data is represented।

---


# Chapter Theory 70: Database Architecture এবং Data Independence

## বিস্তারিত Theory Note

Three-schema architecture view-level applicationকে global logical schema ও physical storage থেকে decouple করে। সম্পূর্ণ independence বাস্তবে কঠিন, কিন্তু mapping layer change impact কমায়।

Physical independence সাধারণত অর্জন সহজ; conceptual schema change application semantics প্রভাবিত করতে পারে বলে logical independence কঠিন।

## মূল ধারণার মানচিত্র

- **Three-schema Architecture:** External, conceptual ও internal level আলাদা করে data abstraction ও independence প্রদান।
- **External Schema:** নির্দিষ্ট user/application-এর view of database।
- **Conceptual Schema:** সম্পূর্ণ database-এর global logical structure, storage detail ছাড়া।
- **Internal Schema:** Physical storage, record layout, file organization ও access path বর্ণনা।
- **Logical Data Independence:** Conceptual schema পরিবর্তনেও external view/program যতটা সম্ভব অপরিবর্তিত রাখা।
- **Physical Data Independence:** Internal storage/index পরিবর্তনেও conceptual/external schema ও program অপরিবর্তিত রাখা।
- **Centralized Database:** Data প্রধানত একটি site/system-এ managed।
- **Client-Server DB:** Client request পাঠায়, database server query/transaction process করে।
- **Data Abstraction:** Unnecessary lower-level detail লুকিয়ে relevant view প্রদান।
- **Database Catalog:** Schema-level description ও optimizer statistics রাখে।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Database Architecture এবং Data Independence

# Batch 18 — Question 801–850

## প্রশ্ন 801 | Topic: Database Management System > DB Architecture | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`External, conceptual ও internal level আলাদা করে data abstraction ও independence প্রদান।`

A) Three-schema Architecture
B) Database Catalog
C) Physical Data Independence
D) Logical Data Independence

**সঠিক উত্তর: A) Three-schema Architecture**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** External, conceptual ও internal level আলাদা করে data abstraction ও independence প্রদান।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Database Catalog` বলতে Schema-level description ও optimizer statistics রাখে। বোঝায়; প্রশ্নের বর্ণনা `Three-schema Architecture`-এর।
- **C option কেন ভুল:** `Physical Data Independence` বলতে Internal storage/index পরিবর্তনেও conceptual/external schema ও program অপরিবর্তিত রাখা। বোঝায়; প্রশ্নের বর্ণনা `Three-schema Architecture`-এর।
- **D option কেন ভুল:** `Logical Data Independence` বলতে Conceptual schema পরিবর্তনেও external view/program যতটা সম্ভব অপরিবর্তিত রাখা। বোঝায়; প্রশ্নের বর্ণনা `Three-schema Architecture`-এর।
- **Related Concept:** ANSI/SPARC model।
- **মনে রাখার টিপস:** Views, logical schema, storage।

---

## প্রশ্ন 802 | Topic: Database Management System > DB Architecture | Difficulty: Medium | Type: Theory

Q. `External Schema` সম্পর্কে কোন statement সঠিক?

A) Schema-level description ও optimizer statistics রাখে।
B) Unnecessary lower-level detail লুকিয়ে relevant view প্রদান।
C) নির্দিষ্ট user/application-এর view of database।
D) Physical storage, record layout, file organization ও access path বর্ণনা।

**সঠিক উত্তর: C) নির্দিষ্ট user/application-এর view of database।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** নির্দিষ্ট user/application-এর view of database।
- **A option কেন ভুল:** এই statementটি `Database Catalog` ধারণাকে বর্ণনা করে; `External Schema`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Data Abstraction` ধারণাকে বর্ণনা করে; `External Schema`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Internal Schema` ধারণাকে বর্ণনা করে; `External Schema`-কে নয়।
- **Related Concept:** একাধিক external view থাকতে পারে।
- **মনে রাখার টিপস:** User-specific view।

---

## প্রশ্ন 803 | Topic: Database Management System > DB Architecture | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `সম্পূর্ণ database-এর global logical structure, storage detail ছাড়া।`—এখানে কোন concept প্রযোজ্য?

A) Three-schema Architecture
B) Centralized Database
C) Client-Server DB
D) Conceptual Schema

**সঠিক উত্তর: D) Conceptual Schema**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** সম্পূর্ণ database-এর global logical structure, storage detail ছাড়া।
- **A option কেন ভুল:** `Three-schema Architecture` বলতে External, conceptual ও internal level আলাদা করে data abstraction ও independence প্রদান। বোঝায়; প্রশ্নের বর্ণনা `Conceptual Schema`-এর।
- **B option কেন ভুল:** `Centralized Database` বলতে Data প্রধানত একটি site/system-এ managed। বোঝায়; প্রশ্নের বর্ণনা `Conceptual Schema`-এর।
- **C option কেন ভুল:** `Client-Server DB` বলতে Client request পাঠায়, database server query/transaction process করে। বোঝায়; প্রশ্নের বর্ণনা `Conceptual Schema`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Entity, relation, constraint।
- **মনে রাখার টিপস:** Global logical design।

---

## প্রশ্ন 804 | Topic: Database Management System > DB Architecture | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Physical storage, record layout, file organization ও access path বর্ণনা।`

A) Physical Data Independence
B) External Schema
C) Database Catalog
D) Internal Schema

**সঠিক উত্তর: D) Internal Schema**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Physical storage, record layout, file organization ও access path বর্ণনা।
- **A option কেন ভুল:** `Physical Data Independence` বলতে Internal storage/index পরিবর্তনেও conceptual/external schema ও program অপরিবর্তিত রাখা। বোঝায়; প্রশ্নের বর্ণনা `Internal Schema`-এর।
- **B option কেন ভুল:** `External Schema` বলতে নির্দিষ্ট user/application-এর view of database। বোঝায়; প্রশ্নের বর্ণনা `Internal Schema`-এর।
- **C option কেন ভুল:** `Database Catalog` বলতে Schema-level description ও optimizer statistics রাখে। বোঝায়; প্রশ্নের বর্ণনা `Internal Schema`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Lowest abstraction level।
- **মনে রাখার টিপস:** How stored।

---

## প্রশ্ন 805 | Topic: Database Management System > DB Architecture | Difficulty: Hard | Type: Tracing

Q. Table-এ নতুন optional column যোগ হলেও পুরোনো user view একই থাকে। এটি কোন independence?

A) Physical
B) No independence
C) Logical
D) Transaction isolation

**সঠিক উত্তর: C) Logical**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Conceptual logical structure পরিবর্তনের পর external view বজায় রাখা logical data independence।

#### Step-by-step সমাধান

```text
Change level: conceptual schema
Unaffected level: external view/program
Type: logical data independence
```
- **A option কেন ভুল:** Storage file/index change সম্পর্কিত।
- **B option কেন ভুল:** View unchanged হওয়াই independence।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Concurrent execution property।
- **Related Concept:** External–conceptual mapping পরিবর্তন absorb করে।
- **মনে রাখার টিপস:** Logical schema change → logical independence।

---

## প্রশ্ন 806 | Topic: Database Management System > DB Architecture | Difficulty: Easy | Type: Tracing

Q. Heap file-এর বদলে B+ Tree index যোগ করা হলো, SQL table definition বদলাল না। কোন independence?

A) Physical
B) Logical
C) Referential
D) Semantic

**সঠিক উত্তর: A) Physical**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Internal access path বদলেছে, conceptual relation অপরিবর্তিত।

#### Step-by-step সমাধান

```text
Before: heap scan
After : B+ tree access path
Logical table unchanged
Result: physical data independence
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Conceptual schema change নয়।
- **C option কেন ভুল:** Foreign-key integrity।
- **D option কেন ভুল:** Standard data-independence category নয়।
- **Related Concept:** Index implementation detail।
- **মনে রাখার টিপস:** Storage change → physical independence।

---

## প্রশ্ন 807 | Topic: Database Management System > DB Architecture | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Data প্রধানত একটি site/system-এ managed।`

A) Database Catalog
B) Physical Data Independence
C) Client-Server DB
D) Centralized Database

**সঠিক উত্তর: D) Centralized Database**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Data প্রধানত একটি site/system-এ managed।
- **A option কেন ভুল:** `Database Catalog` বলতে Schema-level description ও optimizer statistics রাখে। বোঝায়; প্রশ্নের বর্ণনা `Centralized Database`-এর।
- **B option কেন ভুল:** `Physical Data Independence` বলতে Internal storage/index পরিবর্তনেও conceptual/external schema ও program অপরিবর্তিত রাখা। বোঝায়; প্রশ্নের বর্ণনা `Centralized Database`-এর।
- **C option কেন ভুল:** `Client-Server DB` বলতে Client request পাঠায়, database server query/transaction process করে। বোঝায়; প্রশ্নের বর্ণনা `Centralized Database`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Administration সহজ, single-site risk।
- **মনে রাখার টিপস:** One main location।

---

## প্রশ্ন 808 | Topic: Database Management System > DB Architecture | Difficulty: Medium | Type: Theory

Q. `Client-Server DB` সম্পর্কে কোন statement সঠিক?

A) Client request পাঠায়, database server query/transaction process করে।
B) Internal storage/index পরিবর্তনেও conceptual/external schema ও program অপরিবর্তিত রাখা।
C) সম্পূর্ণ database-এর global logical structure, storage detail ছাড়া।
D) নির্দিষ্ট user/application-এর view of database।

**সঠিক উত্তর: A) Client request পাঠায়, database server query/transaction process করে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Client request পাঠায়, database server query/transaction process করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Physical Data Independence` ধারণাকে বর্ণনা করে; `Client-Server DB`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Conceptual Schema` ধারণাকে বর্ণনা করে; `Client-Server DB`-কে নয়।
- **D option কেন ভুল:** এই statementটি `External Schema` ধারণাকে বর্ণনা করে; `Client-Server DB`-কে নয়।
- **Related Concept:** Two-tier/three-tier architecture।
- **মনে রাখার টিপস:** DB service over network।

---

## প্রশ্ন 809 | Topic: Database Management System > DB Architecture | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Unnecessary lower-level detail লুকিয়ে relevant view প্রদান।`—এখানে কোন concept প্রযোজ্য?

A) Logical Data Independence
B) Conceptual Schema
C) Data Abstraction
D) Centralized Database

**সঠিক উত্তর: C) Data Abstraction**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Unnecessary lower-level detail লুকিয়ে relevant view প্রদান।
- **A option কেন ভুল:** `Logical Data Independence` বলতে Conceptual schema পরিবর্তনেও external view/program যতটা সম্ভব অপরিবর্তিত রাখা। বোঝায়; প্রশ্নের বর্ণনা `Data Abstraction`-এর।
- **B option কেন ভুল:** `Conceptual Schema` বলতে সম্পূর্ণ database-এর global logical structure, storage detail ছাড়া। বোঝায়; প্রশ্নের বর্ণনা `Data Abstraction`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Centralized Database` বলতে Data প্রধানত একটি site/system-এ managed। বোঝায়; প্রশ্নের বর্ণনা `Data Abstraction`-এর।
- **Related Concept:** Physical, logical, view levels।
- **মনে রাখার টিপস:** Hide lower details।

---

## প্রশ্ন 810 | Topic: Database Management System > DB Architecture | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Schema-level description ও optimizer statistics রাখে।`

A) Database Catalog
B) Conceptual Schema
C) Physical Data Independence
D) Data Abstraction

**সঠিক উত্তর: A) Database Catalog**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Schema-level description ও optimizer statistics রাখে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Conceptual Schema` বলতে সম্পূর্ণ database-এর global logical structure, storage detail ছাড়া। বোঝায়; প্রশ্নের বর্ণনা `Database Catalog`-এর।
- **C option কেন ভুল:** `Physical Data Independence` বলতে Internal storage/index পরিবর্তনেও conceptual/external schema ও program অপরিবর্তিত রাখা। বোঝায়; প্রশ্নের বর্ণনা `Database Catalog`-এর।
- **D option কেন ভুল:** `Data Abstraction` বলতে Unnecessary lower-level detail লুকিয়ে relevant view প্রদান। বোঝায়; প্রশ্নের বর্ণনা `Database Catalog`-এর।
- **Related Concept:** Metadata repository।
- **মনে রাখার টিপস:** System metadata store।

---


# Chapter Theory 71: Entity–Relationship Modeling

## বিস্তারিত Theory Note

ER modeling requirement থেকে conceptual structure তৈরি করে। Entity identity, attribute ও relationship constraint স্পষ্ট না হলে relational mapping-এ anomaly তৈরি হতে পারে।

Weak entity owner ছাড়া identify/exist করতে পারে না। Cardinality maximum relationship count এবং participation minimum requirement প্রকাশ করে।

## মূল ধারণার মানচিত্র

- **Entity:** স্বতন্ত্রভাবে শনাক্তযোগ্য real-world object বা concept।
- **Entity Set:** একই type-এর entity collection।
- **Attribute:** Entity বা relationship-এর property।
- **Key Attribute:** Entity set-এর প্রতিটি entity uniquely identify করে।
- **Relationship:** দুই বা ততোধিক entity type-এর association।
- **Cardinality Ratio:** Relationship-এ 1:1, 1:N, M:N participation limit।
- **Participation Constraint:** Entity set-এর সব entity relationship-এ অংশ নেয় কি না; total বা partial।
- **Weak Entity:** নিজস্ব পূর্ণ key নেই; owner entity key ও partial key দিয়ে শনাক্ত।
- **Composite Attribute:** একাধিক component-এ ভাগ করা যায়, যেমন Address।
- **Derived Attribute:** অন্য stored data থেকে হিসাব করা যায়, যেমন DateOfBirth থেকে Age।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Entity–Relationship Modeling

## প্রশ্ন 811 | Topic: Database Management System > ER Model | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`স্বতন্ত্রভাবে শনাক্তযোগ্য real-world object বা concept।`

A) Entity
B) Entity Set
C) Key Attribute
D) Derived Attribute

**সঠিক উত্তর: A) Entity**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** স্বতন্ত্রভাবে শনাক্তযোগ্য real-world object বা concept।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Entity Set` বলতে একই type-এর entity collection। বোঝায়; প্রশ্নের বর্ণনা `Entity`-এর।
- **C option কেন ভুল:** `Key Attribute` বলতে Entity set-এর প্রতিটি entity uniquely identify করে। বোঝায়; প্রশ্নের বর্ণনা `Entity`-এর।
- **D option কেন ভুল:** `Derived Attribute` বলতে অন্য stored data থেকে হিসাব করা যায়, যেমন DateOfBirth থেকে Age। বোঝায়; প্রশ্নের বর্ণনা `Entity`-এর।
- **Related Concept:** Student, Course, Account উদাহরণ।
- **মনে রাখার টিপস:** Thing with identity।

---

## প্রশ্ন 812 | Topic: Database Management System > ER Model | Difficulty: Easy | Type: Theory

Q. `Entity Set` সম্পর্কে কোন statement সঠিক?

A) একাধিক component-এ ভাগ করা যায়, যেমন Address।
B) Entity বা relationship-এর property।
C) দুই বা ততোধিক entity type-এর association।
D) একই type-এর entity collection।

**সঠিক উত্তর: D) একই type-এর entity collection।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একই type-এর entity collection।
- **A option কেন ভুল:** এই statementটি `Composite Attribute` ধারণাকে বর্ণনা করে; `Entity Set`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Attribute` ধারণাকে বর্ণনা করে; `Entity Set`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Relationship` ধারণাকে বর্ণনা করে; `Entity Set`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** সব Student entity।
- **মনে রাখার টিপস:** Collection of entities।

---

## প্রশ্ন 813 | Topic: Database Management System > ER Model | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Entity বা relationship-এর property।`—এখানে কোন concept প্রযোজ্য?

A) Entity Set
B) Attribute
C) Entity
D) Relationship

**সঠিক উত্তর: B) Attribute**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Entity বা relationship-এর property।
- **A option কেন ভুল:** `Entity Set` বলতে একই type-এর entity collection। বোঝায়; প্রশ্নের বর্ণনা `Attribute`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Entity` বলতে স্বতন্ত্রভাবে শনাক্তযোগ্য real-world object বা concept। বোঝায়; প্রশ্নের বর্ণনা `Attribute`-এর।
- **D option কেন ভুল:** `Relationship` বলতে দুই বা ততোধিক entity type-এর association। বোঝায়; প্রশ্নের বর্ণনা `Attribute`-এর।
- **Related Concept:** Simple, composite, multivalued, derived হতে পারে।
- **মনে রাখার টিপস:** Descriptive property।

---

## প্রশ্ন 814 | Topic: Database Management System > ER Model | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Entity set-এর প্রতিটি entity uniquely identify করে।`

A) Participation Constraint
B) Entity Set
C) Key Attribute
D) Relationship

**সঠিক উত্তর: C) Key Attribute**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Entity set-এর প্রতিটি entity uniquely identify করে।
- **A option কেন ভুল:** `Participation Constraint` বলতে Entity set-এর সব entity relationship-এ অংশ নেয় কি না; total বা partial। বোঝায়; প্রশ্নের বর্ণনা `Key Attribute`-এর।
- **B option কেন ভুল:** `Entity Set` বলতে একই type-এর entity collection। বোঝায়; প্রশ্নের বর্ণনা `Key Attribute`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Relationship` বলতে দুই বা ততোধিক entity type-এর association। বোঝায়; প্রশ্নের বর্ণনা `Key Attribute`-এর।
- **Related Concept:** ER diagram-এ underline convention।
- **মনে রাখার টিপস:** Unique identifier।

---

## প্রশ্ন 815 | Topic: Database Management System > ER Model | Difficulty: Medium | Type: Theory

Q. `Relationship` সম্পর্কে কোন statement সঠিক?

A) দুই বা ততোধিক entity type-এর association।
B) নিজস্ব পূর্ণ key নেই; owner entity key ও partial key দিয়ে শনাক্ত।
C) একাধিক component-এ ভাগ করা যায়, যেমন Address।
D) Entity বা relationship-এর property।

**সঠিক উত্তর: A) দুই বা ততোধিক entity type-এর association।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** দুই বা ততোধিক entity type-এর association।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Weak Entity` ধারণাকে বর্ণনা করে; `Relationship`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Composite Attribute` ধারণাকে বর্ণনা করে; `Relationship`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Attribute` ধারণাকে বর্ণনা করে; `Relationship`-কে নয়।
- **Related Concept:** WorksFor, Enrolls।
- **মনে রাখার টিপস:** Association among entities।

---

## প্রশ্ন 816 | Topic: Database Management System > ER Model | Difficulty: Easy | Type: Tracing

Q. এক Department-এ বহু Employee, কিন্তু প্রতিটি Employee এক Department-এ। Cardinality কী?

A) 1:1
B) M:N
C) N:1 Department→Employee
D) 1:N Department→Employee

**সঠিক উত্তর: D) 1:N Department→Employee**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** এক Department বহু Employee-এর সঙ্গে related; employee side থেকে এক department।

#### Step-by-step সমাধান

```text
Department count per employee=1
Employee count per department=many
Department -> Employee = 1:N
```
- **A option কেন ভুল:** বহু employee অনুমোদন করে না।
- **B option কেন ভুল:** Employee একাধিক department নয়।
- **C option কেন ভুল:** Direction উল্টো।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Direction উল্লেখ করে cardinality পড়ুন।
- **মনে রাখার টিপস:** One department, many employees।

---

## প্রশ্ন 817 | Topic: Database Management System > ER Model | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Entity set-এর সব entity relationship-এ অংশ নেয় কি না; total বা partial।`

A) Entity Set
B) Participation Constraint
C) Relationship
D) Attribute

**সঠিক উত্তর: B) Participation Constraint**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Entity set-এর সব entity relationship-এ অংশ নেয় কি না; total বা partial।
- **A option কেন ভুল:** `Entity Set` বলতে একই type-এর entity collection। বোঝায়; প্রশ্নের বর্ণনা `Participation Constraint`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Relationship` বলতে দুই বা ততোধিক entity type-এর association। বোঝায়; প্রশ্নের বর্ণনা `Participation Constraint`-এর।
- **D option কেন ভুল:** `Attribute` বলতে Entity বা relationship-এর property। বোঝায়; প্রশ্নের বর্ণনা `Participation Constraint`-এর।
- **Related Concept:** Existence dependency প্রকাশ।
- **মনে রাখার টিপস:** Must participate?

---

## প্রশ্ন 818 | Topic: Database Management System > ER Model | Difficulty: Hard | Type: Tracing

Q. Weak entity Dependent-এর partial key `name`, owner Employee key `emp_id`। Dependent-এর relational primary key কী হতে পারে?

A) name only
B) emp_id only
C) কোনো key নয়
D) (emp_id,name)

**সঠিক উত্তর: D) (emp_id,name)**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Owner key ও partial key combine করে unique identity।

#### Step-by-step সমাধান

```text
Owner identifier=emp_id
Partial key=name
Full identifier=(emp_id,name)
```
- **A option কেন ভুল:** ভিন্ন employee-এর dependent একই name হতে পারে।
- **B option কেন ভুল:** এক employee-এর বহু dependent।
- **C option কেন ভুল:** Composite key তৈরি করা যায়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Weak entity table-এ owner key foreign keyও।
- **মনে রাখার টিপস:** Owner key + partial key।

---

## প্রশ্ন 819 | Topic: Database Management System > ER Model | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `একাধিক component-এ ভাগ করা যায়, যেমন Address।`—এখানে কোন concept প্রযোজ্য?

A) Cardinality Ratio
B) Composite Attribute
C) Attribute
D) Entity

**সঠিক উত্তর: B) Composite Attribute**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একাধিক component-এ ভাগ করা যায়, যেমন Address।
- **A option কেন ভুল:** `Cardinality Ratio` বলতে Relationship-এ 1:1, 1:N, M:N participation limit। বোঝায়; প্রশ্নের বর্ণনা `Composite Attribute`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Attribute` বলতে Entity বা relationship-এর property। বোঝায়; প্রশ্নের বর্ণনা `Composite Attribute`-এর।
- **D option কেন ভুল:** `Entity` বলতে স্বতন্ত্রভাবে শনাক্তযোগ্য real-world object বা concept। বোঝায়; প্রশ্নের বর্ণনা `Composite Attribute`-এর।
- **Related Concept:** Street,City,Zip।
- **মনে রাখার টিপস:** Attribute with parts।

---

## প্রশ্ন 820 | Topic: Database Management System > ER Model | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`অন্য stored data থেকে হিসাব করা যায়, যেমন DateOfBirth থেকে Age।`

A) Key Attribute
B) Relationship
C) Composite Attribute
D) Derived Attribute

**সঠিক উত্তর: D) Derived Attribute**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** অন্য stored data থেকে হিসাব করা যায়, যেমন DateOfBirth থেকে Age।
- **A option কেন ভুল:** `Key Attribute` বলতে Entity set-এর প্রতিটি entity uniquely identify করে। বোঝায়; প্রশ্নের বর্ণনা `Derived Attribute`-এর।
- **B option কেন ভুল:** `Relationship` বলতে দুই বা ততোধিক entity type-এর association। বোঝায়; প্রশ্নের বর্ণনা `Derived Attribute`-এর।
- **C option কেন ভুল:** `Composite Attribute` বলতে একাধিক component-এ ভাগ করা যায়, যেমন Address। বোঝায়; প্রশ্নের বর্ণনা `Derived Attribute`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** সবসময় store করা দরকার নেই।
- **মনে রাখার টিপস:** Computed property।

---


# Chapter Theory 72: Relational Model এবং Keys

## বিস্তারিত Theory Note

Relational model relation, tuple, attribute ও domain-এর ওপর ভিত্তি করে। Mathematical set semantics duplicate tuple ও orderকে essential মনে করে না; SQL বাস্তবে bag semantics ব্যবহার করতে পারে।

Key reasoning-এ uniqueness-এর সঙ্গে minimality আলাদা পরীক্ষা করুন। Foreign key null হতে পারে policy অনুযায়ী, তবে non-null হলে referenced row থাকা দরকার।

## মূল ধারণার মানচিত্র

- **Relation:** Named table-like set of tuples over defined attributes; mathematical relation-এ duplicate tuple নেই।
- **Tuple:** Relation-এর একটি row বা record instance।
- **Domain:** এক attribute-এর অনুমোদিত atomic value set।
- **Superkey:** Relation-এর tuple uniquely identify করতে সক্ষম attribute set, অতিরিক্ত attribute থাকতে পারে।
- **Candidate Key:** Minimal superkey; কোনো proper subset unique নয়।
- **Primary Key:** Selected candidate key যা main tuple identifier হিসেবে ব্যবহৃত।
- **Alternate Key:** Primary হিসেবে নির্বাচিত হয়নি এমন candidate key।
- **Foreign Key:** এক relation-এর attribute set অন্য/একই relation-এর candidate/primary key reference করে।
- **Composite Key:** একাধিক attribute নিয়ে গঠিত key।
- **Entity Integrity:** Primary key component null হতে পারে না।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Relational Model এবং Keys

## প্রশ্ন 821 | Topic: Database Management System > Relational Model | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Named table-like set of tuples over defined attributes; mathematical relation-এ duplicate tuple নেই।`

A) Relation
B) Superkey
C) Entity Integrity
D) Domain

**সঠিক উত্তর: A) Relation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Named table-like set of tuples over defined attributes; mathematical relation-এ duplicate tuple নেই।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Superkey` বলতে Relation-এর tuple uniquely identify করতে সক্ষম attribute set, অতিরিক্ত attribute থাকতে পারে। বোঝায়; প্রশ্নের বর্ণনা `Relation`-এর।
- **C option কেন ভুল:** `Entity Integrity` বলতে Primary key component null হতে পারে না। বোঝায়; প্রশ্নের বর্ণনা `Relation`-এর।
- **D option কেন ভুল:** `Domain` বলতে এক attribute-এর অনুমোদিত atomic value set। বোঝায়; প্রশ্নের বর্ণনা `Relation`-এর।
- **Related Concept:** Order conceptually গুরুত্বপূর্ণ নয়।
- **মনে রাখার টিপস:** Set of tuples।

---

## প্রশ্ন 822 | Topic: Database Management System > Relational Model | Difficulty: Medium | Type: Theory

Q. `Tuple` সম্পর্কে কোন statement সঠিক?

A) Primary হিসেবে নির্বাচিত হয়নি এমন candidate key।
B) Relation-এর tuple uniquely identify করতে সক্ষম attribute set, অতিরিক্ত attribute থাকতে পারে।
C) Relation-এর একটি row বা record instance।
D) এক relation-এর attribute set অন্য/একই relation-এর candidate/primary key reference করে।

**সঠিক উত্তর: C) Relation-এর একটি row বা record instance।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Relation-এর একটি row বা record instance।
- **A option কেন ভুল:** এই statementটি `Alternate Key` ধারণাকে বর্ণনা করে; `Tuple`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Superkey` ধারণাকে বর্ণনা করে; `Tuple`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Foreign Key` ধারণাকে বর্ণনা করে; `Tuple`-কে নয়।
- **Related Concept:** Attribute values-এর ordered association।
- **মনে রাখার টিপস:** One row।

---

## প্রশ্ন 823 | Topic: Database Management System > Relational Model | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `এক attribute-এর অনুমোদিত atomic value set।`—এখানে কোন concept প্রযোজ্য?

A) Domain
B) Alternate Key
C) Tuple
D) Candidate Key

**সঠিক উত্তর: A) Domain**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** এক attribute-এর অনুমোদিত atomic value set।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Alternate Key` বলতে Primary হিসেবে নির্বাচিত হয়নি এমন candidate key। বোঝায়; প্রশ্নের বর্ণনা `Domain`-এর।
- **C option কেন ভুল:** `Tuple` বলতে Relation-এর একটি row বা record instance। বোঝায়; প্রশ্নের বর্ণনা `Domain`-এর।
- **D option কেন ভুল:** `Candidate Key` বলতে Minimal superkey; কোনো proper subset unique নয়। বোঝায়; প্রশ্নের বর্ণনা `Domain`-এর।
- **Related Concept:** Type ও semantic constraint।
- **মনে রাখার টিপস:** Allowed values।

---

## প্রশ্ন 824 | Topic: Database Management System > Relational Model | Difficulty: Hard | Type: Tracing

Q. Attribute set `{A,B}` unique, কিন্তু `{A}` একাই unique। `{A,B}` কী?

A) Candidate key only
B) Superkey কিন্তু minimal নয়
C) Foreign key
D) Non-key

**সঠিক উত্তর: B) Superkey কিন্তু minimal নয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** AB unique, তাই superkey; A proper subset unique, তাই minimal candidate নয়।

#### Step-by-step সমাধান

```text
AB uniquely identifies tuples -> superkey
A alone unique -> AB has redundant B
Therefore AB is not minimal
```
- **A option কেন ভুল:** Minimality ভাঙে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Reference information নেই।
- **D option কেন ভুল:** Uniqueness আছে।
- **Related Concept:** Candidate key=minimal superkey।
- **মনে রাখার টিপস:** Extra attribute থাকলে superkey only।

---

## প্রশ্ন 825 | Topic: Database Management System > Relational Model | Difficulty: Easy | Type: Theory

Q. `Candidate Key` সম্পর্কে কোন statement সঠিক?

A) Minimal superkey; কোনো proper subset unique নয়।
B) এক attribute-এর অনুমোদিত atomic value set।
C) Relation-এর একটি row বা record instance।
D) Primary হিসেবে নির্বাচিত হয়নি এমন candidate key।

**সঠিক উত্তর: A) Minimal superkey; কোনো proper subset unique নয়।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Minimal superkey; কোনো proper subset unique নয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Domain` ধারণাকে বর্ণনা করে; `Candidate Key`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Tuple` ধারণাকে বর্ণনা করে; `Candidate Key`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Alternate Key` ধারণাকে বর্ণনা করে; `Candidate Key`-কে নয়।
- **Related Concept:** একাধিক candidate থাকতে পারে।
- **মনে রাখার টিপস:** Minimal unique identifier।

---

## প্রশ্ন 826 | Topic: Database Management System > Relational Model | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `Selected candidate key যা main tuple identifier হিসেবে ব্যবহৃত।`—এখানে কোন concept প্রযোজ্য?

A) Tuple
B) Primary Key
C) Foreign Key
D) Domain

**সঠিক উত্তর: B) Primary Key**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Selected candidate key যা main tuple identifier হিসেবে ব্যবহৃত।
- **A option কেন ভুল:** `Tuple` বলতে Relation-এর একটি row বা record instance। বোঝায়; প্রশ্নের বর্ণনা `Primary Key`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Foreign Key` বলতে এক relation-এর attribute set অন্য/একই relation-এর candidate/primary key reference করে। বোঝায়; প্রশ্নের বর্ণনা `Primary Key`-এর।
- **D option কেন ভুল:** `Domain` বলতে এক attribute-এর অনুমোদিত atomic value set। বোঝায়; প্রশ্নের বর্ণনা `Primary Key`-এর।
- **Related Concept:** Unique এবং non-null policy।
- **মনে রাখার টিপস:** Chosen candidate।

---

## প্রশ্ন 827 | Topic: Database Management System > Relational Model | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Primary হিসেবে নির্বাচিত হয়নি এমন candidate key।`

A) Relation
B) Alternate Key
C) Composite Key
D) Domain

**সঠিক উত্তর: B) Alternate Key**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Primary হিসেবে নির্বাচিত হয়নি এমন candidate key।
- **A option কেন ভুল:** `Relation` বলতে Named table-like set of tuples over defined attributes; mathematical relation-এ duplicate tuple নেই। বোঝায়; প্রশ্নের বর্ণনা `Alternate Key`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Composite Key` বলতে একাধিক attribute নিয়ে গঠিত key। বোঝায়; প্রশ্নের বর্ণনা `Alternate Key`-এর।
- **D option কেন ভুল:** `Domain` বলতে এক attribute-এর অনুমোদিত atomic value set। বোঝায়; প্রশ্নের বর্ণনা `Alternate Key`-এর।
- **Related Concept:** তবুও unique।
- **মনে রাখার টিপস:** Other candidate।

---

## প্রশ্ন 828 | Topic: Database Management System > Relational Model | Difficulty: Medium | Type: Theory

Q. `Foreign Key` সম্পর্কে কোন statement সঠিক?

A) Selected candidate key যা main tuple identifier হিসেবে ব্যবহৃত।
B) Primary হিসেবে নির্বাচিত হয়নি এমন candidate key।
C) এক relation-এর attribute set অন্য/একই relation-এর candidate/primary key reference করে।
D) Relation-এর tuple uniquely identify করতে সক্ষম attribute set, অতিরিক্ত attribute থাকতে পারে।

**সঠিক উত্তর: C) এক relation-এর attribute set অন্য/একই relation-এর candidate/primary key reference করে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** এক relation-এর attribute set অন্য/একই relation-এর candidate/primary key reference করে।
- **A option কেন ভুল:** এই statementটি `Primary Key` ধারণাকে বর্ণনা করে; `Foreign Key`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Alternate Key` ধারণাকে বর্ণনা করে; `Foreign Key`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Superkey` ধারণাকে বর্ণনা করে; `Foreign Key`-কে নয়।
- **Related Concept:** Referential integrity।
- **মনে রাখার টিপস:** Reference another row।

---

## প্রশ্ন 829 | Topic: Database Management System > Relational Model | Difficulty: Hard | Type: Tracing

Q. Enrollment(student_id, course_id) pair unique; student একাধিক course ও course-এ বহু student। Suitable primary key কী?

A) student_id
B) (student_id,course_id)
C) course_id
D) কোনোটিই নয়

**সঠিক উত্তর: B) (student_id,course_id)**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Many-to-many junction-এ pair enrollment uniquely identify করে।

#### Step-by-step সমাধান

```text
student_id repeats across courses
course_id repeats across students
Pair is unique
```
- **A option কেন ভুল:** এক student-এর বহু enrollment।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এক course-এর বহু enrollment।
- **D option কেন ভুল:** Composite key valid।
- **Related Concept:** Junction relation often composite key।
- **মনে রাখার টিপস:** Both foreign keys together।

---

## প্রশ্ন 830 | Topic: Database Management System > Relational Model | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Primary key component null হতে পারে না।`

A) Entity Integrity
B) Primary Key
C) Domain
D) Candidate Key

**সঠিক উত্তর: A) Entity Integrity**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Primary key component null হতে পারে না।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Primary Key` বলতে Selected candidate key যা main tuple identifier হিসেবে ব্যবহৃত। বোঝায়; প্রশ্নের বর্ণনা `Entity Integrity`-এর।
- **C option কেন ভুল:** `Domain` বলতে এক attribute-এর অনুমোদিত atomic value set। বোঝায়; প্রশ্নের বর্ণনা `Entity Integrity`-এর।
- **D option কেন ভুল:** `Candidate Key` বলতে Minimal superkey; কোনো proper subset unique নয়। বোঝায়; প্রশ্নের বর্ণনা `Entity Integrity`-এর।
- **Related Concept:** Tuple identity নিশ্চিত।
- **মনে রাখার টিপস:** Primary key not null।

---


# Chapter Theory 73: Relational Algebra

## বিস্তারিত Theory Note

Relational Algebra procedural query foundation। Selection row কমায়, projection column কমায়, join related table combine করে। Operation composition optimizer rewrite-এর ভিত্তি।

Cardinality estimation-এ key/foreign-key constraint গুরুত্বপূর্ণ। Cartesian product upper bound হলেও predicate join result অনেক ছোট।

## মূল ধারণার মানচিত্র

- **Selection:** Predicate অনুযায়ী relation-এর row filter করা unary relational algebra operation।
- **Projection:** নির্দিষ্ট attribute column নির্বাচন; pure relational algebra duplicate remove করে।
- **Union:** Union-compatible relation-এর tuple একত্র করে।
- **Set Difference:** প্রথম relation-এ আছে কিন্তু দ্বিতীয়তে নেই এমন tuple।
- **Cartesian Product:** দুই relation-এর প্রতিটি tuple pair combine করে।
- **Join:** Related attribute/predicate অনুযায়ী দুই relation-এর matching tuple combine।
- **Natural Join:** একই নামের common attribute equality দিয়ে join এবং duplicate common column remove।
- **Rename:** Relation বা attribute-এর নাম পরিবর্তন করে expression disambiguate।
- **Division:** যেসব entity দ্বিতীয় relation-এর সব value-এর সঙ্গে related, এমন query প্রকাশ।
- **Closure Property:** Relational algebra operation-এর result আবার relation।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Relational Algebra

## প্রশ্ন 831 | Topic: Database Management System > Relational Algebra | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Predicate অনুযায়ী relation-এর row filter করা unary relational algebra operation।`

A) Union
B) Projection
C) Selection
D) Join

**সঠিক উত্তর: C) Selection**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Predicate অনুযায়ী relation-এর row filter করা unary relational algebra operation।
- **A option কেন ভুল:** `Union` বলতে Union-compatible relation-এর tuple একত্র করে। বোঝায়; প্রশ্নের বর্ণনা `Selection`-এর।
- **B option কেন ভুল:** `Projection` বলতে নির্দিষ্ট attribute column নির্বাচন; pure relational algebra duplicate remove করে। বোঝায়; প্রশ্নের বর্ণনা `Selection`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Join` বলতে Related attribute/predicate অনুযায়ী দুই relation-এর matching tuple combine। বোঝায়; প্রশ্নের বর্ণনা `Selection`-এর।
- **Related Concept:** Sigma notation।
- **মনে রাখার টিপস:** Choose rows।

---

## প্রশ্ন 832 | Topic: Database Management System > Relational Algebra | Difficulty: Medium | Type: Calculation

Q. Relation R(A,B,C)-তে projection π_A,B(R) করলে output attribute count কত?

A) 1
B) 3
C) 2
D) R row count

**সঠিক উত্তর: C) 2**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Projection list A ও B—দুই attribute।

#### Step-by-step সমাধান

```text
Projection attributes={A,B}
Count=2
```
- **A option কেন ভুল:** এক column বাদ।
- **B option কেন ভুল:** C-ও ধরে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Attribute count row count নয়।
- **Related Concept:** Projection duplicate tuple eliminate করতে পারে।
- **মনে রাখার টিপস:** Listed columns count।

---

## প্রশ্ন 833 | Topic: Database Management System > Relational Algebra | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Union-compatible relation-এর tuple একত্র করে।`—এখানে কোন concept প্রযোজ্য?

A) Selection
B) Union
C) Join
D) Division

**সঠিক উত্তর: B) Union**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Union-compatible relation-এর tuple একত্র করে।
- **A option কেন ভুল:** `Selection` বলতে Predicate অনুযায়ী relation-এর row filter করা unary relational algebra operation। বোঝায়; প্রশ্নের বর্ণনা `Union`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Join` বলতে Related attribute/predicate অনুযায়ী দুই relation-এর matching tuple combine। বোঝায়; প্রশ্নের বর্ণনা `Union`-এর।
- **D option কেন ভুল:** `Division` বলতে যেসব entity দ্বিতীয় relation-এর সব value-এর সঙ্গে related, এমন query প্রকাশ। বোঝায়; প্রশ্নের বর্ণনা `Union`-এর।
- **Related Concept:** Same arity ও compatible domain।
- **মনে রাখার টিপস:** Rows from either।

---

## প্রশ্ন 834 | Topic: Database Management System > Relational Algebra | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`প্রথম relation-এ আছে কিন্তু দ্বিতীয়তে নেই এমন tuple।`

A) Projection
B) Set Difference
C) Cartesian Product
D) Natural Join

**সঠিক উত্তর: B) Set Difference**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রথম relation-এ আছে কিন্তু দ্বিতীয়তে নেই এমন tuple।
- **A option কেন ভুল:** `Projection` বলতে নির্দিষ্ট attribute column নির্বাচন; pure relational algebra duplicate remove করে। বোঝায়; প্রশ্নের বর্ণনা `Set Difference`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Cartesian Product` বলতে দুই relation-এর প্রতিটি tuple pair combine করে। বোঝায়; প্রশ্নের বর্ণনা `Set Difference`-এর।
- **D option কেন ভুল:** `Natural Join` বলতে একই নামের common attribute equality দিয়ে join এবং duplicate common column remove। বোঝায়; প্রশ্নের বর্ণনা `Set Difference`-এর।
- **Related Concept:** Union compatibility প্রয়োজন।
- **মনে রাখার টিপস:** Rows only in first।

---

## প্রশ্ন 835 | Topic: Database Management System > Relational Algebra | Difficulty: Easy | Type: Calculation

Q. R-এ 4 tuple এবং S-এ 3 tuple। Cartesian product R×S-এ tuple কত?

A) 7
B) 4
C) 12
D) 3

**সঠিক উত্তর: C) 12**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি R tuple প্রতিটি S tuple-এর সঙ্গে pair:4×3=12।

#### Step-by-step সমাধান

```text
|R x S|=|R|x|S|=4x3=12
```
- **A option কেন ভুল:** যোগ।
- **B option কেন ভুল:** শুধু R count।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** শুধু S count।
- **Related Concept:** Product cardinality multiplication।
- **মনে রাখার টিপস:** m×n।

---

## প্রশ্ন 836 | Topic: Database Management System > Relational Algebra | Difficulty: Hard | Type: Calculation

Q. Employee relation 10 row, Department 3 row। Equi-join-এ প্রত্যেক employee ঠিক এক department match করলে result row কত?

A) 3
B) 13
C) 30
D) 10

**সঠিক উত্তর: D) 10**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতি employee এক match, তাই দশ joined tuple।

#### Step-by-step সমাধান

```text
Employees=10
Matches per employee=1
Joined rows=10x1=10
```
- **A option কেন ভুল:** Department count।
- **B option কেন ভুল:** যোগ।
- **C option কেন ভুল:** Cartesian product, join predicate উপেক্ষা।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Join cardinality relationship constraint নির্ভর।
- **মনে রাখার টিপস:** One match per employee।

---

## প্রশ্ন 837 | Topic: Database Management System > Relational Algebra | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`একই নামের common attribute equality দিয়ে join এবং duplicate common column remove।`

A) Set Difference
B) Division
C) Natural Join
D) Join

**সঠিক উত্তর: C) Natural Join**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একই নামের common attribute equality দিয়ে join এবং duplicate common column remove।
- **A option কেন ভুল:** `Set Difference` বলতে প্রথম relation-এ আছে কিন্তু দ্বিতীয়তে নেই এমন tuple। বোঝায়; প্রশ্নের বর্ণনা `Natural Join`-এর।
- **B option কেন ভুল:** `Division` বলতে যেসব entity দ্বিতীয় relation-এর সব value-এর সঙ্গে related, এমন query প্রকাশ। বোঝায়; প্রশ্নের বর্ণনা `Natural Join`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Join` বলতে Related attribute/predicate অনুযায়ী দুই relation-এর matching tuple combine। বোঝায়; প্রশ্নের বর্ণনা `Natural Join`-এর।
- **Related Concept:** Accidental same-name risk।
- **মনে রাখার টিপস:** Automatic common-column join।

---

## প্রশ্ন 838 | Topic: Database Management System > Relational Algebra | Difficulty: Medium | Type: Theory

Q. `Rename` সম্পর্কে কোন statement সঠিক?

A) দুই relation-এর প্রতিটি tuple pair combine করে।
B) Union-compatible relation-এর tuple একত্র করে।
C) প্রথম relation-এ আছে কিন্তু দ্বিতীয়তে নেই এমন tuple।
D) Relation বা attribute-এর নাম পরিবর্তন করে expression disambiguate।

**সঠিক উত্তর: D) Relation বা attribute-এর নাম পরিবর্তন করে expression disambiguate।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Relation বা attribute-এর নাম পরিবর্তন করে expression disambiguate।
- **A option কেন ভুল:** এই statementটি `Cartesian Product` ধারণাকে বর্ণনা করে; `Rename`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Union` ধারণাকে বর্ণনা করে; `Rename`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Set Difference` ধারণাকে বর্ণনা করে; `Rename`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Self-join-এ গুরুত্বপূর্ণ।
- **মনে রাখার টিপস:** Alias in algebra।

---

## প্রশ্ন 839 | Topic: Database Management System > Relational Algebra | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `যেসব entity দ্বিতীয় relation-এর সব value-এর সঙ্গে related, এমন query প্রকাশ।`—এখানে কোন concept প্রযোজ্য?

A) Union
B) Join
C) Projection
D) Division

**সঠিক উত্তর: D) Division**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** যেসব entity দ্বিতীয় relation-এর সব value-এর সঙ্গে related, এমন query প্রকাশ।
- **A option কেন ভুল:** `Union` বলতে Union-compatible relation-এর tuple একত্র করে। বোঝায়; প্রশ্নের বর্ণনা `Division`-এর।
- **B option কেন ভুল:** `Join` বলতে Related attribute/predicate অনুযায়ী দুই relation-এর matching tuple combine। বোঝায়; প্রশ্নের বর্ণনা `Division`-এর।
- **C option কেন ভুল:** `Projection` বলতে নির্দিষ্ট attribute column নির্বাচন; pure relational algebra duplicate remove করে। বোঝায়; প্রশ্নের বর্ণনা `Division`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** “All” query।
- **মনে রাখার টিপস:** For all relation।

---

## প্রশ্ন 840 | Topic: Database Management System > Relational Algebra | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Relational algebra operation-এর result আবার relation।`

A) Closure Property
B) Join
C) Set Difference
D) Natural Join

**সঠিক উত্তর: A) Closure Property**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Relational algebra operation-এর result আবার relation।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Join` বলতে Related attribute/predicate অনুযায়ী দুই relation-এর matching tuple combine। বোঝায়; প্রশ্নের বর্ণনা `Closure Property`-এর।
- **C option কেন ভুল:** `Set Difference` বলতে প্রথম relation-এ আছে কিন্তু দ্বিতীয়তে নেই এমন tuple। বোঝায়; প্রশ্নের বর্ণনা `Closure Property`-এর।
- **D option কেন ভুল:** `Natural Join` বলতে একই নামের common attribute equality দিয়ে join এবং duplicate common column remove। বোঝায়; প্রশ্নের বর্ণনা `Closure Property`-এর।
- **Related Concept:** Operation compose করা যায়।
- **মনে রাখার টিপস:** Relation in, relation out।

---


# Chapter Theory 74: SQL DDL, DML এবং NULL

## বিস্তারিত Theory Note

DDL schema, DML data নিয়ে কাজ করে। Production SQL-এ explicit column list, restrictive WHERE, transaction ও constraint awareness নিরাপত্তা বাড়ায়।

NULL তিন-valued logic তৈরি করে: TRUE, FALSE, UNKNOWN। WHERE শুধু TRUE row রাখে; তাই ordinary equality দিয়ে NULL match হয় না।

## মূল ধারণার মানচিত্র

- **DDL:** Schema object define/alter/drop করা SQL category।
- **DML:** Data retrieve/insert/update/delete করার SQL category।
- **CREATE TABLE:** Column, type ও constraintসহ নতুন table define করে।
- **ALTER TABLE:** Existing table schema পরিবর্তন করে।
- **DROP TABLE:** Table definition ও data remove করে।
- **INSERT:** নতুন row table-এ যোগ করে।
- **UPDATE:** Matching existing row-এর value পরিবর্তন করে।
- **DELETE:** Matching row remove করে, table structure রাখে।
- **NULL:** Unknown, missing বা inapplicable value marker; ordinary value নয়।
- **DEFAULT:** Insert-এ value না দিলে predefined column value ব্যবহার।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: SQL DDL, DML এবং NULL

## প্রশ্ন 841 | Topic: Database Management System > SQL Fundamentals | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Schema object define/alter/drop করা SQL category।`

A) DEFAULT
B) DDL
C) NULL
D) ALTER TABLE

**সঠিক উত্তর: B) DDL**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Schema object define/alter/drop করা SQL category।
- **A option কেন ভুল:** `DEFAULT` বলতে Insert-এ value না দিলে predefined column value ব্যবহার। বোঝায়; প্রশ্নের বর্ণনা `DDL`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `NULL` বলতে Unknown, missing বা inapplicable value marker; ordinary value নয়। বোঝায়; প্রশ্নের বর্ণনা `DDL`-এর।
- **D option কেন ভুল:** `ALTER TABLE` বলতে Existing table schema পরিবর্তন করে। বোঝায়; প্রশ্নের বর্ণনা `DDL`-এর।
- **Related Concept:** CREATE, ALTER, DROP।
- **মনে রাখার টিপস:** Structure commands।

---

## প্রশ্ন 842 | Topic: Database Management System > SQL Fundamentals | Difficulty: Medium | Type: Theory

Q. `DML` সম্পর্কে কোন statement সঠিক?

A) Column, type ও constraintসহ নতুন table define করে।
B) Data retrieve/insert/update/delete করার SQL category।
C) Unknown, missing বা inapplicable value marker; ordinary value নয়।
D) নতুন row table-এ যোগ করে।

**সঠিক উত্তর: B) Data retrieve/insert/update/delete করার SQL category।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Data retrieve/insert/update/delete করার SQL category।
- **A option কেন ভুল:** এই statementটি `CREATE TABLE` ধারণাকে বর্ণনা করে; `DML`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `NULL` ধারণাকে বর্ণনা করে; `DML`-কে নয়।
- **D option কেন ভুল:** এই statementটি `INSERT` ধারণাকে বর্ণনা করে; `DML`-কে নয়।
- **Related Concept:** SELECT, INSERT, UPDATE, DELETE।
- **মনে রাখার টিপস:** Data commands।

---

## প্রশ্ন 843 | Topic: Database Management System > SQL Fundamentals | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `Column, type ও constraintসহ নতুন table define করে।`—এখানে কোন concept প্রযোজ্য?

A) DELETE
B) INSERT
C) NULL
D) CREATE TABLE

**সঠিক উত্তর: D) CREATE TABLE**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Column, type ও constraintসহ নতুন table define করে।
- **A option কেন ভুল:** `DELETE` বলতে Matching row remove করে, table structure রাখে। বোঝায়; প্রশ্নের বর্ণনা `CREATE TABLE`-এর।
- **B option কেন ভুল:** `INSERT` বলতে নতুন row table-এ যোগ করে। বোঝায়; প্রশ্নের বর্ণনা `CREATE TABLE`-এর।
- **C option কেন ভুল:** `NULL` বলতে Unknown, missing বা inapplicable value marker; ordinary value নয়। বোঝায়; প্রশ্নের বর্ণনা `CREATE TABLE`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** DDL statement।
- **মনে রাখার টিপস:** Make table।

---

## প্রশ্ন 844 | Topic: Database Management System > SQL Fundamentals | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Existing table schema পরিবর্তন করে।`

A) DEFAULT
B) ALTER TABLE
C) UPDATE
D) DROP TABLE

**সঠিক উত্তর: B) ALTER TABLE**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Existing table schema পরিবর্তন করে।
- **A option কেন ভুল:** `DEFAULT` বলতে Insert-এ value না দিলে predefined column value ব্যবহার। বোঝায়; প্রশ্নের বর্ণনা `ALTER TABLE`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `UPDATE` বলতে Matching existing row-এর value পরিবর্তন করে। বোঝায়; প্রশ্নের বর্ণনা `ALTER TABLE`-এর।
- **D option কেন ভুল:** `DROP TABLE` বলতে Table definition ও data remove করে। বোঝায়; প্রশ্নের বর্ণনা `ALTER TABLE`-এর।
- **Related Concept:** Column/constraint add/drop DBMSভেদে।
- **মনে রাখার টিপস:** Change structure।

---

## প্রশ্ন 845 | Topic: Database Management System > SQL Fundamentals | Difficulty: Medium | Type: Theory

Q. `DROP TABLE` সম্পর্কে কোন statement সঠিক?

A) Existing table schema পরিবর্তন করে।
B) Table definition ও data remove করে।
C) Column, type ও constraintসহ নতুন table define করে।
D) নতুন row table-এ যোগ করে।

**সঠিক উত্তর: B) Table definition ও data remove করে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Table definition ও data remove করে।
- **A option কেন ভুল:** এই statementটি `ALTER TABLE` ধারণাকে বর্ণনা করে; `DROP TABLE`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `CREATE TABLE` ধারণাকে বর্ণনা করে; `DROP TABLE`-কে নয়।
- **D option কেন ভুল:** এই statementটি `INSERT` ধারণাকে বর্ণনা করে; `DROP TABLE`-কে নয়।
- **Related Concept:** Transaction behavior DBMSভেদে।
- **মনে রাখার টিপস:** Remove table।

---

## প্রশ্ন 846 | Topic: Database Management System > SQL Fundamentals | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `নতুন row table-এ যোগ করে।`—এখানে কোন concept প্রযোজ্য?

A) INSERT
B) DROP TABLE
C) ALTER TABLE
D) UPDATE

**সঠিক উত্তর: A) INSERT**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** নতুন row table-এ যোগ করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `DROP TABLE` বলতে Table definition ও data remove করে। বোঝায়; প্রশ্নের বর্ণনা `INSERT`-এর।
- **C option কেন ভুল:** `ALTER TABLE` বলতে Existing table schema পরিবর্তন করে। বোঝায়; প্রশ্নের বর্ণনা `INSERT`-এর।
- **D option কেন ভুল:** `UPDATE` বলতে Matching existing row-এর value পরিবর্তন করে। বোঝায়; প্রশ্নের বর্ণনা `INSERT`-এর।
- **Related Concept:** Column list দেওয়া নিরাপদ।
- **মনে রাখার টিপস:** Add rows।

---

## প্রশ্ন 847 | Topic: Database Management System > SQL Fundamentals | Difficulty: Medium | Type: Code

Q. Table-এ 100 row। `UPDATE Employee SET salary=salary*1.1;`-এ WHERE নেই। কত row target হবে?

A) 100
B) 0
C) 1
D) 10

**সঠিক উত্তর: A) 100**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** WHERE ছাড়া UPDATE সব row target করে।

#### Step-by-step সমাধান

```text
Existing rows=100
WHERE clause=none
Target rows=100
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Statement valid।
- **C option কেন ভুল:** Single-row key condition নেই।
- **D option কেন ভুল:** 10% salary increment row count নয়।
- **Related Concept:** Mass update-এর আগে transaction/preview গুরুত্বপূর্ণ।
- **মনে রাখার টিপস:** No WHERE = all rows।

---

## প্রশ্ন 848 | Topic: Database Management System > SQL Fundamentals | Difficulty: Medium | Type: Theory

Q. `DELETE` সম্পর্কে কোন statement সঠিক?

A) Insert-এ value না দিলে predefined column value ব্যবহার।
B) Existing table schema পরিবর্তন করে।
C) Matching row remove করে, table structure রাখে।
D) Unknown, missing বা inapplicable value marker; ordinary value নয়।

**সঠিক উত্তর: C) Matching row remove করে, table structure রাখে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Matching row remove করে, table structure রাখে।
- **A option কেন ভুল:** এই statementটি `DEFAULT` ধারণাকে বর্ণনা করে; `DELETE`-কে নয়।
- **B option কেন ভুল:** এই statementটি `ALTER TABLE` ধারণাকে বর্ণনা করে; `DELETE`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `NULL` ধারণাকে বর্ণনা করে; `DELETE`-কে নয়।
- **Related Concept:** WHERE না থাকলে সব row।
- **মনে রাখার টিপস:** Remove rows।

---

## প্রশ্ন 849 | Topic: Database Management System > SQL Fundamentals | Difficulty: Medium | Type: Code

Q. SQL-এ `salary = NULL` predicate-এর পরিবর্তে কোনটি ব্যবহার করা উচিত?

A) salary <> NULL
B) salary LIKE NULL
C) salary IN NULL
D) salary IS NULL

**সঠিক উত্তর: D) salary IS NULL**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** NULL equality truth unknown; IS NULL dedicated predicate।

#### Step-by-step সমাধান

```text
Wrong: salary = NULL
Correct: salary IS NULL
```
- **A option কেন ভুল:** Comparisonও unknown।
- **B option কেন ভুল:** Pattern comparison নয়।
- **C option কেন ভুল:** Invalid/incorrect form।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** NULL-এর সঙ্গে = বা <> নয়।
- **মনে রাখার টিপস:** NULL test → IS NULL।

---

## প্রশ্ন 850 | Topic: Database Management System > SQL Fundamentals | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Insert-এ value না দিলে predefined column value ব্যবহার।`

A) ALTER TABLE
B) UPDATE
C) DEFAULT
D) DML

**সঠিক উত্তর: C) DEFAULT**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Insert-এ value না দিলে predefined column value ব্যবহার।
- **A option কেন ভুল:** `ALTER TABLE` বলতে Existing table schema পরিবর্তন করে। বোঝায়; প্রশ্নের বর্ণনা `DEFAULT`-এর।
- **B option কেন ভুল:** `UPDATE` বলতে Matching existing row-এর value পরিবর্তন করে। বোঝায়; প্রশ্নের বর্ণনা `DEFAULT`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `DML` বলতে Data retrieve/insert/update/delete করার SQL category। বোঝায়; প্রশ্নের বর্ণনা `DEFAULT`-এর।
- **Related Concept:** Explicit NULL আলাদা হতে পারে।
- **মনে রাখার টিপস:** Fallback value।

---


# Chapter Theory 75: SQL Joins এবং Subqueries

## বিস্তারিত Theory Note

Join result cardinality relationship multiplicity-এর ওপর নির্ভর করে। Outer join-এর preserved side WHERE filter দিয়ে ভুলভাবে বাদ দিলে outer join কার্যত inner join হতে পারে।

EXISTS row existence পরীক্ষা করে; IN value membership। Correlated subquery outer row reference করে, তবে optimizer join-এ rewrite করতে পারে।

## মূল ধারণার মানচিত্র

- **INNER JOIN:** শুধু join predicate match করা row return করে।
- **LEFT OUTER JOIN:** Left table-এর সব row এবং matching right row; match না থাকলে right column NULL।
- **RIGHT OUTER JOIN:** Right table-এর সব row preserve করে।
- **FULL OUTER JOIN:** দুই table-এর matched ও উভয় side-এর unmatched row preserve করে।
- **CROSS JOIN:** Cartesian product তৈরি করে।
- **Self Join:** এক table-কে alias দিয়ে নিজের সঙ্গেই join।
- **Correlated Subquery:** Outer query-এর current row value reference করে এবং conceptually প্রতি row evaluate হতে পারে।
- **EXISTS:** Subquery অন্তত একটি row return করে কি না পরীক্ষা।
- **IN Predicate:** Value subquery/list-এর কোনো member-এর সমান কি না পরীক্ষা।
- **Scalar Subquery:** সর্বোচ্চ এক row ও এক column value return করার expected subquery।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: SQL Joins এবং Subqueries

# Batch 19 — Question 851–900

## প্রশ্ন 851 | Topic: Database Management System > SQL Querying I | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`শুধু join predicate match করা row return করে।`

A) IN Predicate
B) CROSS JOIN
C) INNER JOIN
D) EXISTS

**সঠিক উত্তর: C) INNER JOIN**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** শুধু join predicate match করা row return করে।
- **A option কেন ভুল:** `IN Predicate` বলতে Value subquery/list-এর কোনো member-এর সমান কি না পরীক্ষা। বোঝায়; প্রশ্নের বর্ণনা `INNER JOIN`-এর।
- **B option কেন ভুল:** `CROSS JOIN` বলতে Cartesian product তৈরি করে। বোঝায়; প্রশ্নের বর্ণনা `INNER JOIN`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `EXISTS` বলতে Subquery অন্তত একটি row return করে কি না পরীক্ষা। বোঝায়; প্রশ্নের বর্ণনা `INNER JOIN`-এর।
- **Related Concept:** Unmatched row বাদ।
- **মনে রাখার টিপস:** Matches only।

---

## প্রশ্ন 852 | Topic: Database Management System > SQL Querying I | Difficulty: Easy | Type: Calculation

Q. Left table 5 row; 3 row match, 2 unmatched। প্রতিটি left row সর্বোচ্চ এক right row match। LEFT JOIN result row কত?

A) 3
B) 5
C) 7
D) 10

**সঠিক উত্তর: B) 5**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** সব 5 left row থাকে; unmatched 2-তে right NULL।

#### Step-by-step সমাধান

```text
Matched left rows=3 ->3 result
Unmatched left rows=2 ->2 result with NULL
Total=5
```
- **A option কেন ভুল:** Inner join count।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Match ও left total যোগ করে double count।
- **D option কেন ভুল:** Product assumption।
- **Related Concept:** One-to-many match থাকলে result left count-এর চেয়ে বড় হতে পারে।
- **মনে রাখার টিপস:** LEFT JOIN preserves every left row।

---

## প্রশ্ন 853 | Topic: Database Management System > SQL Querying I | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `Right table-এর সব row preserve করে।`—এখানে কোন concept প্রযোজ্য?

A) Self Join
B) FULL OUTER JOIN
C) RIGHT OUTER JOIN
D) Correlated Subquery

**সঠিক উত্তর: C) RIGHT OUTER JOIN**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Right table-এর সব row preserve করে।
- **A option কেন ভুল:** `Self Join` বলতে এক table-কে alias দিয়ে নিজের সঙ্গেই join। বোঝায়; প্রশ্নের বর্ণনা `RIGHT OUTER JOIN`-এর।
- **B option কেন ভুল:** `FULL OUTER JOIN` বলতে দুই table-এর matched ও উভয় side-এর unmatched row preserve করে। বোঝায়; প্রশ্নের বর্ণনা `RIGHT OUTER JOIN`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Correlated Subquery` বলতে Outer query-এর current row value reference করে এবং conceptually প্রতি row evaluate হতে পারে। বোঝায়; প্রশ্নের বর্ণনা `RIGHT OUTER JOIN`-এর।
- **Related Concept:** Left join table order বদলে equivalent হতে পারে।
- **মনে রাখার টিপস:** Keep all right।

---

## প্রশ্ন 854 | Topic: Database Management System > SQL Querying I | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`দুই table-এর matched ও উভয় side-এর unmatched row preserve করে।`

A) Self Join
B) FULL OUTER JOIN
C) CROSS JOIN
D) Scalar Subquery

**সঠিক উত্তর: B) FULL OUTER JOIN**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** দুই table-এর matched ও উভয় side-এর unmatched row preserve করে।
- **A option কেন ভুল:** `Self Join` বলতে এক table-কে alias দিয়ে নিজের সঙ্গেই join। বোঝায়; প্রশ্নের বর্ণনা `FULL OUTER JOIN`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `CROSS JOIN` বলতে Cartesian product তৈরি করে। বোঝায়; প্রশ্নের বর্ণনা `FULL OUTER JOIN`-এর।
- **D option কেন ভুল:** `Scalar Subquery` বলতে সর্বোচ্চ এক row ও এক column value return করার expected subquery। বোঝায়; প্রশ্নের বর্ণনা `FULL OUTER JOIN`-এর।
- **Related Concept:** DBMS support ভিন্ন।
- **মনে রাখার টিপস:** Keep both sides।

---

## প্রশ্ন 855 | Topic: Database Management System > SQL Querying I | Difficulty: Medium | Type: Calculation

Q. Table A-তে 4 row ও B-তে 6 row। CROSS JOIN row কত?

A) 10
B) 6
C) 4
D) 24

**সঠিক উত্তর: D) 24**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Cartesian product 4×6=24।

#### Step-by-step সমাধান

```text
4x6=24
```
- **A option কেন ভুল:** যোগ।
- **B option কেন ভুল:** শুধু B।
- **C option কেন ভুল:** শুধু A।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** CROSS JOIN predicate ছাড়া all pairs।
- **মনে রাখার টিপস:** Rows multiply।

---

## প্রশ্ন 856 | Topic: Database Management System > SQL Querying I | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `এক table-কে alias দিয়ে নিজের সঙ্গেই join।`—এখানে কোন concept প্রযোজ্য?

A) Self Join
B) LEFT OUTER JOIN
C) INNER JOIN
D) Scalar Subquery

**সঠিক উত্তর: A) Self Join**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** এক table-কে alias দিয়ে নিজের সঙ্গেই join।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `LEFT OUTER JOIN` বলতে Left table-এর সব row এবং matching right row; match না থাকলে right column NULL। বোঝায়; প্রশ্নের বর্ণনা `Self Join`-এর।
- **C option কেন ভুল:** `INNER JOIN` বলতে শুধু join predicate match করা row return করে। বোঝায়; প্রশ্নের বর্ণনা `Self Join`-এর।
- **D option কেন ভুল:** `Scalar Subquery` বলতে সর্বোচ্চ এক row ও এক column value return করার expected subquery। বোঝায়; প্রশ্নের বর্ণনা `Self Join`-এর।
- **Related Concept:** Employee-manager hierarchy।
- **মনে রাখার টিপস:** Table joins itself।

---

## প্রশ্ন 857 | Topic: Database Management System > SQL Querying I | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Outer query-এর current row value reference করে এবং conceptually প্রতি row evaluate হতে পারে।`

A) INNER JOIN
B) CROSS JOIN
C) LEFT OUTER JOIN
D) Correlated Subquery

**সঠিক উত্তর: D) Correlated Subquery**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Outer query-এর current row value reference করে এবং conceptually প্রতি row evaluate হতে পারে।
- **A option কেন ভুল:** `INNER JOIN` বলতে শুধু join predicate match করা row return করে। বোঝায়; প্রশ্নের বর্ণনা `Correlated Subquery`-এর।
- **B option কেন ভুল:** `CROSS JOIN` বলতে Cartesian product তৈরি করে। বোঝায়; প্রশ্নের বর্ণনা `Correlated Subquery`-এর।
- **C option কেন ভুল:** `LEFT OUTER JOIN` বলতে Left table-এর সব row এবং matching right row; match না থাকলে right column NULL। বোঝায়; প্রশ্নের বর্ণনা `Correlated Subquery`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Optimizer rewrite করতে পারে।
- **মনে রাখার টিপস:** Subquery depends on outer row।

---

## প্রশ্ন 858 | Topic: Database Management System > SQL Querying I | Difficulty: Medium | Type: Tracing

Q. Correlated `EXISTS` subquery কোনো outer row-এর জন্য 0 row return করলে predicate কী?

A) TRUE
B) FALSE
C) NULL always
D) Error

**সঠিক উত্তর: B) FALSE**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** EXISTS অন্তত এক row থাকলে true; zero হলে false।

#### Step-by-step সমাধান

```text
Subquery row count=0
EXISTS(0 rows)=FALSE
```
- **A option কেন ভুল:** Row থাকলে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** EXISTS boolean result দেয়।
- **D option কেন ভুল:** Empty subquery valid।
- **Related Concept:** EXISTS data value নয়, row presence দেখে।
- **মনে রাখার টিপস:** 0 row=False।

---

## প্রশ্ন 859 | Topic: Database Management System > SQL Querying I | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Value subquery/list-এর কোনো member-এর সমান কি না পরীক্ষা।`—এখানে কোন concept প্রযোজ্য?

A) LEFT OUTER JOIN
B) Correlated Subquery
C) IN Predicate
D) Scalar Subquery

**সঠিক উত্তর: C) IN Predicate**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Value subquery/list-এর কোনো member-এর সমান কি না পরীক্ষা।
- **A option কেন ভুল:** `LEFT OUTER JOIN` বলতে Left table-এর সব row এবং matching right row; match না থাকলে right column NULL। বোঝায়; প্রশ্নের বর্ণনা `IN Predicate`-এর।
- **B option কেন ভুল:** `Correlated Subquery` বলতে Outer query-এর current row value reference করে এবং conceptually প্রতি row evaluate হতে পারে। বোঝায়; প্রশ্নের বর্ণনা `IN Predicate`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Scalar Subquery` বলতে সর্বোচ্চ এক row ও এক column value return করার expected subquery। বোঝায়; প্রশ্নের বর্ণনা `IN Predicate`-এর।
- **Related Concept:** NULL semantics সতর্কতা।
- **মনে রাখার টিপস:** Membership test।

---

## প্রশ্ন 860 | Topic: Database Management System > SQL Querying I | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`সর্বোচ্চ এক row ও এক column value return করার expected subquery।`

A) INNER JOIN
B) Scalar Subquery
C) FULL OUTER JOIN
D) Correlated Subquery

**সঠিক উত্তর: B) Scalar Subquery**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** সর্বোচ্চ এক row ও এক column value return করার expected subquery।
- **A option কেন ভুল:** `INNER JOIN` বলতে শুধু join predicate match করা row return করে। বোঝায়; প্রশ্নের বর্ণনা `Scalar Subquery`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `FULL OUTER JOIN` বলতে দুই table-এর matched ও উভয় side-এর unmatched row preserve করে। বোঝায়; প্রশ্নের বর্ণনা `Scalar Subquery`-এর।
- **D option কেন ভুল:** `Correlated Subquery` বলতে Outer query-এর current row value reference করে এবং conceptually প্রতি row evaluate হতে পারে। বোঝায়; প্রশ্নের বর্ণনা `Scalar Subquery`-এর।
- **Related Concept:** Multiple row হলে error হতে পারে।
- **মনে রাখার টিপস:** Single value query।

---


# Chapter Theory 76: SQL Aggregate, GROUP BY এবং HAVING

## বিস্তারিত Theory Note

SQL logical processing-এ FROM/JOIN, WHERE, GROUP BY, HAVING, SELECT, ORDER BY—এই conceptual order aggregate reasoning সহজ করে। WHERE row কমায়; HAVING group কমায়।

NULL aggregate semantics গুরুত্বপূর্ণ। COUNT(*) সব row; COUNT(expr), SUM ও AVG সাধারণত NULL বাদ দেয়। Window function group collapse না করে analytic result যোগ করে।

## মূল ধারণার মানচিত্র

- **COUNT(*):** Result group-এর সব row count করে, NULL নির্বিশেষে।
- **SUM:** Group-এর non-null numeric value যোগ করে।
- **AVG:** Non-null numeric value-এর sum/count।
- **MIN:** Minimum non-null value।
- **MAX:** Maximum non-null value।
- **GROUP BY:** একই grouping key row-গুলো এক group করে aggregate হিসাব।
- **HAVING:** Aggregation/grouping-এর পরে group filter করে।
- **WHERE:** Grouping-এর আগে individual row filter করে।
- **DISTINCT:** Duplicate result value/tuple eliminate করে।
- **Window Function:** Row collapse না করে partition/order context-এ aggregate/rank compute।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: SQL Aggregate, GROUP BY এবং HAVING

## প্রশ্ন 861 | Topic: Database Management System > SQL Querying II | Difficulty: Hard | Type: Calculation

Q. Column values `10, NULL, 20, NULL`। `COUNT(*)` ও `COUNT(column)` যথাক্রমে কত?

A) 2 ও4
B) 4 ও4
C) 4 ও2
D) 2 ও2

**সঠিক উত্তর: C) 4 ও2**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** COUNT(*) চার row; COUNT(column) দুই non-null।

#### Step-by-step সমাধান

```text
Rows=4
Non-null values=2
COUNT(*)=4
COUNT(column)=2
```
- **A option কেন ভুল:** উল্টো।
- **B option কেন ভুল:** NULL column values count করা হয়েছে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** COUNT(*)-তে NULL row বাদ।
- **Related Concept:** COUNT(*) rows, COUNT(expr) non-null expressions।
- **মনে রাখার টিপস:** Star counts rows।

---

## প্রশ্ন 862 | Topic: Database Management System > SQL Querying II | Difficulty: Easy | Type: Theory

Q. `SUM` সম্পর্কে কোন statement সঠিক?

A) Group-এর non-null numeric value যোগ করে।
B) Maximum non-null value।
C) Result group-এর সব row count করে, NULL নির্বিশেষে।
D) Row collapse না করে partition/order context-এ aggregate/rank compute।

**সঠিক উত্তর: A) Group-এর non-null numeric value যোগ করে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Group-এর non-null numeric value যোগ করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `MAX` ধারণাকে বর্ণনা করে; `SUM`-কে নয়।
- **C option কেন ভুল:** এই statementটি `COUNT(*)` ধারণাকে বর্ণনা করে; `SUM`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Window Function` ধারণাকে বর্ণনা করে; `SUM`-কে নয়।
- **Related Concept:** Empty/all-null result DBMS semantics NULL।
- **মনে রাখার টিপস:** Add values।

---

## প্রশ্ন 863 | Topic: Database Management System > SQL Querying II | Difficulty: Medium | Type: Calculation

Q. Values `10,20,NULL,30`। AVG কত?

A) 20
B) 15
C) 30
D) 60

**সঠিক উত্তর: A) 20**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Non-null sum60/count3=20।

#### Step-by-step সমাধান

```text
Sum=10+20+30=60
Count=3
AVG=60/3=20
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** NULL-সহ চার denominator।
- **C option কেন ভুল:** Max/ভুল division।
- **D option কেন ভুল:** Sum, average নয়।
- **Related Concept:** AVG NULL বাদ দেয়।
- **মনে রাখার টিপস:** Sum non-null / count non-null।

---

## প্রশ্ন 864 | Topic: Database Management System > SQL Querying II | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Minimum non-null value।`

A) MIN
B) GROUP BY
C) AVG
D) DISTINCT

**সঠিক উত্তর: A) MIN**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Minimum non-null value।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `GROUP BY` বলতে একই grouping key row-গুলো এক group করে aggregate হিসাব। বোঝায়; প্রশ্নের বর্ণনা `MIN`-এর।
- **C option কেন ভুল:** `AVG` বলতে Non-null numeric value-এর sum/count। বোঝায়; প্রশ্নের বর্ণনা `MIN`-এর।
- **D option কেন ভুল:** `DISTINCT` বলতে Duplicate result value/tuple eliminate করে। বোঝায়; প্রশ্নের বর্ণনা `MIN`-এর।
- **Related Concept:** Comparable type।
- **মনে রাখার টিপস:** Smallest value।

---

## প্রশ্ন 865 | Topic: Database Management System > SQL Querying II | Difficulty: Medium | Type: Theory

Q. `MAX` সম্পর্কে কোন statement সঠিক?

A) Duplicate result value/tuple eliminate করে।
B) Row collapse না করে partition/order context-এ aggregate/rank compute।
C) Group-এর non-null numeric value যোগ করে।
D) Maximum non-null value।

**সঠিক উত্তর: D) Maximum non-null value।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Maximum non-null value।
- **A option কেন ভুল:** এই statementটি `DISTINCT` ধারণাকে বর্ণনা করে; `MAX`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Window Function` ধারণাকে বর্ণনা করে; `MAX`-কে নয়।
- **C option কেন ভুল:** এই statementটি `SUM` ধারণাকে বর্ণনা করে; `MAX`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Comparable type।
- **মনে রাখার টিপস:** Largest value।

---

## প্রশ্ন 866 | Topic: Database Management System > SQL Querying II | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `একই grouping key row-গুলো এক group করে aggregate হিসাব।`—এখানে কোন concept প্রযোজ্য?

A) AVG
B) GROUP BY
C) COUNT(*)
D) MAX

**সঠিক উত্তর: B) GROUP BY**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একই grouping key row-গুলো এক group করে aggregate হিসাব।
- **A option কেন ভুল:** `AVG` বলতে Non-null numeric value-এর sum/count। বোঝায়; প্রশ্নের বর্ণনা `GROUP BY`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `COUNT(*)` বলতে Result group-এর সব row count করে, NULL নির্বিশেষে। বোঝায়; প্রশ্নের বর্ণনা `GROUP BY`-এর।
- **D option কেন ভুল:** `MAX` বলতে Maximum non-null value। বোঝায়; প্রশ্নের বর্ণনা `GROUP BY`-এর।
- **Related Concept:** Nonaggregated select column group-compatible হতে হয়।
- **মনে রাখার টিপস:** Group rows by key।

---

## প্রশ্ন 867 | Topic: Database Management System > SQL Querying II | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Aggregation/grouping-এর পরে group filter করে।`

A) WHERE
B) HAVING
C) MIN
D) SUM

**সঠিক উত্তর: B) HAVING**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Aggregation/grouping-এর পরে group filter করে।
- **A option কেন ভুল:** `WHERE` বলতে Grouping-এর আগে individual row filter করে। বোঝায়; প্রশ্নের বর্ণনা `HAVING`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `MIN` বলতে Minimum non-null value। বোঝায়; প্রশ্নের বর্ণনা `HAVING`-এর।
- **D option কেন ভুল:** `SUM` বলতে Group-এর non-null numeric value যোগ করে। বোঝায়; প্রশ্নের বর্ণনা `HAVING`-এর।
- **Related Concept:** WHERE row filter আগে।
- **মনে রাখার টিপস:** Filter groups।

---

## প্রশ্ন 868 | Topic: Database Management System > SQL Querying II | Difficulty: Easy | Type: Theory

Q. `WHERE` সম্পর্কে কোন statement সঠিক?

A) Aggregation/grouping-এর পরে group filter করে।
B) Non-null numeric value-এর sum/count।
C) Grouping-এর আগে individual row filter করে।
D) Row collapse না করে partition/order context-এ aggregate/rank compute।

**সঠিক উত্তর: C) Grouping-এর আগে individual row filter করে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Grouping-এর আগে individual row filter করে।
- **A option কেন ভুল:** এই statementটি `HAVING` ধারণাকে বর্ণনা করে; `WHERE`-কে নয়।
- **B option কেন ভুল:** এই statementটি `AVG` ধারণাকে বর্ণনা করে; `WHERE`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Window Function` ধারণাকে বর্ণনা করে; `WHERE`-কে নয়।
- **Related Concept:** Aggregate সাধারণত সরাসরি WHERE-তে নয়।
- **মনে রাখার টিপস:** Filter rows first।

---

## প্রশ্ন 869 | Topic: Database Management System > SQL Querying II | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Duplicate result value/tuple eliminate করে।`—এখানে কোন concept প্রযোজ্য?

A) DISTINCT
B) GROUP BY
C) HAVING
D) WHERE

**সঠিক উত্তর: A) DISTINCT**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Duplicate result value/tuple eliminate করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `GROUP BY` বলতে একই grouping key row-গুলো এক group করে aggregate হিসাব। বোঝায়; প্রশ্নের বর্ণনা `DISTINCT`-এর।
- **C option কেন ভুল:** `HAVING` বলতে Aggregation/grouping-এর পরে group filter করে। বোঝায়; প্রশ্নের বর্ণনা `DISTINCT`-এর।
- **D option কেন ভুল:** `WHERE` বলতে Grouping-এর আগে individual row filter করে। বোঝায়; প্রশ্নের বর্ণনা `DISTINCT`-এর।
- **Related Concept:** Sorting/hash cost হতে পারে।
- **মনে রাখার টিপস:** Remove duplicates।

---

## প্রশ্ন 870 | Topic: Database Management System > SQL Querying II | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Row collapse না করে partition/order context-এ aggregate/rank compute।`

A) MAX
B) GROUP BY
C) Window Function
D) DISTINCT

**সঠিক উত্তর: C) Window Function**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Row collapse না করে partition/order context-এ aggregate/rank compute।
- **A option কেন ভুল:** `MAX` বলতে Maximum non-null value। বোঝায়; প্রশ্নের বর্ণনা `Window Function`-এর।
- **B option কেন ভুল:** `GROUP BY` বলতে একই grouping key row-গুলো এক group করে aggregate হিসাব। বোঝায়; প্রশ্নের বর্ণনা `Window Function`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `DISTINCT` বলতে Duplicate result value/tuple eliminate করে। বোঝায়; প্রশ্নের বর্ণনা `Window Function`-এর।
- **Related Concept:** OVER clause।
- **মনে রাখার টিপস:** Analytics while retaining rows।

---


# Chapter Theory 77: Constraints, Views এবং Indexes

## বিস্তারিত Theory Note

Constraint invalid state database boundary-তেই আটকায়। Application validation helpful হলেও concurrent বা alternate client-এর কারণে DB constraint অপরিহার্য।

View logical abstraction; materialized view stored result। Index read latency কমায় কিন্তু insert/update/delete-এ key maintenance, storage ও locking cost যোগ করে।

## মূল ধারণার মানচিত্র

- **NOT NULL:** Column-এ NULL নিষিদ্ধ constraint।
- **UNIQUE:** Specified column set-এর duplicate non-null key value নিয়ন্ত্রণ করে; NULL behavior DBMSভেদে।
- **CHECK:** Row value predicate satisfy করতে বাধ্য করে।
- **PRIMARY KEY:** Unique ও non-null প্রধান identifier constraint।
- **FOREIGN KEY:** Referenced key-এর সঙ্গে referential integrity enforce করে।
- **View:** Stored query-derived virtual table interface।
- **Materialized View:** Query result physically store ও refresh করা view।
- **Index:** Search/order access path যা read দ্রুত করতে পারে, কিন্তু storage ও write maintenance cost বাড়ায়।
- **Clustered Index:** Table row physical/order organization index key-এর কাছাকাছি নির্ধারণ করে।
- **Covering Index:** Query প্রয়োজনীয় সব column index থেকেই পেলে table lookup এড়ানো যায়।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Constraints, Views এবং Indexes

## প্রশ্ন 871 | Topic: Database Management System > Database Objects | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Column-এ NULL নিষিদ্ধ constraint।`

A) FOREIGN KEY
B) Materialized View
C) UNIQUE
D) NOT NULL

**সঠিক উত্তর: D) NOT NULL**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Column-এ NULL নিষিদ্ধ constraint।
- **A option কেন ভুল:** `FOREIGN KEY` বলতে Referenced key-এর সঙ্গে referential integrity enforce করে। বোঝায়; প্রশ্নের বর্ণনা `NOT NULL`-এর।
- **B option কেন ভুল:** `Materialized View` বলতে Query result physically store ও refresh করা view। বোঝায়; প্রশ্নের বর্ণনা `NOT NULL`-এর।
- **C option কেন ভুল:** `UNIQUE` বলতে Specified column set-এর duplicate non-null key value নিয়ন্ত্রণ করে; NULL behavior DBMSভেদে। বোঝায়; প্রশ্নের বর্ণনা `NOT NULL`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** অন্য uniqueness দেয় না।
- **মনে রাখার টিপস:** Value required।

---

## প্রশ্ন 872 | Topic: Database Management System > Database Objects | Difficulty: Hard | Type: Theory

Q. `UNIQUE` সম্পর্কে কোন statement সঠিক?

A) Specified column set-এর duplicate non-null key value নিয়ন্ত্রণ করে; NULL behavior DBMSভেদে।
B) Query result physically store ও refresh করা view।
C) Table row physical/order organization index key-এর কাছাকাছি নির্ধারণ করে।
D) Stored query-derived virtual table interface।

**সঠিক উত্তর: A) Specified column set-এর duplicate non-null key value নিয়ন্ত্রণ করে; NULL behavior DBMSভেদে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Specified column set-এর duplicate non-null key value নিয়ন্ত্রণ করে; NULL behavior DBMSভেদে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Materialized View` ধারণাকে বর্ণনা করে; `UNIQUE`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Clustered Index` ধারণাকে বর্ণনা করে; `UNIQUE`-কে নয়।
- **D option কেন ভুল:** এই statementটি `View` ধারণাকে বর্ণনা করে; `UNIQUE`-কে নয়।
- **Related Concept:** Candidate key enforce।
- **মনে রাখার টিপস:** No duplicates।

---

## প্রশ্ন 873 | Topic: Database Management System > Database Objects | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Row value predicate satisfy করতে বাধ্য করে।`—এখানে কোন concept প্রযোজ্য?

A) Clustered Index
B) Materialized View
C) FOREIGN KEY
D) CHECK

**সঠিক উত্তর: D) CHECK**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Row value predicate satisfy করতে বাধ্য করে।
- **A option কেন ভুল:** `Clustered Index` বলতে Table row physical/order organization index key-এর কাছাকাছি নির্ধারণ করে। বোঝায়; প্রশ্নের বর্ণনা `CHECK`-এর।
- **B option কেন ভুল:** `Materialized View` বলতে Query result physically store ও refresh করা view। বোঝায়; প্রশ্নের বর্ণনা `CHECK`-এর।
- **C option কেন ভুল:** `FOREIGN KEY` বলতে Referenced key-এর সঙ্গে referential integrity enforce করে। বোঝায়; প্রশ্নের বর্ণনা `CHECK`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Domain/business rule।
- **মনে রাখার টিপস:** Row condition।

---

## প্রশ্ন 874 | Topic: Database Management System > Database Objects | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Unique ও non-null প্রধান identifier constraint।`

A) PRIMARY KEY
B) UNIQUE
C) CHECK
D) NOT NULL

**সঠিক উত্তর: A) PRIMARY KEY**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Unique ও non-null প্রধান identifier constraint।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `UNIQUE` বলতে Specified column set-এর duplicate non-null key value নিয়ন্ত্রণ করে; NULL behavior DBMSভেদে। বোঝায়; প্রশ্নের বর্ণনা `PRIMARY KEY`-এর।
- **C option কেন ভুল:** `CHECK` বলতে Row value predicate satisfy করতে বাধ্য করে। বোঝায়; প্রশ্নের বর্ণনা `PRIMARY KEY`-এর।
- **D option কেন ভুল:** `NOT NULL` বলতে Column-এ NULL নিষিদ্ধ constraint। বোঝায়; প্রশ্নের বর্ণনা `PRIMARY KEY`-এর।
- **Related Concept:** এক table-এ এক primary key, composite হতে পারে।
- **মনে রাখার টিপস:** Main key।

---

## প্রশ্ন 875 | Topic: Database Management System > Database Objects | Difficulty: Medium | Type: Tracing

Q. Child table-এর foreign-key value parent table-এ নেই এবং NULLও নয়। Insert করলে কী হওয়া উচিত?

A) Accept always
B) Primary-key update
C) View refresh
D) Referential-integrity violation

**সঠিক উত্তর: D) Referential-integrity violation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Non-null foreign key-এর matching referenced key থাকা দরকার।

#### Step-by-step সমাধান

```text
Child FK=value X
Parent key set does not contain X
X is not NULL
Result=violation
```
- **A option কেন ভুল:** Constraint ভাঙে।
- **B option কেন ভুল:** Parent key automatic তৈরি নয়।
- **C option কেন ভুল:** Unrelated।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** ON DELETE/UPDATE action existing relation change নিয়ন্ত্রণ করে।
- **মনে রাখার টিপস:** Reference must exist।

---

## প্রশ্ন 876 | Topic: Database Management System > Database Objects | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Stored query-derived virtual table interface।`—এখানে কোন concept প্রযোজ্য?

A) Index
B) View
C) PRIMARY KEY
D) Materialized View

**সঠিক উত্তর: B) View**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Stored query-derived virtual table interface।
- **A option কেন ভুল:** `Index` বলতে Search/order access path যা read দ্রুত করতে পারে, কিন্তু storage ও write maintenance cost বাড়ায়। বোঝায়; প্রশ্নের বর্ণনা `View`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `PRIMARY KEY` বলতে Unique ও non-null প্রধান identifier constraint। বোঝায়; প্রশ্নের বর্ণনা `View`-এর।
- **D option কেন ভুল:** `Materialized View` বলতে Query result physically store ও refresh করা view। বোঝায়; প্রশ্নের বর্ণনা `View`-এর।
- **Related Concept:** Security ও abstraction, কিছু materialized নয়।
- **মনে রাখার টিপস:** Query as table।

---

## প্রশ্ন 877 | Topic: Database Management System > Database Objects | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Query result physically store ও refresh করা view।`

A) Materialized View
B) FOREIGN KEY
C) Clustered Index
D) Index

**সঠিক উত্তর: A) Materialized View**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Query result physically store ও refresh করা view।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `FOREIGN KEY` বলতে Referenced key-এর সঙ্গে referential integrity enforce করে। বোঝায়; প্রশ্নের বর্ণনা `Materialized View`-এর।
- **C option কেন ভুল:** `Clustered Index` বলতে Table row physical/order organization index key-এর কাছাকাছি নির্ধারণ করে। বোঝায়; প্রশ্নের বর্ণনা `Materialized View`-এর।
- **D option কেন ভুল:** `Index` বলতে Search/order access path যা read দ্রুত করতে পারে, কিন্তু storage ও write maintenance cost বাড়ায়। বোঝায়; প্রশ্নের বর্ণনা `Materialized View`-এর।
- **Related Concept:** Read দ্রুত, freshness cost।
- **মনে রাখার টিপস:** Stored query result।

---

## প্রশ্ন 878 | Topic: Database Management System > Database Objects | Difficulty: Hard | Type: Calculation

Q. Index যোগে read cost 100 page থেকে 4 page হলো। Page-read reduction কত?

A) 4
B) 24
C) 96
D) 104

**সঠিক উত্তর: C) 96**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 100−4=96 page কম।

#### Step-by-step সমাধান

```text
Reduction=100-4=96 pages
```
- **A option কেন ভুল:** New cost।
- **B option কেন ভুল:** Division-related ভুল।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** যোগ।
- **Related Concept:** Index write overheadও যোগ করে।
- **মনে রাখার টিপস:** Old−new।

---

## প্রশ্ন 879 | Topic: Database Management System > Database Objects | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Table row physical/order organization index key-এর কাছাকাছি নির্ধারণ করে।`—এখানে কোন concept প্রযোজ্য?

A) Materialized View
B) Index
C) Clustered Index
D) FOREIGN KEY

**সঠিক উত্তর: C) Clustered Index**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Table row physical/order organization index key-এর কাছাকাছি নির্ধারণ করে।
- **A option কেন ভুল:** `Materialized View` বলতে Query result physically store ও refresh করা view। বোঝায়; প্রশ্নের বর্ণনা `Clustered Index`-এর।
- **B option কেন ভুল:** `Index` বলতে Search/order access path যা read দ্রুত করতে পারে, কিন্তু storage ও write maintenance cost বাড়ায়। বোঝায়; প্রশ্নের বর্ণনা `Clustered Index`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `FOREIGN KEY` বলতে Referenced key-এর সঙ্গে referential integrity enforce করে। বোঝায়; প্রশ্নের বর্ণনা `Clustered Index`-এর।
- **Related Concept:** সাধারণত এক clustering order।
- **মনে রাখার টিপস:** Data ordered with index।

---

## প্রশ্ন 880 | Topic: Database Management System > Database Objects | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Query প্রয়োজনীয় সব column index থেকেই পেলে table lookup এড়ানো যায়।`

A) Clustered Index
B) Covering Index
C) Materialized View
D) UNIQUE

**সঠিক উত্তর: B) Covering Index**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Query প্রয়োজনীয় সব column index থেকেই পেলে table lookup এড়ানো যায়।
- **A option কেন ভুল:** `Clustered Index` বলতে Table row physical/order organization index key-এর কাছাকাছি নির্ধারণ করে। বোঝায়; প্রশ্নের বর্ণনা `Covering Index`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Materialized View` বলতে Query result physically store ও refresh করা view। বোঝায়; প্রশ্নের বর্ণনা `Covering Index`-এর।
- **D option কেন ভুল:** `UNIQUE` বলতে Specified column set-এর duplicate non-null key value নিয়ন্ত্রণ করে; NULL behavior DBMSভেদে। বোঝায়; প্রশ্নের বর্ণনা `Covering Index`-এর।
- **Related Concept:** Include column ব্যবহার হতে পারে।
- **মনে রাখার টিপস:** Index contains query data।

---


# Chapter Theory 78: Normalization এবং 1NF–BCNF

## বিস্তারিত Theory Note

Normalization fact-এর determinant শনাক্ত করে আলাদা relation-এ রাখে। 2NF composite candidate key-এর partial dependency সরায়; 3NF non-key transitive dependency সীমিত করে; BCNF সব determinant superkey চায়।

Decomposition শুধু normal form নয়—lossless join ও dependency preservation পরীক্ষা জরুরি।

## মূল ধারণার মানচিত্র

- **Normalization:** Functional/multivalued dependency অনুযায়ী relation decompose করে redundancy ও anomaly কমানো design process।
- **Update Anomaly:** এক fact বহু row-তে থাকায় সব copy update না করলে inconsistency।
- **Insertion Anomaly:** অন্য unrelated fact ছাড়া একটি fact insert করা না যাওয়া।
- **Deletion Anomaly:** এক row delete করতে গিয়ে অন্য প্রয়োজনীয় fact হারানো।
- **First Normal Form:** Attribute value atomic/single-valued এবং repeating group relational representation-এ নেই।
- **Second Normal Form:** 1NF এবং কোনো non-prime attribute candidate key-এর proper subset-এর ওপর partially dependent নয়।
- **Third Normal Form:** প্রতি nontrivial FD X→A-তে X superkey অথবা A prime attribute।
- **BCNF:** প্রতি nontrivial FD X→Y-তে X superkey।
- **Lossless Decomposition:** Decomposed relation natural join করলে spurious tuple ছাড়া original relation ফিরে আসে।
- **Dependency Preservation:** Original FD-গুলো decomposed relation-এ local constraint check দিয়েই enforce করা যায়।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Normalization এবং 1NF–BCNF

## প্রশ্ন 881 | Topic: Database Management System > Normalization I | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Functional/multivalued dependency অনুযায়ী relation decompose করে redundancy ও anomaly কমানো design process।`

A) Normalization
B) Deletion Anomaly
C) Lossless Decomposition
D) Second Normal Form

**সঠিক উত্তর: A) Normalization**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Functional/multivalued dependency অনুযায়ী relation decompose করে redundancy ও anomaly কমানো design process।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Deletion Anomaly` বলতে এক row delete করতে গিয়ে অন্য প্রয়োজনীয় fact হারানো। বোঝায়; প্রশ্নের বর্ণনা `Normalization`-এর।
- **C option কেন ভুল:** `Lossless Decomposition` বলতে Decomposed relation natural join করলে spurious tuple ছাড়া original relation ফিরে আসে। বোঝায়; প্রশ্নের বর্ণনা `Normalization`-এর।
- **D option কেন ভুল:** `Second Normal Form` বলতে 1NF এবং কোনো non-prime attribute candidate key-এর proper subset-এর ওপর partially dependent নয়। বোঝায়; প্রশ্নের বর্ণনা `Normalization`-এর।
- **Related Concept:** Lossless ও dependency preservation লক্ষ্য।
- **মনে রাখার টিপস:** Organize facts by dependency।

---

## প্রশ্ন 882 | Topic: Database Management System > Normalization I | Difficulty: Hard | Type: Theory

Q. `Update Anomaly` সম্পর্কে কোন statement সঠিক?

A) অন্য unrelated fact ছাড়া একটি fact insert করা না যাওয়া।
B) প্রতি nontrivial FD X→Y-তে X superkey।
C) এক fact বহু row-তে থাকায় সব copy update না করলে inconsistency।
D) Decomposed relation natural join করলে spurious tuple ছাড়া original relation ফিরে আসে।

**সঠিক উত্তর: C) এক fact বহু row-তে থাকায় সব copy update না করলে inconsistency।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** এক fact বহু row-তে থাকায় সব copy update না করলে inconsistency।
- **A option কেন ভুল:** এই statementটি `Insertion Anomaly` ধারণাকে বর্ণনা করে; `Update Anomaly`-কে নয়।
- **B option কেন ভুল:** এই statementটি `BCNF` ধারণাকে বর্ণনা করে; `Update Anomaly`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Lossless Decomposition` ধারণাকে বর্ণনা করে; `Update Anomaly`-কে নয়।
- **Related Concept:** Redundancy result।
- **মনে রাখার টিপস:** Same fact updated many places।

---

## প্রশ্ন 883 | Topic: Database Management System > Normalization I | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `অন্য unrelated fact ছাড়া একটি fact insert করা না যাওয়া।`—এখানে কোন concept প্রযোজ্য?

A) Insertion Anomaly
B) Deletion Anomaly
C) Dependency Preservation
D) First Normal Form

**সঠিক উত্তর: A) Insertion Anomaly**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** অন্য unrelated fact ছাড়া একটি fact insert করা না যাওয়া।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Deletion Anomaly` বলতে এক row delete করতে গিয়ে অন্য প্রয়োজনীয় fact হারানো। বোঝায়; প্রশ্নের বর্ণনা `Insertion Anomaly`-এর।
- **C option কেন ভুল:** `Dependency Preservation` বলতে Original FD-গুলো decomposed relation-এ local constraint check দিয়েই enforce করা যায়। বোঝায়; প্রশ্নের বর্ণনা `Insertion Anomaly`-এর।
- **D option কেন ভুল:** `First Normal Form` বলতে Attribute value atomic/single-valued এবং repeating group relational representation-এ নেই। বোঝায়; প্রশ্নের বর্ণনা `Insertion Anomaly`-এর।
- **Related Concept:** Poor combined relation।
- **মনে রাখার টিপস:** Cannot add one fact alone।

---

## প্রশ্ন 884 | Topic: Database Management System > Normalization I | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`এক row delete করতে গিয়ে অন্য প্রয়োজনীয় fact হারানো।`

A) Dependency Preservation
B) Normalization
C) Second Normal Form
D) Deletion Anomaly

**সঠিক উত্তর: D) Deletion Anomaly**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** এক row delete করতে গিয়ে অন্য প্রয়োজনীয় fact হারানো।
- **A option কেন ভুল:** `Dependency Preservation` বলতে Original FD-গুলো decomposed relation-এ local constraint check দিয়েই enforce করা যায়। বোঝায়; প্রশ্নের বর্ণনা `Deletion Anomaly`-এর।
- **B option কেন ভুল:** `Normalization` বলতে Functional/multivalued dependency অনুযায়ী relation decompose করে redundancy ও anomaly কমানো design process। বোঝায়; প্রশ্নের বর্ণনা `Deletion Anomaly`-এর।
- **C option কেন ভুল:** `Second Normal Form` বলতে 1NF এবং কোনো non-prime attribute candidate key-এর proper subset-এর ওপর partially dependent নয়। বোঝায়; প্রশ্নের বর্ণনা `Deletion Anomaly`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Mixed facts in one table।
- **মনে রাখার টিপস:** Delete one loses another।

---

## প্রশ্ন 885 | Topic: Database Management System > Normalization I | Difficulty: Hard | Type: Tracing

Q. এক column-এ value `'01711,01822'` comma-separated দুই phone রাখা হয়েছে। কোন normal form সমস্যা?

A) 2NF only
B) 1NF
C) BCNF only
D) No problem

**সঠিক উত্তর: B) 1NF**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** এক cell-এ multiple phone/repeating value atomicity ভাঙে।

#### Step-by-step সমাধান

```text
Cell contains two phone values
Not single atomic value
Violation=1NF
```
- **A option কেন ভুল:** প্রথমেই 1NF ভাঙা।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Higher form-এর আগে 1NF প্রয়োজন।
- **D option কেন ভুল:** Query ও constraint কঠিন।
- **Related Concept:** Phone আলাদা child relation করা যায়।
- **মনে রাখার টিপস:** Multiple values in one cell → 1NF issue।

---

## প্রশ্ন 886 | Topic: Database Management System > Normalization I | Difficulty: Easy | Type: Tracing

Q. Relation key `(Student,Course)` এবং FD `Student→StudentName`। কোন dependency?

A) Partial dependency
B) Full dependency
C) Multivalued only
D) No dependency

**সঠিক উত্তর: A) Partial dependency**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** StudentName composite key-এর subset Student-এর ওপর নির্ভর।

#### Step-by-step সমাধান

```text
Key={Student,Course}
Determinant={Student}
Student is proper subset of key
Non-prime StudentName -> partial dependency
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** সম্পূর্ণ key দরকার নয়।
- **C option কেন ভুল:** এটি ordinary FD।
- **D option কেন ভুল:** FD স্পষ্ট।
- **Related Concept:** 2NF partial dependency সরায়।
- **মনে রাখার টিপস:** Composite key subset determinant।

---

## প্রশ্ন 887 | Topic: Database Management System > Normalization I | Difficulty: Medium | Type: Tracing

Q. FD: `EmpID→DeptID` এবং `DeptID→DeptName`। EmpID থেকে DeptName dependency কী ধরনের?

A) Partial
B) Transitive
C) Trivial
D) Multivalued

**সঠিক উত্তর: B) Transitive**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** EmpID→DeptID→DeptName chain, non-key intermediate।

#### Step-by-step সমাধান

```text
EmpID -> DeptID
DeptID -> DeptName
Therefore EmpID -> DeptName transitively
```
- **A option কেন ভুল:** Composite key subset নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** DeptName determinant subset নয়।
- **D option কেন ভুল:** Ordinary functional chain।
- **Related Concept:** 3NF transitive non-key dependency target করে।
- **মনে রাখার টিপস:** Key→nonkey→nonkey।

---

## প্রশ্ন 888 | Topic: Database Management System > Normalization I | Difficulty: Medium | Type: Theory

Q. `BCNF` সম্পর্কে কোন statement সঠিক?

A) Attribute value atomic/single-valued এবং repeating group relational representation-এ নেই।
B) 1NF এবং কোনো non-prime attribute candidate key-এর proper subset-এর ওপর partially dependent নয়।
C) প্রতি nontrivial FD X→Y-তে X superkey।
D) প্রতি nontrivial FD X→A-তে X superkey অথবা A prime attribute।

**সঠিক উত্তর: C) প্রতি nontrivial FD X→Y-তে X superkey।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতি nontrivial FD X→Y-তে X superkey।
- **A option কেন ভুল:** এই statementটি `First Normal Form` ধারণাকে বর্ণনা করে; `BCNF`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Second Normal Form` ধারণাকে বর্ণনা করে; `BCNF`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Third Normal Form` ধারণাকে বর্ণনা করে; `BCNF`-কে নয়।
- **Related Concept:** 3NF-এর চেয়ে stricter।
- **মনে রাখার টিপস:** Every determinant superkey।

---

## প্রশ্ন 889 | Topic: Database Management System > Normalization I | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Decomposed relation natural join করলে spurious tuple ছাড়া original relation ফিরে আসে।`—এখানে কোন concept প্রযোজ্য?

A) Dependency Preservation
B) BCNF
C) Lossless Decomposition
D) Third Normal Form

**সঠিক উত্তর: C) Lossless Decomposition**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Decomposed relation natural join করলে spurious tuple ছাড়া original relation ফিরে আসে।
- **A option কেন ভুল:** `Dependency Preservation` বলতে Original FD-গুলো decomposed relation-এ local constraint check দিয়েই enforce করা যায়। বোঝায়; প্রশ্নের বর্ণনা `Lossless Decomposition`-এর।
- **B option কেন ভুল:** `BCNF` বলতে প্রতি nontrivial FD X→Y-তে X superkey। বোঝায়; প্রশ্নের বর্ণনা `Lossless Decomposition`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Third Normal Form` বলতে প্রতি nontrivial FD X→A-তে X superkey অথবা A prime attribute। বোঝায়; প্রশ্নের বর্ণনা `Lossless Decomposition`-এর।
- **Related Concept:** Information preservation।
- **মনে রাখার টিপস:** Join gives exactly original।

---

## প্রশ্ন 890 | Topic: Database Management System > Normalization I | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Original FD-গুলো decomposed relation-এ local constraint check দিয়েই enforce করা যায়।`

A) Dependency Preservation
B) Third Normal Form
C) Lossless Decomposition
D) First Normal Form

**সঠিক উত্তর: A) Dependency Preservation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Original FD-গুলো decomposed relation-এ local constraint check দিয়েই enforce করা যায়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Third Normal Form` বলতে প্রতি nontrivial FD X→A-তে X superkey অথবা A prime attribute। বোঝায়; প্রশ্নের বর্ণনা `Dependency Preservation`-এর।
- **C option কেন ভুল:** `Lossless Decomposition` বলতে Decomposed relation natural join করলে spurious tuple ছাড়া original relation ফিরে আসে। বোঝায়; প্রশ্নের বর্ণনা `Dependency Preservation`-এর।
- **D option কেন ভুল:** `First Normal Form` বলতে Attribute value atomic/single-valued এবং repeating group relational representation-এ নেই। বোঝায়; প্রশ্নের বর্ণনা `Dependency Preservation`-এর।
- **Related Concept:** Join ছাড়াই enforce।
- **মনে রাখার টিপস:** Constraints remain locally checkable।

---


# Chapter Theory 79: Functional Dependency, Closure এবং Minimal Cover

## বিস্তারিত Theory Note

Functional dependency schema semantics প্রকাশ করে। Closure iterative inference দিয়ে superkey ও candidate key পরীক্ষা করে। Current sample data-তে pattern দেখা গেলেই FD নিশ্চিত নয়; business rule দরকার।

Minimal cover equivalent constraint setকে সহজ করে। RHS split, LHS extraneous removal ও redundant FD removal—প্রতিটি ধাপে equivalence পরীক্ষা হয়।

## মূল ধারণার মানচিত্র

- **Functional Dependency:** X value সমান হলে Y valueও অবশ্যই সমান—এমন constraint X→Y।
- **Trivial FD:** Y subset of X হলে X→Y trivial।
- **Attribute Closure:** Given FD set-এর অধীনে X থেকে functionally determined সব attribute set X+।
- **Armstrong Reflexivity:** Y⊆X হলে X→Y infer করা যায়।
- **Armstrong Augmentation:** X→Y হলে XZ→YZ।
- **Armstrong Transitivity:** X→Y এবং Y→Z হলে X→Z।
- **Extraneous Attribute:** FD side-এর attribute বাদ দিলেও equivalent implication থাকলে অপ্রয়োজনীয় attribute।
- **Minimal Cover:** Equivalent FD set যেখানে RHS single, LHS extraneous নেই ও redundant FD নেই।
- **Candidate Key via Closure:** Minimal attribute set K যার closure সব relation attribute ধারণ করে।
- **Prime Attribute:** কমপক্ষে একটি candidate key-এর member attribute।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Functional Dependency, Closure এবং Minimal Cover

## প্রশ্ন 891 | Topic: Database Management System > Normalization II | Difficulty: Medium | Type: Theory

Q. FD `A→B`-এর অর্থ কোনটি?

A) একই B হলে একই A
B) A ও B সবসময় equal
C) A null হতে হবে
D) একই A হলে একই B

**সঠিক উত্তর: D) একই A হলে একই B**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** দুই tuple-এর A সমান হলে B ভিন্ন হতে পারবে না।

#### Step-by-step সমাধান

```text
For any tuples t1,t2:
If t1[A]=t2[A]
Then t1[B]=t2[B]
```
- **A option কেন ভুল:** এটি B→A।
- **B option কেন ভুল:** Value equality নয়।
- **C option কেন ভুল:** NULL constraint নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** FD data semantics, accidental current pattern নয়।
- **মনে রাখার টিপস:** Arrow direction determinant থেকে dependent।

---

## প্রশ্ন 892 | Topic: Database Management System > Normalization II | Difficulty: Easy | Type: Theory

Q. `Trivial FD` সম্পর্কে কোন statement সঠিক?

A) X→Y হলে XZ→YZ।
B) Y subset of X হলে X→Y trivial।
C) Given FD set-এর অধীনে X থেকে functionally determined সব attribute set X+।
D) কমপক্ষে একটি candidate key-এর member attribute।

**সঠিক উত্তর: B) Y subset of X হলে X→Y trivial।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Y subset of X হলে X→Y trivial।
- **A option কেন ভুল:** এই statementটি `Armstrong Augmentation` ধারণাকে বর্ণনা করে; `Trivial FD`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `Attribute Closure` ধারণাকে বর্ণনা করে; `Trivial FD`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Prime Attribute` ধারণাকে বর্ণনা করে; `Trivial FD`-কে নয়।
- **Related Concept:** Reflexivity।
- **মনে রাখার টিপস:** RHS already in LHS।

---

## প্রশ্ন 893 | Topic: Database Management System > Normalization II | Difficulty: Medium | Type: Calculation

Q. R(A,B,C,D), FDs: `A→B`, `B→C`, `C→D`। A+ কী?

A) {A,B}
B) {A,B,C}
C) {A,B,C,D}
D) {A}

**সঠিক উত্তর: C) {A,B,C,D}**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** A→B, B→C, C→D chain-এ সব attribute।

#### Step-by-step সমাধান

```text
Start A+={A}
A->B => {A,B}
B->C => {A,B,C}
C->D => {A,B,C,D}
```
- **A option কেন ভুল:** Transitivity chain থামানো।
- **B option কেন ভুল:** C→D প্রয়োগ হয়নি।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** কোনো FD প্রয়োগ হয়নি।
- **Related Concept:** A superkey কারণ closure universe।
- **মনে রাখার টিপস:** Closure-তে নতুন attribute না আসা পর্যন্ত repeat।

---

## প্রশ্ন 894 | Topic: Database Management System > Normalization II | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Y⊆X হলে X→Y infer করা যায়।`

A) Attribute Closure
B) Armstrong Reflexivity
C) Minimal Cover
D) Functional Dependency

**সঠিক উত্তর: B) Armstrong Reflexivity**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Y⊆X হলে X→Y infer করা যায়।
- **A option কেন ভুল:** `Attribute Closure` বলতে Given FD set-এর অধীনে X থেকে functionally determined সব attribute set X+। বোঝায়; প্রশ্নের বর্ণনা `Armstrong Reflexivity`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Minimal Cover` বলতে Equivalent FD set যেখানে RHS single, LHS extraneous নেই ও redundant FD নেই। বোঝায়; প্রশ্নের বর্ণনা `Armstrong Reflexivity`-এর।
- **D option কেন ভুল:** `Functional Dependency` বলতে X value সমান হলে Y valueও অবশ্যই সমান—এমন constraint X→Y। বোঝায়; প্রশ্নের বর্ণনা `Armstrong Reflexivity`-এর।
- **Related Concept:** Sound inference axiom।
- **মনে রাখার টিপস:** Subset dependency।

---

## প্রশ্ন 895 | Topic: Database Management System > Normalization II | Difficulty: Hard | Type: Theory

Q. `Armstrong Augmentation` সম্পর্কে কোন statement সঠিক?

A) Minimal attribute set K যার closure সব relation attribute ধারণ করে।
B) Y subset of X হলে X→Y trivial।
C) FD side-এর attribute বাদ দিলেও equivalent implication থাকলে অপ্রয়োজনীয় attribute।
D) X→Y হলে XZ→YZ।

**সঠিক উত্তর: D) X→Y হলে XZ→YZ।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** X→Y হলে XZ→YZ।
- **A option কেন ভুল:** এই statementটি `Candidate Key via Closure` ধারণাকে বর্ণনা করে; `Armstrong Augmentation`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Trivial FD` ধারণাকে বর্ণনা করে; `Armstrong Augmentation`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Extraneous Attribute` ধারণাকে বর্ণনা করে; `Armstrong Augmentation`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Both side same attributes add।
- **মনে রাখার টিপস:** Add same context।

---

## প্রশ্ন 896 | Topic: Database Management System > Normalization II | Difficulty: Hard | Type: Tracing

Q. FDs `A→B`, `B→C` থেকে কোন FD Transitivity-তে পাওয়া যায়?

A) A→C
B) B→A
C) C→A
D) AB→A only

**সঠিক উত্তর: A) A→C**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** A→B ও B→C chain।

#### Step-by-step সমাধান

```text
A -> B
B -> C
Therefore A -> C
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Reverse inference valid নয়।
- **C option কেন ভুল:** Reverse chain।
- **D option কেন ভুল:** Trivial, asked transitive implication নয়।
- **Related Concept:** Armstrong axiom sound ও complete।
- **মনে রাখার টিপস:** Follow arrow।

---

## প্রশ্ন 897 | Topic: Database Management System > Normalization II | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`FD side-এর attribute বাদ দিলেও equivalent implication থাকলে অপ্রয়োজনীয় attribute।`

A) Trivial FD
B) Minimal Cover
C) Prime Attribute
D) Extraneous Attribute

**সঠিক উত্তর: D) Extraneous Attribute**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** FD side-এর attribute বাদ দিলেও equivalent implication থাকলে অপ্রয়োজনীয় attribute।
- **A option কেন ভুল:** `Trivial FD` বলতে Y subset of X হলে X→Y trivial। বোঝায়; প্রশ্নের বর্ণনা `Extraneous Attribute`-এর।
- **B option কেন ভুল:** `Minimal Cover` বলতে Equivalent FD set যেখানে RHS single, LHS extraneous নেই ও redundant FD নেই। বোঝায়; প্রশ্নের বর্ণনা `Extraneous Attribute`-এর।
- **C option কেন ভুল:** `Prime Attribute` বলতে কমপক্ষে একটি candidate key-এর member attribute। বোঝায়; প্রশ্নের বর্ণনা `Extraneous Attribute`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Minimal cover simplification।
- **মনে রাখার টিপস:** Redundant in FD।

---

## প্রশ্ন 898 | Topic: Database Management System > Normalization II | Difficulty: Easy | Type: Tracing

Q. Minimal cover তৈরিতে FD `A→BC` প্রথমে কীভাবে split করা হয়?

A) AB→C
B) B→A এবং C→A
C) A→BC অপরিবর্তিত বাধ্যতামূলক
D) A→B এবং A→C

**সঠিক উত্তর: D) A→B এবং A→C**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Minimal cover-এ RHS single attribute করা হয়।

#### Step-by-step সমাধান

```text
A -> BC
Decompose RHS:
A -> B
A -> C
```
- **A option কেন ভুল:** Equivalent নয়।
- **B option কেন ভুল:** Direction উল্টো।
- **C option কেন ভুল:** Decomposition rule valid।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Union/decomposition inference।
- **মনে রাখার টিপস:** RHS one attribute।

---

## প্রশ্ন 899 | Topic: Database Management System > Normalization II | Difficulty: Easy | Type: Calculation

Q. R(A,B,C), FDs `A→B`, `A→C`। Candidate key কোনটি?

A) B
B) C
C) BC
D) A

**সঠিক উত্তর: D) A**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** A+={A,B,C}; A minimal single attribute।

#### Step-by-step সমাধান

```text
A+ starts {A}
A->B add B
A->C add C
A+={A,B,C}
A is candidate key
```
- **A option কেন ভুল:** B closure শুধু B।
- **B option কেন ভুল:** C closure শুধু C।
- **C option কেন ভুল:** A derive হয় না।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Closure universe এবং proper subset test।
- **মনে রাখার টিপস:** Single A determines all।

---

## প্রশ্ন 900 | Topic: Database Management System > Normalization II | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`কমপক্ষে একটি candidate key-এর member attribute।`

A) Armstrong Transitivity
B) Prime Attribute
C) Armstrong Augmentation
D) Attribute Closure

**সঠিক উত্তর: B) Prime Attribute**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** কমপক্ষে একটি candidate key-এর member attribute।
- **A option কেন ভুল:** `Armstrong Transitivity` বলতে X→Y এবং Y→Z হলে X→Z। বোঝায়; প্রশ্নের বর্ণনা `Prime Attribute`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Armstrong Augmentation` বলতে X→Y হলে XZ→YZ। বোঝায়; প্রশ্নের বর্ণনা `Prime Attribute`-এর।
- **D option কেন ভুল:** `Attribute Closure` বলতে Given FD set-এর অধীনে X থেকে functionally determined সব attribute set X+। বোঝায়; প্রশ্নের বর্ণনা `Prime Attribute`-এর।
- **Related Concept:** 3NF definition-এ গুরুত্বপূর্ণ।
- **মনে রাখার টিপস:** Belongs to some candidate key।

---


# Chapter Theory 80: 4NF, 5NF এবং Decomposition Quality

## বিস্তারিত Theory Note

4NF independent multivalued facts আলাদা করে Cartesian repetition কমায়। 5NF আরও general join dependency নিয়ে কাজ করে এবং practical schema-তে তুলনামূলক বিরল।

Higher normal form performance guarantee নয়। Denormalization deliberate হলে source-of-truth, refresh ও consistency strategy দরকার।

## মূল ধারণার মানচিত্র

- **Multivalued Dependency:** X-এর জন্য Y value set অন্য attribute set থেকে independent হলে X↠Y।
- **Fourth Normal Form:** প্রতি nontrivial MVD X↠Y-তে X superkey।
- **Join Dependency:** Relation একাধিক projection-এর join হিসেবে বাধ্যতামূলকভাবে reconstruct হওয়ার constraint।
- **Fifth Normal Form:** Every nontrivial join dependency candidate key দ্বারা implied।
- **Spurious Tuple:** Lossy decomposition join-এ original-এ না থাকা অতিরিক্ত tuple তৈরি।
- **Chase Test:** Dependency প্রয়োগ করে decomposition lossless/dependency properties যাচাই করার tableau method।
- **Denormalization:** Performance/read simplicity-এর জন্য controlled redundancy পুনরায় যোগ।
- **Surrogate Key:** Business meaning ছাড়া generated identifier।
- **Natural Key:** Domain/business attribute থেকে পাওয়া real-world identifier।
- **Dependency Preservation Trade-off:** BCNF decomposition কখনও dependency preservation হারাতে পারে, 3NF synthesis preserve করতে পারে।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: 4NF, 5NF এবং Decomposition Quality

# Batch 20 — Question 901–950

## প্রশ্ন 901 | Topic: Database Management System > Normalization III | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`X-এর জন্য Y value set অন্য attribute set থেকে independent হলে X↠Y।`

A) Denormalization
B) Spurious Tuple
C) Multivalued Dependency
D) Join Dependency

**সঠিক উত্তর: C) Multivalued Dependency**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** X-এর জন্য Y value set অন্য attribute set থেকে independent হলে X↠Y।
- **A option কেন ভুল:** `Denormalization` বলতে Performance/read simplicity-এর জন্য controlled redundancy পুনরায় যোগ। বোঝায়; প্রশ্নের বর্ণনা `Multivalued Dependency`-এর।
- **B option কেন ভুল:** `Spurious Tuple` বলতে Lossy decomposition join-এ original-এ না থাকা অতিরিক্ত tuple তৈরি। বোঝায়; প্রশ্নের বর্ণনা `Multivalued Dependency`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Join Dependency` বলতে Relation একাধিক projection-এর join হিসেবে বাধ্যতামূলকভাবে reconstruct হওয়ার constraint। বোঝায়; প্রশ্নের বর্ণনা `Multivalued Dependency`-এর।
- **Related Concept:** 4NF-এ গুরুত্বপূর্ণ।
- **মনে রাখার টিপস:** Independent multiple values।

---

## প্রশ্ন 902 | Topic: Database Management System > Normalization III | Difficulty: Medium | Type: Tracing

Q. Relation `(Student,Hobby,Language)`-এ Student-এর hobbies ও languages স্বাধীন multiple set। সমস্যাটি কোন normal form target করে?

A) 2NF
B) 3NF
C) 5NF only
D) 4NF

**সঠিক উত্তর: D) 4NF**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Independent multivalued dependencies Student↠Hobby এবং Student↠Language 4NF decomposition চায়।

#### Step-by-step সমাধান

```text
Student ->> Hobby
Student ->> Language
Hobby independent of Language
Target=4NF
```
- **A option কেন ভুল:** Partial FD focus।
- **B option কেন ভুল:** Transitive FD focus।
- **C option কেন ভুল:** MVD specifically 4NF।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Student-Hobby ও Student-Language আলাদা relation।
- **মনে রাখার টিপস:** Independent multi-values → 4NF।

---

## প্রশ্ন 903 | Topic: Database Management System > Normalization III | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Relation একাধিক projection-এর join হিসেবে বাধ্যতামূলকভাবে reconstruct হওয়ার constraint।`—এখানে কোন concept প্রযোজ্য?

A) Multivalued Dependency
B) Join Dependency
C) Dependency Preservation Trade-off
D) Denormalization

**সঠিক উত্তর: B) Join Dependency**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Relation একাধিক projection-এর join হিসেবে বাধ্যতামূলকভাবে reconstruct হওয়ার constraint।
- **A option কেন ভুল:** `Multivalued Dependency` বলতে X-এর জন্য Y value set অন্য attribute set থেকে independent হলে X↠Y। বোঝায়; প্রশ্নের বর্ণনা `Join Dependency`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Dependency Preservation Trade-off` বলতে BCNF decomposition কখনও dependency preservation হারাতে পারে, 3NF synthesis preserve করতে পারে। বোঝায়; প্রশ্নের বর্ণনা `Join Dependency`-এর।
- **D option কেন ভুল:** `Denormalization` বলতে Performance/read simplicity-এর জন্য controlled redundancy পুনরায় যোগ। বোঝায়; প্রশ্নের বর্ণনা `Join Dependency`-এর।
- **Related Concept:** 5NF foundation।
- **মনে রাখার টিপস:** Must equal join of projections।

---

## প্রশ্ন 904 | Topic: Database Management System > Normalization III | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Every nontrivial join dependency candidate key দ্বারা implied।`

A) Fifth Normal Form
B) Multivalued Dependency
C) Fourth Normal Form
D) Join Dependency

**সঠিক উত্তর: A) Fifth Normal Form**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Every nontrivial join dependency candidate key দ্বারা implied।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Multivalued Dependency` বলতে X-এর জন্য Y value set অন্য attribute set থেকে independent হলে X↠Y। বোঝায়; প্রশ্নের বর্ণনা `Fifth Normal Form`-এর।
- **C option কেন ভুল:** `Fourth Normal Form` বলতে প্রতি nontrivial MVD X↠Y-তে X superkey। বোঝায়; প্রশ্নের বর্ণনা `Fifth Normal Form`-এর।
- **D option কেন ভুল:** `Join Dependency` বলতে Relation একাধিক projection-এর join হিসেবে বাধ্যতামূলকভাবে reconstruct হওয়ার constraint। বোঝায়; প্রশ্নের বর্ণনা `Fifth Normal Form`-এর।
- **Related Concept:** Rare complex decomposition।
- **মনে রাখার টিপস:** No non-key join dependency।

---

## প্রশ্ন 905 | Topic: Database Management System > Normalization III | Difficulty: Medium | Type: Calculation

Q. Decomposed relation join করে original 6 row-এর বদলে 9 row পাওয়া গেল। Spurious row কত?

A) 3
B) 6
C) 9
D) 15

**সঠিক উত্তর: A) 3**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Extra=9−6=3।

#### Step-by-step সমাধান

```text
Join rows=9
Original rows=6
Spurious=3
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Original count।
- **C option কেন ভুল:** Joined total।
- **D option কেন ভুল:** যোগ।
- **Related Concept:** Spurious tuple lossy decomposition-এর লক্ষণ।
- **মনে রাখার টিপস:** Joined−original।

---

## প্রশ্ন 906 | Topic: Database Management System > Normalization III | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Dependency প্রয়োগ করে decomposition lossless/dependency properties যাচাই করার tableau method।`—এখানে কোন concept প্রযোজ্য?

A) Chase Test
B) Denormalization
C) Surrogate Key
D) Spurious Tuple

**সঠিক উত্তর: A) Chase Test**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Dependency প্রয়োগ করে decomposition lossless/dependency properties যাচাই করার tableau method।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Denormalization` বলতে Performance/read simplicity-এর জন্য controlled redundancy পুনরায় যোগ। বোঝায়; প্রশ্নের বর্ণনা `Chase Test`-এর।
- **C option কেন ভুল:** `Surrogate Key` বলতে Business meaning ছাড়া generated identifier। বোঝায়; প্রশ্নের বর্ণনা `Chase Test`-এর।
- **D option কেন ভুল:** `Spurious Tuple` বলতে Lossy decomposition join-এ original-এ না থাকা অতিরিক্ত tuple তৈরি। বোঝায়; প্রশ্নের বর্ণনা `Chase Test`-এর।
- **Related Concept:** Formal design tool।
- **মনে রাখার টিপস:** Symbolic dependency test।

---

## প্রশ্ন 907 | Topic: Database Management System > Normalization III | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Performance/read simplicity-এর জন্য controlled redundancy পুনরায় যোগ।`

A) Fourth Normal Form
B) Denormalization
C) Spurious Tuple
D) Join Dependency

**সঠিক উত্তর: B) Denormalization**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Performance/read simplicity-এর জন্য controlled redundancy পুনরায় যোগ।
- **A option কেন ভুল:** `Fourth Normal Form` বলতে প্রতি nontrivial MVD X↠Y-তে X superkey। বোঝায়; প্রশ্নের বর্ণনা `Denormalization`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Spurious Tuple` বলতে Lossy decomposition join-এ original-এ না থাকা অতিরিক্ত tuple তৈরি। বোঝায়; প্রশ্নের বর্ণনা `Denormalization`-এর।
- **D option কেন ভুল:** `Join Dependency` বলতে Relation একাধিক projection-এর join হিসেবে বাধ্যতামূলকভাবে reconstruct হওয়ার constraint। বোঝায়; প্রশ্নের বর্ণনা `Denormalization`-এর।
- **Related Concept:** Consistency maintenance cost।
- **মনে রাখার টিপস:** Intentional redundancy।

---

## প্রশ্ন 908 | Topic: Database Management System > Normalization III | Difficulty: Medium | Type: Theory

Q. `Surrogate Key` সম্পর্কে কোন statement সঠিক?

A) Performance/read simplicity-এর জন্য controlled redundancy পুনরায় যোগ।
B) Domain/business attribute থেকে পাওয়া real-world identifier।
C) X-এর জন্য Y value set অন্য attribute set থেকে independent হলে X↠Y।
D) Business meaning ছাড়া generated identifier।

**সঠিক উত্তর: D) Business meaning ছাড়া generated identifier।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Business meaning ছাড়া generated identifier।
- **A option কেন ভুল:** এই statementটি `Denormalization` ধারণাকে বর্ণনা করে; `Surrogate Key`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Natural Key` ধারণাকে বর্ণনা করে; `Surrogate Key`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Multivalued Dependency` ধারণাকে বর্ণনা করে; `Surrogate Key`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Natural uniqueness constraint আলাদাভাবে দরকার হতে পারে।
- **মনে রাখার টিপস:** Artificial ID।

---

## প্রশ্ন 909 | Topic: Database Management System > Normalization III | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Domain/business attribute থেকে পাওয়া real-world identifier।`—এখানে কোন concept প্রযোজ্য?

A) Natural Key
B) Join Dependency
C) Fifth Normal Form
D) Chase Test

**সঠিক উত্তর: A) Natural Key**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Domain/business attribute থেকে পাওয়া real-world identifier।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Join Dependency` বলতে Relation একাধিক projection-এর join হিসেবে বাধ্যতামূলকভাবে reconstruct হওয়ার constraint। বোঝায়; প্রশ্নের বর্ণনা `Natural Key`-এর।
- **C option কেন ভুল:** `Fifth Normal Form` বলতে Every nontrivial join dependency candidate key দ্বারা implied। বোঝায়; প্রশ্নের বর্ণনা `Natural Key`-এর।
- **D option কেন ভুল:** `Chase Test` বলতে Dependency প্রয়োগ করে decomposition lossless/dependency properties যাচাই করার tableau method। বোঝায়; প্রশ্নের বর্ণনা `Natural Key`-এর।
- **Related Concept:** Meaningful কিন্তু change/size concern।
- **মনে রাখার টিপস:** Business identity।

---

## প্রশ্ন 910 | Topic: Database Management System > Normalization III | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`BCNF decomposition কখনও dependency preservation হারাতে পারে, 3NF synthesis preserve করতে পারে।`

A) Fifth Normal Form
B) Fourth Normal Form
C) Spurious Tuple
D) Dependency Preservation Trade-off

**সঠিক উত্তর: D) Dependency Preservation Trade-off**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** BCNF decomposition কখনও dependency preservation হারাতে পারে, 3NF synthesis preserve করতে পারে।
- **A option কেন ভুল:** `Fifth Normal Form` বলতে Every nontrivial join dependency candidate key দ্বারা implied। বোঝায়; প্রশ্নের বর্ণনা `Dependency Preservation Trade-off`-এর।
- **B option কেন ভুল:** `Fourth Normal Form` বলতে প্রতি nontrivial MVD X↠Y-তে X superkey। বোঝায়; প্রশ্নের বর্ণনা `Dependency Preservation Trade-off`-এর।
- **C option কেন ভুল:** `Spurious Tuple` বলতে Lossy decomposition join-এ original-এ না থাকা অতিরিক্ত tuple তৈরি। বোঝায়; প্রশ্নের বর্ণনা `Dependency Preservation Trade-off`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Design trade-off।
- **মনে রাখার টিপস:** Stricter form vs local enforcement।

---


# Chapter Theory 81: Transactions এবং ACID

## বিস্তারিত Theory Note

Transaction application-level invariantকে atomic boundary-তে রক্ষা করে। ACID property পরস্পর সম্পর্কিত হলেও আলাদা: atomicity incomplete work, consistency rule, isolation concurrency, durability failure persistence।

Commit কখন durable ধরা হবে logging/storage policy নির্ভর। Multi-statement business operation autocommit-এ ভেঙে গেলে atomicity হারাতে পারে।

## মূল ধারণার মানচিত্র

- **Transaction:** Database state-এ logical unit হিসেবে execute হওয়া read/write operation sequence।
- **Atomicity:** Transaction-এর সব effect হবে অথবা কোনো effect থাকবে না।
- **Consistency:** Transaction database-কে এক valid state থেকে অন্য valid state-এ নেয়, constraint বজায়।
- **Isolation:** Concurrent transaction intermediate effect থেকে পরস্পরকে নির্দিষ্ট degree-এ পৃথক রাখে।
- **Durability:** Commit success-এর পরে failure হলেও effect টিকে থাকে।
- **COMMIT:** Transaction effect স্থায়ী করার successful end operation।
- **ROLLBACK:** Transaction-এর uncommitted change undo করে পূর্ব state-এ ফেরানো।
- **Savepoint:** Transaction-এর ভিতরের named partial rollback point।
- **Autocommit:** প্রতিটি statement আলাদা transaction হিসেবে automatic commit হওয়ার mode।
- **Transaction Log:** Change ও transaction state sequential record করে recovery support।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Transactions এবং ACID

## প্রশ্ন 911 | Topic: Database Management System > Transaction Basics | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Database state-এ logical unit হিসেবে execute হওয়া read/write operation sequence।`

A) Transaction
B) Isolation
C) COMMIT
D) ROLLBACK

**সঠিক উত্তর: A) Transaction**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Database state-এ logical unit হিসেবে execute হওয়া read/write operation sequence।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Isolation` বলতে Concurrent transaction intermediate effect থেকে পরস্পরকে নির্দিষ্ট degree-এ পৃথক রাখে। বোঝায়; প্রশ্নের বর্ণনা `Transaction`-এর।
- **C option কেন ভুল:** `COMMIT` বলতে Transaction effect স্থায়ী করার successful end operation। বোঝায়; প্রশ্নের বর্ণনা `Transaction`-এর।
- **D option কেন ভুল:** `ROLLBACK` বলতে Transaction-এর uncommitted change undo করে পূর্ব state-এ ফেরানো। বোঝায়; প্রশ্নের বর্ণনা `Transaction`-এর।
- **Related Concept:** Commit বা rollback boundary।
- **মনে রাখার টিপস:** One logical unit of work।

---

## প্রশ্ন 912 | Topic: Database Management System > Transaction Basics | Difficulty: Medium | Type: Tracing

Q. Bank transfer-এ debit হয়েছে কিন্তু credit-এর আগে crash; recovery দুটোই বাতিল করে। কোন ACID property?

A) Consistency only
B) Isolation
C) Atomicity
D) Durability

**সঠিক উত্তর: C) Atomicity**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Partial effect রাখা হয়নি; whole transaction rollback।

#### Step-by-step সমাধান

```text
Step1 debit executed
Step2 credit not executed
Crash before commit
Recovery undo debit
Final: neither effect
```
- **A option কেন ভুল:** Validityও concern, কিন্তু all-or-nothing specific atomicity।
- **B option কেন ভুল:** Concurrent visibility নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Committed effect persistence।
- **Related Concept:** Transfer classic atomic transaction।
- **মনে রাখার টিপস:** Half transfer must never remain।

---

## প্রশ্ন 913 | Topic: Database Management System > Transaction Basics | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Transaction database-কে এক valid state থেকে অন্য valid state-এ নেয়, constraint বজায়।`—এখানে কোন concept প্রযোজ্য?

A) Transaction
B) Autocommit
C) Savepoint
D) Consistency

**সঠিক উত্তর: D) Consistency**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Transaction database-কে এক valid state থেকে অন্য valid state-এ নেয়, constraint বজায়।
- **A option কেন ভুল:** `Transaction` বলতে Database state-এ logical unit হিসেবে execute হওয়া read/write operation sequence। বোঝায়; প্রশ্নের বর্ণনা `Consistency`-এর।
- **B option কেন ভুল:** `Autocommit` বলতে প্রতিটি statement আলাদা transaction হিসেবে automatic commit হওয়ার mode। বোঝায়; প্রশ্নের বর্ণনা `Consistency`-এর।
- **C option কেন ভুল:** `Savepoint` বলতে Transaction-এর ভিতরের named partial rollback point। বোঝায়; প্রশ্নের বর্ণনা `Consistency`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Application ও DB rule দুটো।
- **মনে রাখার টিপস:** Valid state transition।

---

## প্রশ্ন 914 | Topic: Database Management System > Transaction Basics | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Concurrent transaction intermediate effect থেকে পরস্পরকে নির্দিষ্ট degree-এ পৃথক রাখে।`

A) Isolation
B) Transaction
C) Atomicity
D) Consistency

**সঠিক উত্তর: A) Isolation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Concurrent transaction intermediate effect থেকে পরস্পরকে নির্দিষ্ট degree-এ পৃথক রাখে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Transaction` বলতে Database state-এ logical unit হিসেবে execute হওয়া read/write operation sequence। বোঝায়; প্রশ্নের বর্ণনা `Isolation`-এর।
- **C option কেন ভুল:** `Atomicity` বলতে Transaction-এর সব effect হবে অথবা কোনো effect থাকবে না। বোঝায়; প্রশ্নের বর্ণনা `Isolation`-এর।
- **D option কেন ভুল:** `Consistency` বলতে Transaction database-কে এক valid state থেকে অন্য valid state-এ নেয়, constraint বজায়। বোঝায়; প্রশ্নের বর্ণনা `Isolation`-এর।
- **Related Concept:** Serializable ideal।
- **মনে রাখার টিপস:** Appears separated।

---

## প্রশ্ন 915 | Topic: Database Management System > Transaction Basics | Difficulty: Hard | Type: Tracing

Q. Transaction commit-এর পরে power failure; restart-এ change আছে। কোন property?

A) Atomicity
B) Durability
C) Isolation
D) Serializability

**সঠিক উত্তর: B) Durability**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Committed change failure survive করেছে।

#### Step-by-step সমাধান

```text
Commit acknowledged
Power loss
Recovery
Change remains -> durability
```
- **A option কেন ভুল:** All-or-nothing নয়, persistence focus।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Concurrent visibility নয়।
- **D option কেন ভুল:** Schedule equivalence নয়।
- **Related Concept:** Commit acknowledgment durability contract।
- **মনে রাখার টিপস:** Commit survives crash।

---

## প্রশ্ন 916 | Topic: Database Management System > Transaction Basics | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Transaction effect স্থায়ী করার successful end operation।`—এখানে কোন concept প্রযোজ্য?

A) COMMIT
B) Autocommit
C) Durability
D) Transaction

**সঠিক উত্তর: A) COMMIT**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Transaction effect স্থায়ী করার successful end operation।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Autocommit` বলতে প্রতিটি statement আলাদা transaction হিসেবে automatic commit হওয়ার mode। বোঝায়; প্রশ্নের বর্ণনা `COMMIT`-এর।
- **C option কেন ভুল:** `Durability` বলতে Commit success-এর পরে failure হলেও effect টিকে থাকে। বোঝায়; প্রশ্নের বর্ণনা `COMMIT`-এর।
- **D option কেন ভুল:** `Transaction` বলতে Database state-এ logical unit হিসেবে execute হওয়া read/write operation sequence। বোঝায়; প্রশ্নের বর্ণনা `COMMIT`-এর।
- **Related Concept:** Durability point।
- **মনে রাখার টিপস:** Accept changes।

---

## প্রশ্ন 917 | Topic: Database Management System > Transaction Basics | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Transaction-এর uncommitted change undo করে পূর্ব state-এ ফেরানো।`

A) Atomicity
B) Durability
C) Autocommit
D) ROLLBACK

**সঠিক উত্তর: D) ROLLBACK**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Transaction-এর uncommitted change undo করে পূর্ব state-এ ফেরানো।
- **A option কেন ভুল:** `Atomicity` বলতে Transaction-এর সব effect হবে অথবা কোনো effect থাকবে না। বোঝায়; প্রশ্নের বর্ণনা `ROLLBACK`-এর।
- **B option কেন ভুল:** `Durability` বলতে Commit success-এর পরে failure হলেও effect টিকে থাকে। বোঝায়; প্রশ্নের বর্ণনা `ROLLBACK`-এর।
- **C option কেন ভুল:** `Autocommit` বলতে প্রতিটি statement আলাদা transaction হিসেবে automatic commit হওয়ার mode। বোঝায়; প্রশ্নের বর্ণনা `ROLLBACK`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Savepoint পর্যন্তও হতে পারে।
- **মনে রাখার টিপস:** Cancel changes।

---

## প্রশ্ন 918 | Topic: Database Management System > Transaction Basics | Difficulty: Medium | Type: Theory

Q. `Savepoint` সম্পর্কে কোন statement সঠিক?

A) Database state-এ logical unit হিসেবে execute হওয়া read/write operation sequence।
B) প্রতিটি statement আলাদা transaction হিসেবে automatic commit হওয়ার mode।
C) Transaction-এর ভিতরের named partial rollback point।
D) Transaction-এর সব effect হবে অথবা কোনো effect থাকবে না।

**সঠিক উত্তর: C) Transaction-এর ভিতরের named partial rollback point।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Transaction-এর ভিতরের named partial rollback point।
- **A option কেন ভুল:** এই statementটি `Transaction` ধারণাকে বর্ণনা করে; `Savepoint`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Autocommit` ধারণাকে বর্ণনা করে; `Savepoint`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Atomicity` ধারণাকে বর্ণনা করে; `Savepoint`-কে নয়।
- **Related Concept:** Entire transaction abort ছাড়াই ফিরে যাওয়া।
- **মনে রাখার টিপস:** Checkpoint within transaction।

---

## প্রশ্ন 919 | Topic: Database Management System > Transaction Basics | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `প্রতিটি statement আলাদা transaction হিসেবে automatic commit হওয়ার mode।`—এখানে কোন concept প্রযোজ্য?

A) COMMIT
B) Transaction Log
C) Autocommit
D) Savepoint

**সঠিক উত্তর: C) Autocommit**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি statement আলাদা transaction হিসেবে automatic commit হওয়ার mode।
- **A option কেন ভুল:** `COMMIT` বলতে Transaction effect স্থায়ী করার successful end operation। বোঝায়; প্রশ্নের বর্ণনা `Autocommit`-এর।
- **B option কেন ভুল:** `Transaction Log` বলতে Change ও transaction state sequential record করে recovery support। বোঝায়; প্রশ্নের বর্ণনা `Autocommit`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Savepoint` বলতে Transaction-এর ভিতরের named partial rollback point। বোঝায়; প্রশ্নের বর্ণনা `Autocommit`-এর।
- **Related Concept:** Multi-statement atomicityে disable/explicit transaction দরকার।
- **মনে রাখার টিপস:** Each statement commits।

---

## প্রশ্ন 920 | Topic: Database Management System > Transaction Basics | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Change ও transaction state sequential record করে recovery support।`

A) Durability
B) Autocommit
C) Transaction Log
D) Savepoint

**সঠিক উত্তর: C) Transaction Log**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Change ও transaction state sequential record করে recovery support।
- **A option কেন ভুল:** `Durability` বলতে Commit success-এর পরে failure হলেও effect টিকে থাকে। বোঝায়; প্রশ্নের বর্ণনা `Transaction Log`-এর।
- **B option কেন ভুল:** `Autocommit` বলতে প্রতিটি statement আলাদা transaction হিসেবে automatic commit হওয়ার mode। বোঝায়; প্রশ্নের বর্ণনা `Transaction Log`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Savepoint` বলতে Transaction-এর ভিতরের named partial rollback point। বোঝায়; প্রশ্নের বর্ণনা `Transaction Log`-এর।
- **Related Concept:** WAL ব্যবহৃত।
- **মনে রাখার টিপস:** History for recovery।

---


# Chapter Theory 82: Schedules এবং Serializability

## বিস্তারিত Theory Note

Concurrency correctness শুধু final value নয়; read-from dependency ও commit orderও গুরুত্বপূর্ণ। Conflict graph transaction order constraint capture করে; acyclic হলে topological order serial equivalent।

Recoverable < Cascadeless < Strict—সাধারণভাবে শক্তি বাড়ে। Strict schedule undo/redo ও cascading abort handling সহজ করে।

## মূল ধারণার মানচিত্র

- **Schedule:** একাধিক transaction-এর operation order, প্রতিটি transaction-এর internal order বজায় রেখে।
- **Serial Schedule:** এক transaction সম্পূর্ণ, তারপর অন্য; interleaving নেই।
- **Serializable Schedule:** Interleaved হলেও কোনো serial schedule-এর সমতুল্য effect।
- **Conflict:** Different transaction-এর same item operation এবং অন্তত একটি write।
- **Conflict Serializability:** Nonconflicting operation swap করে serial schedule-এ রূপান্তরযোগ্য।
- **Precedence Graph:** Transaction node; conflict order অনুযায়ী directed edge।
- **Recoverable Schedule:** Tj যদি Ti-এর value পড়ে, Tj commit করার আগে Ti commit করে।
- **Cascadeless Schedule:** Transaction শুধু committed transaction-এর written value পড়ে।
- **Strict Schedule:** Written item writer commit/abort না করা পর্যন্ত অন্য transaction read/write করে না।
- **View Serializability:** Read-from relation ও final write preserve করে serial equivalence; conflict serializability-এর চেয়ে broader।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Schedules এবং Serializability

## প্রশ্ন 921 | Topic: Database Management System > Transaction Schedules | Difficulty: Medium | Type: Tracing

Q. T1-এর `R1(X),W1(X)` সম্পূর্ণ হওয়ার পরে T2-এর `R2(X),W2(X)`—এটি কী schedule?

A) Serial
B) Nonserial only
C) Deadlocked
D) Unrecoverable

**সঠিক উত্তর: A) Serial**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Transaction operation interleave হয়নি।

#### Step-by-step সমাধান

```text
R1(X)
W1(X)
-- T1 ends --
R2(X)
W2(X)
No interleaving
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Interleaving নেই।
- **C option কেন ভুল:** Wait cycle নেই।
- **D option কেন ভুল:** Read dependency committed status তথ্য নেই।
- **Related Concept:** Serial order T1→T2।
- **মনে রাখার টিপস:** এক transaction শেষ, তারপর অন্য।

---

## প্রশ্ন 922 | Topic: Database Management System > Transaction Schedules | Difficulty: Medium | Type: Theory

Q. `Serial Schedule` সম্পর্কে কোন statement সঠিক?

A) Transaction node; conflict order অনুযায়ী directed edge।
B) Different transaction-এর same item operation এবং অন্তত একটি write।
C) এক transaction সম্পূর্ণ, তারপর অন্য; interleaving নেই।
D) Transaction শুধু committed transaction-এর written value পড়ে।

**সঠিক উত্তর: C) এক transaction সম্পূর্ণ, তারপর অন্য; interleaving নেই।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** এক transaction সম্পূর্ণ, তারপর অন্য; interleaving নেই।
- **A option কেন ভুল:** এই statementটি `Precedence Graph` ধারণাকে বর্ণনা করে; `Serial Schedule`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Conflict` ধারণাকে বর্ণনা করে; `Serial Schedule`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Cascadeless Schedule` ধারণাকে বর্ণনা করে; `Serial Schedule`-কে নয়।
- **Related Concept:** Correct কিন্তু concurrency কম।
- **মনে রাখার টিপস:** One transaction at a time।

---

## প্রশ্ন 923 | Topic: Database Management System > Transaction Schedules | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Interleaved হলেও কোনো serial schedule-এর সমতুল্য effect।`—এখানে কোন concept প্রযোজ্য?

A) View Serializability
B) Schedule
C) Conflict Serializability
D) Serializable Schedule

**সঠিক উত্তর: D) Serializable Schedule**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Interleaved হলেও কোনো serial schedule-এর সমতুল্য effect।
- **A option কেন ভুল:** `View Serializability` বলতে Read-from relation ও final write preserve করে serial equivalence; conflict serializability-এর চেয়ে broader। বোঝায়; প্রশ্নের বর্ণনা `Serializable Schedule`-এর।
- **B option কেন ভুল:** `Schedule` বলতে একাধিক transaction-এর operation order, প্রতিটি transaction-এর internal order বজায় রেখে। বোঝায়; প্রশ্নের বর্ণনা `Serializable Schedule`-এর।
- **C option কেন ভুল:** `Conflict Serializability` বলতে Nonconflicting operation swap করে serial schedule-এ রূপান্তরযোগ্য। বোঝায়; প্রশ্নের বর্ণনা `Serializable Schedule`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Concurrency correctness goal।
- **মনে রাখার টিপস:** Concurrent but serial-equivalent।

---

## প্রশ্ন 924 | Topic: Database Management System > Transaction Schedules | Difficulty: Hard | Type: Tracing

Q. T1 `R(X)` এবং T2 `R(X)`—এই দুই operation কি conflict?

A) হ্যাঁ, সব same-item operation conflict
B) না, কারণ দুটোই read
C) হ্যাঁ, কারণ transaction আলাদা
D) শুধু X key হলে

**সঠিক উত্তর: B) না, কারণ দুটোই read**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Conflict-এর জন্য অন্তত একটি write দরকার।

#### Step-by-step সমাধান

```text
Same item: yes
Different transactions: yes
At least one write: no
Conflict: no
```
- **A option কেন ভুল:** RR compatible।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Different transaction প্রয়োজন হলেও writeও দরকার।
- **D option কেন ভুল:** Key status irrelevant।
- **Related Concept:** RW,WR,WW conflict; RR নয়।
- **মনে রাখার টিপস:** No write, no conflict।

---

## প্রশ্ন 925 | Topic: Database Management System > Transaction Schedules | Difficulty: Medium | Type: Theory

Q. `Conflict Serializability` সম্পর্কে কোন statement সঠিক?

A) Interleaved হলেও কোনো serial schedule-এর সমতুল্য effect।
B) Different transaction-এর same item operation এবং অন্তত একটি write।
C) এক transaction সম্পূর্ণ, তারপর অন্য; interleaving নেই।
D) Nonconflicting operation swap করে serial schedule-এ রূপান্তরযোগ্য।

**সঠিক উত্তর: D) Nonconflicting operation swap করে serial schedule-এ রূপান্তরযোগ্য।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Nonconflicting operation swap করে serial schedule-এ রূপান্তরযোগ্য।
- **A option কেন ভুল:** এই statementটি `Serializable Schedule` ধারণাকে বর্ণনা করে; `Conflict Serializability`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Conflict` ধারণাকে বর্ণনা করে; `Conflict Serializability`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Serial Schedule` ধারণাকে বর্ণনা করে; `Conflict Serializability`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Precedence graph acyclic test।
- **মনে রাখার টিপস:** Acyclic conflict graph।

---

## প্রশ্ন 926 | Topic: Database Management System > Transaction Schedules | Difficulty: Medium | Type: Tracing

Q. Precedence graph edges `T1→T2`, `T2→T3`, `T3→T1`। Schedule conflict-serializable কি?

A) হ্যাঁ
B) না, cycle আছে
C) শুধু strict হলে
D) Graph incomplete

**সঠিক উত্তর: B) না, cycle আছে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Directed cycle থাকলে কোনো topological serial order নেই।

#### Step-by-step সমাধান

```text
T1 -> T2 -> T3 -> T1
Directed cycle detected
Conflict-serializable = No
```
- **A option কেন ভুল:** Acyclic প্রয়োজন।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Strictness আলাদা property।
- **D option কেন ভুল:** Edges cycle নির্ধারণে যথেষ্ট।
- **Related Concept:** Serial order = graph topological order।
- **মনে রাখার টিপস:** Cycle means no serial order।

---

## প্রশ্ন 927 | Topic: Database Management System > Transaction Schedules | Difficulty: Easy | Type: Tracing

Q. T2, T1-এর uncommitted value পড়ে এবং T1 abort হলে T2-ও rollback। এটিকে কী বলা হয়?

A) Cascading rollback
B) Strict execution
C) Durable commit
D) Blind write

**সঠিক উত্তর: A) Cascading rollback**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Dirty read dependency writer abort-এ reader rollback ঘটিয়েছে।

#### Step-by-step সমাধান

```text
T1 writes X (uncommitted)
T2 reads X
T1 aborts
T2 used invalid value -> rollback
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Strict schedule dirty read allow করে না।
- **C option কেন ভুল:** Commit persistence নয়।
- **D option কেন ভুল:** Prior read ছাড়া write।
- **Related Concept:** Cascadeless schedule dirty read এড়ায়।
- **মনে রাখার টিপস:** One abort triggers others।

---

## প্রশ্ন 928 | Topic: Database Management System > Transaction Schedules | Difficulty: Easy | Type: Theory

Q. `Cascadeless Schedule` সম্পর্কে কোন statement সঠিক?

A) এক transaction সম্পূর্ণ, তারপর অন্য; interleaving নেই।
B) Tj যদি Ti-এর value পড়ে, Tj commit করার আগে Ti commit করে।
C) Transaction শুধু committed transaction-এর written value পড়ে।
D) Nonconflicting operation swap করে serial schedule-এ রূপান্তরযোগ্য।

**সঠিক উত্তর: C) Transaction শুধু committed transaction-এর written value পড়ে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Transaction শুধু committed transaction-এর written value পড়ে।
- **A option কেন ভুল:** এই statementটি `Serial Schedule` ধারণাকে বর্ণনা করে; `Cascadeless Schedule`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Recoverable Schedule` ধারণাকে বর্ণনা করে; `Cascadeless Schedule`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Conflict Serializability` ধারণাকে বর্ণনা করে; `Cascadeless Schedule`-কে নয়।
- **Related Concept:** Cascading rollback এড়ায়।
- **মনে রাখার টিপস:** No dirty reads।

---

## প্রশ্ন 929 | Topic: Database Management System > Transaction Schedules | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `Written item writer commit/abort না করা পর্যন্ত অন্য transaction read/write করে না।`—এখানে কোন concept প্রযোজ্য?

A) Cascadeless Schedule
B) View Serializability
C) Strict Schedule
D) Serializable Schedule

**সঠিক উত্তর: C) Strict Schedule**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Written item writer commit/abort না করা পর্যন্ত অন্য transaction read/write করে না।
- **A option কেন ভুল:** `Cascadeless Schedule` বলতে Transaction শুধু committed transaction-এর written value পড়ে। বোঝায়; প্রশ্নের বর্ণনা `Strict Schedule`-এর।
- **B option কেন ভুল:** `View Serializability` বলতে Read-from relation ও final write preserve করে serial equivalence; conflict serializability-এর চেয়ে broader। বোঝায়; প্রশ্নের বর্ণনা `Strict Schedule`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Serializable Schedule` বলতে Interleaved হলেও কোনো serial schedule-এর সমতুল্য effect। বোঝায়; প্রশ্নের বর্ণনা `Strict Schedule`-এর।
- **Related Concept:** Recovery সহজ।
- **মনে রাখার টিপস:** No access to uncommitted writes।

---

## প্রশ্ন 930 | Topic: Database Management System > Transaction Schedules | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Read-from relation ও final write preserve করে serial equivalence; conflict serializability-এর চেয়ে broader।`

A) View Serializability
B) Strict Schedule
C) Recoverable Schedule
D) Conflict Serializability

**সঠিক উত্তর: A) View Serializability**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Read-from relation ও final write preserve করে serial equivalence; conflict serializability-এর চেয়ে broader।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Strict Schedule` বলতে Written item writer commit/abort না করা পর্যন্ত অন্য transaction read/write করে না। বোঝায়; প্রশ্নের বর্ণনা `View Serializability`-এর।
- **C option কেন ভুল:** `Recoverable Schedule` বলতে Tj যদি Ti-এর value পড়ে, Tj commit করার আগে Ti commit করে। বোঝায়; প্রশ্নের বর্ণনা `View Serializability`-এর।
- **D option কেন ভুল:** `Conflict Serializability` বলতে Nonconflicting operation swap করে serial schedule-এ রূপান্তরযোগ্য। বোঝায়; প্রশ্নের বর্ণনা `View Serializability`-এর।
- **Related Concept:** Test কঠিন।
- **মনে রাখার টিপস:** View-equivalent to serial।

---


# Chapter Theory 83: Locking, 2PL, Timestamp এবং MVCC

## বিস্তারিত Theory Note

Lock compatibility conflict operation serialize করে। 2PL conflict serializability দেয়, কিন্তু deadlock হতে পারে। Strict 2PL uncommitted writes expose হতে দেয় না।

Timestamp ordering waiting-এর বদলে abort/restart করতে পারে। MVCC read-write blocking কমায়, তবে isolation level অনুযায়ী write conflict ও anomaly ভিন্ন।

## মূল ধারণার মানচিত্র

- **Lock:** Transaction-এর data access right coordinate করা concurrency-control state।
- **Shared Lock:** Read access; বহু transaction compatibleভাবে রাখতে পারে।
- **Exclusive Lock:** Read/write exclusive access; অন্য shared/exclusive lock block।
- **Two-Phase Locking:** Growing phase-এ lock acquire, shrinking phase-এ release; release-এর পরে নতুন lock নয়।
- **Strict 2PL:** Exclusive lock transaction commit/abort পর্যন্ত ধরে।
- **Lock Upgrade:** Shared lock থেকে exclusive lock request।
- **Timestamp Ordering:** Transaction timestamp অনুযায়ী read/write order enforce, conflicting late operation abort হতে পারে।
- **Optimistic Concurrency Control:** Read/compute lock কম, commit-এর আগে validation conflict check।
- **MVCC:** একাধিক row version রেখে readerকে snapshot ও writerকে concurrent progress করতে দেয়।
- **Phantom:** এক predicate query পুনরায় চালালে concurrent insert/delete-এর কারণে row set বদলে যায়।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Locking, 2PL, Timestamp এবং MVCC

## প্রশ্ন 931 | Topic: Database Management System > Concurrency Control | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Transaction-এর data access right coordinate করা concurrency-control state।`

A) Lock
B) Strict 2PL
C) Optimistic Concurrency Control
D) Exclusive Lock

**সঠিক উত্তর: A) Lock**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Transaction-এর data access right coordinate করা concurrency-control state।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Strict 2PL` বলতে Exclusive lock transaction commit/abort পর্যন্ত ধরে। বোঝায়; প্রশ্নের বর্ণনা `Lock`-এর।
- **C option কেন ভুল:** `Optimistic Concurrency Control` বলতে Read/compute lock কম, commit-এর আগে validation conflict check। বোঝায়; প্রশ্নের বর্ণনা `Lock`-এর।
- **D option কেন ভুল:** `Exclusive Lock` বলতে Read/write exclusive access; অন্য shared/exclusive lock block। বোঝায়; প্রশ্নের বর্ণনা `Lock`-এর।
- **Related Concept:** Shared ও exclusive lock।
- **মনে রাখার টিপস:** Controlled access token।

---

## প্রশ্ন 932 | Topic: Database Management System > Concurrency Control | Difficulty: Easy | Type: Tracing

Q. T1 ও T2 একই item-এ Shared lock চায়। Compatibility কী?

A) Incompatible
B) Deadlock নিশ্চিত
C) Compatible
D) Only T1 allowed

**সঠিক উত্তর: C) Compatible**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Read-read concurrently allowed।

#### Step-by-step সমাধান

```text
Requested: S by T1, S by T2
Compatibility matrix S/S=Yes
```
- **A option কেন ভুল:** Shared locks coexist।
- **B option কেন ভুল:** No waiting needed।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Multiple readers allowed।
- **Related Concept:** S-S yes; S-X no; X-X no।
- **মনে রাখার টিপস:** Readers share।

---

## প্রশ্ন 933 | Topic: Database Management System > Concurrency Control | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `Read/write exclusive access; অন্য shared/exclusive lock block।`—এখানে কোন concept প্রযোজ্য?

A) Phantom
B) Exclusive Lock
C) Shared Lock
D) Optimistic Concurrency Control

**সঠিক উত্তর: B) Exclusive Lock**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Read/write exclusive access; অন্য shared/exclusive lock block।
- **A option কেন ভুল:** `Phantom` বলতে এক predicate query পুনরায় চালালে concurrent insert/delete-এর কারণে row set বদলে যায়। বোঝায়; প্রশ্নের বর্ণনা `Exclusive Lock`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Shared Lock` বলতে Read access; বহু transaction compatibleভাবে রাখতে পারে। বোঝায়; প্রশ্নের বর্ণনা `Exclusive Lock`-এর।
- **D option কেন ভুল:** `Optimistic Concurrency Control` বলতে Read/compute lock কম, commit-এর আগে validation conflict check। বোঝায়; প্রশ্নের বর্ণনা `Exclusive Lock`-এর।
- **Related Concept:** Writer lock।
- **মনে রাখার টিপস:** Write lock।

---

## প্রশ্ন 934 | Topic: Database Management System > Concurrency Control | Difficulty: Easy | Type: Tracing

Q. 2PL-এ transaction প্রথম lock release করার পরে নতুন lock চাইলে rule কী?

A) Allowed always
B) Only read lock allowed
C) Commit automatically
D) Disallowed; shrinking phase শুরু

**সঠিক উত্তর: D) Disallowed; shrinking phase শুরু**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Shrinking phase-এ নতুন lock acquire করা যায় না।

#### Step-by-step সমাধান

```text
Acquire A, Acquire B -> growing
Release A -> shrinking begins
Request C -> violates 2PL
```
- **A option কেন ভুল:** 2PL ভাঙে।
- **B option কেন ভুল:** কোনো নতুন lock নয়।
- **C option কেন ভুল:** Release commit বাধ্য করে না basic 2PL-এ।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Growing acquire, shrinking release।
- **মনে রাখার টিপস:** First unlock closes acquisition।

---

## প্রশ্ন 935 | Topic: Database Management System > Concurrency Control | Difficulty: Medium | Type: Theory

Q. `Strict 2PL` সম্পর্কে কোন statement সঠিক?

A) Read/compute lock কম, commit-এর আগে validation conflict check।
B) Transaction-এর data access right coordinate করা concurrency-control state।
C) Exclusive lock transaction commit/abort পর্যন্ত ধরে।
D) Read access; বহু transaction compatibleভাবে রাখতে পারে।

**সঠিক উত্তর: C) Exclusive lock transaction commit/abort পর্যন্ত ধরে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Exclusive lock transaction commit/abort পর্যন্ত ধরে।
- **A option কেন ভুল:** এই statementটি `Optimistic Concurrency Control` ধারণাকে বর্ণনা করে; `Strict 2PL`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Lock` ধারণাকে বর্ণনা করে; `Strict 2PL`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Shared Lock` ধারণাকে বর্ণনা করে; `Strict 2PL`-কে নয়।
- **Related Concept:** Strict schedule ও easier recovery।
- **মনে রাখার টিপস:** Write locks until end।

---

## প্রশ্ন 936 | Topic: Database Management System > Concurrency Control | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Shared lock থেকে exclusive lock request।`—এখানে কোন concept প্রযোজ্য?

A) Strict 2PL
B) MVCC
C) Phantom
D) Lock Upgrade

**সঠিক উত্তর: D) Lock Upgrade**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Shared lock থেকে exclusive lock request।
- **A option কেন ভুল:** `Strict 2PL` বলতে Exclusive lock transaction commit/abort পর্যন্ত ধরে। বোঝায়; প্রশ্নের বর্ণনা `Lock Upgrade`-এর।
- **B option কেন ভুল:** `MVCC` বলতে একাধিক row version রেখে readerকে snapshot ও writerকে concurrent progress করতে দেয়। বোঝায়; প্রশ্নের বর্ণনা `Lock Upgrade`-এর।
- **C option কেন ভুল:** `Phantom` বলতে এক predicate query পুনরায় চালালে concurrent insert/delete-এর কারণে row set বদলে যায়। বোঝায়; প্রশ্নের বর্ণনা `Lock Upgrade`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Concurrent upgrader deadlock হতে পারে।
- **মনে রাখার টিপস:** Read to write lock।

---

## প্রশ্ন 937 | Topic: Database Management System > Concurrency Control | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Transaction timestamp অনুযায়ী read/write order enforce, conflicting late operation abort হতে পারে।`

A) Shared Lock
B) Timestamp Ordering
C) Lock
D) Optimistic Concurrency Control

**সঠিক উত্তর: B) Timestamp Ordering**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Transaction timestamp অনুযায়ী read/write order enforce, conflicting late operation abort হতে পারে।
- **A option কেন ভুল:** `Shared Lock` বলতে Read access; বহু transaction compatibleভাবে রাখতে পারে। বোঝায়; প্রশ্নের বর্ণনা `Timestamp Ordering`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Lock` বলতে Transaction-এর data access right coordinate করা concurrency-control state। বোঝায়; প্রশ্নের বর্ণনা `Timestamp Ordering`-এর।
- **D option কেন ভুল:** `Optimistic Concurrency Control` বলতে Read/compute lock কম, commit-এর আগে validation conflict check। বোঝায়; প্রশ্নের বর্ণনা `Timestamp Ordering`-এর।
- **Related Concept:** Deadlock-free basic form।
- **মনে রাখার টিপস:** Order by transaction time।

---

## প্রশ্ন 938 | Topic: Database Management System > Concurrency Control | Difficulty: Medium | Type: Theory

Q. `Optimistic Concurrency Control` সম্পর্কে কোন statement সঠিক?

A) এক predicate query পুনরায় চালালে concurrent insert/delete-এর কারণে row set বদলে যায়।
B) Read/write exclusive access; অন্য shared/exclusive lock block।
C) Transaction timestamp অনুযায়ী read/write order enforce, conflicting late operation abort হতে পারে।
D) Read/compute lock কম, commit-এর আগে validation conflict check।

**সঠিক উত্তর: D) Read/compute lock কম, commit-এর আগে validation conflict check।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Read/compute lock কম, commit-এর আগে validation conflict check।
- **A option কেন ভুল:** এই statementটি `Phantom` ধারণাকে বর্ণনা করে; `Optimistic Concurrency Control`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Exclusive Lock` ধারণাকে বর্ণনা করে; `Optimistic Concurrency Control`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Timestamp Ordering` ধারণাকে বর্ণনা করে; `Optimistic Concurrency Control`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Low contention workload।
- **মনে রাখার টিপস:** Validate before commit।

---

## প্রশ্ন 939 | Topic: Database Management System > Concurrency Control | Difficulty: Medium | Type: Tracing

Q. Snapshot-এ row version v1 পড়ছে; concurrent writer v2 commit করল। MVCC reader সাধারণত কোন version দেখে?

A) v2 বাধ্যতামূলক mid-query
B) দুটির sum
C) কোনোটিই নয়
D) v1 snapshot version

**সঠিক উত্তর: D) v1 snapshot version**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Snapshot isolation reader-এর consistent older version বজায় রাখে।

#### Step-by-step সমাধান

```text
Reader snapshot time=t1 -> v1 visible
Writer commits v2 at t2>t1
Reader continues using v1
```
- **A option কেন ভুল:** Statement/transaction snapshot policy ভাঙে।
- **B option কেন ভুল:** Version combine হয় না।
- **C option কেন ভুল:** v1 retained।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Old version cleanup active snapshot শেষের পরে।
- **মনে রাখার টিপস:** Reader sees its snapshot।

---

## প্রশ্ন 940 | Topic: Database Management System > Concurrency Control | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`এক predicate query পুনরায় চালালে concurrent insert/delete-এর কারণে row set বদলে যায়।`

A) Shared Lock
B) Phantom
C) Lock
D) Strict 2PL

**সঠিক উত্তর: B) Phantom**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** এক predicate query পুনরায় চালালে concurrent insert/delete-এর কারণে row set বদলে যায়।
- **A option কেন ভুল:** `Shared Lock` বলতে Read access; বহু transaction compatibleভাবে রাখতে পারে। বোঝায়; প্রশ্নের বর্ণনা `Phantom`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Lock` বলতে Transaction-এর data access right coordinate করা concurrency-control state। বোঝায়; প্রশ্নের বর্ণনা `Phantom`-এর।
- **D option কেন ভুল:** `Strict 2PL` বলতে Exclusive lock transaction commit/abort পর্যন্ত ধরে। বোঝায়; প্রশ্নের বর্ণনা `Phantom`-এর।
- **Related Concept:** Range/predicate lock বা serializable isolation।
- **মনে রাখার টিপস:** New matching rows appear।

---


# Chapter Theory 84: Logging, Checkpoint এবং Recovery

## বিস্তারিত Theory Note

WAL logকে data page-এর আগে durable করে। Buffer policy recovery requirement নির্ধারণ করে: steal থাকলে undo, no-force থাকলে redo।

Checkpoint পুরো log মুছে না; recovery-তে relevant starting state দেয়। ARIES analysis-এ active/dirty state, redo-তে history repeat এবং undo-তে loser transaction reverse করে।

## মূল ধারণার মানচিত্র

- **Write-Ahead Logging:** Data page disk-এ লেখার আগে সংশ্লিষ্ট log record stable storage-এ লেখা।
- **Undo:** Uncommitted transaction-এর change previous value দিয়ে বাতিল।
- **Redo:** Committed transaction-এর durable হওয়া উচিত change পুনরায় প্রয়োগ।
- **Checkpoint:** Recovery scan starting point কমাতে transaction/log state record ও page coordination।
- **Immediate Update:** Commit-এর আগে data page disk-এ যেতে পারে; undo ও redo লাগতে পারে।
- **Deferred Update:** Commit-এর আগে database page update disk-এ না দেওয়া policy; সাধারণত redo, undo নয়।
- **Steal Policy:** Buffer manager uncommitted change-সহ page evict করতে পারে।
- **No-force Policy:** Commit-এ সব modified page disk-এ force করা হয় না।
- **ARIES:** Analysis, Redo, Undo phasesসহ WAL-based recovery algorithm family।
- **Log Sequence Number:** Log record ordering ও pageLSN coordination identifier।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Logging, Checkpoint এবং Recovery

## প্রশ্ন 941 | Topic: Database Management System > Recovery | Difficulty: Hard | Type: Tracing

Q. Data page update disk-এ যাওয়ার আগে log stable storage-এ force করা হলো। এটি কোন rule?

A) 2PL
B) WAL
C) Normalization
D) CORS

**সঠিক উত্তর: B) WAL**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Write-Ahead Logging log-first ordering চায়।

#### Step-by-step সমাধান

```text
1. Create log record
2. Flush log to stable storage
3. Data page may be written
```
- **A option কেন ভুল:** Lock phases।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Schema design।
- **D option কেন ভুল:** Web policy।
- **Related Concept:** Crash-এ undo information আগে durable থাকতে হয়।
- **মনে রাখার টিপস:** Log before data।

---

## প্রশ্ন 942 | Topic: Database Management System > Recovery | Difficulty: Medium | Type: Theory

Q. `Undo` সম্পর্কে কোন statement সঠিক?

A) Commit-এর আগে data page disk-এ যেতে পারে; undo ও redo লাগতে পারে।
B) Uncommitted transaction-এর change previous value দিয়ে বাতিল।
C) Committed transaction-এর durable হওয়া উচিত change পুনরায় প্রয়োগ।
D) Data page disk-এ লেখার আগে সংশ্লিষ্ট log record stable storage-এ লেখা।

**সঠিক উত্তর: B) Uncommitted transaction-এর change previous value দিয়ে বাতিল।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Uncommitted transaction-এর change previous value দিয়ে বাতিল।
- **A option কেন ভুল:** এই statementটি `Immediate Update` ধারণাকে বর্ণনা করে; `Undo`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `Redo` ধারণাকে বর্ণনা করে; `Undo`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Write-Ahead Logging` ধারণাকে বর্ণনা করে; `Undo`-কে নয়।
- **Related Concept:** Before-image প্রয়োজন।
- **মনে রাখার টিপস:** Remove incomplete effects।

---

## প্রশ্ন 943 | Topic: Database Management System > Recovery | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `Committed transaction-এর durable হওয়া উচিত change পুনরায় প্রয়োগ।`—এখানে কোন concept প্রযোজ্য?

A) Write-Ahead Logging
B) Undo
C) Redo
D) Checkpoint

**সঠিক উত্তর: C) Redo**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Committed transaction-এর durable হওয়া উচিত change পুনরায় প্রয়োগ।
- **A option কেন ভুল:** `Write-Ahead Logging` বলতে Data page disk-এ লেখার আগে সংশ্লিষ্ট log record stable storage-এ লেখা। বোঝায়; প্রশ্নের বর্ণনা `Redo`-এর।
- **B option কেন ভুল:** `Undo` বলতে Uncommitted transaction-এর change previous value দিয়ে বাতিল। বোঝায়; প্রশ্নের বর্ণনা `Redo`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Checkpoint` বলতে Recovery scan starting point কমাতে transaction/log state record ও page coordination। বোঝায়; প্রশ্নের বর্ণনা `Redo`-এর।
- **Related Concept:** After-image প্রয়োজন।
- **মনে রাখার টিপস:** Reapply committed effects।

---

## প্রশ্ন 944 | Topic: Database Management System > Recovery | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Recovery scan starting point কমাতে transaction/log state record ও page coordination।`

A) Deferred Update
B) Immediate Update
C) Undo
D) Checkpoint

**সঠিক উত্তর: D) Checkpoint**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Recovery scan starting point কমাতে transaction/log state record ও page coordination।
- **A option কেন ভুল:** `Deferred Update` বলতে Commit-এর আগে database page update disk-এ না দেওয়া policy; সাধারণত redo, undo নয়। বোঝায়; প্রশ্নের বর্ণনা `Checkpoint`-এর।
- **B option কেন ভুল:** `Immediate Update` বলতে Commit-এর আগে data page disk-এ যেতে পারে; undo ও redo লাগতে পারে। বোঝায়; প্রশ্নের বর্ণনা `Checkpoint`-এর।
- **C option কেন ভুল:** `Undo` বলতে Uncommitted transaction-এর change previous value দিয়ে বাতিল। বোঝায়; প্রশ্নের বর্ণনা `Checkpoint`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Crash recovery দ্রুত।
- **মনে রাখার টিপস:** Recovery landmark।

---

## প্রশ্ন 945 | Topic: Database Management System > Recovery | Difficulty: Hard | Type: Theory

Q. `Immediate Update` সম্পর্কে কোন statement সঠিক?

A) Data page disk-এ লেখার আগে সংশ্লিষ্ট log record stable storage-এ লেখা।
B) Committed transaction-এর durable হওয়া উচিত change পুনরায় প্রয়োগ।
C) Commit-এর আগে data page disk-এ যেতে পারে; undo ও redo লাগতে পারে।
D) Analysis, Redo, Undo phasesসহ WAL-based recovery algorithm family।

**সঠিক উত্তর: C) Commit-এর আগে data page disk-এ যেতে পারে; undo ও redo লাগতে পারে।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Commit-এর আগে data page disk-এ যেতে পারে; undo ও redo লাগতে পারে।
- **A option কেন ভুল:** এই statementটি `Write-Ahead Logging` ধারণাকে বর্ণনা করে; `Immediate Update`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Redo` ধারণাকে বর্ণনা করে; `Immediate Update`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `ARIES` ধারণাকে বর্ণনা করে; `Immediate Update`-কে নয়।
- **Related Concept:** WAL অপরিহার্য।
- **মনে রাখার টিপস:** Uncommitted pages may reach disk।

---

## প্রশ্ন 946 | Topic: Database Management System > Recovery | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `Commit-এর আগে database page update disk-এ না দেওয়া policy; সাধারণত redo, undo নয়।`—এখানে কোন concept প্রযোজ্য?

A) Undo
B) Deferred Update
C) ARIES
D) Immediate Update

**সঠিক উত্তর: B) Deferred Update**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Commit-এর আগে database page update disk-এ না দেওয়া policy; সাধারণত redo, undo নয়।
- **A option কেন ভুল:** `Undo` বলতে Uncommitted transaction-এর change previous value দিয়ে বাতিল। বোঝায়; প্রশ্নের বর্ণনা `Deferred Update`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `ARIES` বলতে Analysis, Redo, Undo phasesসহ WAL-based recovery algorithm family। বোঝায়; প্রশ্নের বর্ণনা `Deferred Update`-এর।
- **D option কেন ভুল:** `Immediate Update` বলতে Commit-এর আগে data page disk-এ যেতে পারে; undo ও redo লাগতে পারে। বোঝায়; প্রশ্নের বর্ণনা `Deferred Update`-এর।
- **Related Concept:** No-steal conceptual model।
- **মনে রাখার টিপস:** Apply after commit।

---

## প্রশ্ন 947 | Topic: Database Management System > Recovery | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Buffer manager uncommitted change-সহ page evict করতে পারে।`

A) Steal Policy
B) Write-Ahead Logging
C) No-force Policy
D) ARIES

**সঠিক উত্তর: A) Steal Policy**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Buffer manager uncommitted change-সহ page evict করতে পারে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Write-Ahead Logging` বলতে Data page disk-এ লেখার আগে সংশ্লিষ্ট log record stable storage-এ লেখা। বোঝায়; প্রশ্নের বর্ণনা `Steal Policy`-এর।
- **C option কেন ভুল:** `No-force Policy` বলতে Commit-এ সব modified page disk-এ force করা হয় না। বোঝায়; প্রশ্নের বর্ণনা `Steal Policy`-এর।
- **D option কেন ভুল:** `ARIES` বলতে Analysis, Redo, Undo phasesসহ WAL-based recovery algorithm family। বোঝায়; প্রশ্নের বর্ণনা `Steal Policy`-এর।
- **Related Concept:** Undo প্রয়োজন।
- **মনে রাখার টিপস:** Can write uncommitted page।

---

## প্রশ্ন 948 | Topic: Database Management System > Recovery | Difficulty: Medium | Type: Tracing

Q. No-force system-এ commit-এর সময় dirty page disk-এ না গেলে crash recovery-তে কী দরকার?

A) Undo only
B) Redo
C) No log
D) Deadlock detection

**সঠিক উত্তর: B) Redo**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Committed effect data page-এ না-ও থাকতে পারে; log থেকে redo।

#### Step-by-step সমাধান

```text
Transaction commits
Dirty page remains buffer
Crash loses buffer
Redo committed log change
```
- **A option কেন ভুল:** Uncommitted disk page steal concern।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Durability নিশ্চিত নয়।
- **D option কেন ভুল:** Concurrency concern।
- **Related Concept:** No-force → Redo; Steal → Undo।
- **মনে রাখার টিপস:** Committed but not flushed means redo।

---

## প্রশ্ন 949 | Topic: Database Management System > Recovery | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Analysis, Redo, Undo phasesসহ WAL-based recovery algorithm family।`—এখানে কোন concept প্রযোজ্য?

A) Redo
B) ARIES
C) Write-Ahead Logging
D) Checkpoint

**সঠিক উত্তর: B) ARIES**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Analysis, Redo, Undo phasesসহ WAL-based recovery algorithm family।
- **A option কেন ভুল:** `Redo` বলতে Committed transaction-এর durable হওয়া উচিত change পুনরায় প্রয়োগ। বোঝায়; প্রশ্নের বর্ণনা `ARIES`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Write-Ahead Logging` বলতে Data page disk-এ লেখার আগে সংশ্লিষ্ট log record stable storage-এ লেখা। বোঝায়; প্রশ্নের বর্ণনা `ARIES`-এর।
- **D option কেন ভুল:** `Checkpoint` বলতে Recovery scan starting point কমাতে transaction/log state record ও page coordination। বোঝায়; প্রশ্নের বর্ণনা `ARIES`-এর।
- **Related Concept:** Repeat history approach।
- **মনে রাখার টিপস:** Industrial recovery method।

---

## প্রশ্ন 950 | Topic: Database Management System > Recovery | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Log record ordering ও pageLSN coordination identifier।`

A) Log Sequence Number
B) Deferred Update
C) Redo
D) Checkpoint

**সঠিক উত্তর: A) Log Sequence Number**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Log record ordering ও pageLSN coordination identifier।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Deferred Update` বলতে Commit-এর আগে database page update disk-এ না দেওয়া policy; সাধারণত redo, undo নয়। বোঝায়; প্রশ্নের বর্ণনা `Log Sequence Number`-এর।
- **C option কেন ভুল:** `Redo` বলতে Committed transaction-এর durable হওয়া উচিত change পুনরায় প্রয়োগ। বোঝায়; প্রশ্নের বর্ণনা `Log Sequence Number`-এর।
- **D option কেন ভুল:** `Checkpoint` বলতে Recovery scan starting point কমাতে transaction/log state record ও page coordination। বোঝায়; প্রশ্নের বর্ণনা `Log Sequence Number`-এর।
- **Related Concept:** Idempotent redo check।
- **মনে রাখার টিপস:** Ordered log position।

---


# Chapter Theory 85: File Organization এবং Database Indexing

## বিস্তারিত Theory Note

File organization base record placement; index auxiliary path। Heap insert-friendly, sorted range-friendly। Dense index entry বেশি; sparse index ordered file block anchor ব্যবহার করে।

B+ Tree dynamic ordered operations; Hash exact equality। Query optimizer selectivity, clustering ও table size দেখে index বনাম scan বেছে নেয়।

## মূল ধারণার মানচিত্র

- **Heap File:** Record কোনো key order ছাড়া available page-এ রাখা file organization।
- **Sorted File:** Search key order-এ record রাখা।
- **Primary Index:** Ordered data file-এর primary/order key-এর ওপর index।
- **Secondary Index:** File physical order ছাড়া অন্য search attribute-এর index।
- **Dense Index:** প্রতি search-key value/record-এর জন্য index entry।
- **Sparse Index:** কিছু search-key/block-এর জন্য entry; ordered data প্রয়োজন।
- **B+ Tree Index:** Balanced multi-level ordered index, equality ও range query support।
- **Hash Index:** Hash function bucket-এ key map; equality query দ্রুত, range দুর্বল।
- **Clustering Factor:** Table row index order-এর সঙ্গে physical page order কতটা মিল—তার measure।
- **Fan-out:** Index internal node-এ child pointer সংখ্যা।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: File Organization এবং Database Indexing

# Batch 21 — Question 951–1000

## প্রশ্ন 951 | Topic: Database Management System > Storage and Indexing | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Record কোনো key order ছাড়া available page-এ রাখা file organization।`

A) Heap File
B) Primary Index
C) Sorted File
D) Dense Index

**সঠিক উত্তর: A) Heap File**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Record কোনো key order ছাড়া available page-এ রাখা file organization।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Primary Index` বলতে Ordered data file-এর primary/order key-এর ওপর index। বোঝায়; প্রশ্নের বর্ণনা `Heap File`-এর।
- **C option কেন ভুল:** `Sorted File` বলতে Search key order-এ record রাখা। বোঝায়; প্রশ্নের বর্ণনা `Heap File`-এর।
- **D option কেন ভুল:** `Dense Index` বলতে প্রতি search-key value/record-এর জন্য index entry। বোঝায়; প্রশ্নের বর্ণনা `Heap File`-এর।
- **Related Concept:** Insert দ্রুত, search scan হতে পারে।
- **মনে রাখার টিপস:** Unordered records।

---

## প্রশ্ন 952 | Topic: Database Management System > Storage and Indexing | Difficulty: Hard | Type: Theory

Q. `Sorted File` সম্পর্কে কোন statement সঠিক?

A) Hash function bucket-এ key map; equality query দ্রুত, range দুর্বল।
B) Search key order-এ record রাখা।
C) Ordered data file-এর primary/order key-এর ওপর index।
D) Table row index order-এর সঙ্গে physical page order কতটা মিল—তার measure।

**সঠিক উত্তর: B) Search key order-এ record রাখা।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Search key order-এ record রাখা।
- **A option কেন ভুল:** এই statementটি `Hash Index` ধারণাকে বর্ণনা করে; `Sorted File`-কে নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এই statementটি `Primary Index` ধারণাকে বর্ণনা করে; `Sorted File`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Clustering Factor` ধারণাকে বর্ণনা করে; `Sorted File`-কে নয়।
- **Related Concept:** Range read ভালো, insert expensive।
- **মনে রাখার টিপস:** Physically ordered।

---

## প্রশ্ন 953 | Topic: Database Management System > Storage and Indexing | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `Ordered data file-এর primary/order key-এর ওপর index।`—এখানে কোন concept প্রযোজ্য?

A) Dense Index
B) Primary Index
C) Hash Index
D) Secondary Index

**সঠিক উত্তর: B) Primary Index**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Ordered data file-এর primary/order key-এর ওপর index।
- **A option কেন ভুল:** `Dense Index` বলতে প্রতি search-key value/record-এর জন্য index entry। বোঝায়; প্রশ্নের বর্ণনা `Primary Index`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Hash Index` বলতে Hash function bucket-এ key map; equality query দ্রুত, range দুর্বল। বোঝায়; প্রশ্নের বর্ণনা `Primary Index`-এর।
- **D option কেন ভুল:** `Secondary Index` বলতে File physical order ছাড়া অন্য search attribute-এর index। বোঝায়; প্রশ্নের বর্ণনা `Primary Index`-এর।
- **Related Concept:** Sparse হতে পারে।
- **মনে রাখার টিপস:** Index on ordering primary key।

---

## প্রশ্ন 954 | Topic: Database Management System > Storage and Indexing | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`File physical order ছাড়া অন্য search attribute-এর index।`

A) Secondary Index
B) Clustering Factor
C) Dense Index
D) Primary Index

**সঠিক উত্তর: A) Secondary Index**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** File physical order ছাড়া অন্য search attribute-এর index।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Clustering Factor` বলতে Table row index order-এর সঙ্গে physical page order কতটা মিল—তার measure। বোঝায়; প্রশ্নের বর্ণনা `Secondary Index`-এর।
- **C option কেন ভুল:** `Dense Index` বলতে প্রতি search-key value/record-এর জন্য index entry। বোঝায়; প্রশ্নের বর্ণনা `Secondary Index`-এর।
- **D option কেন ভুল:** `Primary Index` বলতে Ordered data file-এর primary/order key-এর ওপর index। বোঝায়; প্রশ্নের বর্ণনা `Secondary Index`-এর।
- **Related Concept:** সাধারণত dense mapping।
- **মনে রাখার টিপস:** Additional access path।

---

## প্রশ্ন 955 | Topic: Database Management System > Storage and Indexing | Difficulty: Medium | Type: Calculation

Q. Dense index-এ 1000 distinct record key থাকলে প্রতি key এক entry ধরে entry count কত?

A) 100
B) 999
C) 2000
D) 1000

**সঠিক উত্তর: D) 1000**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতি key/record এক index entry।

#### Step-by-step সমাধান

```text
Keys=1000
Entries/key=1
Entries=1000
```
- **A option কেন ভুল:** এক দশমাংশ।
- **B option কেন ভুল:** এক কম।
- **C option কেন ভুল:** দ্বিগুণ।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Dense বনাম sparse entry granularity।
- **মনে রাখার টিপস:** Every key means same count।

---

## প্রশ্ন 956 | Topic: Database Management System > Storage and Indexing | Difficulty: Medium | Type: Calculation

Q. Data file 200 block, sparse index প্রতি 10 block-এ এক entry। Index entry কত?

A) 10
B) 100
C) 200
D) 20

**সঠিক উত্তর: D) 20**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 200/10=20।

#### Step-by-step সমাধান

```text
Entries=200/10=20
```
- **A option কেন ভুল:** 20 block interval।
- **B option কেন ভুল:** 2 block interval।
- **C option কেন ভুল:** Dense block entry।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Ceiling দরকার যদি evenly divisible না হয়।
- **মনে রাখার টিপস:** Blocks/interval।

---

## প্রশ্ন 957 | Topic: Database Management System > Storage and Indexing | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Balanced multi-level ordered index, equality ও range query support।`

A) Sorted File
B) Heap File
C) B+ Tree Index
D) Clustering Factor

**সঠিক উত্তর: C) B+ Tree Index**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Balanced multi-level ordered index, equality ও range query support।
- **A option কেন ভুল:** `Sorted File` বলতে Search key order-এ record রাখা। বোঝায়; প্রশ্নের বর্ণনা `B+ Tree Index`-এর।
- **B option কেন ভুল:** `Heap File` বলতে Record কোনো key order ছাড়া available page-এ রাখা file organization। বোঝায়; প্রশ্নের বর্ণনা `B+ Tree Index`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Clustering Factor` বলতে Table row index order-এর সঙ্গে physical page order কতটা মিল—তার measure। বোঝায়; প্রশ্নের বর্ণনা `B+ Tree Index`-এর।
- **Related Concept:** Leaf linked।
- **মনে রাখার টিপস:** Dynamic ordered index।

---

## প্রশ্ন 958 | Topic: Database Management System > Storage and Indexing | Difficulty: Easy | Type: Theory

Q. `Hash Index` সম্পর্কে কোন statement সঠিক?

A) Balanced multi-level ordered index, equality ও range query support।
B) কিছু search-key/block-এর জন্য entry; ordered data প্রয়োজন।
C) Hash function bucket-এ key map; equality query দ্রুত, range দুর্বল।
D) প্রতি search-key value/record-এর জন্য index entry।

**সঠিক উত্তর: C) Hash function bucket-এ key map; equality query দ্রুত, range দুর্বল।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Hash function bucket-এ key map; equality query দ্রুত, range দুর্বল।
- **A option কেন ভুল:** এই statementটি `B+ Tree Index` ধারণাকে বর্ণনা করে; `Hash Index`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Sparse Index` ধারণাকে বর্ণনা করে; `Hash Index`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Dense Index` ধারণাকে বর্ণনা করে; `Hash Index`-কে নয়।
- **Related Concept:** Static/dynamic variants।
- **মনে রাখার টিপস:** Direct bucket lookup।

---

## প্রশ্ন 959 | Topic: Database Management System > Storage and Indexing | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Table row index order-এর সঙ্গে physical page order কতটা মিল—তার measure।`—এখানে কোন concept প্রযোজ্য?

A) Secondary Index
B) Fan-out
C) Clustering Factor
D) Sparse Index

**সঠিক উত্তর: C) Clustering Factor**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Table row index order-এর সঙ্গে physical page order কতটা মিল—তার measure।
- **A option কেন ভুল:** `Secondary Index` বলতে File physical order ছাড়া অন্য search attribute-এর index। বোঝায়; প্রশ্নের বর্ণনা `Clustering Factor`-এর।
- **B option কেন ভুল:** `Fan-out` বলতে Index internal node-এ child pointer সংখ্যা। বোঝায়; প্রশ্নের বর্ণনা `Clustering Factor`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Sparse Index` বলতে কিছু search-key/block-এর জন্য entry; ordered data প্রয়োজন। বোঝায়; প্রশ্নের বর্ণনা `Clustering Factor`-এর।
- **Related Concept:** Range I/O estimation।
- **মনে রাখার টিপস:** Physical order correlation।

---

## প্রশ্ন 960 | Topic: Database Management System > Storage and Indexing | Difficulty: Easy | Type: Calculation

Q. B+ Tree fan-out 100 এবং root থেকে 3 child levels পার হয়ে leaf-এ গেলে আনুমানিক maximum indexed leaves order কত?

A) 100
B) 1,000,000
C) 1,000
D) 10,000

**সঠিক উত্তর: B) 1,000,000**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 100³=1,000,000 branching combinations।

#### Step-by-step সমাধান

```text
Fan-out=100
Child levels=3
Capacity scale=100^3=1,000,000
```
- **A option কেন ভুল:** এক level।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** 100? incorrect 10³।
- **D option কেন ভুল:** দুই level 100²।
- **Related Concept:** উচ্চ fan-out height কমায়।
- **মনে রাখার টিপস:** Fan-out^levels।

---


# Chapter Theory 86: Query Optimization এবং Distributed Database

## বিস্তারিত Theory Note

Optimizer relational expressionকে physical plan-এ রূপান্তর করে। Statistics, selectivity, cardinality ও I/O model ভুল হলে chosen plan খারাপ হতে পারে। Filter early ও small intermediate সাধারণ heuristic।

Distributed database-এ fragmentation locality বাড়ায়, replication availability বাড়ায়, কিন্তু distributed commit ও consistency coordination latency/availability trade-off তৈরি করে।

## মূল ধারণার মানচিত্র

- **Query Plan:** SQL execute করার physical operator tree—scan, join, sort, aggregate ইত্যাদি।
- **Cost-based Optimizer:** Statistics ও cost model দিয়ে candidate plan estimate করে cheapest plan নির্বাচন।
- **Selectivity:** Predicate মোট row-এর কত ছোট fraction match করে।
- **Join Order:** Multiple table কোন sequence-এ join হবে; intermediate size-এ বড় প্রভাব।
- **Predicate Pushdown:** Filterকে data source/plan-এর নিচে আগে প্রয়োগ করে intermediate row কমানো।
- **Distributed Database:** Data একাধিক network site-এ logically integratedভাবে managed।
- **Horizontal Fragmentation:** Relation-এর row subset বিভিন্ন site-এ ভাগ।
- **Vertical Fragmentation:** Relation-এর column subset keyসহ ভাগ।
- **Replication:** Data copy বহু site-এ রাখা availability/read locality বাড়ায়, update coordination লাগে।
- **Two-phase Commit:** Distributed transaction-এর participantsকে prepare ও final commit/abort phases-এ atomic decision coordinate।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Query Optimization এবং Distributed Database

## প্রশ্ন 961 | Topic: Database Management System > Query and Distribution | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`SQL execute করার physical operator tree—scan, join, sort, aggregate ইত্যাদি।`

A) Join Order
B) Cost-based Optimizer
C) Vertical Fragmentation
D) Query Plan

**সঠিক উত্তর: D) Query Plan**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** SQL execute করার physical operator tree—scan, join, sort, aggregate ইত্যাদি।
- **A option কেন ভুল:** `Join Order` বলতে Multiple table কোন sequence-এ join হবে; intermediate size-এ বড় প্রভাব। বোঝায়; প্রশ্নের বর্ণনা `Query Plan`-এর।
- **B option কেন ভুল:** `Cost-based Optimizer` বলতে Statistics ও cost model দিয়ে candidate plan estimate করে cheapest plan নির্বাচন। বোঝায়; প্রশ্নের বর্ণনা `Query Plan`-এর।
- **C option কেন ভুল:** `Vertical Fragmentation` বলতে Relation-এর column subset keyসহ ভাগ। বোঝায়; প্রশ্নের বর্ণনা `Query Plan`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Optimizer alternatives compare করে।
- **মনে রাখার টিপস:** Execution strategy।

---

## প্রশ্ন 962 | Topic: Database Management System > Query and Distribution | Difficulty: Hard | Type: Theory

Q. `Cost-based Optimizer` সম্পর্কে কোন statement সঠিক?

A) Statistics ও cost model দিয়ে candidate plan estimate করে cheapest plan নির্বাচন।
B) Data copy বহু site-এ রাখা availability/read locality বাড়ায়, update coordination লাগে।
C) Predicate মোট row-এর কত ছোট fraction match করে।
D) Distributed transaction-এর participantsকে prepare ও final commit/abort phases-এ atomic decision coordinate।

**সঠিক উত্তর: A) Statistics ও cost model দিয়ে candidate plan estimate করে cheapest plan নির্বাচন।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Statistics ও cost model দিয়ে candidate plan estimate করে cheapest plan নির্বাচন।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Replication` ধারণাকে বর্ণনা করে; `Cost-based Optimizer`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Selectivity` ধারণাকে বর্ণনা করে; `Cost-based Optimizer`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Two-phase Commit` ধারণাকে বর্ণনা করে; `Cost-based Optimizer`-কে নয়।
- **Related Concept:** Estimate ভুল হলে poor plan।
- **মনে রাখার টিপস:** Choose estimated cheapest।

---

## প্রশ্ন 963 | Topic: Database Management System > Query and Distribution | Difficulty: Easy | Type: Calculation

Q. 1,000,000 row table-এ predicate 1,000 row match করে। Selectivity fraction কত?

A) 0.001
B) 0.01
C) 0.1
D) 1000

**সঠিক উত্তর: A) 0.001**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 1000/1,000,000=0.001, অর্থাৎ0.1%।

#### Step-by-step সমাধান

```text
Selectivity=1000/1,000,000=0.001
Percent=0.1%
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** 1%।
- **C option কেন ভুল:** 10%।
- **D option কেন ভুল:** Row count, fraction নয়।
- **Related Concept:** Low fraction highly selective।
- **মনে রাখার টিপস:** Matched/total।

---

## প্রশ্ন 964 | Topic: Database Management System > Query and Distribution | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Multiple table কোন sequence-এ join হবে; intermediate size-এ বড় প্রভাব।`

A) Selectivity
B) Horizontal Fragmentation
C) Cost-based Optimizer
D) Join Order

**সঠিক উত্তর: D) Join Order**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Multiple table কোন sequence-এ join হবে; intermediate size-এ বড় প্রভাব।
- **A option কেন ভুল:** `Selectivity` বলতে Predicate মোট row-এর কত ছোট fraction match করে। বোঝায়; প্রশ্নের বর্ণনা `Join Order`-এর।
- **B option কেন ভুল:** `Horizontal Fragmentation` বলতে Relation-এর row subset বিভিন্ন site-এ ভাগ। বোঝায়; প্রশ্নের বর্ণনা `Join Order`-এর।
- **C option কেন ভুল:** `Cost-based Optimizer` বলতে Statistics ও cost model দিয়ে candidate plan estimate করে cheapest plan নির্বাচন। বোঝায়; প্রশ্নের বর্ণনা `Join Order`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Optimizer search space।
- **মনে রাখার টিপস:** Order of combining tables।

---

## প্রশ্ন 965 | Topic: Database Management System > Query and Distribution | Difficulty: Medium | Type: Theory

Q. `Predicate Pushdown` সম্পর্কে কোন statement সঠিক?

A) Filterকে data source/plan-এর নিচে আগে প্রয়োগ করে intermediate row কমানো।
B) SQL execute করার physical operator tree—scan, join, sort, aggregate ইত্যাদি।
C) Data copy বহু site-এ রাখা availability/read locality বাড়ায়, update coordination লাগে।
D) Relation-এর column subset keyসহ ভাগ।

**সঠিক উত্তর: A) Filterকে data source/plan-এর নিচে আগে প্রয়োগ করে intermediate row কমানো।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Filterকে data source/plan-এর নিচে আগে প্রয়োগ করে intermediate row কমানো।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এই statementটি `Query Plan` ধারণাকে বর্ণনা করে; `Predicate Pushdown`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Replication` ধারণাকে বর্ণনা করে; `Predicate Pushdown`-কে নয়।
- **D option কেন ভুল:** এই statementটি `Vertical Fragmentation` ধারণাকে বর্ণনা করে; `Predicate Pushdown`-কে নয়।
- **Related Concept:** Distributed query-তে network কমায়।
- **মনে রাখার টিপস:** Filter early।

---

## প্রশ্ন 966 | Topic: Database Management System > Query and Distribution | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `Data একাধিক network site-এ logically integratedভাবে managed।`—এখানে কোন concept প্রযোজ্য?

A) Horizontal Fragmentation
B) Distributed Database
C) Cost-based Optimizer
D) Query Plan

**সঠিক উত্তর: B) Distributed Database**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Data একাধিক network site-এ logically integratedভাবে managed।
- **A option কেন ভুল:** `Horizontal Fragmentation` বলতে Relation-এর row subset বিভিন্ন site-এ ভাগ। বোঝায়; প্রশ্নের বর্ণনা `Distributed Database`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Cost-based Optimizer` বলতে Statistics ও cost model দিয়ে candidate plan estimate করে cheapest plan নির্বাচন। বোঝায়; প্রশ্নের বর্ণনা `Distributed Database`-এর।
- **D option কেন ভুল:** `Query Plan` বলতে SQL execute করার physical operator tree—scan, join, sort, aggregate ইত্যাদি। বোঝায়; প্রশ্নের বর্ণনা `Distributed Database`-এর।
- **Related Concept:** Fragmentation, replication ও distributed transaction।
- **মনে রাখার টিপস:** One DB across sites।

---

## প্রশ্ন 967 | Topic: Database Management System > Query and Distribution | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Relation-এর row subset বিভিন্ন site-এ ভাগ।`

A) Vertical Fragmentation
B) Horizontal Fragmentation
C) Cost-based Optimizer
D) Replication

**সঠিক উত্তর: B) Horizontal Fragmentation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Relation-এর row subset বিভিন্ন site-এ ভাগ।
- **A option কেন ভুল:** `Vertical Fragmentation` বলতে Relation-এর column subset keyসহ ভাগ। বোঝায়; প্রশ্নের বর্ণনা `Horizontal Fragmentation`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Cost-based Optimizer` বলতে Statistics ও cost model দিয়ে candidate plan estimate করে cheapest plan নির্বাচন। বোঝায়; প্রশ্নের বর্ণনা `Horizontal Fragmentation`-এর।
- **D option কেন ভুল:** `Replication` বলতে Data copy বহু site-এ রাখা availability/read locality বাড়ায়, update coordination লাগে। বোঝায়; প্রশ্নের বর্ণনা `Horizontal Fragmentation`-এর।
- **Related Concept:** Selection-based fragment।
- **মনে রাখার টিপস:** Split rows।

---

## প্রশ্ন 968 | Topic: Database Management System > Query and Distribution | Difficulty: Easy | Type: Theory

Q. `Vertical Fragmentation` সম্পর্কে কোন statement সঠিক?

A) Statistics ও cost model দিয়ে candidate plan estimate করে cheapest plan নির্বাচন।
B) Relation-এর row subset বিভিন্ন site-এ ভাগ।
C) Relation-এর column subset keyসহ ভাগ।
D) Data একাধিক network site-এ logically integratedভাবে managed।

**সঠিক উত্তর: C) Relation-এর column subset keyসহ ভাগ।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Relation-এর column subset keyসহ ভাগ।
- **A option কেন ভুল:** এই statementটি `Cost-based Optimizer` ধারণাকে বর্ণনা করে; `Vertical Fragmentation`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Horizontal Fragmentation` ধারণাকে বর্ণনা করে; `Vertical Fragmentation`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Distributed Database` ধারণাকে বর্ণনা করে; `Vertical Fragmentation`-কে নয়।
- **Related Concept:** Projection-based fragment।
- **মনে রাখার টিপস:** Split columns।

---

## প্রশ্ন 969 | Topic: Database Management System > Query and Distribution | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `Data copy বহু site-এ রাখা availability/read locality বাড়ায়, update coordination লাগে।`—এখানে কোন concept প্রযোজ্য?

A) Replication
B) Two-phase Commit
C) Selectivity
D) Horizontal Fragmentation

**সঠিক উত্তর: A) Replication**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Data copy বহু site-এ রাখা availability/read locality বাড়ায়, update coordination লাগে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Two-phase Commit` বলতে Distributed transaction-এর participantsকে prepare ও final commit/abort phases-এ atomic decision coordinate। বোঝায়; প্রশ্নের বর্ণনা `Replication`-এর।
- **C option কেন ভুল:** `Selectivity` বলতে Predicate মোট row-এর কত ছোট fraction match করে। বোঝায়; প্রশ্নের বর্ণনা `Replication`-এর।
- **D option কেন ভুল:** `Horizontal Fragmentation` বলতে Relation-এর row subset বিভিন্ন site-এ ভাগ। বোঝায়; প্রশ্নের বর্ণনা `Replication`-এর।
- **Related Concept:** Consistency model দরকার।
- **মনে রাখার টিপস:** Multiple copies।

---

## প্রশ্ন 970 | Topic: Database Management System > Query and Distribution | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Distributed transaction-এর participantsকে prepare ও final commit/abort phases-এ atomic decision coordinate।`

A) Predicate Pushdown
B) Horizontal Fragmentation
C) Two-phase Commit
D) Selectivity

**সঠিক উত্তর: C) Two-phase Commit**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Distributed transaction-এর participantsকে prepare ও final commit/abort phases-এ atomic decision coordinate।
- **A option কেন ভুল:** `Predicate Pushdown` বলতে Filterকে data source/plan-এর নিচে আগে প্রয়োগ করে intermediate row কমানো। বোঝায়; প্রশ্নের বর্ণনা `Two-phase Commit`-এর।
- **B option কেন ভুল:** `Horizontal Fragmentation` বলতে Relation-এর row subset বিভিন্ন site-এ ভাগ। বোঝায়; প্রশ্নের বর্ণনা `Two-phase Commit`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Selectivity` বলতে Predicate মোট row-এর কত ছোট fraction match করে। বোঝায়; প্রশ্নের বর্ণনা `Two-phase Commit`-এর।
- **Related Concept:** Blocking risk।
- **মনে রাখার টিপস:** Prepare then decide।

---


# Chapter Theory 87: NoSQL, CAP, Security এবং Administration

## বিস্তারিত Theory Note

NoSQL একক category নয়; workload ও data model অনুযায়ী key-value, document, wide-column ও graph system আলাদা trade-off দেয়। Flexible schema validation-এর প্রয়োজন দূর করে না।

CAP partition scenario-তে consistency/availability choice ব্যাখ্যা করে। Database administration-এ least privilege, audit, encrypted backup, restore drill ও point-in-time recovery গুরুত্বপূর্ণ।

## মূল ধারণার মানচিত্র

- **Key-Value Store:** Opaque value key দ্বারা retrieve করা NoSQL model।
- **Document Database:** JSON-like nested document ও flexible schema storage model।
- **Column-family Store:** Sparse distributed wide-row data column family অনুযায়ী organize।
- **Graph Database:** Vertex ও edge relationship-first storage/query model।
- **CAP Theorem:** Network partition-এর উপস্থিতিতে consistency ও availability দুটো একসঙ্গে সম্পূর্ণ guarantee করা যায় না।
- **Eventual Consistency:** Update বন্ধ থাকলে replicas সময়ের সঙ্গে একই value-তে converge করবে।
- **Role-based Access Control:** Permission role-এ assign, user role membership পায়।
- **SQL GRANT:** User/role-কে database privilege প্রদান।
- **Backup:** Data/log-এর recoverable copy তৈরি।
- **Point-in-time Recovery:** Base backup ও transaction log ব্যবহার করে নির্দিষ্ট সময় পর্যন্ত database restore।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: NoSQL, CAP, Security এবং Administration

## প্রশ্ন 971 | Topic: Database Management System > NoSQL and Administration | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Opaque value key দ্বারা retrieve করা NoSQL model।`

A) Key-Value Store
B) Backup
C) Eventual Consistency
D) Column-family Store

**সঠিক উত্তর: A) Key-Value Store**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Opaque value key দ্বারা retrieve করা NoSQL model।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Backup` বলতে Data/log-এর recoverable copy তৈরি। বোঝায়; প্রশ্নের বর্ণনা `Key-Value Store`-এর।
- **C option কেন ভুল:** `Eventual Consistency` বলতে Update বন্ধ থাকলে replicas সময়ের সঙ্গে একই value-তে converge করবে। বোঝায়; প্রশ্নের বর্ণনা `Key-Value Store`-এর।
- **D option কেন ভুল:** `Column-family Store` বলতে Sparse distributed wide-row data column family অনুযায়ী organize। বোঝায়; প্রশ্নের বর্ণনা `Key-Value Store`-এর।
- **Related Concept:** Cache/session workload।
- **মনে রাখার টিপস:** Key maps to value।

---

## প্রশ্ন 972 | Topic: Database Management System > NoSQL and Administration | Difficulty: Easy | Type: Theory

Q. `Document Database` সম্পর্কে কোন statement সঠিক?

A) Data/log-এর recoverable copy তৈরি।
B) User/role-কে database privilege প্রদান।
C) JSON-like nested document ও flexible schema storage model।
D) Network partition-এর উপস্থিতিতে consistency ও availability দুটো একসঙ্গে সম্পূর্ণ guarantee করা যায় না।

**সঠিক উত্তর: C) JSON-like nested document ও flexible schema storage model।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** JSON-like nested document ও flexible schema storage model।
- **A option কেন ভুল:** এই statementটি `Backup` ধারণাকে বর্ণনা করে; `Document Database`-কে নয়।
- **B option কেন ভুল:** এই statementটি `SQL GRANT` ধারণাকে বর্ণনা করে; `Document Database`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `CAP Theorem` ধারণাকে বর্ণনা করে; `Document Database`-কে নয়।
- **Related Concept:** Aggregate-oriented query।
- **মনে রাখার টিপস:** Store documents।

---

## প্রশ্ন 973 | Topic: Database Management System > NoSQL and Administration | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Sparse distributed wide-row data column family অনুযায়ী organize।`—এখানে কোন concept প্রযোজ্য?

A) Graph Database
B) Column-family Store
C) Point-in-time Recovery
D) Document Database

**সঠিক উত্তর: B) Column-family Store**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Sparse distributed wide-row data column family অনুযায়ী organize।
- **A option কেন ভুল:** `Graph Database` বলতে Vertex ও edge relationship-first storage/query model। বোঝায়; প্রশ্নের বর্ণনা `Column-family Store`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Point-in-time Recovery` বলতে Base backup ও transaction log ব্যবহার করে নির্দিষ্ট সময় পর্যন্ত database restore। বোঝায়; প্রশ্নের বর্ণনা `Column-family Store`-এর।
- **D option কেন ভুল:** `Document Database` বলতে JSON-like nested document ও flexible schema storage model। বোঝায়; প্রশ্নের বর্ণনা `Column-family Store`-এর।
- **Related Concept:** Large-scale write workload।
- **মনে রাখার টিপস:** Wide rows by families।

---

## প্রশ্ন 974 | Topic: Database Management System > NoSQL and Administration | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Vertex ও edge relationship-first storage/query model।`

A) Backup
B) Column-family Store
C) Point-in-time Recovery
D) Graph Database

**সঠিক উত্তর: D) Graph Database**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Vertex ও edge relationship-first storage/query model।
- **A option কেন ভুল:** `Backup` বলতে Data/log-এর recoverable copy তৈরি। বোঝায়; প্রশ্নের বর্ণনা `Graph Database`-এর।
- **B option কেন ভুল:** `Column-family Store` বলতে Sparse distributed wide-row data column family অনুযায়ী organize। বোঝায়; প্রশ্নের বর্ণনা `Graph Database`-এর।
- **C option কেন ভুল:** `Point-in-time Recovery` বলতে Base backup ও transaction log ব্যবহার করে নির্দিষ্ট সময় পর্যন্ত database restore। বোঝায়; প্রশ্নের বর্ণনা `Graph Database`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Traversal-heavy data।
- **মনে রাখার টিপস:** Connections are central।

---

## প্রশ্ন 975 | Topic: Database Management System > NoSQL and Administration | Difficulty: Medium | Type: Tracing

Q. Network partition চলাকালে system প্রতিটি side-এ request accept করে, কিন্তু তাৎক্ষণিকভাবে একই latest value guarantee করে না। CAP-এ কোন preference?

A) Consistency over Availability
B) Availability over immediate Consistency
C) No Partition tolerance
D) Only Durability

**সঠিক উত্তর: B) Availability over immediate Consistency**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Partition-এর মধ্যে উভয় side response দিলে availability রাখা হয়েছে; strong consistency শিথিল।

#### Step-by-step সমাধান

```text
Partition exists
Both sides accept requests
Responses continue -> Availability
Same immediate value not guaranteed -> strong Consistency relaxed
```
- **A option কেন ভুল:** তাহলে কোনো side request reject/block করতে পারে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Partition scenario accept করা হয়েছে।
- **D option কেন ভুল:** CAP dimension নয়।
- **Related Concept:** CAP failure-free normal condition নয়, partition scenario trade-off।
- **মনে রাখার টিপস:** Partition + always respond → AP tendency।

---

## প্রশ্ন 976 | Topic: Database Management System > NoSQL and Administration | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Update বন্ধ থাকলে replicas সময়ের সঙ্গে একই value-তে converge করবে।`—এখানে কোন concept প্রযোজ্য?

A) Eventual Consistency
B) Point-in-time Recovery
C) Backup
D) SQL GRANT

**সঠিক উত্তর: A) Eventual Consistency**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Update বন্ধ থাকলে replicas সময়ের সঙ্গে একই value-তে converge করবে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Point-in-time Recovery` বলতে Base backup ও transaction log ব্যবহার করে নির্দিষ্ট সময় পর্যন্ত database restore। বোঝায়; প্রশ্নের বর্ণনা `Eventual Consistency`-এর।
- **C option কেন ভুল:** `Backup` বলতে Data/log-এর recoverable copy তৈরি। বোঝায়; প্রশ্নের বর্ণনা `Eventual Consistency`-এর।
- **D option কেন ভুল:** `SQL GRANT` বলতে User/role-কে database privilege প্রদান। বোঝায়; প্রশ্নের বর্ণনা `Eventual Consistency`-এর।
- **Related Concept:** Immediate consistency নয়।
- **মনে রাখার টিপস:** Converges later।

---

## প্রশ্ন 977 | Topic: Database Management System > NoSQL and Administration | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Permission role-এ assign, user role membership পায়।`

A) SQL GRANT
B) Role-based Access Control
C) CAP Theorem
D) Key-Value Store

**সঠিক উত্তর: B) Role-based Access Control**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Permission role-এ assign, user role membership পায়।
- **A option কেন ভুল:** `SQL GRANT` বলতে User/role-কে database privilege প্রদান। বোঝায়; প্রশ্নের বর্ণনা `Role-based Access Control`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `CAP Theorem` বলতে Network partition-এর উপস্থিতিতে consistency ও availability দুটো একসঙ্গে সম্পূর্ণ guarantee করা যায় না। বোঝায়; প্রশ্নের বর্ণনা `Role-based Access Control`-এর।
- **D option কেন ভুল:** `Key-Value Store` বলতে Opaque value key দ্বারা retrieve করা NoSQL model। বোঝায়; প্রশ্নের বর্ণনা `Role-based Access Control`-এর।
- **Related Concept:** Administration সহজ।
- **মনে রাখার টিপস:** Users get roles।

---

## প্রশ্ন 978 | Topic: Database Management System > NoSQL and Administration | Difficulty: Medium | Type: Theory

Q. `SQL GRANT` সম্পর্কে কোন statement সঠিক?

A) JSON-like nested document ও flexible schema storage model।
B) Data/log-এর recoverable copy তৈরি।
C) Base backup ও transaction log ব্যবহার করে নির্দিষ্ট সময় পর্যন্ত database restore।
D) User/role-কে database privilege প্রদান।

**সঠিক উত্তর: D) User/role-কে database privilege প্রদান।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** User/role-কে database privilege প্রদান।
- **A option কেন ভুল:** এই statementটি `Document Database` ধারণাকে বর্ণনা করে; `SQL GRANT`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Backup` ধারণাকে বর্ণনা করে; `SQL GRANT`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Point-in-time Recovery` ধারণাকে বর্ণনা করে; `SQL GRANT`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Least privilege প্রয়োগ।
- **মনে রাখার টিপস:** Give permission।

---

## প্রশ্ন 979 | Topic: Database Management System > NoSQL and Administration | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Data/log-এর recoverable copy তৈরি।`—এখানে কোন concept প্রযোজ্য?

A) CAP Theorem
B) Point-in-time Recovery
C) Backup
D) Graph Database

**সঠিক উত্তর: C) Backup**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Data/log-এর recoverable copy তৈরি।
- **A option কেন ভুল:** `CAP Theorem` বলতে Network partition-এর উপস্থিতিতে consistency ও availability দুটো একসঙ্গে সম্পূর্ণ guarantee করা যায় না। বোঝায়; প্রশ্নের বর্ণনা `Backup`-এর।
- **B option কেন ভুল:** `Point-in-time Recovery` বলতে Base backup ও transaction log ব্যবহার করে নির্দিষ্ট সময় পর্যন্ত database restore। বোঝায়; প্রশ্নের বর্ণনা `Backup`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Graph Database` বলতে Vertex ও edge relationship-first storage/query model। বোঝায়; প্রশ্নের বর্ণনা `Backup`-এর।
- **Related Concept:** Restore test অপরিহার্য।
- **মনে রাখার টিপস:** Copy for recovery।

---

## প্রশ্ন 980 | Topic: Database Management System > NoSQL and Administration | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Base backup ও transaction log ব্যবহার করে নির্দিষ্ট সময় পর্যন্ত database restore।`

A) Graph Database
B) Column-family Store
C) Role-based Access Control
D) Point-in-time Recovery

**সঠিক উত্তর: D) Point-in-time Recovery**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Base backup ও transaction log ব্যবহার করে নির্দিষ্ট সময় পর্যন্ত database restore।
- **A option কেন ভুল:** `Graph Database` বলতে Vertex ও edge relationship-first storage/query model। বোঝায়; প্রশ্নের বর্ণনা `Point-in-time Recovery`-এর।
- **B option কেন ভুল:** `Column-family Store` বলতে Sparse distributed wide-row data column family অনুযায়ী organize। বোঝায়; প্রশ্নের বর্ণনা `Point-in-time Recovery`-এর।
- **C option কেন ভুল:** `Role-based Access Control` বলতে Permission role-এ assign, user role membership পায়। বোঝায়; প্রশ্নের বর্ণনা `Point-in-time Recovery`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** RPO অনুযায়ী।
- **মনে রাখার টিপস:** Restore to chosen moment।

---

# Chapter Theory 88: Networking Fundamentals, OSI এবং Devices

## বিস্তারিত Theory Note

Layering complex communicationকে modular করে। Sender application data নিচের দিকে encapsulate করে; receiver reverse order-এ header process করে। Protocol peer entity-এর rule, service adjacent layer-এর interface।

Hub signal repeat করে, switch frame forward করে, router packet route করে। Device capability implementationভেদে multi-layer হতে পারে, তবে exam-এ primary layer/function ধরতে হয়।

## মূল ধারণার মানচিত্র

- **Computer Network:** দুই বা ততোধিক device communication link ও protocol দিয়ে data/resource exchange করা system।
- **Protocol:** Communication entity-এর message format, order, meaning ও action-এর rule set।
- **OSI Model:** Networking function সাতটি conceptual layer-এ ভাগ করা reference model।
- **TCP/IP Model:** Internet protocol suite-এর practical layered architecture।
- **Encapsulation:** Upper-layer data-তে প্রতিটি lower layer control header/trailer যোগ করে transmission unit তৈরি।
- **Router:** Network-layer address ও routing table ব্যবহার করে ভিন্ন IP network-এর মধ্যে packet forward করে।
- **Switch:** সাধারণ Ethernet LAN-এ MAC address table দিয়ে frame forward করে।
- **Hub:** Physical-layer multiport repeater যা signal সব port-এ ছড়ায়।
- **Gateway:** ভিন্ন protocol/system-এর মধ্যে translation বা application-level interconnection করতে পারে general device/service।
- **NIC:** Device-কে network link-এ যুক্ত করা hardware/interface, MAC address ধারণ করতে পারে।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Networking Fundamentals, OSI এবং Devices

## প্রশ্ন 981 | Topic: Computer Networking > Network Basics | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`দুই বা ততোধিক device communication link ও protocol দিয়ে data/resource exchange করা system।`

A) Computer Network
B) TCP/IP Model
C) Hub
D) Router

**সঠিক উত্তর: A) Computer Network**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** দুই বা ততোধিক device communication link ও protocol দিয়ে data/resource exchange করা system।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `TCP/IP Model` বলতে Internet protocol suite-এর practical layered architecture। বোঝায়; প্রশ্নের বর্ণনা `Computer Network`-এর।
- **C option কেন ভুল:** `Hub` বলতে Physical-layer multiport repeater যা signal সব port-এ ছড়ায়। বোঝায়; প্রশ্নের বর্ণনা `Computer Network`-এর।
- **D option কেন ভুল:** `Router` বলতে Network-layer address ও routing table ব্যবহার করে ভিন্ন IP network-এর মধ্যে packet forward করে। বোঝায়; প্রশ্নের বর্ণনা `Computer Network`-এর।
- **Related Concept:** LAN, WAN ইত্যাদি scope।
- **মনে রাখার টিপস:** Connected devices exchanging data।

---

## প্রশ্ন 982 | Topic: Computer Networking > Network Basics | Difficulty: Hard | Type: Theory

Q. `Protocol` সম্পর্কে কোন statement সঠিক?

A) Device-কে network link-এ যুক্ত করা hardware/interface, MAC address ধারণ করতে পারে।
B) Network-layer address ও routing table ব্যবহার করে ভিন্ন IP network-এর মধ্যে packet forward করে।
C) Communication entity-এর message format, order, meaning ও action-এর rule set।
D) Networking function সাতটি conceptual layer-এ ভাগ করা reference model।

**সঠিক উত্তর: C) Communication entity-এর message format, order, meaning ও action-এর rule set।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Communication entity-এর message format, order, meaning ও action-এর rule set।
- **A option কেন ভুল:** এই statementটি `NIC` ধারণাকে বর্ণনা করে; `Protocol`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Router` ধারণাকে বর্ণনা করে; `Protocol`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `OSI Model` ধারণাকে বর্ণনা করে; `Protocol`-কে নয়।
- **Related Concept:** Syntax, semantics, timing।
- **মনে রাখার টিপস:** Rules of communication।

---

## প্রশ্ন 983 | Topic: Computer Networking > Network Basics | Difficulty: Easy | Type: Calculation

Q. OSI model-এ মোট layer কতটি?

A) 7
B) 4
C) 5
D) 8

**সঠিক উত্তর: A) 7**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** OSI reference model Physical, Data Link, Network, Transport, Session, Presentation ও Application—৭ layer।

#### Step-by-step সমাধান

```text
1 Physical
2 Data Link
3 Network
4 Transport
5 Session
6 Presentation
7 Application
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Simplified TCP/IP model-এর common count।
- **C option কেন ভুল:** Hybrid Internet model count হতে পারে।
- **D option কেন ভুল:** একটি extra layer।
- **Related Concept:** Layer order ও function আলাদা করে পড়ুন।
- **মনে রাখার টিপস:** OSI = 7।

---

## প্রশ্ন 984 | Topic: Computer Networking > Network Basics | Difficulty: Medium | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Internet protocol suite-এর practical layered architecture।`

A) Encapsulation
B) Computer Network
C) Switch
D) TCP/IP Model

**সঠিক উত্তর: D) TCP/IP Model**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Internet protocol suite-এর practical layered architecture।
- **A option কেন ভুল:** `Encapsulation` বলতে Upper-layer data-তে প্রতিটি lower layer control header/trailer যোগ করে transmission unit তৈরি। বোঝায়; প্রশ্নের বর্ণনা `TCP/IP Model`-এর।
- **B option কেন ভুল:** `Computer Network` বলতে দুই বা ততোধিক device communication link ও protocol দিয়ে data/resource exchange করা system। বোঝায়; প্রশ্নের বর্ণনা `TCP/IP Model`-এর।
- **C option কেন ভুল:** `Switch` বলতে সাধারণ Ethernet LAN-এ MAC address table দিয়ে frame forward করে। বোঝায়; প্রশ্নের বর্ণনা `TCP/IP Model`-এর।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Link, Internet, Transport, Application common mapping।
- **মনে রাখার টিপস:** Internet stack।

---

## প্রশ্ন 985 | Topic: Computer Networking > Network Basics | Difficulty: Hard | Type: Calculation

Q. Application data 1000 byte; transport header 20 byte এবং network header 20 byte। Link overhead বাদে IP packet size কত?

A) 1000 byte
B) 1040 byte
C) 1020 byte
D) 2040 byte

**সঠিক উত্তর: B) 1040 byte**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Data+transport header+network header=1000+20+20=1040।

#### Step-by-step সমাধান

```text
Application data=1000
Transport header=20
Network header=20
Packet=1000+20+20=1040 byte
```
- **A option কেন ভুল:** Header বাদ।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** একটি header মাত্র।
- **D option কেন ভুল:** Data দ্বিগুণ।
- **Related Concept:** Encapsulation overhead payload-এর সঙ্গে যোগ হয়।
- **মনে রাখার টিপস:** প্রতি layer header যোগ।

---

## প্রশ্ন 986 | Topic: Computer Networking > Network Basics | Difficulty: Medium | Type: Tracing

Q. Host A network `192.168.1.0/24` এবং Host B `192.168.2.0/24`। তাদের মধ্যে packet forward করতে কোন device প্রয়োজন?

A) Hub
B) Layer-2 repeater
C) Passive splitter
D) Router

**সঠিক উত্তর: D) Router**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** দুটি পৃথক IP network-এর মধ্যে network-layer forwarding দরকার।

#### Step-by-step সমাধান

```text
A subnet=192.168.1.0/24
B subnet=192.168.2.0/24
Subnets differ
Need Layer-3 forwarding
```
- **A option কেন ভুল:** এক LAN signal repeat করে।
- **B option কেন ভুল:** IP subnet route করে না।
- **C option কেন ভুল:** Address-based forwarding নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Default gateway সাধারণত router interface।
- **মনে রাখার টিপস:** Different subnet → Router।

---

## প্রশ্ন 987 | Topic: Computer Networking > Network Basics | Difficulty: Medium | Type: Calculation

Q. এক switch 8টি active port ব্যবহার করছে। প্রতিটি port পৃথক collision domain হলে collision domain কত?

A) 1
B) 4
C) 16
D) 8

**সঠিক উত্তর: D) 8**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Modern switch-এর প্রতিটি port আলাদা collision domain।

#### Step-by-step সমাধান

```text
Active switch ports=8
Domains/port=1
Total=8
```
- **A option কেন ভুল:** Hub-এর মতো shared domain।
- **B option কেন ভুল:** অর্ধেক।
- **C option কেন ভুল:** প্রতি port দুই domain নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** VLAN/broadcast domain আলাদা concept।
- **মনে রাখার টিপস:** One switch port = one collision domain।

---

## প্রশ্ন 988 | Topic: Computer Networking > Network Basics | Difficulty: Hard | Type: Theory

Q. `Hub` সম্পর্কে কোন statement সঠিক?

A) Networking function সাতটি conceptual layer-এ ভাগ করা reference model।
B) Device-কে network link-এ যুক্ত করা hardware/interface, MAC address ধারণ করতে পারে।
C) Physical-layer multiport repeater যা signal সব port-এ ছড়ায়।
D) দুই বা ততোধিক device communication link ও protocol দিয়ে data/resource exchange করা system।

**সঠিক উত্তর: C) Physical-layer multiport repeater যা signal সব port-এ ছড়ায়।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Physical-layer multiport repeater যা signal সব port-এ ছড়ায়।
- **A option কেন ভুল:** এই statementটি `OSI Model` ধারণাকে বর্ণনা করে; `Hub`-কে নয়।
- **B option কেন ভুল:** এই statementটি `NIC` ধারণাকে বর্ণনা করে; `Hub`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Computer Network` ধারণাকে বর্ণনা করে; `Hub`-কে নয়।
- **Related Concept:** Single collision domain, no address learning।
- **মনে রাখার টিপস:** Repeats to all ports।

---

## প্রশ্ন 989 | Topic: Computer Networking > Network Basics | Difficulty: Easy | Type: Theory

Q. একটি system বা scenario-তে `ভিন্ন protocol/system-এর মধ্যে translation বা application-level interconnection করতে পারে general device/service।`—এখানে কোন concept প্রযোজ্য?

A) Router
B) OSI Model
C) Gateway
D) Hub

**সঠিক উত্তর: C) Gateway**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** ভিন্ন protocol/system-এর মধ্যে translation বা application-level interconnection করতে পারে general device/service।
- **A option কেন ভুল:** `Router` বলতে Network-layer address ও routing table ব্যবহার করে ভিন্ন IP network-এর মধ্যে packet forward করে। বোঝায়; প্রশ্নের বর্ণনা `Gateway`-এর।
- **B option কেন ভুল:** `OSI Model` বলতে Networking function সাতটি conceptual layer-এ ভাগ করা reference model। বোঝায়; প্রশ্নের বর্ণনা `Gateway`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Hub` বলতে Physical-layer multiport repeater যা signal সব port-এ ছড়ায়। বোঝায়; প্রশ্নের বর্ণনা `Gateway`-এর।
- **Related Concept:** Default gateway routerও হতে পারে।
- **মনে রাখার টিপস:** Protocol/inter-system bridge।

---

## প্রশ্ন 990 | Topic: Computer Networking > Network Basics | Difficulty: Easy | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Device-কে network link-এ যুক্ত করা hardware/interface, MAC address ধারণ করতে পারে।`

A) TCP/IP Model
B) NIC
C) OSI Model
D) Switch

**সঠিক উত্তর: B) NIC**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Device-কে network link-এ যুক্ত করা hardware/interface, MAC address ধারণ করতে পারে।
- **A option কেন ভুল:** `TCP/IP Model` বলতে Internet protocol suite-এর practical layered architecture। বোঝায়; প্রশ্নের বর্ণনা `NIC`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `OSI Model` বলতে Networking function সাতটি conceptual layer-এ ভাগ করা reference model। বোঝায়; প্রশ্নের বর্ণনা `NIC`-এর।
- **D option কেন ভুল:** `Switch` বলতে সাধারণ Ethernet LAN-এ MAC address table দিয়ে frame forward করে। বোঝায়; প্রশ্নের বর্ণনা `NIC`-এর।
- **Related Concept:** Wired বা wireless।
- **মনে রাখার টিপস:** Network interface।

---


# Chapter Theory 89: Bandwidth, Throughput এবং Delay

## বিস্তারিত Theory Note

Bandwidth capacity; throughput actual achieved rate; goodput application-useful payload rate। Latency component আলাদা করলে bottleneck বোঝা যায়।

Propagation distance/speed নির্ভর, transmission packet size/rate নির্ভর। Queueing traffic-এর সঙ্গে nonlinearভাবে বাড়তে পারে। Duplex mode direction ও simultaneous transmission capability বোঝায়।

## মূল ধারণার মানচিত্র

- **Bandwidth:** Communication channel-এর theoretical capacity বা frequency range; networking-এ প্রায়ই bit/s capacity বোঝায়।
- **Throughput:** বাস্তবে unit time-এ successfully delivered data rate।
- **Latency:** Source থেকে destination-এ data পৌঁছাতে total delay।
- **Propagation Delay:** Signal medium-এর distance অতিক্রম করতে সময়; distance/propagation speed।
- **Transmission Delay:** সব packet bit link-এ push করতে সময়; packet size/data rate।
- **Queueing Delay:** Router/switch buffer-এ service-এর অপেক্ষা।
- **Simplex:** Communication শুধু এক direction-এ।
- **Half-duplex:** দুই direction-এ communication সম্ভব, কিন্তু একই সময়ে নয়।
- **Full-duplex:** দুই direction-এ একই সময়ে communication।
- **Packet Switching:** Data packet-এ ভাগ হয়ে shared network link দিয়ে store-and-forward হতে পারে।

## পরীক্ষায় গুরুত্বপূর্ণ সংযোগ

- Definition, purpose, limitation ও application—চার দিক থেকে concept চিনুন।
- Calculation/Tracing প্রশ্নে Formula → Given Data → Substitution → State Update → Final Answer অনুসরণ করুন।
- কাছাকাছি term-এর পার্থক্য option analysis থেকে পুনরাবৃত্তি করুন।

---

# MCQ Practice: Bandwidth, Throughput এবং Delay

## প্রশ্ন 991 | Topic: Computer Networking > Data Communication Performance | Difficulty: Medium | Type: Calculation

Q. Link capacity 100 Mbps, measured useful throughput 80 Mbps। Utilization কত?

A) 20%
B) 80%
C) 100%
D) 125%

**সঠিক উত্তর: B) 80%**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Throughput/bandwidth×100=80/100×100=80%।

#### Step-by-step সমাধান

```text
Utilization=80/100 x100=80%
```
- **A option কেন ভুল:** Unused fraction।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Measured rate capacity নয়।
- **D option কেন ভুল:** Formula উল্টো।
- **Related Concept:** Protocol overhead থাকায় utilization 100%-এর কম হতে পারে।
- **মনে রাখার টিপস:** Actual ÷ capacity।

---

## প্রশ্ন 992 | Topic: Computer Networking > Data Communication Performance | Difficulty: Medium | Type: Theory

Q. `Throughput` সম্পর্কে কোন statement সঠিক?

A) সব packet bit link-এ push করতে সময়; packet size/data rate।
B) Source থেকে destination-এ data পৌঁছাতে total delay।
C) Signal medium-এর distance অতিক্রম করতে সময়; distance/propagation speed।
D) বাস্তবে unit time-এ successfully delivered data rate।

**সঠিক উত্তর: D) বাস্তবে unit time-এ successfully delivered data rate।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** বাস্তবে unit time-এ successfully delivered data rate।
- **A option কেন ভুল:** এই statementটি `Transmission Delay` ধারণাকে বর্ণনা করে; `Throughput`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Latency` ধারণাকে বর্ণনা করে; `Throughput`-কে নয়।
- **C option কেন ভুল:** এই statementটি `Propagation Delay` ধারণাকে বর্ণনা করে; `Throughput`-কে নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Overhead, congestion ও loss-এ bandwidth-এর কম।
- **মনে রাখার টিপস:** Actual data rate।

---

## প্রশ্ন 993 | Topic: Computer Networking > Data Communication Performance | Difficulty: Medium | Type: Calculation

Q. Propagation delay 5 ms, transmission delay 2 ms, processing 1 ms, queueing 4 ms। One-way latency কত?

A) 7 ms
B) 10 ms
C) 20 ms
D) 12 ms

**সঠিক উত্তর: D) 12 ms**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** সব delay component যোগ:5+2+1+4=12।

#### Step-by-step সমাধান

```text
5+2+1+4=12 ms
```
- **A option কেন ভুল:** Propagation+transmission মাত্র।
- **B option কেন ভুল:** এক component বাদ।
- **C option কেন ভুল:** অতিরিক্ত।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** End-to-end delay component sum।
- **মনে রাখার টিপস:** সব delay যোগ।

---

## প্রশ্ন 994 | Topic: Computer Networking > Data Communication Performance | Difficulty: Medium | Type: Calculation

Q. Distance 2000 km, propagation speed 2×10^8 m/s। Propagation delay কত?

A) 1 ms
B) 10 ms
C) 100 ms
D) 0.1 ms

**সঠিক উত্তর: B) 10 ms**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** 2000 km=2×10^6 m; delay=2×10^6/(2×10^8)=0.01 s=10 ms।

#### Step-by-step সমাধান

```text
Distance=2000 km=2,000,000 m
Speed=200,000,000 m/s
Delay=2,000,000/200,000,000=0.01 s=10 ms
```
- **A option কেন ভুল:** Distance এক order কম।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এক order বেশি।
- **D option কেন ভুল:** দুই order কম।
- **Related Concept:** Distance/speed, unit convert।
- **মনে রাখার টিপস:** km→m এবং s→ms।

---

## প্রশ্ন 995 | Topic: Computer Networking > Data Communication Performance | Difficulty: Medium | Type: Calculation

Q. 1500-byte packet 10 Mbps link-এ transmit করতে কত সময়? 1 byte=8 bit।

A) 1.2 ms
B) 0.12 ms
C) 12 ms
D) 120 ms

**সঠিক উত্তর: A) 1.2 ms**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Bits=12000; 12000/10,000,000 s=0.0012 s=1.2 ms।

#### Step-by-step সমাধান

```text
Packet bits=1500x8=12000
Rate=10,000,000 bit/s
Delay=12000/10,000,000 s
     =0.0012 s
     =1.2 ms
```
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Rate/bit conversionে এক zero ভুল।
- **C option কেন ভুল:** এক order বেশি।
- **D option কেন ভুল:** দুই order বেশি।
- **Related Concept:** Transmission=packet bits/link rate।
- **মনে রাখার টিপস:** Byte×8 আগে।

---

## প্রশ্ন 996 | Topic: Computer Networking > Data Communication Performance | Difficulty: Medium | Type: Theory

Q. একটি system বা scenario-তে `Router/switch buffer-এ service-এর অপেক্ষা।`—এখানে কোন concept প্রযোজ্য?

A) Bandwidth
B) Half-duplex
C) Queueing Delay
D) Full-duplex

**সঠিক উত্তর: C) Queueing Delay**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Router/switch buffer-এ service-এর অপেক্ষা।
- **A option কেন ভুল:** `Bandwidth` বলতে Communication channel-এর theoretical capacity বা frequency range; networking-এ প্রায়ই bit/s capacity বোঝায়। বোঝায়; প্রশ্নের বর্ণনা `Queueing Delay`-এর।
- **B option কেন ভুল:** `Half-duplex` বলতে দুই direction-এ communication সম্ভব, কিন্তু একই সময়ে নয়। বোঝায়; প্রশ্নের বর্ণনা `Queueing Delay`-এর।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** `Full-duplex` বলতে দুই direction-এ একই সময়ে communication। বোঝায়; প্রশ্নের বর্ণনা `Queueing Delay`-এর।
- **Related Concept:** Traffic load অনুযায়ী variable।
- **মনে রাখার টিপস:** Waiting in buffer।

---

## প্রশ্ন 997 | Topic: Computer Networking > Data Communication Performance | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Communication শুধু এক direction-এ।`

A) Full-duplex
B) Simplex
C) Propagation Delay
D) Bandwidth

**সঠিক উত্তর: B) Simplex**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Communication শুধু এক direction-এ।
- **A option কেন ভুল:** `Full-duplex` বলতে দুই direction-এ একই সময়ে communication। বোঝায়; প্রশ্নের বর্ণনা `Simplex`-এর।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** `Propagation Delay` বলতে Signal medium-এর distance অতিক্রম করতে সময়; distance/propagation speed। বোঝায়; প্রশ্নের বর্ণনা `Simplex`-এর।
- **D option কেন ভুল:** `Bandwidth` বলতে Communication channel-এর theoretical capacity বা frequency range; networking-এ প্রায়ই bit/s capacity বোঝায়। বোঝায়; প্রশ্নের বর্ণনা `Simplex`-এর।
- **Related Concept:** Broadcast sensor example।
- **মনে রাখার টিপস:** One-way only।

---

## প্রশ্ন 998 | Topic: Computer Networking > Data Communication Performance | Difficulty: Easy | Type: Theory

Q. `Half-duplex` সম্পর্কে কোন statement সঠিক?

A) সব packet bit link-এ push করতে সময়; packet size/data rate।
B) Communication channel-এর theoretical capacity বা frequency range; networking-এ প্রায়ই bit/s capacity বোঝায়।
C) দুই direction-এ communication সম্ভব, কিন্তু একই সময়ে নয়।
D) Data packet-এ ভাগ হয়ে shared network link দিয়ে store-and-forward হতে পারে।

**সঠিক উত্তর: C) দুই direction-এ communication সম্ভব, কিন্তু একই সময়ে নয়।**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** দুই direction-এ communication সম্ভব, কিন্তু একই সময়ে নয়।
- **A option কেন ভুল:** এই statementটি `Transmission Delay` ধারণাকে বর্ণনা করে; `Half-duplex`-কে নয়।
- **B option কেন ভুল:** এই statementটি `Bandwidth` ধারণাকে বর্ণনা করে; `Half-duplex`-কে নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এই statementটি `Packet Switching` ধারণাকে বর্ণনা করে; `Half-duplex`-কে নয়।
- **Related Concept:** Walkie-talkie।
- **মনে রাখার টিপস:** Both ways, take turns।

---

## প্রশ্ন 999 | Topic: Computer Networking > Data Communication Performance | Difficulty: Hard | Type: Theory

Q. একটি system বা scenario-তে `দুই direction-এ একই সময়ে communication।`—এখানে কোন concept প্রযোজ্য?

A) Full-duplex
B) Bandwidth
C) Propagation Delay
D) Queueing Delay

**সঠিক উত্তর: A) Full-duplex**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** দুই direction-এ একই সময়ে communication।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Bandwidth` বলতে Communication channel-এর theoretical capacity বা frequency range; networking-এ প্রায়ই bit/s capacity বোঝায়। বোঝায়; প্রশ্নের বর্ণনা `Full-duplex`-এর।
- **C option কেন ভুল:** `Propagation Delay` বলতে Signal medium-এর distance অতিক্রম করতে সময়; distance/propagation speed। বোঝায়; প্রশ্নের বর্ণনা `Full-duplex`-এর।
- **D option কেন ভুল:** `Queueing Delay` বলতে Router/switch buffer-এ service-এর অপেক্ষা। বোঝায়; প্রশ্নের বর্ণনা `Full-duplex`-এর।
- **Related Concept:** Switched Ethernet link।
- **মনে রাখার টিপস:** Both ways simultaneously।

---

## প্রশ্ন 1000 | Topic: Computer Networking > Data Communication Performance | Difficulty: Hard | Type: Theory

Q. নিচের বর্ণনাটি কোন ধারণাকে নির্দেশ করে?

`Data packet-এ ভাগ হয়ে shared network link দিয়ে store-and-forward হতে পারে।`

A) Packet Switching
B) Half-duplex
C) Full-duplex
D) Latency

**সঠিক উত্তর: A) Packet Switching**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Data packet-এ ভাগ হয়ে shared network link দিয়ে store-and-forward হতে পারে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** `Half-duplex` বলতে দুই direction-এ communication সম্ভব, কিন্তু একই সময়ে নয়। বোঝায়; প্রশ্নের বর্ণনা `Packet Switching`-এর।
- **C option কেন ভুল:** `Full-duplex` বলতে দুই direction-এ একই সময়ে communication। বোঝায়; প্রশ্নের বর্ণনা `Packet Switching`-এর।
- **D option কেন ভুল:** `Latency` বলতে Source থেকে destination-এ data পৌঁছাতে total delay। বোঝায়; প্রশ্নের বর্ণনা `Packet Switching`-এর।
- **Related Concept:** Internet foundation।
- **মনে রাখার টিপস:** Shared links, packets।

---


# Combined Quality Audit

```text
Numbering continuity          : Passed (501–1000)
Total question count          : Passed (500)
Theory/Calculation target     : Passed (362/138)
Difficulty per 50 questions   : Passed (13/25/12)
Answer balance per 50         : Passed (13/13/12/12)
Plain-text Math alignment     : Passed
Raw LaTeX rendering issue     : Removed
Technical keywords            : Preserved
Chapter Theory before MCQ     : Included
Correct-option explanation    : Included
Wrong-option explanation      : Included
Related concept and memory tip: Included
```

## Remaining Master Bank

```text
Completed through Question 1000
Remaining: Question 1001–1120
Section : Computer Networking
```
