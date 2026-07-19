# ১৯তম নিবন্ধন — প্রভাষক ICT

## Section 3: Data Structure, Algorithm & Combinatorial Optimization

### Batch 11 — Question 451–500

**Subject Code:** 452  
**Covered Area:** B-Tree, B+ Tree, Dijkstra, Bellman–Ford, Floyd–Warshall, Minimum Spanning Tree, Kruskal, Prim, Topological Sorting, Greedy Strategy, Fractional Knapsack, Activity Selection, Huffman Encoding এবং Task Scheduling  
**Theory/Scenario MCQ:** 30  
**Math/Calculation/Tracing MCQ:** 20  
**Difficulty:** Easy 13, Medium 25, Hard 12  
**Answer Distribution:** A = 13, B = 13, C = 12, D = 12

> **Math-format policy:** সব Formula, Given Data, Substitution, table update, graph state, edge selection ও calculation plain-text aligned block-এ দেখানো হয়েছে। Raw LaTeX command ব্যবহার করা হয়নি।

---

# Chapter Theory 35: B-Tree এবং B+ Tree

## মূল ধারণা

`B-Tree` ও `B+ Tree` হলো height-balanced multiway search tree। Disk page বা storage block থেকে data পড়া main-memory comparison-এর তুলনায় অনেক ব্যয়বহুল। তাই একটি node-এ অনেক key ও child pointer রেখে branching factor বাড়ানো হয়। এর ফলে tree height এবং disk I/O কমে।

এই README-তে `order m` বলতে একটি node-এর maximum child সংখ্যা বোঝানো হয়েছে।

```text
Maximum children                    = m
Maximum keys                        = m - 1
Minimum non-root children           = ceil(m / 2)
Minimum non-root keys               = ceil(m / 2) - 1
```

সব leaf একই level-এ থাকে। Search current node-এর sorted key পরীক্ষা করে উপযুক্ত child অনুসরণ করে। Insertion leaf-এ হয়; full node split হলে median parent-এ promote হয়। Split root পর্যন্ত পৌঁছালে tree height বাড়ে। Deletion-এ borrow, merge, predecessor বা successor replacement লাগতে পারে।

## B-Tree বনাম B+ Tree

```text
বিষয়                  B-Tree                     B+ Tree
----------------------------------------------------------------
Record location        Internal ও leaf            শুধু leaf
Search end             Internal-এ শেষ হতে পারে    Leaf-এ শেষ
Leaf connection        সাধারণত linked নয়          সাধারণত linked
Range query            ভালো                       খুব কার্যকর
Internal fan-out       তুলনামূলক কম               তুলনামূলক বেশি
```

B+ Tree-তে internal node search key ও child pointer রাখে। Actual record বা record pointer leaf-এ থাকে। Leaf-গুলো sorted linked sequence হওয়ায় lower bound খুঁজে পরপর leaf scan করে range query দ্রুত করা যায়।

## Common Mistakes

- Order m-কে maximum key count ধরা
- Root-এর minimum occupancy-কে ordinary node-এর মতো ধরা
- B+ Tree internal node-এ সব record থাকে মনে করা
- Split-এর সময় promoted key ও child distribution ভুল করা
- Hash Index-কে ordered range query-এর জন্য B+ Tree-এর চেয়ে ভালো ধরা

## Exam Tips

```text
Order m                 -> Maximum key m - 1
Non-root minimum key    -> ceil(m/2) - 1
B+ Tree data            -> Leaf
B+ Tree leaves          -> Linked
Disk index              -> B-Tree/B+ Tree
Range query             -> B+ Tree
```

---

# Chapter Theory 36: Shortest Path Algorithms

## Relaxation

Shortest path algorithm-এর মূল operation হলো `relaxation`।

```text
candidate = distance[u] + weight(u,v)

if candidate < distance[v]:
    distance[v] = candidate
    parent[v]   = u
```

## Dijkstra

Dijkstra single-source shortest path বের করে, যদি সব edge weight non-negative হয়। Source distance 0 এবং অন্য distance infinity দিয়ে শুরু হয়। Minimum tentative distance vertex finalize করে তার edge relax করা হয়।

```text
Priority Queue implementation:
Time ≈ O((V + E) log V)
```

Negative edge থাকলে finalized distance পরে কমে যেতে পারে; তাই standard Dijkstra সঠিক নয়।

## Bellman–Ford

Bellman–Ford negative edge handle করতে পারে। সব edge `V−1` pass relax করা হয়। আরও একটি pass-এ update হলে source থেকে reachable negative cycle আছে।

```text
Time = O(VE)
```

## Floyd–Warshall

সব pair-এর shortest distance বের করে।

```text
D[i][j] = min(D[i][j], D[i][k] + D[k][j])
```

```text
Time  = O(V^3)
Space = O(V^2)
```

Negative edge handle করতে পারে। Final matrix-এ `D[i][i] < 0` negative cycle-এর indication।

## Algorithm Selection

```text
Unweighted graph             -> BFS
Non-negative weighted graph  -> Dijkstra
Negative edge                -> Bellman–Ford
All-pairs                    -> Floyd–Warshall
DAG                          -> Topological-order relaxation
```

## Common Mistakes

- Dijkstra negative edge-এ ব্যবহার করা
- Bellman–Ford main pass V ধরা; সঠিক V−1
- Path cost-এ edge sign উপেক্ষা করা
- Floyd–Warshall-এ direct path ও via-k path তুলনা না করা
- Minimum edge count ও minimum weight path একই মনে করা

---

# Chapter Theory 37: Minimum Spanning Tree

Connected weighted undirected graph-এর spanning tree সব vertex connect করে, cycle রাখে না এবং `V−1` edge ধারণ করে। সব spanning tree-এর মধ্যে minimum total weight-এর tree হলো MST।

## Kruskal

```text
1. Edge weight অনুযায়ী sort
2. ছোট edge থেকে শুরু
3. Cycle না হলে select
4. V - 1 edge হলে stop
```

Cycle detection-এর জন্য Disjoint Set Union বা Union-Find কার্যকর।

```text
Time ≈ O(E log E)
```

## Prim

একটি vertex থেকে শুরু করে current tree ও বাইরের vertex-এর cut crossing minimum edge নির্বাচন করে tree বাড়ায়।

```text
Priority Queue implementation:
Time ≈ O(E log V)
```

## Cut এবং Cycle Property

```text
Cut Property:
Cut crossing unique minimum edge প্রতিটি MST-তে থাকে।

Cycle Property:
Cycle-এর unique maximum edge কোনো MST-তে থাকে না।
```

সব edge weight distinct হলে MST unique। Disconnected graph-এর একক spanning tree নেই; প্রতিটি component-এর MST নিয়ে minimum spanning forest পাওয়া যায়।

## Kruskal বনাম Prim

```text
Kruskal                         Prim
-------------------------------------------------------
Global edge selection           One tree grows
Edge sorting                    Cut frontier
DSU cycle check                 Priority Queue
Sparse graph-এ সুবিধাজনক        Dense graph-এও কার্যকর
Forest তৈরি করতে পারে           Component ধরে চালাতে হয়
```

## Common Mistakes

- Directed graph-এ standard MST প্রয়োগ করা
- Vটি edge নির্বাচন করা
- Kruskal-এ cycle check বাদ দেওয়া
- Prim-এ current tree-এর বাইরে global edge নেওয়া
- MST-কে source shortest-path tree মনে করা

---

# Chapter Theory 38: Topological Sorting

Topological order হলো DAG vertex-এর linear ordering, যেখানে edge `u -> v` থাকলে `u`, `v`-এর আগে থাকবে। Directed cycle থাকলে এমন ordering অসম্ভব।

## Kahn’s Algorithm

```text
1. সব in-degree গণনা
2. In-degree 0 vertex Queue-তে
3. Queue থেকে remove করে output
4. Outgoing neighbour-এর in-degree কমান
5. নতুন zero in-degree vertex Queue-তে
6. Processed count < V হলে cycle
```

Time complexity:

```text
O(V + E)
```

## DFS Method

DFS-এ vertex-এর সব outgoing neighbour process শেষ হলে stack-এ push করা হয়। Stack pop order topological order দেয়। Cycle detection-এর জন্য recursion-stack বা color state লাগে।

একই সময়ে একাধিক zero in-degree vertex থাকলে একাধিক valid order হতে পারে।

## Application

- Course prerequisite
- Build dependency
- Package installation
- Task scheduling
- Compilation order
- Spreadsheet dependency

## Exam Tips

```text
Topological sort -> DAG
Kahn             -> In-degree + Queue
DFS              -> Reverse finish order
Processed < V    -> Cycle
Edge u -> v      -> u আগে, v পরে
```

