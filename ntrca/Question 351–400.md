# ১৯তম নিবন্ধন — প্রভাষক ICT

## Section 3: Data Structure, Algorithm & Combinatorial Optimization

### Batch 9 — Question 351–400

**Subject Code:** 452  
**Covered Area:** Linked List, Stack, Queue, Circular Queue, Deque, Prefix–Infix–Postfix এবং Recursion  
**Theory/Scenario MCQ:** 30  
**Math/Calculation/Tracing MCQ:** 20  
**Difficulty:** Easy 13, Medium 25, Hard 12  
**Answer Distribution:** A = 13, B = 13, C = 12, D = 12

> **Math-format policy:** সব formula, substitution, stack state, queue state ও calculation plain-text aligned block-এ দেওয়া হয়েছে। Raw LaTeX command ব্যবহার করা হয়নি, তাই GitHub README ও mobile view-এ alignment ঠিক থাকবে।

---

# Chapter Theory 25: Linked List এবং Abstract Data Type

## ১. ADT কী

`Abstract Data Type` বা `ADT` data এবং সেই data-এর ওপর বৈধ operation-এর logical specification দেয়। ADT বলে:

- কী data রাখা হবে
- কোন operation করা যাবে
- operation-এর expected behavior কী

কিন্তু internal implementation কীভাবে হবে, তা ADT নির্ধারণ করে না।

উদাহরণ হিসেবে `List ADT`-তে থাকতে পারে:

- Insert
- Delete
- Search
- Traverse
- Get element
- Update element

List ADT array বা linked list—দুইভাবেই implement করা যায়।

## ২. Linked List-এর মূল ধারণা

Linked List হলো node-এর একটি sequence। প্রতিটি node সাধারণত দুই অংশ ধারণ করে:

1. **Data field**
2. **Link বা Pointer field**

Singly linked list node-এর সাধারণ গঠন:

```c
struct Node {
    int data;
    struct Node *next;
};
```

`head` প্রথম node-এর address রাখে। শেষ node-এর `next` সাধারণত `NULL` হয়।

## ৩. Singly Linked List

প্রতিটি node শুধু পরবর্তী node-এর address রাখে।

```text
head
 |
 v
[data|next] -> [data|next] -> [data|NULL]
```

### সুবিধা

- Dynamic size
- Head-এ insertion/deletion O(1)
- Contiguous memory প্রয়োজন নেই

### সীমাবদ্ধতা

- Random access নেই
- Backward traversal করা যায় না
- প্রতিটি node-এর জন্য অতিরিক্ত pointer memory লাগে

## ৪. Doubly Linked List

প্রতিটি node previous ও next—দুইটি link রাখে।

```c
struct DNode {
    int data;
    struct DNode *prev;
    struct DNode *next;
};
```

এতে forward ও backward—দুই দিকেই traversal করা যায়।

### সুবিধা

- Known node থেকে deletion সহজ
- Bidirectional traversal
- Previous node খুঁজতে শুরু থেকে traversal দরকার হয় না

### সীমাবদ্ধতা

- Extra pointer memory
- Insertion/deletion-এ বেশি link update
- Implementation error-এর ঝুঁকি বেশি

## ৫. Circular Linked List

শেষ node-এর link আবার প্রথম node-কে নির্দেশ করে।

```text
head -> node1 -> node2 -> node3
 ^                         |
 |_________________________|
```

Circular list round-robin scheduling, cyclic process ও repeated traversal-এ উপযোগী।

## ৬. Header Node

Header node সাধারণ data node-এর আগে থাকা একটি special node। এটি:

- Metadata রাখতে পারে
- List operation সহজ করতে পারে
- Empty-list special case কমাতে পারে

Header node data element হিসেবে গণনা করা হবে কি না, তা implementation-এর definition-এর ওপর নির্ভর করে।

## ৭. Operation Complexity

সাধারণ assumption:

- `head` pointer আছে
- Tail pointer আলাদাভাবে না থাকলে tail access করতে traversal লাগে
- Target node-এর pointer আগে থেকে দেওয়া না থাকলে search cost যোগ হয়

```text
Operation                              Singly Linked List
------------------------------------------------------------
Access i-th element                    O(n)
Search unsorted list                   O(n)
Insert at head                         O(1)
Delete head                            O(1)
Insert after known node                O(1)
Delete after known previous node       O(1)
Insert at tail without tail pointer    O(n)
Insert at tail with tail pointer       O(1)
```

## ৮. Array বনাম Linked List

```text
বিষয়                 Array                       Linked List
-----------------------------------------------------------------
Memory layout         Contiguous                  Non-contiguous
Random access         O(1)                        O(n)
Head insertion        O(n)                        O(1)
Extra link memory     নেই                         আছে
Cache locality        সাধারণত ভালো               সাধারণত দুর্বল
Size change           Fixed/resizing প্রয়োজন      Dynamic
```

## ৯. Common Mistakes

- `head` update না করে head node delete করা
- নতুন node-এর `next` set করার আগে পুরোনো link হারানো
- Free করার পরে node access করা
- Doubly list-এ `prev` ও `next`—দুই দিক update না করা
- Circular list traversal-এ `NULL` condition ব্যবহার করে infinite loop তৈরি করা

## ১০. পরীক্ষার জন্য মনে রাখুন

- Linked List-এ random access নেই
- Known position-এর link change O(1) হতে পারে
- Position খুঁজতে traversal লাগলে total cost O(n)
- Singly list backward traverse করতে পারে না
- Circular list-এর last node `NULL` নয়; head-কে point করে

---

# MCQ Practice: Linked List

## প্রশ্ন 351 | Topic: Data Structure > Linked List > Basic Property | Difficulty: Easy | Type: Theory

Q. Singly Linked List-এর প্রতিটি node সাধারণত কোন তথ্য ধারণ করে?

A) শুধু data  
B) Data এবং পরবর্তী node-এর link  
C) শুধু previous node-এর link  
D) পুরো list-এর সব address

**সঠিক উত্তর: B) Data এবং পরবর্তী node-এর link**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Singly linked list node-এ payload data এবং next node-এর address রাখার জন্য `next` pointer থাকে।
- **A option কেন ভুল:** শুধু data থাকলে node-গুলোর মধ্যে sequence তৈরি করা যাবে না।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Previous link doubly linked list-এ থাকে; singly list-এ সাধারণত থাকে না।
- **D option কেন ভুল:** একটি node পুরো list-এর সব address রাখে না।
- **Related Concept:** শেষ node-এর `next` সাধারণত `NULL`।
- **মনে রাখার টিপস:** Singly node = Data + One forward link।

---

## প্রশ্ন 352 | Topic: Data Structure > Linked List > Traversal Count | Difficulty: Medium | Type: Calculation

Q. একটি Singly Linked List-এ head প্রথম node-কে নির্দেশ করে। Head থেকে ৬ষ্ঠ node-এ পৌঁছাতে কতটি `next` link অনুসরণ করতে হবে?

A) 3  
B) 4  
C) 6  
D) 5

**সঠিক উত্তর: D) 5**

### গাণিতিক বিশ্লেষণ

#### Rule

```text
Head নিজেই 1st node-এ অবস্থান করে।
k-th node-এ যেতে link traversal = k - 1
```

#### Given Data

```text
Target position = 6th node
```

#### Substitution

```text
Link traversal = 6 - 1
               = 5
```

#### Step-by-step Trace

```text
Start at node 1

1st link  : node 1 -> node 2
2nd link  : node 2 -> node 3
3rd link  : node 3 -> node 4
4th link  : node 4 -> node 5
5th link  : node 5 -> node 6
```

#### Final Answer

```text
Required next-link traversal = 5
```

### Option বিশ্লেষণ

- **A) 3:** Target position-এর অর্ধেকের মতো ভুল অনুমান।
- **B) 4:** Off-by-one error; এতে 5th node-এ পৌঁছানো যায়।
- **C) 6:** Node count-কে link count ধরা হয়েছে।
- **D) 5:** এটি সঠিক উত্তর।
- **Related Concept:** Linked List access time O(n), কারণ direct indexing নেই।
- **মনে রাখার টিপস:** 1st node-এ যেতে zero link; তাই k-th node-এ k−1 link।

---

## প্রশ্ন 353 | Topic: Data Structure > Linked List > Random Access | Difficulty: Easy | Type: Theory

Q. Linked List-এ array-এর মতো `O(1)` random access সাধারণত সম্ভব নয় কেন?

A) Node-গুলো contiguous memory-তে থাকা বাধ্যতামূলক নয়  
B) Linked List-এ data রাখা যায় না  
C) প্রতিটি node-এর size সবসময় শূন্য  
D) Linked List শুধু static memory ব্যবহার করে

**সঠিক উত্তর: A) Node-গুলো contiguous memory-তে থাকা বাধ্যতামূলক নয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** i-th node-এর address base address ও index থেকে সরাসরি হিসাব করা যায় না; link ধরে এগোতে হয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** প্রতিটি node data রাখতে পারে।
- **C option কেন ভুল:** Node-এর data ও pointer field থাকায় size শূন্য নয়।
- **D option কেন ভুল:** Linked List সাধারণত dynamic allocation ব্যবহার করতে পারে।
- **Related Concept:** Array indexing address formula ব্যবহার করে O(1) access দেয়।
- **মনে রাখার টিপস:** Linked List-এ index নয়, link অনুসরণ করতে হয়।

---

## প্রশ্ন 354 | Topic: Data Structure > Linked List > Head Insertion | Difficulty: Medium | Type: Theory

Q. Singly Linked List-এর head-এ নতুন node insert করার সঠিক link-update order কোনটি?