---

# Chapter Theory 39: Greedy Strategy এবং Classic Problems

Greedy algorithm প্রতিটি ধাপে locally best choice নেয়। Greedy সঠিক হওয়ার জন্য সাধারণত `greedy-choice property` এবং `optimal substructure` দরকার। Local best সব problem-এ global best দেয় না; correctness proof প্রয়োজন।

## Fractional Knapsack

Item-এর fraction নেওয়া যায়।

```text
Priority = Value / Weight ratio
```

Highest ratio item আগে নেওয়া হয়। শেষ item আংশিক নেওয়া যায়। Ratio-based greedy optimal।

## 0/1 Knapsack

Item পুরো নিতে হবে বা বাদ দিতে হবে। Ratio greedy সবসময় optimal নয়। Dynamic Programming বা Branch-and-Bound ব্যবহার করা যেতে পারে।

## Activity Selection

Maximum non-overlapping activity select করতে:

```text
Earliest finish time first
```

একটি activity select করার পরে তার finish time-এর আগে শুরু হওয়া activity reject করা হয়।

## Huffman Encoding

```text
1. Frequency Min-Heap-এ রাখুন
2. দুই minimum node remove
3. Sum frequency-এর parent বানান
4. Parent আবার heap-এ
5. এক root পর্যন্ত repeat
```

Huffman code prefix-free এবং given frequency-এর জন্য optimal prefix code। Frequent symbol সাধারণত ছোট code পায়।

## Job Sequencing with Deadline

Unit-time job হলে:

```text
Profit descending order
প্রতিটি job deadline-এর আগে latest free slot-এ
```

## Greedy Coin Change Limitation

```text
Coins  = {1, 3, 4}
Amount = 6

Greedy  = 4 + 1 + 1 = 3 coins
Optimal = 3 + 3     = 2 coins
```

## Common Mistakes

- 0/1 Knapsack-এ Fractional rule প্রয়োগ করা
- Activity Selection-এ earliest start নেওয়া
- Huffman-এ দুই highest frequency merge করা
- Arbitrary coin system-এ greedy optimal ধরা
- Greedy solution proof ছাড়া গ্রহণ করা

---

# MCQ Practice: Batch 11

## প্রশ্ন 451 | Topic: Data Structure > B-Tree > Core Property | Difficulty: Easy | Type: Theory

Q. B-Tree-এর সব leaf node সম্পর্কে কোন statement সঠিক?

A) সব leaf একই depth বা level-এ থাকে  
B) Leaf node-এর কোনো key থাকে না  
C) প্রতিটি leaf-এর ঠিক দুইটি child থাকে  
D) Leaf-গুলো random depth-এ থাকে  

**সঠিক উত্তর: A) সব leaf একই depth বা level-এ থাকে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** B-Tree height-balanced multiway search tree; root থেকে সব leaf-এর distance সমান।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Leaf node-এ key থাকে।
- **C option কেন ভুল:** Leaf-এর কোনো child থাকে না।
- **D option কেন ভুল:** Random depth হলে tree balanced থাকত না।
- **Related Concept:** B+ Tree-তেও সব leaf একই level-এ থাকে।
- **মনে রাখার টিপস:** B-Tree balance মানে সব leaf সমান গভীরে।

---

## প্রশ্ন 452 | Topic: Data Structure > B-Tree > Maximum Keys | Difficulty: Medium | Type: Calculation

Q. Order 7 B-Tree-এ একটি node সর্বোচ্চ কতটি key ধারণ করতে পারে? এখানে order মানে maximum child সংখ্যা।

A) 7  
B) 6  
C) 5  
D) 8  

**সঠিক উত্তর: B) 6**

### গাণিতিক/Tracing বিশ্লেষণ
#### Formula
```text
Maximum keys = m - 1
```
#### Given Data
```text
m = 7
```
#### Calculation
```text
Maximum keys = 7 - 1
             = 6
```
#### Final Answer
```text
Maximum keys per node = 6
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Order m হলে maximum key = m−1।
- **A option কেন ভুল:** Maximum child count-কে key count ধরা হয়েছে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** দুই কমানো হয়েছে।
- **D option কেন ভুল:** এক যোগ করা হয়েছে।
- **Related Concept:** kটি key-যুক্ত internal node-এর সর্বোচ্চ child k+1।
- **মনে রাখার টিপস:** Order m দেখলে max key m−1।

---

## প্রশ্ন 453 | Topic: Data Structure > B+ Tree > Record Placement | Difficulty: Easy | Type: Theory

Q. B+ Tree-তে actual record বা record pointer সাধারণত কোথায় থাকে?

A) শুধু root node-এ  
B) প্রতিটি internal node-এ বাধ্যতামূলকভাবে  
C) Leaf node-এ  
D) Tree-এর বাইরে, index-এর সঙ্গে সম্পর্ক নেই  

**সঠিক উত্তর: C) Leaf node-এ**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** B+ Tree internal node search guide করে; actual data entry leaf level-এ থাকে।
- **A option কেন ভুল:** Root সব record রাখে না।
- **B option কেন ভুল:** Internal node সাধারণত separator key ও child pointer রাখে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Leaf entry record বা record location নির্দেশ করে।
- **Related Concept:** Internal key match হলেও search leaf পর্যন্ত যায়।
- **মনে রাখার টিপস:** B+ Tree-এর data lives at leaves।

---

## প্রশ্ন 454 | Topic: Data Structure > B-Tree > Search I/O | Difficulty: Medium | Type: Calculation

Q. একটি B-Tree-এর root থেকে leaf পর্যন্ত 4টি level আছে এবং প্রতিটি level access-এ সর্বোচ্চ 1টি page read লাগে। Worst-case search-এ কতটি page read লাগতে পারে?

A) 3  
B) 5  
C) 8  
D) 4  

**সঠিক উত্তর: D) 4**

### গাণিতিক/Tracing বিশ্লেষণ
#### Given Data
```text
Root-to-leaf levels = 4
Read per level      = 1 page
```
#### Calculation
```text
Total page reads = 4 × 1
                 = 4
```
#### Level Trace
```text
Level 1: Root
Level 2: Internal
Level 3: Internal
Level 4: Leaf
```
#### Final Answer
```text
Maximum page reads = 4
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** চারটি level-এর প্রত্যেকটি একবার পড়লে মোট 4 page read হয়।
- **A option কেন ভুল:** Root বা leaf-এর একটি level বাদ দেওয়া হয়েছে।
- **B option কেন ভুল:** একটি অতিরিক্ত page যোগ করা হয়েছে।
- **C option কেন ভুল:** প্রতি level-এ দুই page ধরা হয়েছে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Root memory-তে cached থাকলে বাস্তব disk I/O কম হতে পারে।
- **মনে রাখার টিপস:** Level count ও edge count গুলিয়ে ফেলবেন না।

---

## প্রশ্ন 455 | Topic: Data Structure > B-Tree > Root Split | Difficulty: Hard | Type: Tracing

Q. Order 4 B-Tree-এর full root `[10, 20, 30]`-কে top-down insertion-এ আগে split করে তারপর key 25 insert করা হলো। Promoted key কোনটি?

A) 20  
B) 10  
C) 25  
D) 30  

**সঠিক উত্তর: A) 20**

### গাণিতিক/Tracing বিশ্লেষণ
#### Before Split
```text
Root = [10, 20, 30]
```
#### Split
```text
Promote    = 20
Left child = [10]
Right child= [30]
```
#### Insert 25
```text
25 > 20 and 25 < 30

       [20]
      /       [10]  [25,30]
```
#### Final Answer
```text
Promoted key = 20
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Order 4 node-এর full তিন key split করলে middle key 20 parent/root হয়; পরে 25 right child-এ insert হয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Minimum key promote করা হয়েছে।
- **C option কেন ভুল:** 25 split-এর পরে insert হয়; promoted median নয়।
- **D option কেন ভুল:** Maximum key promote করা হয়েছে।
- **Related Concept:** Root split হলে tree height এক বাড়ে।
- **মনে রাখার টিপস:** Full 3-key node split: middle key ওপরে।

---

## প্রশ্ন 456 | Topic: Data Structure > B+ Tree > Range Query | Difficulty: Medium | Type: Theory

Q. B+ Tree range query-তে বিশেষভাবে কার্যকর হওয়ার প্রধান কারণ কোনটি?

A) Internal node-এ সব complete record থাকে  
B) Leaf node-গুলো sorted এবং linked থাকে  
C) কোনো search key লাগে না  
D) Tree সবসময় height 1  

**সঠিক উত্তর: B) Leaf node-গুলো sorted এবং linked থাকে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Lower-bound leaf পাওয়ার পর linked leaf ধরে sequential scan করা যায়।
- **A option কেন ভুল:** Actual record সাধারণত leaf-এ থাকে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Range locate করতে search key দরকার।
- **D option কেন ভুল:** Large B+ Tree-এর একাধিক level থাকে।
- **Related Concept:** Database BETWEEN query ও ordered scan-এ B+ Tree উপযোগী।
- **মনে রাখার টিপস:** B+ leaf link = fast range scan।

---

## প্রশ্ন 457 | Topic: Data Structure > B-Tree > Minimum Keys | Difficulty: Hard | Type: Calculation

Q. Order 8 B-Tree-এ একটি non-root internal node-এর minimum key সংখ্যা কত? এখানে order মানে maximum child সংখ্যা।

A) 4  
B) 2  
C) 3  
D) 7  

**সঠিক উত্তর: C) 3**

### গাণিতিক/Tracing বিশ্লেষণ
#### Formula
```text
Minimum children = ceil(m / 2)
Minimum keys     = Minimum children - 1
```
#### Given Data
```text
m = 8
```
#### Calculation
```text
Minimum children = ceil(8 / 2)
                 = 4

Minimum keys = 4 - 1
             = 3
```
#### Final Answer
```text
Minimum keys = 3
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Minimum children ceil(8/2)=4; তাই minimum key = 4−1 = 3।
- **A option কেন ভুল:** Minimum child count নেওয়া হয়েছে।
- **B option কেন ভুল:** Ceiling ও minus-one rule ভুল হয়েছে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Maximum key count নেওয়া হয়েছে।
- **Related Concept:** Root-এর minimum occupancy rule আলাদা।
- **মনে রাখার টিপস:** Non-root min key = ceil(m/2)−1।

---

## প্রশ্ন 458 | Topic: Data Structure > B+ Tree > Leaf Link | Difficulty: Easy | Type: Theory

Q. B+ Tree-এর leaf node-গুলো সাধারণত কেন linked থাকে?

A) Root delete করার জন্য  
B) Hash collision handle করার জন্য  
C) Tree-কে binary করার জন্য  
D) Sequential ও range traversal দ্রুত করার জন্য  

**সঠিক উত্তর: D) Sequential ও range traversal দ্রুত করার জন্য**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রথম relevant leaf পাওয়ার পর পরবর্তী key-এর জন্য parent-এ ফিরে যেতে হয় না।
- **A option কেন ভুল:** Root deletion-এর সঙ্গে সম্পর্ক নেই।
- **B option কেন ভুল:** এটি hashing নয়।
- **C option কেন ভুল:** B+ Tree multiway tree।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Leaf link next leaf-এ যায়; কখনও doubly linked-ও হয়।
- **মনে রাখার টিপস:** Linked leaves = ordered scanning।

---

## প্রশ্ন 459 | Topic: Data Structure > B-Tree > Disk Index | Difficulty: Medium | Type: Scenario

Q. কোটি কোটি record disk-এ index করতে ordinary unbalanced BST-এর পরিবর্তে B-Tree বেছে নেওয়ার প্রধান কারণ কী?

A) বড় fan-out tree height ও disk I/O কমায়  
B) B-Tree কোনো comparison করে না  
C) B-Tree সব search O(1) করে  
D) B-Tree-এর node-এ শুধু একটি key থাকে  

**সঠিক উত্তর: A) বড় fan-out tree height ও disk I/O কমায়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** এক disk page-এ বহু key ও child রাখায় অল্প level-এ বিশাল index ধারণ করা যায়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Key comparison প্রয়োজন।
- **C option কেন ভুল:** Search logarithmic; constant নয়।
- **D option কেন ভুল:** এক node বহু key রাখে।
- **Related Concept:** B-Tree node size সাধারণত storage block size-এর সঙ্গে মিলিয়ে নেওয়া হয়।
- **মনে রাখার টিপস:** Disk index-এ height কমানোই বড় লাভ।

---

## প্রশ্ন 460 | Topic: Data Structure > B+ Tree > Index Selection | Difficulty: Hard | Type: Scenario

Q. একটি database workload-এ equality search-এর পাশাপাশি প্রচুর ordered range scan আছে। কোন index সবচেয়ে উপযুক্ত?

A) Unordered array  
B) B+ Tree index  
C) Stack  
D) Linear Queue  

**সঠিক উত্তর: B) B+ Tree index**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** B+ Tree equality search, ordered traversal ও range scan—সব সমর্থন করে।
- **A option কেন ভুল:** Unordered array-এ full scan লাগতে পারে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Stack indexing structure নয়।
- **D option কেন ভুল:** Queue FIFO processing দেয়।
- **Related Concept:** শুধু exact-match workload-এ Hash Index কার্যকর হতে পারে।
- **মনে রাখার টিপস:** Equality + Range = B+ Tree।

---

## প্রশ্ন 461 | Topic: Algorithm > Dijkstra > Weight Restriction | Difficulty: Easy | Type: Theory

Q. Standard Dijkstra Algorithm সঠিকভাবে কাজ করার জন্য edge weight সম্পর্কে কোন শর্ত প্রয়োজন?

A) সব edge weight একই হতে হবে  
B) সব edge weight integer হতে হবে  
C) Edge weight non-negative হতে হবে  
D) Graph complete হতে হবে  

**সঠিক উত্তর: C) Edge weight non-negative হতে হবে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Negative edge finalized vertex-এর distance পরে কমিয়ে দিতে পারে; non-negative weight assumption এই ঝুঁকি দূর করে।
- **A option কেন ভুল:** Weight ভিন্ন হতে পারে।
- **B option কেন ভুল:** Non-negative real weight-ও গ্রহণযোগ্য।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Graph complete হওয়া দরকার নেই।
- **Related Concept:** Negative edge থাকলে Bellman–Ford ব্যবহার করা যায়।
- **মনে রাখার টিপস:** Dijkstra dislikes negative weights।

---

## প্রশ্ন 462 | Topic: Algorithm > Dijkstra > Distance Trace | Difficulty: Hard | Type: Tracing

Q. Source `S` থেকে directed weighted edge:
```text
S -> A = 4
S -> B = 1
B -> A = 2
A -> C = 1
B -> C = 5
```
Dijkstra ব্যবহার করলে `S` থেকে `C`-এর shortest distance কত?

A) 5  
B) 6  
C) 7  
D) 4  

**সঠিক উত্তর: D) 4**

### গাণিতিক/Tracing বিশ্লেষণ
#### Initial
```text
dist[S]=0, dist[A]=∞, dist[B]=∞, dist[C]=∞
```
#### Process S
```text
dist[A] = 4
dist[B] = 1
```
#### Process B
```text
dist[A] = min(4, 1+2) = 3
dist[C] = min(∞, 1+5) = 6
```
#### Process A
```text
dist[C] = min(6, 3+1) = 4
```
#### Final Answer
```text
Shortest path = S -> B -> A -> C
Distance      = 4
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** সেরা path `S -> B -> A -> C`; cost `1+2+1 = 4`।
- **A option কেন ভুল:** `S->A->C` path নেওয়া হয়েছে।
- **B option কেন ভুল:** `S->B->C` path নেওয়া হয়েছে।
- **C option কেন ভুল:** Edge cost ভুল যোগ করা হয়েছে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Tentative distance finalize হওয়ার আগে একাধিকবার কমতে পারে।
- **মনে রাখার টিপস:** Minimum tentative vertex আগে process করুন।

---

## প্রশ্ন 463 | Topic: Algorithm > Dijkstra > Negative Edge | Difficulty: Medium | Type: Theory

Q. Graph-এ negative edge থাকলে Standard Dijkstra ব্যবহার না করার প্রধান কারণ কী?

A) Finalized distance পরে আরও কমে যেতে পারে  
B) Dijkstra কোনো edge relax করে না  
C) Dijkstra শুধু tree-তে চলে  
D) Negative edge graph-কে disconnected করে  

**সঠিক উত্তর: A) Finalized distance পরে আরও কমে যেতে পারে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Greedy finalization non-negative edge assumption-এর ওপর নির্ভর করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Relaxation Dijkstra-এর মূল operation।
- **C option কেন ভুল:** General graph-এ কাজ করে।
- **D option কেন ভুল:** Negative weight connectivity বদলায় না।
- **Related Concept:** Reachable negative cycle থাকলে finite shortest path নাও থাকতে পারে।
- **মনে রাখার টিপস:** Negative edge ভাঙে Dijkstra-এর proof।

---

## প্রশ্ন 464 | Topic: Algorithm > Bellman-Ford > Relaxation Pass | Difficulty: Medium | Type: Calculation

Q. ৮টি vertex-এর graph-এ Bellman–Ford main relaxation phase-এ সব edge সর্বোচ্চ কতবার pass করা হয়?

A) 8  
B) 7  
C) 6  
D) 64  

**সঠিক উত্তর: B) 7**

### গাণিতিক/Tracing বিশ্লেষণ
#### Formula
```text
Main passes = V - 1
```
#### Given Data
```text
V = 8
```
#### Calculation
```text
Passes = 8 - 1
       = 7