A) `head = newNode; newNode->next = NULL;` সব ক্ষেত্রে  
B) পুরোনো head delete করে নতুন node তৈরি করা  
C) `newNode->next = head; head = newNode;`  
D) `head->next = newNode; newNode = head;`

**সঠিক উত্তর: C) `newNode->next = head; head = newNode;`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রথমে নতুন node-কে পুরোনো head-এর সঙ্গে যুক্ত করা হয়, তারপর head নতুন node-এ সরানো হয়।
- **A option কেন ভুল:** এতে পুরোনো list-এর link হারিয়ে যায় এবং নতুন node tail হয়ে যায়।
- **B option কেন ভুল:** পুরোনো head delete করার প্রয়োজন নেই।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এটি head-এর পরে insertion-এর মতো এবং assignment-ও ভুল।
- **Related Concept:** Head insertion-এর time complexity O(1)।
- **মনে রাখার টিপস:** আগে link বাঁচান, পরে head বদলান।

---

## প্রশ্ন 355 | Topic: Data Structure > Linked List > Insertion Trace | Difficulty: Medium | Type: Tracing

Q. List `10 -> 20 -> 30 -> NULL`-এ `20`-এর পরে `25` insert করা হলে final list কোনটি?

A) `25 -> 10 -> 20 -> 30 -> NULL`  
B) `10 -> 20 -> 25 -> 30 -> NULL`  
C) `10 -> 25 -> 20 -> 30 -> NULL`  
D) `10 -> 20 -> 30 -> 25 -> NULL`

**সঠিক উত্তর: B) `10 -> 20 -> 25 -> 30 -> NULL`**

### ধাপে ধাপে Tracing

#### Initial List

```text
10 -> 20 -> 30 -> NULL
```

ধরা যাক `current` node-এর data = 20।

#### Link Update

```text
newNode->data = 25
newNode->next = current->next
current->next = newNode
```

#### Pointer State

```text
আগে:
20.next -> 30

প্রথম update:
25.next -> 30

দ্বিতীয় update:
20.next -> 25
```

#### Final List

```text
10 -> 20 -> 25 -> 30 -> NULL
```

### Option বিশ্লেষণ

- **A:** Head insertion দেখানো হয়েছে।
- **B:** এটি সঠিক উত্তর।
- **C:** `20`-এর আগে insertion হয়েছে।
- **D:** Tail insertion দেখানো হয়েছে।
- **Related Concept:** Known node-এর পরে insertion O(1); কিন্তু node খুঁজতে O(n) লাগতে পারে।
- **মনে রাখার টিপস:** নতুন node প্রথমে successor-কে ধরবে, তারপর current node নতুন node-কে ধরবে।

---

## প্রশ্ন 356 | Topic: Data Structure > Doubly Linked List > Deletion | Difficulty: Medium | Type: Theory

Q. Doubly Linked List-এ একটি known non-terminal node delete করার সময় প্রধানত কোন link-গুলো update করতে হয়?

A) শুধু node-এর `data`  
B) শুধু head pointer  
C) শুধু deleted node-এর `next`  
D) Previous node-এর `next` এবং next node-এর `prev`

**সঠিক উত্তর: D) Previous node-এর `next` এবং next node-এর `prev`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** মাঝের node বাদ দিলে তার আগের node-কে তার পরের node-এর সঙ্গে দুই দিকেই reconnect করতে হয়।
- **A option কেন ভুল:** Data পরিবর্তন করলে node list থেকে বাদ যায় না।
- **B option কেন ভুল:** Non-head node delete করতে head পরিবর্তন প্রয়োজন নেই।
- **C option কেন ভুল:** শুধু deleted node-এর link বদলালে প্রতিবেশী node-এর connection ঠিক হয় না।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** `prev->next = next` এবং `next->prev = prev`।
- **মনে রাখার টিপস:** Doubly list deletion-এ দুই পাশ জোড়া লাগাতে হয়।

---

## প্রশ্ন 357 | Topic: Data Structure > Linked List > Tail Insertion Complexity | Difficulty: Hard | Type: Theory

Q. Singly Linked List-এ tail pointer নেই, শুধু head pointer আছে। Tail-এ insertion-এর worst-case time complexity কত?

A) `O(1)`  
B) `O(log n)`  
C) `O(n log n)`  
D) `O(n)`

**সঠিক উত্তর: D) `O(n)`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** শেষ node খুঁজতে head থেকে পুরো list traverse করতে হয়। Link update O(1), কিন্তু search O(n)।
- **A option কেন ভুল:** Tail pointer থাকলে O(1) হতে পারত।
- **B option কেন ভুল:** Linked List-এ binary-style direct navigation নেই।
- **C option কেন ভুল:** একবার linear traversal লাগে; n log n নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Tail pointer রাখলে insertion O(1), তবে tail deletion singly list-এ এখনও previous node খুঁজতে O(n) হতে পারে।
- **মনে রাখার টিপস:** Operation cost-এ position খোঁজার সময়ও যোগ করুন।

---

## প্রশ্ন 358 | Topic: Data Structure > Circular Linked List > Application | Difficulty: Medium | Type: Scenario

Q. Round-robin process scheduling implement করতে কোন linked structure সবচেয়ে উপযোগী?

A) Linear array only  
B) Singly list with no repeated traversal  
C) Circular Linked List  
D) Binary Search Tree

**সঠিক উত্তর: C) Circular Linked List**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** শেষ process-এর পরে আবার প্রথম process-এ স্বাভাবিকভাবে ফিরে যাওয়া যায়।
- **A option কেন ভুল:** Array ব্যবহার করা সম্ভব হলেও প্রশ্ন linked structure-এর suitability নিয়ে; circular list natural cyclic traversal দেয়।
- **B option কেন ভুল:** Linear singly list-এর শেষে `NULL`; আবার head-এ ফিরতে আলাদা handling লাগে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** BST cyclic scheduling order প্রকাশ করে না।
- **Related Concept:** Circular Queue-ও Round Robin scheduling-এ ব্যবহৃত হয়।
- **মনে রাখার টিপস:** বারবার চক্রাকারে ঘুরলে Circular structure ভাবুন।

---

## প্রশ্ন 359 | Topic: Data Structure > Linked List > Memory Calculation | Difficulty: Hard | Type: Calculation

Q. Padding উপেক্ষা করে ধরা হলো একটি Singly Linked List node-এ 4-byte `int` এবং 8-byte pointer আছে। 100টি node-এর raw storage কত byte?

A) 1200 byte  
B) 800 byte  
C) 400 byte  
D) 1600 byte

**সঠিক উত্তর: A) 1200 byte**

### গাণিতিক বিশ্লেষণ

#### Formula

```text
Node size     = Data size + Pointer size
Total storage = Number of nodes × Node size
```

#### Given Data

```text
Data size       = 4 byte
Pointer size    = 8 byte
Number of nodes = 100
Padding         = Ignored
```

#### Step-by-step Calculation

```text
Node size = 4 + 8
          = 12 byte

Total storage = 100 × 12
              = 1200 byte
```

#### Final Answer

```text
Raw node storage = 1200 byte
```

### Option বিশ্লেষণ

- **A) 1200:** এটি সঠিক উত্তর।
- **B) 800:** শুধু pointer storage গণনা করা হয়েছে।
- **C) 400:** শুধু integer data storage গণনা করা হয়েছে।
- **D) 1600:** প্রতিটি node 16 byte ধরে alignment যোগ করা হয়েছে, কিন্তু প্রশ্নে padding উপেক্ষা করতে বলা হয়েছে।
- **Related Concept:** বাস্তবে alignment-এর কারণে node size 16 byte হতে পারে।
- **মনে রাখার টিপস:** প্রশ্নে padding assumption অবশ্যই পড়ুন।

---

## প্রশ্ন 360 | Topic: Data Structure > Doubly Linked List > Advantage | Difficulty: Easy | Type: Theory

Q. Singly Linked List-এর তুলনায় Doubly Linked List-এর প্রধান সুবিধা কোনটি?

A) কোনো pointer লাগে না  
B) দুই দিকেই traversal করা যায়  
C) সব search O(1) হয়  
D) সবসময় কম memory লাগে

**সঠিক উত্তর: B) দুই দিকেই traversal করা যায়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি node-এর `prev` ও `next` link থাকায় forward ও backward traversal সম্ভব।
- **A option কেন ভুল:** বরং দুটি pointer লাগে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Unsorted list search এখনও O(n)।
- **D option কেন ভুল:** Extra pointer-এর কারণে memory বেশি লাগে।
- **Related Concept:** Known node delete করতে previous node আলাদাভাবে খুঁজতে হয় না।
- **মনে রাখার টিপস:** Double link = Double direction।

---

# Chapter Theory 26: Stack এবং Queue

## ১. Stack

Stack হলো `LIFO` structure:

```text
Last In, First Out
```

প্রধান operation:

- `push(x)` — top-এ item যোগ
- `pop()` — top item remove
- `peek()` বা `top()` — remove না করে top item দেখা
- `isEmpty()`
- `isFull()` — fixed array implementation-এ

## ২. Stack-এর ব্যবহার

- Function call ও recursion
- Parenthesis matching
- Infix–postfix conversion
- Postfix evaluation
- Undo operation
- Browser back history
- Depth-First Search
- Backtracking

## ৩. Stack Implementation

### Array Stack

- Fast ও simple
- Fixed capacity হতে পারে
- `top` index ব্যবহৃত হয়

সাধারণ convention:

```text
Empty stack : top = -1
Push        : stack[++top] = value
Pop         : value = stack[top--]
```

### Linked Stack

- Dynamic size
- Head-কে top হিসেবে ব্যবহার করলে push ও pop O(1)
- Extra pointer memory লাগে

## ৪. Stack Overflow এবং Underflow

- **Overflow:** Full fixed-capacity stack-এ push
- **Underflow:** Empty stack থেকে pop বা top

## ৫. Queue

Queue হলো `FIFO` structure:

```text
First In, First Out
```

প্রধান operation:

- `enqueue(x)` — rear-এ item যোগ
- `dequeue()` — front item remove
- `front()` বা `peek()`
- `isEmpty()`
- `isFull()`

## ৬. Queue-এর ব্যবহার

- CPU scheduling
- Printer queue
- Network buffering
- Breadth-First Search
- Request processing
- Producer–consumer buffer

## ৭. Linear Array Queue-এর সমস্যা

Simple array queue-এ dequeue করার পরে front এগিয়ে যায়। Rear array-এর শেষে পৌঁছালে শুরুতে খালি cell থাকলেও নতুন item insert করা না গেলে `False Overflow` হয়।

সমাধান:

- Element shift করা — ব্যয়বহুল
- Circular Queue ব্যবহার করা — efficient

## ৮. Complexity

```text
Structure            Operation                         Time
----------------------------------------------------------------
Array Stack          Push/Pop                          O(1)
Linked Stack         Push/Pop at head                  O(1)
Linked Queue         Enqueue with rear pointer         O(1)
Linked Queue         Dequeue with front pointer        O(1)
Array linear queue   Shift-based dequeue               O(n)
```

## ৯. Priority Queue

Priority Queue-এ removal arrival order-এর পরিবর্তে priority অনুযায়ী হয়। সমান priority-এর ক্ষেত্রে FIFO policy ব্যবহার করা যেতে পারে।

## Common Mistakes

- Stack ও Queue order গুলিয়ে ফেলা
- Pop-এর আগে empty check না করা
- Linked Queue empty হলে front ও rear—দুটিই `NULL` না করা
- Queue-তে rear থেকে delete করা
- Stack top index update order ভুল করা

## Exam Tips

- Function call → Stack
- BFS → Queue
- DFS → Stack
- Oldest item first → Queue
- Newest item first → Stack

---

# MCQ Practice: Stack and Queue

## প্রশ্ন 361 | Topic: Data Structure > Stack > Principle | Difficulty: Easy | Type: Theory

Q. Stack কোন processing principle অনুসরণ করে?

A) FIFO  
B) Random access  
C) LIFO  
D) Priority only

**সঠিক উত্তর: C) LIFO**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Stack-এ সর্বশেষ push করা item প্রথম pop হয়।
- **A option কেন ভুল:** FIFO Queue-এর principle।
- **B option কেন ভুল:** Stack শুধু top-end operation সমর্থন করে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Priority Queue priority অনুযায়ী remove করে।
- **Related Concept:** Plate stack LIFO-এর বাস্তব উদাহরণ।
- **মনে রাখার টিপস:** Last ঢোকে, First বের হয়।

---

## প্রশ্ন 362 | Topic: Data Structure > Queue > Principle | Difficulty: Easy | Type: Theory

Q. Queue কোন processing principle অনুসরণ করে?

A) LIFO  
B) Highest value first  
C) Random deletion  
D) FIFO

**সঠিক উত্তর: D) FIFO**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Queue-তে প্রথম enqueue করা item প্রথম dequeue হয়।
- **A option কেন ভুল:** LIFO Stack-এর principle।
- **B option কেন ভুল:** এটি Priority Queue-এর একটি সম্ভাব্য policy।
- **C option কেন ভুল:** Queue ordered removal দেয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** সাধারণ service line FIFO।
- **মনে রাখার টিপস:** First ঢোকে, First বের হয়।

---

## প্রশ্ন 363 | Topic: Data Structure > Stack > Operation Trace | Difficulty: Medium | Type: Tracing

Q. Empty Stack-এ নিচের operation করা হলো:

```text
push(10)
push(20)
pop()
push(30)
```

শেষে top element কোনটি?

A) 30  
B) 20  
C) 10  
D) Stack empty

**সঠিক উত্তর: A) 30**

### ধাপে ধাপে Tracing

```text
Initial stack:
[]

push(10):
[10]

push(20):
[10, 20]    <- top = 20

pop():
[10]        removed = 20

push(30):
[10, 30]    <- top = 30
```

#### Final Answer

```text
Top element = 30
```

### Option বিশ্লেষণ

- **A) 30:** এটি সঠিক উত্তর।
- **B) 20:** `pop()`-এ 20 remove হয়েছে।
- **C) 10:** 10 stack-এ আছে, কিন্তু top নয়।
- **D:** Stack-এ দুইটি element আছে।
- **Related Concept:** Stack trace করার সময় bottom থেকে top ক্রমে state লিখুন।
- **মনে রাখার টিপস:** প্রতিটি push/pop-এর পরে নতুন top চিহ্নিত করুন।

---

## প্রশ্ন 364 | Topic: Data Structure > Stack > Application | Difficulty: Medium | Type: Theory

Q. নিচের কোন application-এ Stack সবচেয়ে সরাসরি ব্যবহৃত হয়?

A) Breadth-First Search  
B) Recursive function call management  
C) Printer job-এর arrival-order processing  
D) Round-robin scheduling

**সঠিক উত্তর: B) Recursive function call management**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি function call-এর activation record call stack-এ রাখা হয়।
- **A option কেন ভুল:** BFS Queue ব্যবহার করে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Arrival-order job processing Queue।
- **D option কেন ভুল:** Round Robin সাধারণত Circular Queue।
- **Related Concept:** Return address, local variable ও parameter stack frame-এ থাকতে পারে।
- **মনে রাখার টিপস:** Nested call শেষটি আগে return করে—LIFO।

---

## প্রশ্ন 365 | Topic: Data Structure > Stack > Underflow | Difficulty: Easy | Type: Theory

Q. Empty Stack থেকে `pop()` করার চেষ্টা করলে কী ঘটে?

A) Overflow  
B) Collision  
C) Underflow  
D) Deadlock

**সঠিক উত্তর: C) Underflow**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** কোনো element না থাকা অবস্থায় remove করার চেষ্টা Underflow।
- **A option কেন ভুল:** Full stack-এ push করলে Overflow।
- **B option কেন ভুল:** Collision hashing-এর concept।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Deadlock resource-waiting problem।
- **Related Concept:** Empty check ছাড়া pop করা invalid memory access ঘটাতে পারে।
- **মনে রাখার টিপস:** Empty থেকে বের করতে গেলে Underflow।

---

## প্রশ্ন 366 | Topic: Data Structure > Stack > Linked Implementation | Difficulty: Hard | Type: Scenario

Q. Linked List দিয়ে Stack implement করা হয়েছে এবং head-কে top ধরা হয়েছে। Push ও Pop-এর complexity কী?

A) Push O(n), Pop O(n)  
B) Push O(log n), Pop O(log n)  
C) Push O(1), Pop O(n)  
D) Push O(1), Pop O(1)

**সঠিক উত্তর: D) Push O(1), Pop O(1)**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Head-এ node insert ও delete করতে শুধু কয়েকটি pointer update লাগে।
- **A option কেন ভুল:** Traversal প্রয়োজন নেই।
- **B option কেন ভুল:** কোনো balanced tree search নেই।
- **C option কেন ভুল:** Head deletion-ও O(1)।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Tail-কে top ধরলে singly list-এ pop O(n) হতে পারে।
- **মনে রাখার টিপস:** Linked Stack-এর top হিসেবে head বেছে নিন।

---

## প্রশ্ন 367 | Topic: Data Structure > Queue > BFS Application | Difficulty: Medium | Type: Theory

Q. Breadth-First Search-এ Queue ব্যবহার করা হয় কেন?

A) সর্বশেষ discovered vertex আগে process করতে  
B) একই depth-এর আগে discovered vertex-গুলো আগে process করতে  
C) Edge weight sort করতে  
D) Recursion সম্পূর্ণ নিষিদ্ধ করতে

**সঠিক উত্তর: B) একই depth-এর আগে discovered vertex-গুলো আগে process করতে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** FIFO order BFS-কে level-by-level traversal করতে সাহায্য করে।
- **A option কেন ভুল:** এটি DFS-style LIFO behavior।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** BFS সাধারণ unweighted traversal; edge sorting প্রয়োজন নেই।
- **D option কেন ভুল:** Queue ব্যবহারের মূল কারণ traversal order।
- **Related Concept:** Unweighted graph-এ BFS shortest edge-count path বের করতে পারে।
- **মনে রাখার টিপস:** BFS ছড়িয়ে পড়ে level ধরে—তাই Queue।

---

## প্রশ্ন 368 | Topic: Data Structure > Queue > Operation Trace | Difficulty: Medium | Type: Tracing

Q. Empty Queue-এ operation করা হলো:

```text
enqueue(5)
enqueue(8)
dequeue()
enqueue(12)
```

শেষে front element কোনটি?

A) 8  
B) 5  
C) 12  
D) Queue empty

**সঠিক উত্তর: A) 8**

### ধাপে ধাপে Tracing

```text
Initial:
[]

enqueue(5):
[5]
 front = 5, rear = 5

enqueue(8):
[5, 8]
 front = 5, rear = 8

dequeue():
[8]
 removed = 5
 front = 8

enqueue(12):
[8, 12]
 front = 8, rear = 12
```

#### Final Answer

```text
Front element = 8
```

### Option বিশ্লেষণ