```
#### Final Answer
```text
Main relaxation passes = 7
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Simple shortest path সর্বোচ্চ V−1 edge ধারণ করে; তাই 7 main pass।
- **A option কেন ভুল:** Extra cycle-check pass-সহ count করা হয়েছে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এক pass কম।
- **D option কেন ভুল:** V² করা হয়েছে।
- **Related Concept:** V-th pass negative-cycle detection-এর জন্য।
- **মনে রাখার টিপস:** Bellman main pass = V−1।

---

## প্রশ্ন 465 | Topic: Algorithm > Bellman-Ford > Relaxation | Difficulty: Hard | Type: Calculation

Q. বর্তমানে `dist[U] = 6`, `dist[V] = 15` এবং edge `U -> V`-এর weight `-4`। Relaxation-এর পরে `dist[V]` কত হবে?

A) 11  
B) 15  
C) 2  
D) -10  

**সঠিক উত্তর: C) 2**

### গাণিতিক/Tracing বিশ্লেষণ
#### Formula
```text
candidate = dist[U] + weight(U,V)
dist[V]   = min(dist[V], candidate)
```
#### Calculation
```text
candidate = 6 + (-4)
          = 2

dist[V] = min(15, 2)
        = 2
```
#### Final Answer
```text
Updated dist[V] = 2
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Candidate distance `6 + (-4) = 2`; এটি 15-এর চেয়ে ছোট।
- **A option কেন ভুল:** 15−4 করা হয়েছে; source distance ব্যবহার করা হয়নি।
- **B option কেন ভুল:** Better path উপেক্ষা করা হয়েছে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Sign ও distance ভুল মিশ্রিত হয়েছে।
- **Related Concept:** Relaxation current destination ও new candidate তুলনা করে।
- **মনে রাখার টিপস:** New path = source distance + edge weight।

---

## প্রশ্ন 466 | Topic: Algorithm > Bellman-Ford > Negative Cycle | Difficulty: Easy | Type: Theory

Q. Bellman–Ford-এ V−1 pass-এর পরে আরও একটি pass-এ distance update হলে কী বোঝায়?

A) Graph অবশ্যই complete  
B) Source unreachable  
C) সব edge positive  
D) Source থেকে reachable negative-weight cycle আছে  

**সঠিক উত্তর: D) Source থেকে reachable negative-weight cycle আছে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** V−1 edge-এর simple path-এর পরেও improvement মানে cycle ব্যবহার করে cost কমছে।
- **A option কেন ভুল:** Completeness-এর সঙ্গে সম্পর্ক নেই।
- **B option কেন ভুল:** Update হওয়া মানে কিছু path reachable।
- **C option কেন ভুল:** Positive edge graph-এ এমন improvement হওয়ার কথা নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Unreachable negative cycle source-based run detect নাও করতে পারে।
- **মনে রাখার টিপস:** Extra pass update = negative cycle warning।

---

## প্রশ্ন 467 | Topic: Algorithm > Floyd-Warshall > Problem Type | Difficulty: Medium | Type: Theory

Q. Floyd–Warshall Algorithm প্রধানত কোন সমস্যা সমাধান করে?

A) All-pairs shortest path  
B) Minimum Spanning Tree  
C) Topological sorting  
D) String matching  

**সঠিক উত্তর: A) All-pairs shortest path**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** এটি প্রতিটি vertex pair-এর shortest distance matrix compute করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** MST-এর জন্য Kruskal/Prim।
- **C option কেন ভুল:** Topological sort DAG ordering।
- **D option কেন ভুল:** এটি string algorithm নয়।
- **Related Concept:** Warshall transitive closure algorithm-এর structure কাছাকাছি।
- **মনে রাখার টিপস:** Floyd = every source to every destination।

---

## প্রশ্ন 468 | Topic: Algorithm > Floyd-Warshall > Matrix Update | Difficulty: Hard | Type: Calculation

Q. Floyd–Warshall update-এ বর্তমানে:
```text
D[i][j] = 12
D[i][k] = 5
D[k][j] = 4
```
Intermediate `k` বিবেচনা করার পরে নতুন `D[i][j]` কত?

A) 12  
B) 9  
C) 21  
D) 1  

**সঠিক উত্তর: B) 9**

### গাণিতিক/Tracing বিশ্লেষণ
#### Formula
```text
D[i][j] = min(D[i][j], D[i][k] + D[k][j])
```
#### Calculation
```text
via_k = 5 + 4
      = 9

D[i][j] = min(12, 9)
        = 9
```
#### Final Answer
```text
Updated D[i][j] = 9
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Direct cost 12 এবং via-k cost 5+4=9; minimum 9।
- **A option কেন ভুল:** Better route উপেক্ষা করা হয়েছে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** তিন distance যোগ করা হয়েছে।
- **D option কেন ভুল:** Difference নেওয়া হয়েছে।
- **Related Concept:** Via-k route shorter না হলে old value অপরিবর্তিত থাকে।
- **মনে রাখার টিপস:** Direct বনাম via-k—যেটি ছোট।

---

## প্রশ্ন 469 | Topic: Algorithm > Floyd-Warshall > Update Count | Difficulty: Medium | Type: Calculation

Q. Floyd–Warshall-এর তিনটি nested loop-এ ৫টি vertex থাকলে `(i,j,k)` combination মোট কতটি হবে?

A) 25  
B) 75  
C) 125  
D) 625  

**সঠিক উত্তর: C) 125**

### গাণিতিক/Tracing বিশ্লেষণ
#### Formula
```text
Total combinations = V × V × V
                   = V^3
```
#### Calculation
```text
5 × 5 × 5 = 125
```
#### Final Answer
```text
Total combinations = 125
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** তিনটি loop প্রত্যেকটি V বার চলে; total V³ = 125।
- **A option কেন ভুল:** শুধু দুই loop count করা হয়েছে।
- **B option কেন ভুল:** 5×5×3 করা হয়েছে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** V⁴ করা হয়েছে।
- **Related Concept:** Floyd–Warshall time complexity O(V³)।
- **মনে রাখার টিপস:** All pairs + every intermediate = three V loops।

---

## প্রশ্ন 470 | Topic: Algorithm > Shortest Path > Path Cost | Difficulty: Medium | Type: Calculation

Q. একটি path-এর edge weight যথাক্রমে `3, -2, 5, 1`। Path cost কত?

A) 5  
B) 6  
C) 9  
D) 7  

**সঠিক উত্তর: D) 7**

### গাণিতিক/Tracing বিশ্লেষণ
#### Calculation
```text
Cost = 3 + (-2) + 5 + 1
     = 1 + 5 + 1
     = 7
```
#### Final Answer
```text
Path cost = 7
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** সব edge weight signসহ যোগ করলে `3−2+5+1 = 7`।
- **A option কেন ভুল:** একটি term বাদ গেছে।
- **B option কেন ভুল:** Negative sign ভুল handle হয়েছে।
- **C option কেন ভুল:** −2-কে +2 ধরা হয়েছে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** কম edge-এর path সবসময় কম cost নয়।
- **মনে রাখার টিপস:** Weight signসহ সব edge যোগ করুন।

---

## প্রশ্ন 471 | Topic: Algorithm > MST > Definition | Difficulty: Easy | Type: Theory

Q. Minimum Spanning Tree কোন ধরনের graph-এর জন্য standardভাবে সংজ্ঞায়িত?

A) Connected weighted undirected graph  
B) শুধু directed acyclic graph  
C) শুধু unweighted complete graph  
D) যেকোনো disconnected directed graph  

**সঠিক উত্তর: A) Connected weighted undirected graph**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Spanning tree সব vertex connect করে, undirected ও acyclic; weight total minimum করা হয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Directed graph-এর জন্য arborescence আলাদা concept।
- **C option কেন ভুল:** Weight না থাকলে minimum cost distinction থাকে না।
- **D option কেন ভুল:** Disconnected graph-এর একক spanning tree নেই।
- **Related Concept:** Disconnected undirected graph-এ minimum spanning forest হয়।
- **মনে রাখার টিপস:** MST = connected, weighted, undirected।

---

## প্রশ্ন 472 | Topic: Algorithm > MST > Edge Count | Difficulty: Easy | Type: Calculation