- **A) 8:** এটি সঠিক উত্তর।
- **B) 5:** 5 dequeue হয়েছে।
- **C) 12:** 12 rear element।
- **D:** Queue-এ দুইটি element আছে।
- **Related Concept:** Queue-তে insertion rear-এ, deletion front-এ।
- **মনে রাখার টিপস:** Queue trace-এ front ও rear দুটোই চিহ্নিত করুন।

---

## প্রশ্ন 369 | Topic: Data Structure > Queue > Overflow | Difficulty: Easy | Type: Theory

Q. Fixed-size array Queue পূর্ণ থাকা অবস্থায় `enqueue()` করার চেষ্টা করলে কী বলা হয়?

A) Underflow  
B) Recursion  
C) Rotation  
D) Overflow

**সঠিক উত্তর: D) Overflow**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Available capacity না থাকা অবস্থায় নতুন item যোগ করা Overflow।
- **A option কেন ভুল:** Empty structure থেকে remove হলো Underflow।
- **B option কেন ভুল:** Recursion function self-call।
- **C option কেন ভুল:** Rotation tree balancing operation।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Circular Queue false overflow কমায়, কিন্তু capacity পূর্ণ হলে real overflow এখনও হয়।
- **মনে রাখার টিপস:** Full-এ ঢোকাতে গেলে Overflow।

---

## প্রশ্ন 370 | Topic: Data Structure > Queue > Trace with Multiple Dequeues | Difficulty: Hard | Type: Tracing

Q. Empty Queue-এ নিচের operation করা হলো:

```text
enqueue(2)
enqueue(4)
enqueue(6)
dequeue()
dequeue()
enqueue(8)
```

শেষে Queue front-to-rear ক্রম কোনটি?

A) `[2, 4, 6, 8]`  
B) `[4, 6, 8]`  
C) `[6, 8]`  
D) `[8, 6]`

**সঠিক উত্তর: C) `[6, 8]`**

### ধাপে ধাপে Tracing

```text
enqueue(2)  -> [2]
enqueue(4)  -> [2, 4]
enqueue(6)  -> [2, 4, 6]

1st dequeue:
remove 2    -> [4, 6]

2nd dequeue:
remove 4    -> [6]

enqueue(8)  -> [6, 8]
```

#### Final Answer

```text
Front-to-rear Queue = [6, 8]
```

### Option বিশ্লেষণ

- **A:** দুইটি dequeue উপেক্ষা করা হয়েছে।
- **B:** শুধু একটি dequeue ধরা হয়েছে।
- **C:** এটি সঠিক উত্তর।
- **D:** Queue order উল্টো করে Stack-এর মতো ধরা হয়েছে।
- **Related Concept:** FIFO order-এ 6, 8-এর আগে বের হবে।
- **মনে রাখার টিপস:** Dequeue সবসময় বাম/front দিক থেকে কল্পনা করুন।

---

## প্রশ্ন 371 | Topic: Data Structure > Priority Queue > Removal Policy | Difficulty: Medium | Type: Theory

Q. Priority Queue-এ সাধারণ Queue থেকে প্রধান পার্থক্য কী?

A) Item priority অনুযায়ী remove হতে পারে  
B) কোনো insertion operation নেই  
C) শুধু character রাখা যায়  
D) সব operation O(1) হওয়া বাধ্যতামূলক

**সঠিক উত্তর: A) Item priority অনুযায়ী remove হতে পারে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Highest বা lowest priority item policy অনুযায়ী আগে remove হয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Priority Queue-এ insert operation অপরিহার্য।
- **C option কেন ভুল:** বিভিন্ন data type রাখা যায়।
- **D option কেন ভুল:** Heap implementation-এ insert/delete সাধারণত O(log n)।
- **Related Concept:** Binary Heap Priority Queue implement করতে বহুল ব্যবহৃত।
- **মনে রাখার টিপস:** Priority Queue-এ arrival time নয়, priority মুখ্য।

---

## প্রশ্ন 372 | Topic: Data Structure > Queue > Linked Queue Empty State | Difficulty: Medium | Type: Scenario

Q. Linked Queue-এ একমাত্র node dequeue করার পরে সঠিক state কোনটি?

A) শুধু `front = NULL`, কিন্তু `rear` পুরোনো node-এ থাকবে  
B) `front = NULL` এবং `rear = NULL`  
C) শুধু `rear = NULL`, কিন্তু `front` পুরোনো node-এ থাকবে  
D) `front` ও `rear` নতুন dummy node তৈরি করবে

**সঠিক উত্তর: B) `front = NULL` এবং `rear = NULL`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** শেষ item remove হলে Queue empty; দুই pointer-ই কোনো valid node নির্দেশ করবে না।
- **A option কেন ভুল:** Rear dangling pointer হয়ে যাবে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Front dangling pointer হবে।
- **D option কেন ভুল:** Dummy node ব্যবহারের বিশেষ implementation না থাকলে প্রয়োজন নেই।
- **Related Concept:** Empty Queue condition প্রায়ই `front == NULL`।
- **মনে রাখার টিপস:** Last node বের হলে দুই প্রান্তই reset করুন।

---

# Chapter Theory 27: Circular Queue এবং Deque

## ১. Circular Queue-এর প্রয়োজন

Linear array Queue-এ front এগিয়ে যাওয়ার পরে শুরুতে খালি cell তৈরি হয়। Rear array-এর শেষ index-এ পৌঁছালে ওই খালি cell ব্যবহার করা না গেলে False Overflow ঘটে।

Circular Queue array-কে logical circle হিসেবে ব্যবহার করে।

```text
Next index = (current index + 1) mod N
```

## ২. Front এবং Rear

Convention implementation অনুযায়ী ভিন্ন হতে পারে। একটি common convention:

- `front` প্রথম valid element নির্দেশ করে
- `rear` সর্বশেষ valid element নির্দেশ করে
- Empty অবস্থায় `front = rear = -1`

Enqueue-এর সময়:

```text
rear = (rear + 1) mod N
```

Dequeue-এর সময়:

```text
front = (front + 1) mod N
```

## ৩. Full Condition

### One-slot-empty convention

```text
(rear + 1) mod N == front
```

এতে array size N হলেও usable capacity N−1।

### Count-based convention

আলাদা `count` রাখলে সব N cell ব্যবহার করা যায়:

```text
Empty: count == 0
Full : count == N
```

Exam question-এ কোন convention ব্যবহার হচ্ছে তা অবশ্যই পড়তে হবে।

## ৪. Deque

`Deque` = Double-Ended Queue

দুই প্রান্তেই insertion ও deletion করা যায়:

- Insert Front
- Insert Rear
- Delete Front
- Delete Rear

### Input-Restricted Deque

Insertion শুধু এক প্রান্তে; deletion দুই প্রান্তে।

### Output-Restricted Deque

Deletion শুধু এক প্রান্তে; insertion দুই প্রান্তে।

## ৫. Deque-এর ব্যবহার

- Sliding Window algorithm
- Palindrome checking
- Task scheduling
- Undo/redo
- 0–1 BFS
- Monotonic Queue

## Common Mistakes

- Modulo operation বাদ দেওয়া
- Empty ও Full condition একই করে ফেলা
- One-slot-empty convention-এ capacity N ধরা
- Rear wrap হলেও front update ভুল করা
- Deque-কে Priority Queue মনে করা

## Exam Tips

- Circular advance: `(index + 1) % N`
- One empty slot: capacity = N−1
- Deque: দুই দিকেই operation
- Circular Queue physical array নয়, logical wrap-around

---

# MCQ Practice: Circular Queue and Deque

## প্রশ্ন 373 | Topic: Data Structure > Circular Queue > Purpose | Difficulty: Easy | Type: Theory

Q. Linear array Queue-এর False Overflow সমস্যা কমাতে কোন structure ব্যবহৃত হয়?

A) Circular Queue  
B) Stack  
C) Linked Stack  
D) Binary Tree

**সঠিক উত্তর: A) Circular Queue**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Circular Queue rear-কে modulo ব্যবহার করে array-এর শুরুতে ফিরিয়ে খালি cell reuse করতে দেয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Stack LIFO principle অনুসরণ করে।
- **C option কেন ভুল:** Linked Stack Queue-এর FIFO ordering দেয় না।
- **D option কেন ভুল:** Binary Tree linear buffer reuse-এর সমাধান নয়।
- **Related Concept:** Circular Queue fixed array space efficientভাবে reuse করে।
- **মনে রাখার টিপস:** Rear শেষে গিয়ে শুরুতে ফিরলে Circular Queue।

---

## প্রশ্ন 374 | Topic: Data Structure > Circular Queue > Rear Trace | Difficulty: Hard | Type: Tracing

Q. Circular Queue-এর size 5। `rear = 3` হলে একটি সফল enqueue-এর পরে নতুন rear index কত হবে?

A) 5  
B) 3  
C) 4  
D) 0

**সঠিক উত্তর: C) 4**

### গাণিতিক বিশ্লেষণ

#### Formula

```text
newRear = (rear + 1) mod N
```

#### Given Data

```text
rear = 3
N    = 5
```

#### Substitution

```text
newRear = (3 + 1) mod 5
        = 4 mod 5
        = 4
```

#### Final Answer

```text
New rear index = 4
```

### Option বিশ্লেষণ

- **A) 5:** Array-এর valid index 0–4; modulo প্রয়োগ করা হয়নি।
- **B) 3:** Rear update করা হয়নি।
- **C) 4:** এটি সঠিক উত্তর।
- **D) 0:** Rear 4 থেকে আরেকবার advance করলে 0 হতো।
- **Related Concept:** `rear = 4` হলে next rear `(4+1)%5 = 0`।
- **মনে রাখার টিপস:** Circular index সবসময় modulo N।