Q. ১২টি vertex-এর একটি MST-তে edge সংখ্যা কত?

A) 10  
B) 11  
C) 12  
D) 24  

**সঠিক উত্তর: B) 11**

### গাণিতিক/Tracing বিশ্লেষণ
#### Formula
```text
Edges = V - 1
```
#### Calculation
```text
Edges = 12 - 1
      = 11
```
#### Final Answer
```text
MST edges = 11
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** যেকোনো tree-তে edge = vertex−1; তাই 11।
- **A option কেন ভুল:** এক edge কম।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Vertex count নেওয়া হয়েছে।
- **D option কেন ভুল:** Vertex দ্বিগুণ করা হয়েছে।
- **Related Concept:** Connected V−1 edge graph acyclic হলে tree।
- **মনে রাখার টিপস:** Tree edge সবসময় vertex-এর এক কম।

---

## প্রশ্ন 473 | Topic: Algorithm > Kruskal > Edge Selection | Difficulty: Medium | Type: Theory

Q. Kruskal Algorithm-এর প্রথম প্রধান ধাপ কোনটি?

A) একটি source থেকে distance 0 করা  
B) Vertex-কে topological order-এ রাখা  
C) Edge-গুলো weight অনুযায়ী sort করা  
D) সব edge select করা  

**সঠিক উত্তর: C) Edge-গুলো weight অনুযায়ী sort করা**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Kruskal ছোট weight edge থেকে cycle-free selection করে।
- **A option কেন ভুল:** এটি shortest-path initialization।
- **B option কেন ভুল:** এটি DAG ordering।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Cycle তৈরি করা edge বাদ দিতে হয়।
- **Related Concept:** DSU cycle check দ্রুত করে।
- **মনে রাখার টিপস:** Kruskal = sort, cycle check, select।

---

## প্রশ্ন 474 | Topic: Algorithm > Prim > Growth Strategy | Difficulty: Medium | Type: Theory

Q. Prim Algorithm প্রতিটি ধাপে কোন edge নির্বাচন করে?

A) Graph-এর যেকোনো maximum edge  
B) Cycle-এর সব edge  
C) শুধু source-এর সবচেয়ে বড় edge  
D) Current tree থেকে বাইরের vertex-এ যাওয়া minimum-weight edge  

**সঠিক উত্তর: D) Current tree থেকে বাইরের vertex-এ যাওয়া minimum-weight edge**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Prim visited set ও unvisited set-এর cut crossing minimum edge নেয়।
- **A option কেন ভুল:** Minimum নয়।
- **B option কেন ভুল:** Cycle এড়াতে হয়।
- **C option কেন ভুল:** শুধু source edge-এ সীমাবদ্ধ নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Priority Queue-তে vertex key cheapest current connection বোঝায়।
- **মনে রাখার টিপস:** Prim একটি tree ধীরে ধীরে বড় করে।

---

## প্রশ্ন 475 | Topic: Algorithm > Kruskal > MST Trace | Difficulty: Hard | Type: Tracing

Q. Undirected graph-এর edge:
```text
A-B = 1
B-C = 2
A-C = 3
C-D = 4
B-D = 5
```
Kruskal Algorithm অনুযায়ী MST total weight কত?

A) 7  
B) 8  
C) 6  
D) 9  

**সঠিক উত্তর: A) 7**

### গাণিতিক/Tracing বিশ্লেষণ
#### Sorted Edges
```text
A-B=1, B-C=2, A-C=3, C-D=4, B-D=5
```
#### Selection
```text
Select A-B = 1
Select B-C = 2
Skip A-C   = 3  (cycle)
Select C-D = 4
```
#### Total
```text
1 + 2 + 4 = 7
```
#### Final Answer
```text
MST weight = 7
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** A-B, B-C select; A-C cycle হওয়ায় skip; C-D select। Total `1+2+4=7`।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Cycle-forming A-C নেওয়া হয়েছে।
- **C option কেন ভুল:** D connect করার cost বাদ গেছে।
- **D option কেন ভুল:** B-D বড় edge নেওয়া হয়েছে।
- **Related Concept:** V=4, তাই 3টি edge select হলেই stop।
- **মনে রাখার টিপস:** Cheapest edge নিন, কিন্তু cycle নয়।

---

## প্রশ্ন 476 | Topic: Algorithm > Prim > MST Trace | Difficulty: Hard | Type: Tracing

Q. Undirected graph:
```text
A-B = 2
A-C = 6
B-C = 3
B-D = 5
C-D = 1
```
Prim Algorithm `A` থেকে শুরু করলে MST total weight কত?

A) 10  
B) 6  
C) 8  
D) 9  

**সঠিক উত্তর: B) 6**

### গাণিতিক/Tracing বিশ্লেষণ
#### Start at A
```text
Candidate: A-B=2, A-C=6
Select A-B=2
```
#### Tree {A,B}
```text
Candidate: A-C=6, B-C=3, B-D=5
Select B-C=3
```
#### Tree {A,B,C}
```text
Candidate: B-D=5, C-D=1
Select C-D=1
```
#### Total
```text
2 + 3 + 1 = 6
```
#### Final Answer
```text
MST weight = 6
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** A-B=2, B-C=3 এবং C-D=1 select হয়; total 6।
- **A option কেন ভুল:** বড় edge নেওয়া হয়েছে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** B-D=5 নেওয়া হয়েছে।
- **D option কেন ভুল:** Selection total ভুল।
- **Related Concept:** Start vertex ভিন্ন হলেও minimum total weight একই; tied edge set বদলাতে পারে।
- **মনে রাখার টিপস:** Current tree cut-এর cheapest edge নিন।

---

## প্রশ্ন 477 | Topic: Algorithm > MST > Cycle Property | Difficulty: Medium | Type: Theory

Q. একটি cycle-এর unique maximum-weight edge সম্পর্কে MST Cycle Property কী বলে?

A) Edge-টি সব MST-তে থাকতে হবে  
B) Edge-টি root হতে হবে  
C) Edge-টি কোনো MST-তে থাকবে না  
D) Edge-টি negative হতে হবে  

**সঠিক উত্তর: C) Edge-টি কোনো MST-তে থাকবে না**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Maximum edge বাদ দিয়েও cycle-এর বাকি path connectivity রাখে এবং cost কমায়।
- **A option কেন ভুল:** উল্টো property।
- **B option কেন ভুল:** MST-তে root বাধ্যতামূলক নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Weight negative হওয়া প্রয়োজন নেই।
- **Related Concept:** Equal maximum edge থাকলে নির্দিষ্ট কোনটি বাদ যাবে তা tie-এর ওপর নির্ভর করে।
- **মনে রাখার টিপস:** Cycle-এর unique heaviest edge বাদ দিন।

---

## প্রশ্ন 478 | Topic: Algorithm > MST > Cut Property | Difficulty: Medium | Type: Theory

Q. MST Cut Property অনুযায়ী একটি cut crossing edge-গুলোর মধ্যে unique minimum edge সম্পর্কে কোন statement সঠিক?

A) Edge-টি কখনো MST-তে থাকে না  
B) Edge-টি শুধু directed graph-এ ব্যবহৃত  
C) Edge-টি cycle তৈরি করতেই হবে  
D) Edge-টি প্রতিটি MST-তে থাকে  

**সঠিক উত্তর: D) Edge-টি প্রতিটি MST-তে থাকে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Unique lightest crossing edge safe; অন্য crossing edge নিলে cost বাড়ে।
- **A option কেন ভুল:** এটি cycle maximum property-এর বিপরীত।
- **B option কেন ভুল:** Standard MST undirected graph।
- **C option কেন ভুল:** Safe edge দুই side connect করে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Kruskal ও Prim correctness cut property দিয়ে প্রমাণ করা যায়।
- **মনে রাখার টিপস:** Cut-এর unique lightest bridge must be chosen।

---

## প্রশ্ন 479 | Topic: Algorithm > MST > Uniqueness | Difficulty: Hard | Type: Theory

Q. একটি connected weighted undirected graph-এর সব edge weight distinct হলে MST সম্পর্কে কী নিশ্চিত?

A) MST unique  
B) MST থাকবে না  
C) একাধিক MST বাধ্যতামূলক  
D) MST-তে V edge থাকবে  

**সঠিক উত্তর: A) MST unique**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Weight tie না থাকায় cut ও cycle choice uniquely determined হয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Connected graph-এর spanning tree আছে।
- **C option কেন ভুল:** Distinct weight multiple MST বাধ্যতামূলক করে না।
- **D option কেন ভুল:** Tree edge V−1।
- **Related Concept:** Duplicate weight থাকলেও MST unique হতে পারে; distinct weight sufficient condition।
- **মনে রাখার টিপস:** All weights distinct → unique MST।

---

## প্রশ্ন 480 | Topic: Algorithm > MST > Minimum Spanning Forest | Difficulty: Medium | Type: Calculation

Q. একটি undirected graph-এ 10টি vertex এবং 3টি connected component আছে। প্রতিটি component-এর spanning tree নিয়ে forest তৈরি করলে মোট edge কত হবে?

A) 10  
B) 7  
C) 6  
D) 13  

**সঠিক উত্তর: B) 7**

### গাণিতিক/Tracing বিশ্লেষণ
#### Formula
```text
Forest edges = V - C
```
#### Given Data
```text
V = 10
C = 3
```
#### Calculation
```text
Edges = 10 - 3
      = 7