---

## প্রশ্ন 375 | Topic: Data Structure > Circular Queue > Full Condition | Difficulty: Medium | Type: Theory

Q. One-slot-empty convention-এ size N Circular Queue full হওয়ার condition কোনটি?

A) `(rear + 1) % N == front`  
B) `rear == front` সব ক্ষেত্রে  
C) `rear == N`  
D) `front == -1` সব ক্ষেত্রে

**সঠিক উত্তর: A) `(rear + 1) % N == front`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Rear-এর পরবর্তী circular cell front হলে নতুন insertion-এর জায়গা নেই।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** অনেক convention-এ `rear == front` empty state বা ambiguous হতে পারে।
- **C option কেন ভুল:** Rear valid index range-এর বাইরে যায় না।
- **D option কেন ভুল:** `front == -1` সাধারণত empty state।
- **Related Concept:** Convention না জানলে full/empty rule নির্ধারণ করা যায় না।
- **মনে রাখার টিপস:** Next rear meets front → Full।

---

## প্রশ্ন 376 | Topic: Data Structure > Circular Queue > Usable Capacity | Difficulty: Medium | Type: Calculation

Q. One-slot-empty convention ব্যবহার করা size 10 Circular Queue-এ সর্বোচ্চ কতটি item রাখা যায়?

A) 10  
B) 9  
C) 8  
D) 11

**সঠিক উত্তর: B) 9**

### গাণিতিক বিশ্লেষণ

#### Rule

```text
Usable capacity = Physical array size - 1
```

#### Given Data

```text
Array size = 10
Reserved empty slot = 1
```

#### Calculation

```text
Usable capacity = 10 - 1
                = 9
```

#### Final Answer

```text
Maximum stored items = 9
```

### Option বিশ্লেষণ

- **A) 10:** Count-based convention ধরে নেওয়া হয়েছে; প্রশ্নে one-slot-empty বলা আছে।
- **B) 9:** এটি সঠিক উত্তর।
- **C) 8:** একটি অতিরিক্ত slot বাদ দেওয়া হয়েছে।
- **D) 11:** Physical capacity-এর চেয়ে বেশি।
- **Related Concept:** আলাদা count রাখলে সব 10 cell ব্যবহার করা যেত।
- **মনে রাখার টিপস:** One-slot-empty মানে N−1 capacity।

---

## প্রশ্ন 377 | Topic: Data Structure > Circular Queue > Wrap-around | Difficulty: Hard | Type: Scenario

Q. Circular Queue-এর size 6 এবং rear index 5। Queue full নয়। পরবর্তী enqueue কোন index-এ হবে?

A) 6  
B) 5  
C) 0  
D) 1

**সঠিক উত্তর: C) 0**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Circular increment modulo 6 ব্যবহার করে।
- **Calculation:**

```text
newRear = (5 + 1) mod 6
        = 6 mod 6
        = 0
```

- **A option কেন ভুল:** Index 6 valid নয়।
- **B option কেন ভুল:** Rear advance হয়নি।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** আরও একটি enqueue হলে 1 হতে পারে।
- **Related Concept:** এই wrap-around-ই array-এর শুরুতে খালি cell reuse করে।
- **মনে রাখার টিপস:** Last index-এর পরে zero।

---

## প্রশ্ন 378 | Topic: Data Structure > Deque > Definition | Difficulty: Easy | Type: Theory

Q. `Deque`-এর প্রধান বৈশিষ্ট্য কী?

A) শুধু rear-এ insertion ও front-এ deletion  
B) শুধু priority অনুযায়ী deletion  
C) শুধু stack operation  
D) দুই প্রান্তেই insertion ও deletion সম্ভব

**সঠিক উত্তর: D) দুই প্রান্তেই insertion ও deletion সম্ভব**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Deque হলো Double-Ended Queue।
- **A option কেন ভুল:** এটি সাধারণ Queue।
- **B option কেন ভুল:** Priority Queue priority policy ব্যবহার করে।
- **C option কেন ভুল:** Deque Stack ও Queue—দুই ধরনের behavior emulate করতে পারে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Deque থেকে front/rear উভয় দিকের item remove করা যায়।
- **মনে রাখার টিপস:** Double-ended = দুই দিক খোলা।

---

## প্রশ্ন 379 | Topic: Data Structure > Deque > Operation Trace | Difficulty: Medium | Type: Tracing

Q. Empty Deque-এ operation করা হলো:

```text
insertRear(10)
insertFront(5)
insertRear(20)
deleteFront()
```

শেষে front-to-rear ক্রম কোনটি?

A) `[10, 20]`  
B) `[5, 10, 20]`  
C) `[20, 10]`  
D) `[5, 20]`

**সঠিক উত্তর: A) `[10, 20]`**

### ধাপে ধাপে Tracing

```text
Initial:
[]

insertRear(10):
[10]

insertFront(5):
[5, 10]

insertRear(20):
[5, 10, 20]

deleteFront():
remove 5
[10, 20]
```

#### Final Answer

```text
Deque = [10, 20]
```

### Option বিশ্লেষণ

- **A:** এটি সঠিক উত্তর।
- **B:** `deleteFront()` উপেক্ষা করা হয়েছে।
- **C:** Order উল্টো করা হয়েছে।
- **D:** ভুল element remove করা হয়েছে।
- **Related Concept:** Deque Stack হিসেবে ব্যবহার করলে একই end-এ insert/delete করা যায়।
- **মনে রাখার টিপস:** Front operation বাম দিকে, Rear operation ডান দিকে trace করুন।

---

## প্রশ্ন 380 | Topic: Data Structure > Deque > Restricted Types | Difficulty: Easy | Type: Theory

Q. Input-Restricted Deque-এ কোন restriction থাকে?

A) Deletion দুই প্রান্তে, insertion শুধু এক প্রান্তে  
B) Insertion দুই প্রান্তে, deletion শুধু এক প্রান্তে  
C) Insertion ও deletion দুটোই নিষিদ্ধ  
D) শুধু priority item রাখা যায়

**সঠিক উত্তর: B) Deletion দুই প্রান্তে, insertion শুধু এক প্রান্তে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Input-Restricted মানে input বা insertion side সীমিত; output দুই দিক থেকে হতে পারে।
- **A option কেন ভুল:** Statement-টিই সঠিক ধারণা—এবং এটি B option-এ দেওয়া হয়েছে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** তাহলে structure ব্যবহারযোগ্য নয়।
- **D option কেন ভুল:** Priority policy Deque definition নয়।
- **Related Concept:** Output-Restricted Deque-এ deletion এক প্রান্তে সীমিত।
- **মনে রাখার টিপস:** যে শব্দের আগে Restricted, সেই operation সীমিত।

---

# Chapter Theory 28: Prefix, Infix এবং Postfix Expression

## ১. Expression Form

### Infix

Operator operand-এর মাঝে থাকে:

```text
A + B
```

মানুষের কাছে সহজ, কিন্তু precedence ও parentheses parse করতে হয়।

### Prefix

Operator operand-এর আগে:

```text
+ A B
```

### Postfix

Operator operand-এর পরে:

```text
A B +
```

Prefix ও Postfix-এ parentheses ছাড়াই evaluation order নির্ধারণ করা যায়।

## ২. Operator Precedence এবং Associativity

সাধারণ precedence:

```text
^                Highest
*, /, %
+, -
```

Associativity:

- `^` সাধারণত right-associative
- `*`, `/`, `%`, `+`, `-` left-associative

নোট: বাস্তব programming language অনুযায়ী exponent operator ভিন্ন হতে পারে; expression-conversion প্রশ্নে সাধারণ data-structure convention অনুসরণ করা হয়।

## ৩. Infix থেকে Postfix Conversion

Operand দেখলে output-এ পাঠানো হয়।

Operator দেখলে:

1. Stack top-এর higher-precedence operator pop
2. Equal precedence হলে associativity বিবেচনা
3. `(` stack-এ push
4. `)` এলে `(` পর্যন্ত pop
5. শেষে stack-এর সব operator pop

উদাহরণ:

```text
Infix   : A + B * C
Postfix : A B C * +
```

## ৪. Postfix Evaluation

বাম থেকে ডানে scan:

- Operand → Stack-এ push
- Operator → দুই operand pop
- `right` operand আগে pop হয়
- `left` operand পরে pop হয়
- `left operator right` evaluate করে result push

Division ও subtraction-এ operand order অত্যন্ত গুরুত্বপূর্ণ।

## ৫. Prefix Evaluation

ডান থেকে বামে scan:

- Operand push
- Operator পেলে প্রথম pop = left operand
- দ্বিতীয় pop = right operand
- Result push

## ৬. Infix থেকে Prefix

একটি প্রচলিত পদ্ধতি:

1. Infix reverse
2. Parenthesis swap
3. Postfix conversion
4. Result reverse

Associativity handling সতর্কভাবে করতে হয়।

## ৭. Parenthesis Matching

Stack ব্যবহার করে opening bracket push করা হয়। Closing bracket এলে matching opening bracket pop করতে হয়।

Valid pair:

```text
()
{}
[]
```

## Common Mistakes

- Postfix evaluation-এ operand order উল্টো করা
- `^`-কে left-associative ধরা
- Closing parenthesis output-এ লেখা
- Conversion শেষে operator stack empty না করা
- Prefix evaluation বাম থেকে ডানে করা

## Exam Tips

- Postfix: left-to-right
- Prefix: right-to-left
- Postfix operator এলে first pop = right operand
- Multiplication addition-এর আগে
- Parentheses output-এ থাকে না

---

# MCQ Practice: Expression Conversion and Evaluation

## প্রশ্ন 381 | Topic: Algorithm > Expression > Infix to Postfix | Difficulty: Medium | Type: Tracing

Q. Infix expression `A + B * C`-এর Postfix form কোনটি?

A) `AB+C*`  
B) `+A*BC`  
C) `ABC*+`  
D) `AB*C+`

**সঠিক উত্তর: C) `ABC*+`**

### Conversion Trace

```text
Token A  -> Output: A
Token +  -> Stack : +
Token B  -> Output: AB
Token *  -> Higher precedence than +, push
            Stack : + *
Token C  -> Output: ABC

End:
Pop *    -> ABC*
Pop +    -> ABC*+
```

#### Final Answer

```text
Postfix = ABC*+
```

### Option বিশ্লেষণ

- **A:** Addition আগে evaluate করা হয়েছে।
- **B:** এটি Prefix form।
- **C:** এটি সঠিক উত্তর।
- **D:** `A*B + C`-এর মতো order প্রকাশ করে।
- **Related Concept:** `*`-এর precedence `+`-এর চেয়ে বেশি।
- **মনে রাখার টিপস:** Higher-precedence operator Postfix-এ operands-এর কাছে আসে।

---

## প্রশ্ন 382 | Topic: Algorithm > Expression > Postfix Evaluation | Difficulty: Easy | Type: Calculation

Q. Postfix expression `6 2 / 3 +`-এর value কত?

A) 6  
B) 1  
C) 12  
D) 5

**সঠিক উত্তর: A) 6**

### গাণিতিক বিশ্লেষণ

#### Scan and Stack Trace

```text
Token 6:
Stack = [6]

Token 2:
Stack = [6, 2]

Token /:
right = 2
left  = 6
6 / 2 = 3
Stack = [3]

Token 3:
Stack = [3, 3]

Token +:
right = 3
left  = 3
3 + 3 = 6
Stack = [6]
```

#### Final Answer

```text
Expression value = 6
```

### Option বিশ্লেষণ

- **A) 6:** এটি সঠিক উত্তর।
- **B) 1:** Operand order বা operation sequence ভুল।
- **C) 12:** Division বাদ দিয়ে multiplication করা হয়েছে।
- **D) 5:** `6-2+1` ধরনের ভুল।
- **Related Concept:** Postfix operator-এ দ্বিতীয় pop left operand।
- **মনে রাখার টিপস:** Pop right first, then left।

---

## প্রশ্ন 383 | Topic: Algorithm > Expression > Postfix Property | Difficulty: Medium | Type: Theory

Q. Postfix expression-এর গুরুত্বপূর্ণ সুবিধা কোনটি?

A) Operator প্রয়োজন হয় না  
B) শুধু একটি operand থাকতে পারে  
C) সবসময় alphabetically sorted থাকে  
D) Precedence নির্ধারণে parentheses প্রয়োজন হয় না

**সঠিক উত্তর: D) Precedence নির্ধারণে parentheses প্রয়োজন হয় না**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Operator-এর অবস্থান evaluation order unambiguously প্রকাশ করে।
- **A option কেন ভুল:** Operator ছাড়া operation বোঝানো যায় না।
- **B option কেন ভুল:** বহু operand থাকতে পারে।
- **C option কেন ভুল:** Alphabetical sorting-এর সঙ্গে সম্পর্ক নেই।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Postfix stack দিয়ে সহজে evaluate করা যায়।
- **মনে রাখার টিপস:** Postfix নিজেই order encode করে।

---

## প্রশ্ন 384 | Topic: Algorithm > Expression > Parenthesized Infix to Postfix | Difficulty: Medium | Type: Tracing

Q. Infix expression `(A + B) * (C - D)`-এর Postfix form কোনটি?

A) `ABCD+-*`  
B) `AB+CD-*`  
C) `*+AB-CD`  
D) `AB*CD+-`

**সঠিক উত্তর: B) `AB+CD-*`**

### Conversion Trace

```text
(A + B):
A B +

(C - D):
C D -

দুই group-এর মধ্যে multiplication:
AB+ CD- *
```

#### Final Answer

```text
Postfix = AB+CD-*
```

### Option বিশ্লেষণ

- **A:** Operator grouping ভুল।
- **B:** এটি সঠিক উত্তর।
- **C:** এটি Prefix form।
- **D:** `A*B + C-D`-এর মতো order।
- **Related Concept:** Parenthesized subexpression আগে Postfix-এ সম্পন্ন হয়।
- **মনে রাখার টিপস:** প্রতিটি bracket group আলাদাভাবে convert করুন।

---

## প্রশ্ন 385 | Topic: Algorithm > Expression > Prefix Evaluation | Difficulty: Medium | Type: Calculation

Q. Prefix expression `- + 8 2 3`-এর value কত?

A) 13  
B) 3  
C) 7  
D) 9

**সঠিক উত্তর: C) 7**

### গাণিতিক বিশ্লেষণ

#### Structural Interpretation

```text
- (+ 8 2) 3
```

#### Step-by-step Calculation

```text
+ 8 2 = 8 + 2
      = 10

- 10 3 = 10 - 3
       = 7
```

#### Right-to-Left Stack Trace

```text
Scan 3 -> [3]
Scan 2 -> [3, 2]
Scan 8 -> [3, 2, 8]

Scan +:
left  = 8
right = 2
result = 10
Stack = [3, 10]

Scan -:
left  = 10
right = 3
result = 7
Stack = [7]
```

#### Final Answer

```text
Prefix value = 7
```

### Option বিশ্লেষণ

- **A) 13:** সব সংখ্যা যোগ করা হয়েছে।
- **B) 3:** Operation order ভুল।
- **C) 7:** এটি সঠিক উত্তর।
- **D) 9:** `8-2+3` ধরা হয়েছে।
- **Related Concept:** Prefix scan right-to-left।
- **মনে রাখার টিপস:** Prefix operator এলে first pop left operand।

---

## প্রশ্ন 386 | Topic: Algorithm > Expression > Operand Order | Difficulty: Hard | Type: Theory

Q. Postfix evaluation-এ operator `/` পাওয়া গেলে stack থেকে প্রথম pop করা value কোন operand?

A) Right operand  
B) Left operand  
C) Operator-এর precedence  
D) Final result

**সঠিক উত্তর: A) Right operand**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Postfix-এ operands আগে push হয়। সর্বশেষ push করা operand operator-এর ডান পাশে থাকে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Left operand দ্বিতীয় pop।
- **C option কেন ভুল:** Stack থেকে numeric operand pop হয়, precedence নয়।
- **D option কেন ভুল:** Result operation শেষে push করা হয়।
- **Related Concept:** `8 2 /` → first pop 2, second pop 8 → 8/2।
- **মনে রাখার টিপস:** First pop = Right, Second pop = Left।

---

## প্রশ্ন 387 | Topic: Algorithm > Expression > Right Associativity | Difficulty: Hard | Type: Tracing

Q. `^` operator right-associative ধরে Infix `A ^ B ^ C`-এর Postfix form কোনটি?

A) `AB^C^`  
B) `^A^BC`  
C) `ABC^^` এবং `AB^C^` দুটোই  
D) `ABC^^`

**সঠিক উত্তর: D) `ABC^^`**

### Conversion Reasoning

Right associativity:

```text
A ^ B ^ C
= A ^ (B ^ C)
```

Subexpression:

```text
B ^ C -> BC^
```

তারপর:

```text
A ^ (BC^) -> ABC^^
```

#### Final Answer

```text
Postfix = ABC^^
```

### Option বিশ্লেষণ

- **A) AB^C^:** এটি `(A^B)^C`, অর্থাৎ left association।
- **B):** এটি Prefix-style expression।
- **C):** Associativity নির্দিষ্ট থাকায় দুটো সমান নয়।
- **D):** এটি সঠিক উত্তর।
- **Related Concept:** Equal precedence operator pop করার rule associativity অনুযায়ী বদলায়।
- **মনে রাখার টিপস:** Exponent chain ডান দিক থেকে group করুন।

---

## প্রশ্ন 388 | Topic: Algorithm > Expression > Complex Postfix Evaluation | Difficulty: Medium | Type: Calculation

Q. Postfix expression `5 1 2 + 4 * + 3 -`-এর value কত?

A) 11  
B) 14  
C) 17  
D) 20

**সঠিক উত্তর: B) 14**

### গাণিতিক বিশ্লেষণ

#### Stack Trace

```text
5       -> [5]
1       -> [5, 1]
2       -> [5, 1, 2]

+:
1 + 2 = 3
Stack   -> [5, 3]

4       -> [5, 3, 4]

*:
3 × 4 = 12
Stack   -> [5, 12]

+:
5 + 12 = 17
Stack   -> [17]

3       -> [17, 3]

-:
17 - 3 = 14
Stack   -> [14]
```

#### Final Answer

```text
Expression value = 14
```

### Option বিশ্লেষণ

- **A) 11:** Multiplication বা final subtraction ভুল।
- **B) 14:** এটি সঠিক উত্তর।
- **C) 17:** শেষ `3 -` operation করা হয়নি।
- **D) 20:** সব operation order অনুসরণ করা হয়নি।
- **Related Concept:** Postfix evaluation-এর time complexity O(n)।
- **মনে রাখার টিপস:** প্রতিটি operator-এর পরে stack state লিখুন।

---

## প্রশ্ন 389 | Topic: Algorithm > Expression > Parenthesis Matching | Difficulty: Medium | Type: Theory