```
#### Final Answer
```text
Minimum spanning forest edges = 7
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Forest edge = total vertex − component = 10−3 = 7।
- **A option কেন ভুল:** Vertex count নেওয়া হয়েছে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এক edge কম।
- **D option কেন ভুল:** V+C করা হয়েছে।
- **Related Concept:** Connected graph হলে component=1 এবং formula V−1।
- **মনে রাখার টিপস:** Forest edge = Vertex − Component।

---

## প্রশ্ন 481 | Topic: Algorithm > Topological Sort > Graph Type | Difficulty: Easy | Type: Theory

Q. Topological Sorting কোন graph-এর জন্য সংজ্ঞায়িত?

A) সব undirected graph  
B) সব weighted graph  
C) Directed Acyclic Graph  
D) Complete graph only  

**সঠিক উত্তর: C) Directed Acyclic Graph**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Directed dependency order থাকতে হয় এবং cycle থাকলে precedence contradiction তৈরি হয়।
- **A option কেন ভুল:** Undirected edge directional precedence দেয় না।
- **B option কেন ভুল:** Weight নয়, direction ও acyclicity গুরুত্বপূর্ণ।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Complete graph হওয়া প্রয়োজন নেই।
- **Related Concept:** DAG shortest path topological order দিয়ে linear time-এ করা যায়।
- **মনে রাখার টিপস:** Topological = dependency order of DAG।

---

## প্রশ্ন 482 | Topic: Algorithm > Kahn’s Algorithm > Data Structure | Difficulty: Easy | Type: Theory

Q. Kahn’s topological sorting algorithm সাধারণত কোন vertex-গুলো Queue-তে রাখে?

A) Maximum out-degree vertex  
B) Random vertex  
C) Negative weight vertex  
D) In-degree 0 vertex  

**সঠিক উত্তর: D) In-degree 0 vertex**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** In-degree zero মানে vertex-এর কোনো unmet predecessor নেই।
- **A option কেন ভুল:** Out-degree priority নয়।
- **B option কেন ভুল:** Dependency constraint মানতে হয়।
- **C option কেন ভুল:** Weight topological sort-এ প্রাসঙ্গিক নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Min-heap ব্যবহার করলে lexicographically smallest topological order পাওয়া যায়।
- **মনে রাখার টিপস:** No incoming dependency → ready।

---

## প্রশ্ন 483 | Topic: Algorithm > Topological Sort > Kahn Trace | Difficulty: Hard | Type: Tracing

Q. Directed edge:
```text
A -> C
B -> C
C -> D
B -> E
```
Zero in-degree vertex alphabetical order-এ নেওয়া হলে একটি valid topological order কোনটি?

A) A, B, C, D, E  
B) C, A, B, D, E  
C) B, C, A, E, D  
D) A, C, B, D, E  

**সঠিক উত্তর: A) A, B, C, D, E**

### গাণিতিক/Tracing বিশ্লেষণ
#### Initial In-degree
```text
A=0, B=0, C=2, D=1, E=1
Queue = [A, B]
```
#### Process
```text
Output A -> C becomes 1
Output B -> C becomes 0, E becomes 0
Queue = [C, E]

Output C -> D becomes 0
Queue = [D, E]

Output D
Output E
```
#### Final Answer
```text
A, B, C, D, E
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** A ও B প্রথমে zero in-degree; alphabetical order-এ A, B। এরপর C ও E zero হয়; C আগে, তারপর D ও E।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** C predecessor A ও B-এর আগে এসেছে।
- **C option কেন ভুল:** C, A-এর আগে এসেছে।
- **D option কেন ভুল:** C, B-এর আগে এসেছে।
- **Related Concept:** `A,B,C,E,D`-ও valid হতে পারে; tie-breaking order output নির্ধারণ করে।
- **মনে রাখার টিপস:** প্রতিটি edge-এর source destination-এর আগে আছে কি না দেখুন।

---

## প্রশ্ন 484 | Topic: Algorithm > Kahn’s Algorithm > Cycle Detection | Difficulty: Medium | Type: Theory

Q. Kahn’s Algorithm শেষে processed vertex count V-এর চেয়ে কম হলে কী বোঝায়?

A) Graph complete  
B) Directed cycle আছে  
C) সব vertex isolated  
D) Graph weighted নয়  

**সঠিক উত্তর: B) Directed cycle আছে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Cycle-এর vertex-গুলোর in-degree zero হতে পারে না; তাই কিছু vertex process না হয়েই algorithm থামে।
- **A option কেন ভুল:** Completeness নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Isolated vertex-এর in-degree zero, process হয়ে যেত।
- **D option কেন ভুল:** Weight ব্যবহার করা হয় না।
- **Related Concept:** DFS recursion-stack back edge দিয়েও cycle detect করা যায়।
- **মনে রাখার টিপস:** Queue থেমে গেছে কিন্তু vertex বাকি → cycle।

---

## প্রশ্ন 485 | Topic: Algorithm > Topological Sort > Initial Zero In-degree | Difficulty: Medium | Type: Calculation

Q. Directed graph-এর in-degree:
```text
A=0, B=2, C=0, D=1, E=0, F=3
```
Kahn’s Algorithm শুরুতে Queue-তে কতটি vertex থাকবে?

A) 2  
B) 4  
C) 3  
D) 6  

**সঠিক উত্তর: C) 3**

### গাণিতিক/Tracing বিশ্লেষণ
#### Zero In-degree Vertices
```text
A = 0
C = 0
E = 0
```
#### Count
```text
Total = 3
```
#### Final Answer
```text
Initial Queue size = 3
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** A, C ও E—মোট তিনটি vertex-এর in-degree zero।
- **A option কেন ভুল:** একটি zero vertex বাদ গেছে।
- **B option কেন ভুল:** D=1-কে zero ধরা হয়েছে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** সব vertex count করা হয়েছে।
- **Related Concept:** Multiple initial zero vertex থাকলে multiple topological order সম্ভব হতে পারে।
- **মনে রাখার টিপস:** শুধু exact zero count করুন।

---

## প্রশ্ন 486 | Topic: Algorithm > DFS Topological Sort > Output Order | Difficulty: Medium | Type: Theory

Q. DFS-based topological sort-এ vertex কখন output stack-এ push করা হয়?

A) Vertex discover করার সঙ্গে সঙ্গে  
B) শুধু root হলে  
C) In-degree zero হলে বাধ্যতামূলকভাবে  
D) তার সব outgoing neighbour process শেষ হওয়ার পরে  

**সঠিক উত্তর: D) তার সব outgoing neighbour process শেষ হওয়ার পরে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** DFS finish-time reverse order topological ordering দেয়।
- **A option কেন ভুল:** Discovery order dependency মানবে না।
- **B option কেন ভুল:** সব vertex push হয়।
- **C option কেন ভুল:** এটি Kahn algorithm-এর rule।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Postorder reverse করেই topological order তৈরি হয়।
- **মনে রাখার টিপস:** DFS topo-তে finish first, output later।

---

## প্রশ্ন 487 | Topic: Algorithm > Greedy > Greedy-choice Property | Difficulty: Easy | Type: Theory

Q. Greedy-choice property কী নির্দেশ করে?

A) Locally optimal choice দিয়ে কোনো globally optimal solution শুরু করা সম্ভব  
B) সব subproblem একাধিকবার solve করতে হবে  
C) Algorithm অবশ্যই recursion ব্যবহার করবে  
D) সব edge negative হতে হবে  

**সঠিক উত্তর: A) Locally optimal choice দিয়ে কোনো globally optimal solution শুরু করা সম্ভব**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একটি safe local choice optimal solution-এর অংশ হিসেবে স্থির করা যায়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** এটি overlapping subproblem-এর ধারণা।
- **C option কেন ভুল:** Greedy iterative হতে পারে।
- **D option কেন ভুল:** Edge sign generic greedy property নয়।
- **Related Concept:** Exchange argument greedy choice-এর safety প্রমাণ করতে পারে।
- **মনে রাখার টিপস:** Take best now—কিন্তু proof থাকতে হবে।