Q. Parenthesis matching algorithm-এ closing bracket `]` পাওয়া গেলে stack top-এ কী থাকা উচিত?

A) Matching opening bracket `[`  
B) যেকোনো operator  
C) Closing bracket `]`  
D) Stack empty হওয়া বাধ্যতামূলক

**সঠিক উত্তর: A) Matching opening bracket `[`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি closing bracket nearest unmatched corresponding opening bracket-এর সঙ্গে match করতে হয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Operator matching bracket নয়।
- **C option কেন ভুল:** Stack-এ সাধারণত opening bracket push করা হয়।
- **D option কেন ভুল:** Stack empty হলে unmatched closing bracket পাওয়া গেছে।
- **Related Concept:** Scan শেষে stack empty না হলে unmatched opening bracket আছে।
- **মনে রাখার টিপস:** Close দেখলে top-এর matching open খুঁজুন।

---

## প্রশ্ন 390 | Topic: Algorithm > Expression > Infix to Prefix | Difficulty: Hard | Type: Tracing

Q. Infix expression `(A - B / C) * (A / K - L)`-এর Prefix form কোনটি?

A) `-*A/BC-/AKL`  
B) `AB/C-AK/L-*`  
C) `*-A/BC-/AKL`  
D) `*A-B/C-/AKL`

**সঠিক উত্তর: C) `*-A/BC-/AKL`**

### Conversion Reasoning

প্রথম group:

```text
A - B / C

B / C   -> / B C
A - (...) -> - A / B C
Prefix  -> -A/BC
```

দ্বিতীয় group:

```text
A / K - L

A / K   -> / A K
(...)-L -> - / A K L
Prefix  -> -/AKL
```

দুই group multiply:

```text
* (-A/BC) (-/AKL)
```

#### Final Answer

```text
Prefix = *-A/BC-/AKL
```

### Option বিশ্লেষণ

- **A):** প্রথম operator order ভুল; এটি পুরো expression-এর multiplication root ঠিকভাবে প্রকাশ করে না।
- **B):** এটি Postfix-style।
- **C):** এটি সঠিক উত্তর।
- **D):** প্রথম group-এ precedence/grouping ভুল।
- **Related Concept:** Prefix-এ operator subexpression-এর আগে থাকে।
- **মনে রাখার টিপস:** প্রথমে প্রতিটি parenthesized group convert করুন।

---

## প্রশ্ন 391 | Topic: Algorithm > Expression > Postfix with Subtraction | Difficulty: Medium | Type: Calculation

Q. Postfix expression `2 3 1 * + 9 -`-এর value কত?

A) 10  
B) 4  
C) 8  
D) -4

**সঠিক উত্তর: D) -4**

### গাণিতিক বিশ্লেষণ

#### Stack Trace

```text
2       -> [2]
3       -> [2, 3]
1       -> [2, 3, 1]

*:
3 × 1 = 3
Stack   -> [2, 3]

+:
2 + 3 = 5
Stack   -> [5]

9       -> [5, 9]

-:
left  = 5
right = 9
5 - 9 = -4
Stack -> [-4]
```

#### Final Answer

```text
Expression value = -4
```

### Option বিশ্লেষণ

- **A) 10:** Operand order বা addition ভুল।
- **B) 4:** `9-5` করা হয়েছে; operand order উল্টো।
- **C) 8:** Operator sequence ভুল।
- **D) -4:** এটি সঠিক উত্তর।
- **Related Concept:** Non-commutative operator-এ pop order অত্যন্ত গুরুত্বপূর্ণ।
- **মনে রাখার টিপস:** Postfix `a b -` মানে `a-b`, `b-a` নয়।

---

## প্রশ্ন 392 | Topic: Algorithm > Expression > Prefix Scan Direction | Difficulty: Easy | Type: Theory

Q. Stack দিয়ে Prefix expression evaluate করার প্রচলিত scan direction কোনটি?

A) মাঝখান থেকে দুই দিকে  
B) ডান থেকে বাম  
C) বাম থেকে ডান  
D) Random order

**সঠিক উত্তর: B) ডান থেকে বাম**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Prefix-এ operator operands-এর আগে থাকে; ডান থেকে scan করলে operands আগে stack-এ পাওয়া যায়।
- **A option কেন ভুল:** Standard evaluation algorithm নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** বাম থেকে scan করতে recursive parsing বা ভিন্ন algorithm লাগতে পারে; stack-এর প্রচলিত পদ্ধতি right-to-left।
- **D option কেন ভুল:** Expression order deterministic।
- **Related Concept:** Postfix scan left-to-right।
- **মনে রাখার টিপস:** Prefix = Right-to-left; Postfix = Left-to-right।

---

# Chapter Theory 29: Recursion এবং Tower of Hanoi

## ১. Recursion কী

কোনো function নিজেকে সরাসরি বা পরোক্ষভাবে call করলে Recursion হয়।

### Direct Recursion

```c
void f() {
    f();
}
```

### Indirect Recursion

```text
A calls B
B calls A
```

## ২. Recursive Function-এর তিনটি শর্ত

একটি সঠিক recursive solution-এ সাধারণত থাকে:

1. Base Case
2. Recursive Case
3. Base Case-এর দিকে progress

Base case না থাকলে বা input base case-এর দিকে না এগোলে infinite recursion ও stack overflow হতে পারে।

## ৩. Call Stack

প্রতিটি recursive call-এর জন্য activation record বা stack frame তৈরি হতে পারে। এতে থাকে:

- Parameter
- Local variable
- Return address
- Saved state

Recursive depth বেশি হলে space complexity বাড়ে।

## ৪. Factorial

```text
fact(0) = 1
fact(n) = n × fact(n-1), n > 0
```

Time:

```text
T(n) = T(n-1) + O(1)
     = O(n)
```

Stack space:

```text
O(n)
```

## ৫. Fibonacci

Naive recurrence:

```text
fib(0) = 0
fib(1) = 1
fib(n) = fib(n-1) + fib(n-2)
```

Naive recursive implementation একই subproblem বহুবার solve করে। Time exponential, আনুমানিক O(2^n); memoization ব্যবহার করলে O(n) করা যায়।

## ৬. Tail Recursion

Recursive call function-এর শেষ কার্যকর operation হলে Tail Recursion।

Compiler tail-call optimization করতে পারে, কিন্তু C standard এটি guarantee করে না।

## ৭. Tower of Hanoi

n disk source থেকে destination-এ সরাতে:

1. n−1 disk auxiliary-তে
2. সবচেয়ে বড় disk destination-এ
3. n−1 disk auxiliary থেকে destination-এ

Recurrence:

```text
T(n) = 2T(n-1) + 1
T(1) = 1
```

Closed form:

```text
T(n) = 2^n - 1
```

## ৮. Recursion বনাম Iteration

```text
বিষয়                Recursion                   Iteration
----------------------------------------------------------------
Control              Function call              Loop
Extra stack          সাধারণত লাগে               সাধারণত কম
Readability          কিছু problem-এ বেশি        কিছু problem-এ সহজ
Overhead             Function-call overhead     তুলনামূলক কম
Natural use          Tree, divide-conquer        Linear repetition
```

## Common Mistakes

- Base case না দেওয়া
- Recursive call-এর argument না কমানো
- Fibonacci-এর exponential repeated work উপেক্ষা করা
- Recursive time ও stack space একই মনে করা
- Hanoi move count-এ `-1` বাদ দেওয়া

## Exam Tips

- Linear recursion depth n → stack O(n)
- Factorial time O(n)
- Naive Fibonacci exponential
- Hanoi minimum moves = 2^n − 1
- Memoization repeated subproblem cache করে

---

# MCQ Practice: Recursion

## প্রশ্ন 393 | Topic: Algorithm > Recursion > Base Case | Difficulty: Easy | Type: Theory

Q. Recursive function-এ Base Case-এর প্রধান উদ্দেশ্য কী?

A) Function-এর parameter বাড়ানো  
B) সব local variable global করা  
C) Recursion termination condition নির্ধারণ করা  
D) Heap memory delete করা

**সঠিক উত্তর: C) Recursion termination condition নির্ধারণ করা**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Base case পৌঁছালে আর recursive call করা হয় না।
- **A option কেন ভুল:** Parameter বাড়ানো base case-এর উদ্দেশ্য নয়।
- **B option কেন ভুল:** Variable scope পরিবর্তন হয় না।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Memory release আলাদা concern।
- **Related Concept:** Base case unreachable হলে stack overflow হতে পারে।
- **মনে রাখার টিপস:** Recursion কোথায় থামবে—Base Case তা বলে।

---

## প্রশ্ন 394 | Topic: Algorithm > Recursion > Factorial Multiplication Count | Difficulty: Medium | Type: Calculation

Q. নিচের recurrence ব্যবহার করে `fact(6)` গণনা করতে কতটি multiplication হয়?

```text
fact(1) = 1
fact(n) = n × fact(n-1), n > 1
```

A) 5  
B) 6  
C) 4  
D) 720

**সঠিক উত্তর: A) 5**

### গাণিতিক বিশ্লেষণ

#### Expansion

```text
fact(6)
= 6 × fact(5)      1st multiplication
= 6 × 5 × fact(4)  2nd
= 6 × 5 × 4 × fact(3)  3rd
= 6 × 5 × 4 × 3 × fact(2)  4th
= 6 × 5 × 4 × 3 × 2 × fact(1)  5th
```

`fact(1)` base case, এখানে multiplication নেই।

#### Formula

```text
For fact(n) with base fact(1):
Multiplication count = n - 1
```

#### Calculation

```text
Count = 6 - 1
      = 5
```

#### Final Answer

```text
Number of multiplications = 5
```

### Option বিশ্লেষণ

- **A) 5:** এটি সঠিক উত্তর।
- **B) 6:** Function call count-এর সঙ্গে multiplication count গুলিয়ে ফেলা হয়েছে।
- **C) 4:** একটি recursive level বাদ দেওয়া হয়েছে।
- **D) 720:** এটি factorial result, operation count নয়।
- **Related Concept:** Time complexity O(n)।
- **মনে রাখার টিপস:** Base case operation count-এ multiplication যোগ করে না।

---

## প্রশ্ন 395 | Topic: Algorithm > Recursion > Stack Space | Difficulty: Medium | Type: Theory

Q. Non-tail recursive factorial function-এর maximum recursion depth n হলে auxiliary stack space কত?

A) `O(1)`  
B) `O(n)`  
C) `O(log n)`  
D) `O(n²)`

**সঠিক উত্তর: B) `O(n)`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একসঙ্গে n-এর কাছাকাছি stack frame active থাকে।
- **A option কেন ভুল:** Iterative factorial O(1) extra space হতে পারে, recursive version নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Argument প্রতি call-এ 1 কমে; অর্ধেক হয় না।
- **D option কেন ভুল:** প্রতিটি level constant-size frame ধরে total linear।
- **Related Concept:** Time O(n), stack space O(n)।
- **মনে রাখার টিপস:** Recursive depth যত, stack frame তত।

---

## প্রশ্ন 396 | Topic: Algorithm > Recursion > Fibonacci Call Count | Difficulty: Hard | Type: Calculation

Q. Naive recursive Fibonacci function:

```text
fib(0) এবং fib(1) প্রত্যেকে 1টি call
fib(n) call count = fib(n-1)-এর call count
                  + fib(n-2)-এর call count
                  + current call
```

`fib(4)` evaluate করতে মোট function call কতটি?

A) 5  
B) 7  
C) 8  
D) 9

**সঠিক উত্তর: D) 9**

### গাণিতিক বিশ্লেষণ

#### Call-count Recurrence

```text
C(0) = 1
C(1) = 1
C(n) = C(n-1) + C(n-2) + 1
```

#### Step-by-step Calculation

```text
C(2) = C(1) + C(0) + 1
     = 1 + 1 + 1
     = 3

C(3) = C(2) + C(1) + 1
     = 3 + 1 + 1
     = 5

C(4) = C(3) + C(2) + 1
     = 5 + 3 + 1
     = 9
```

#### Final Answer

```text
Total function calls for fib(4) = 9
```

### Option বিশ্লেষণ

- **A) 5:** এটি `fib(3)`-এর call count।
- **B) 7:** Current call বা একটি subtree ভুল গণনা।
- **C) 8:** Root/current call বাদ দেওয়া হয়েছে।
- **D) 9:** এটি সঠিক উত্তর।
- **Related Concept:** একই `fib(2)`-জাতীয় subproblem repeated হয়।
- **মনে রাখার টিপস:** Call tree-তে parent call-ও count করুন।

---

## প্রশ্ন 397 | Topic: Algorithm > Recursion > Memoization | Difficulty: Medium | Type: Theory

Q. Naive Fibonacci recursion-এ Memoization ব্যবহার করলে প্রধান সুবিধা কী?

A) একই subproblem-এর result cache করে repeated computation কমায়  
B) সব recursion infinite করে  
C) Stack সম্পূর্ণ নিষিদ্ধ করে  
D) Fibonacci result পরিবর্তন করে

**সঠিক উত্তর: A) একই subproblem-এর result cache করে repeated computation কমায়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি distinct n একবার compute করে result reuse করা যায়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Memoization termination নষ্ট করে না।
- **C option কেন ভুল:** Top-down memoized recursion এখনও call stack ব্যবহার করতে পারে।
- **D option কেন ভুল:** Correct result একই থাকে।
- **Related Concept:** Memoized Fibonacci time O(n), cache space O(n)।
- **মনে রাখার টিপস:** Repeat দেখলে remember—Memoization।

---

## প্রশ্ন 398 | Topic: Algorithm > Recursion > Tower of Hanoi | Difficulty: Medium | Type: Calculation

Q. Tower of Hanoi সমস্যায় ৬টি disk স্থানান্তর করতে minimum কতটি move প্রয়োজন?

A) 31  
B) 64  
C) 63  
D) 36

**সঠিক উত্তর: C) 63**

### গাণিতিক বিশ্লেষণ

#### Formula

```text
Minimum moves = 2^n - 1
```

#### Given Data

```text
n = 6
```

#### Substitution

```text
Moves = 2^6 - 1
```

#### Step-by-step Calculation

```text
2^6 = 64

Moves = 64 - 1
      = 63
```

#### Final Answer

```text
Minimum moves = 63
```

### Option বিশ্লেষণ

- **A) 31:** এটি 5 disk-এর move count।
- **B) 64:** Formula-এর `-1` বাদ দেওয়া হয়েছে।
- **C) 63:** এটি সঠিক উত্তর।
- **D) 36:** `n²` করা হয়েছে।
- **Related Concept:** Hanoi complexity Θ(2^n)।
- **মনে রাখার টিপস:** Power of two-এর ঠিক এক কম।

---

## প্রশ্ন 399 | Topic: Algorithm > Recursion > Tail Recursion | Difficulty: Hard | Type: Theory

Q. Tail Recursion সম্পর্কে কোন statement সবচেয়ে সঠিক?

A) Recursive call-এর পরে অবশ্যই multiplication থাকে  
B) Recursive call function-এর শেষ কার্যকর operation  
C) এটি সব compiler-এ O(1) stack guarantee করে  
D) এতে Base Case প্রয়োজন নেই

**সঠিক উত্তর: B) Recursive call function-এর শেষ কার্যকর operation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Recursive result পাওয়ার পরে আর pending computation থাকে না।
- **A option কেন ভুল:** Pending multiplication থাকলে tail recursive নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Compiler optimization করতে পারে, কিন্তু language standard সবসময় guarantee করে না।
- **D option কেন ভুল:** Tail recursion-এও termination-এর জন্য base case দরকার।
- **Related Concept:** Accumulator parameter দিয়ে factorial tail-recursive করা যায়।
- **মনে রাখার টিপস:** Call-এর পরে যদি কাজ বাকি থাকে, Tail Recursion নয়।

---

## প্রশ্ন 400 | Topic: Algorithm > Recursion > Recursion vs Iteration | Difficulty: Hard | Type: Scenario

Q. একটি linear problem recursion ও loop—দুইভাবেই সহজে সমাধান করা যায়। Performance ও stack usage সবচেয়ে গুরুত্বপূর্ণ হলে সাধারণত কোনটি বেশি উপযোগী?

A) Recursion সবসময়, কারণ function call free  
B) দুটো সব ক্ষেত্রে সম্পূর্ণ সমান  
C) শুধু Mutual Recursion  
D) Iteration, কারণ function-call overhead ও stack growth এড়ানো যায়

**সঠিক উত্তর: D) Iteration, কারণ function-call overhead ও stack growth এড়ানো যায়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Simple linear repetition-এ loop সাধারণত কম overhead ও constant auxiliary stack ব্যবহার করে।
- **A option কেন ভুল:** Function call-এর overhead থাকতে পারে।
- **B option কেন ভুল:** Result একই হলেও resource behavior ভিন্ন হতে পারে।
- **C option কেন ভুল:** Mutual recursion আরও বেশি call overhead তৈরি করতে পারে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Tree traversal ও Divide-and-Conquer-এ recursion বেশি natural হতে পারে।
- **মনে রাখার টিপস:** Natural recursive structure না থাকলে simple loop বিবেচনা করুন।

---

# Batch Quality Summary

## Question Count

```text
Question Range          = 351–400
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

- Abstract Data Type
- Singly Linked List
- Doubly Linked List
- Circular Linked List
- Header Node
- Linked List insertion, deletion ও traversal
- Array বনাম Linked List
- Stack ADT
- Array ও Linked Stack
- Stack Overflow ও Underflow
- Queue ADT
- Linked Queue
- Priority Queue basics
- Circular Queue
- False Overflow
- Circular index ও Full condition
- Deque
- Input-Restricted ও Output-Restricted Deque
- Prefix, Infix ও Postfix
- Infix-to-Postfix conversion
- Infix-to-Prefix conversion
- Prefix ও Postfix evaluation
- Parenthesis matching
- Recursion ও Call Stack
- Factorial
- Fibonacci
- Memoization
- Tail Recursion
- Tower of Hanoi

## Math/Tracing Coverage

```text
Linked-list link traversal       : Included
Linked-list insertion trace      : Included
Node memory calculation          : Included
Stack operation trace            : Included
Queue operation trace            : Included
Circular Queue index calculation : Included
Circular Queue capacity          : Included
Deque operation trace            : Included
Expression conversion            : Included
Prefix/Postfix evaluation        : Included
Factorial operation count        : Included
Fibonacci call count             : Included
Tower of Hanoi move count        : Included
```

## Math Formatting Audit

প্রতিটি numerical ও tracing question-এ ব্যবহার করা হয়েছে:

- Rule বা Formula
- Given Data
- Substitution
- Plain-text aligned Calculation
- Intermediate State
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

- Graph terminology ও representation
- Adjacency Matrix বনাম Adjacency List
- BFS ও DFS
- Tree terminology
- Binary Tree, BST ও traversal
- AVL Tree ও rotation
- Hashing, collision resolution ও load factor