---

## প্রশ্ন 488 | Topic: Algorithm > Greedy > Optimal Substructure | Difficulty: Medium | Type: Theory

Q. Optimal Substructure বলতে কী বোঝায়?

A) Problem-এ কোনো subproblem নেই  
B) Optimal solution-এর অংশ সংশ্লিষ্ট subproblem-এর optimal solution  
C) সব local choice ভুল  
D) শুধু graph problem-এ প্রযোজ্য  

**সঠিক উত্তর: B) Optimal solution-এর অংশ সংশ্লিষ্ট subproblem-এর optimal solution**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** বড় optimal solution ছোট optimal component দিয়ে গঠিত হতে পারে।
- **A option কেন ভুল:** Subproblem থাকাই concept-এর ভিত্তি।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Local choice safe হতে পারে।
- **D option কেন ভুল:** Knapsack, sequence ও scheduling-এও প্রযোজ্য।
- **Related Concept:** Dynamic Programming ও Greedy উভয়েই optimal substructure ব্যবহার করতে পারে।
- **মনে রাখার টিপস:** Optimal whole contains optimal parts।

---

## প্রশ্ন 489 | Topic: Algorithm > Fractional Knapsack > Greedy Rule | Difficulty: Easy | Type: Theory

Q. Fractional Knapsack-এ item select করার standard greedy priority কোনটি?

A) সর্বনিম্ন weight  
B) সর্বোচ্চ total value  
C) সর্বোচ্চ value-to-weight ratio  
D) সর্বশেষ input item  

**সঠিক উত্তর: C) সর্বোচ্চ value-to-weight ratio**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতি unit weight-এ সর্বাধিক value দেওয়া item আগে নেওয়া হয়।
- **A option কেন ভুল:** হালকা item-এর ratio কম হতে পারে।
- **B option কেন ভুল:** বড় total value item খুব ভারী হতে পারে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Input order optimality নির্ধারণ করে না।
- **Related Concept:** Fraction allowed হওয়ায় remaining capacity আংশিক item দিয়ে পূরণ করা যায়।
- **মনে রাখার টিপস:** Fractional = value per unit weight।

---

## প্রশ্ন 490 | Topic: Algorithm > Fractional Knapsack > Value Calculation | Difficulty: Hard | Type: Calculation

Q. Knapsack capacity 50। Item:
```text
A: weight 10, value 60
B: weight 20, value 100
C: weight 30, value 120
```
Fractional Knapsack-এর maximum value কত?

A) 220  
B) 200  
C) 230  
D) 240  

**সঠিক উত্তর: D) 240**

### গাণিতিক/Tracing বিশ্লেষণ
#### Ratio
```text
A = 60/10  = 6
B = 100/20 = 5
C = 120/30 = 4
```
#### Fill Capacity
```text
Take A fully:
Weight=10, Value=60, Remaining=40

Take B fully:
Weight=20, Value=100, Remaining=20
Current value = 160
```
#### Fraction of C
```text
Fraction     = 20/30
Value gained = 120 × 20/30
             = 80
```
#### Final Answer
```text
Maximum value = 160 + 80
              = 240
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Ratio order A(6), B(5), C(4)। A ও B সম্পূর্ণ এবং C-এর 20/30 অংশ নিলে total 240।
- **A option কেন ভুল:** 0/1-এর ভালো combination নেওয়া হয়েছে।
- **B option কেন ভুল:** Partial item value বাদ গেছে।
- **C option কেন ভুল:** Fraction value ভুল হয়েছে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** 0/1 Knapsack হলে B+C=220 সর্বোচ্চ; fractional-এ 240।
- **মনে রাখার টিপস:** Ratio sort করুন, শেষে fraction নিন।

---

## প্রশ্ন 491 | Topic: Algorithm > Knapsack > 0/1 vs Fractional | Difficulty: Medium | Type: Theory

Q. Value/weight ratio greedy rule 0/1 Knapsack-এ সবসময় optimal নয় কেন?

A) Item fraction নেওয়া যায় না  
B) সব item-এর value zero  
C) Capacity অসীম  
D) Weight ব্যবহার করা হয় না  

**সঠিক উত্তর: A) Item fraction নেওয়া যায় না**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** High-ratio item পুরো নেওয়া পরে আরও ভালো item combination block করতে পারে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** General problem-এ value positive হতে পারে।
- **C option কেন ভুল:** Capacity সীমিত বলেই choice দরকার।
- **D option কেন ভুল:** Weight constraint problem-এর মূল অংশ।
- **Related Concept:** 0/1 Knapsack Dynamic Programming classic problem।
- **মনে রাখার টিপস:** Fraction না থাকলে combination গুরুত্বপূর্ণ।

---

## প্রশ্ন 492 | Topic: Algorithm > Activity Selection > Greedy Rule | Difficulty: Medium | Type: Theory

Q. Maximum non-overlapping activity select করার standard greedy rule কোনটি?

A) Earliest start time  
B) Earliest finish time  
C) Longest duration  
D) Highest activity ID  

**সঠিক উত্তর: B) Earliest finish time**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** যে activity আগে শেষ হয়, তা ভবিষ্যৎ activity-এর জন্য বেশি সময় খালি রাখে।
- **A option কেন ভুল:** আগে শুরু হলেও অনেক দেরিতে শেষ হতে পারে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Long duration বেশি interval block করে।
- **D option কেন ভুল:** ID scheduling value নয়।
- **Related Concept:** Exchange argument earliest-finish choice safe দেখায়।
- **মনে রাখার টিপস:** Finish early, leave room for more।

---

## প্রশ্ন 493 | Topic: Algorithm > Activity Selection > Selection Trace | Difficulty: Medium | Type: Tracing

Q. Activity-গুলো finish time অনুযায়ী sorted:
```text
A(1,4)
B(3,5)
C(0,6)
D(5,7)
E(8,9)
F(5,9)
```
Earliest-finish greedy selection কোন set দেবে?

A) {B, D, E}  
B) {A, B, E}  
C) {A, D, E}  
D) {C, E}  

**সঠিক উত্তর: C) {A, D, E}**

### গাণিতিক/Tracing বিশ্লেষণ
#### Selection
```text
Select A(1,4)
Last finish = 4

B starts 3 < 4 -> Reject
C starts 0 < 4 -> Reject

D starts 5 >= 4 -> Select
Last finish = 7

E starts 8 >= 7 -> Select
Last finish = 9

F starts 5 < 9 -> Reject
```
#### Final Answer
```text
Selected set = {A, D, E}
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** A select; B ও C overlap; D compatible; এরপর E compatible।
- **A option কেন ভুল:** B প্রথম selected নয়।
- **B option কেন ভুল:** A ও B overlap।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** C দীর্ঘ সময় block করে activity count কমায়।
- **Related Concept:** Finish-time sorted থাকলে selection phase O(n)।
- **মনে রাখার টিপস:** Last finish time প্রতিটি selection-এর পরে update করুন।

---

## প্রশ্ন 494 | Topic: Algorithm > Activity Selection > Tie Handling | Difficulty: Medium | Type: Theory

Q. দুইটি activity-এর finish time সমান হলে standard activity-selection optimality সম্পর্কে কোন statement সবচেয়ে সঠিক?

A) দুটোই একসঙ্গে নিতে হবে  
B) কোনো activity নেওয়া যাবে না  
C) Longest activity বাধ্যতামূলক  
D) যেকোনো একটি নেওয়া যেতে পারে; future availability একই finish time থেকে শুরু হয়  

**সঠিক উত্তর: D) যেকোনো একটি নেওয়া যেতে পারে; future availability একই finish time থেকে শুরু হয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একই finish time হলে ভবিষ্যৎ compatible activity-এর জন্য একই সময় থেকে সুযোগ শুরু হয়।
- **A option কেন ভুল:** Activity-দুটি overlap করতে পারে।
- **B option কেন ভুল:** একটি নেওয়া সম্ভব।
- **C option কেন ভুল:** Longest duration criterion নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Deterministic output-এর জন্য start time বা ID tie-break ব্যবহার করা যায়।
- **মনে রাখার টিপস:** Primary key finish time; tie choice flexible হতে পারে।

---

## প্রশ্ন 495 | Topic: Algorithm > Huffman Encoding > Merge Rule | Difficulty: Easy | Type: Theory

Q. Huffman Encoding-এর প্রতিটি ধাপে কোন দুইটি node merge করা হয়?

A) সর্বনিম্ন frequency-এর দুইটি node  
B) সর্বোচ্চ frequency-এর দুইটি node  
C) Alphabetically প্রথম দুইটি  
D) Random দুইটি  

**সঠিক উত্তর: A) সর্বনিম্ন frequency-এর দুইটি node**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Low-frequency symbol গভীরে রেখে frequent symbol-এর code ছোট করার জন্য দুই minimum merge করা হয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Frequent symbol গভীরে গেলে average length বাড়ে।
- **C option কেন ভুল:** Frequency মূল criterion।
- **D option কেন ভুল:** Random merge optimality দেয় না।
- **Related Concept:** Min-Heap Huffman implementation-এ কার্যকর।
- **মনে রাখার টিপস:** Huffman = two smallest merge।

---

## প্রশ্ন 496 | Topic: Algorithm > Huffman Encoding > Weighted Path Length | Difficulty: Medium | Type: Calculation

Q. একটি prefix code-এ:
```text
A: frequency 5, code length 1
B: frequency 2, code length 3
C: frequency 1, code length 3
```
মোট encoded bit contribution কত?

A) 8  
B) 14  
C) 10  
D) 11  

**সঠিক উত্তর: B) 14**

### গাণিতিক/Tracing বিশ্লেষণ
#### Formula
```text
Total bits = Sum(frequency × code length)
```
#### Calculation
```text
A = 5 × 1 = 5
B = 2 × 3 = 6
C = 1 × 3 = 3
----------------
Total      = 14
```
#### Final Answer
```text
Total encoded bits = 14
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Total bits = `5×1 + 2×3 + 1×3 = 14`।
- **A option কেন ভুল:** Frequency ও length যোগ করা হয়েছে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** একটি contribution ভুল।
- **D option কেন ভুল:** একটি symbol বাদ গেছে।
- **Related Concept:** Average code length = total bits / total symbol count।
- **মনে রাখার টিপস:** Frequency × code length করে সব যোগ করুন।

---

## প্রশ্ন 497 | Topic: Algorithm > Huffman Encoding > Prefix-free Property | Difficulty: Easy | Type: Theory

Q. Prefix-free code-এর অর্থ কী?

A) সব code একই length  
B) কোনো code-এ 0 নেই  
C) কোনো valid codeword অন্য codeword-এর prefix নয়  
D) Code decode করা যায় না  

**সঠিক উত্তর: C) কোনো valid codeword অন্য codeword-এর prefix নয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** কোনো complete codeword অন্য code-এর শুরু না হওয়ায় bit stream unambiguously decode করা যায়।
- **A option কেন ভুল:** Huffman variable-length code।
- **B option কেন ভুল:** 0 ও 1 দুটোই থাকতে পারে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Prefix-free property decoding সহজ করে।
- **Related Concept:** Huffman tree-এর symbol leaf-এ থাকে; কোনো leaf অন্য leaf-এর ancestor নয়।
- **মনে রাখার টিপস:** Complete code আরেক code-এর শুরু নয়।

---

## প্রশ্ন 498 | Topic: Algorithm > Task Scheduling > Job Sequencing | Difficulty: Medium | Type: Scenario

Q. Unit-time job, deadline এবং profit দেওয়া থাকলে Job Sequencing with Deadlines-এর greedy strategy কী?

A) Lowest profit job আগে  
B) Earliest input job আগে  
C) Deadline উপেক্ষা করা  
D) Profit descending order-এ job নিয়ে deadline-এর আগে latest free slot-এ বসানো  

**সঠিক উত্তর: D) Profit descending order-এ job নিয়ে deadline-এর আগে latest free slot-এ বসানো**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** High-profit job আগে বিবেচনা এবং latest feasible slot ব্যবহার করলে আগের slot অন্য job-এর জন্য থাকে।
- **A option কেন ভুল:** Profit maximize হবে না।
- **B option কেন ভুল:** Input order optimality দেয় না।
- **C option কেন ভুল:** Deadline feasibility-এর মূল constraint।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** DSU দিয়ে latest free slot দ্রুত খোঁজা যায়।
- **মনে রাখার টিপস:** High profit first, place as late as possible।

---

## প্রশ্ন 499 | Topic: Algorithm > Greedy > Coin Change Failure | Difficulty: Hard | Type: Calculation

Q. Coin denomination `{1, 3, 4}` এবং amount 6। Largest-coin-first greedy এবং optimal solution-এর coin count যথাক্রমে কত?

A) Greedy 3, Optimal 2  
B) Greedy 2, Optimal 3  
C) Greedy 2, Optimal 2  
D) Greedy 6, Optimal 1  

**সঠিক উত্তর: A) Greedy 3, Optimal 2**

### গাণিতিক/Tracing বিশ্লেষণ
#### Greedy
```text
Take 4 -> Remaining 2
Take 1 -> Remaining 1
Take 1 -> Remaining 0

Greedy count = 3
```
#### Optimal
```text
3 + 3 = 6
Optimal count = 2
```
#### Final Answer
```text
Greedy  = 3 coins
Optimal = 2 coins
```

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Greedy `4+1+1` দিয়ে 3 coin নেয়; optimal `3+3` দিয়ে 2 coin।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Greedy ও optimal উল্টো।
- **C option কেন ভুল:** Greedy failure উপেক্ষা করা হয়েছে।
- **D option কেন ভুল:** 6 denomination নেই।
- **Related Concept:** Arbitrary coin system-এ DP minimum coin guarantee করতে পারে।
- **মনে রাখার টিপস:** Largest coin first সব denomination-এ optimal নয়।

---

## প্রশ্ন 500 | Topic: Algorithm > Greedy > Algorithm Selection | Difficulty: Medium | Type: Theory

Q. নিচের problem–algorithm matching-এর কোনটি সঠিক?

A) Negative-edge shortest path → Dijkstra  
B) Fractional Knapsack → Value/weight ratio greedy  
C) Topological Sorting → Undirected cyclic graph  
D) Range indexing → Stack  

**সঠিক উত্তর: B) Fractional Knapsack → Value/weight ratio greedy**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Fractional Knapsack-এ value density descending greedy optimal।
- **A option কেন ভুল:** Negative edge-এর জন্য Bellman–Ford।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Topological sort DAG-এর জন্য।
- **D option কেন ভুল:** Range indexing-এর জন্য B+ Tree বা ordered index।
- **Related Concept:** Algorithm selection input property-এর ওপর নির্ভর করে।
- **মনে রাখার টিপস:** Problem constraint না দেখে algorithm প্রয়োগ করবেন না।

---

# Batch Quality Summary

## Question Count

```text
Question Range          = 451–500
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

- B-Tree properties, search, split ও occupancy
- B+ Tree record placement, linked leaf ও range query
- Relaxation
- Dijkstra Algorithm
- Bellman–Ford ও negative-cycle detection
- Floyd–Warshall ও all-pairs shortest path
- Spanning Tree ও Minimum Spanning Tree
- Kruskal ও Prim
- Cut Property ও Cycle Property
- Minimum Spanning Forest
- Topological Sorting
- Kahn’s Algorithm
- DFS-based Topological Sort
- Greedy-choice property ও Optimal Substructure
- Fractional ও 0/1 Knapsack
- Activity Selection
- Huffman Encoding
- Job Sequencing with Deadline
- Greedy Coin Change limitation

## Math and Tracing Coverage

```text
B-Tree maximum/minimum key count : Included
B-Tree page-read calculation      : Included
B-Tree split trace                : Included
Dijkstra distance trace           : Included
Bellman-Ford pass/relaxation      : Included
Floyd-Warshall update/count       : Included
Path-cost calculation             : Included
MST edge count                    : Included
Kruskal ও Prim trace              : Included
Spanning-forest edge count        : Included
Kahn topological trace            : Included
Zero in-degree count              : Included
Fractional Knapsack calculation   : Included
Activity Selection trace          : Included
Huffman bit calculation           : Included
Coin Change greedy failure        : Included
```

## Quality Checks

```text
Numbering continuity       : Passed
Question total             : Passed
Difficulty distribution    : Passed
Answer distribution        : Passed
Theory/Math distribution   : Passed
Calculation verification   : Passed
Plain-text math alignment  : Passed
Raw LaTeX issue            : Removed
Bangla explanation         : Passed
Technical keywords         : Preserved
```

---

## Next Coverage

পরবর্তী Batch 12 — Question 501–550:

- Divide and Conquer
- Merge Sort ও Quick Sort advanced analysis
- Greedy বনাম Dynamic Programming
- Dynamic Programming principles
- Coin Change DP
- Matrix Chain Multiplication
- Longest Common Subsequence
- Assembly Line Scheduling
- Viterbi
- TSP এবং Backtracking
