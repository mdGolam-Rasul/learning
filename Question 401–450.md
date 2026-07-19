# ১৯তম নিবন্ধন — প্রভাষক ICT

## Section 3: Data Structure, Algorithm & Combinatorial Optimization

### Batch 10 — Question 401–450

**Subject Code:** 452  
**Covered Area:** Graph Terminology, Graph Representation, BFS, DFS, Tree, Binary Tree, BST, Tree Traversal, AVL Tree এবং Hashing  
**Theory/Scenario MCQ:** 30  
**Math/Calculation/Tracing MCQ:** 20  
**Difficulty:** Easy 13, Medium 25, Hard 12  
**Answer Distribution:** A = 13, B = 13, C = 12, D = 12

> **Math-format policy:** Formula, graph state, queue/stack state, traversal, tree construction ও hashing probe sequence plain-text aligned block-এ দেখানো হয়েছে। Raw LaTeX command ব্যবহার করা হয়নি।

---

# Chapter Theory 30: Graph Fundamentals and Representation

## ১. Graph-এর মূল ধারণা

`Graph` হলো vertex এবং edge-এর সমষ্টি।

```text
G = (V, E)

V = Vertex set
E = Edge set
```

উদাহরণ:

```text
V = {A, B, C, D}
E = {(A,B), (B,C), (C,D)}
```

Vertex-কে `Node`-ও বলা হয়। Edge দুটি vertex-এর relationship বা connection প্রকাশ করে।

## ২. Directed এবং Undirected Graph

### Undirected Graph

Edge-এর নির্দিষ্ট direction নেই।

```text
A — B
```

এখানে A থেকে B এবং B থেকে A—দুই দিকের connection একই edge দিয়ে বোঝানো হয়।

### Directed Graph বা Digraph

প্রতিটি edge-এর direction থাকে।

```text
A -> B
```

এখানে A থেকে B যাওয়া যায়; B থেকে A যাওয়া যাবে কি না, তা আলাদা edge-এর ওপর নির্ভর করে।

## ৩. Weighted Graph

প্রতিটি edge-এর সঙ্গে cost, distance, time বা weight যুক্ত থাকলে সেটি Weighted Graph।

```text
A --5--> B
```

এখানে edge weight = 5।

## ৪. Degree

### Undirected Graph

একটি vertex-এর সঙ্গে incident edge-এর সংখ্যা তার degree।

Self-loop একটি vertex-এর degree-তে 2 যোগ করে।

`Handshaking Lemma`:

```text
Sum of all vertex degrees = 2 × Number of edges
```

### Directed Graph

- `In-degree`: Vertex-এ প্রবেশ করা edge-এর সংখ্যা
- `Out-degree`: Vertex থেকে বের হওয়া edge-এর সংখ্যা

```text
Sum of all in-degrees  = Number of directed edges
Sum of all out-degrees = Number of directed edges
```

## ৫. Path, Cycle এবং Connectivity

- **Walk:** Vertex ও edge-এর sequence; পুনরাবৃত্তি থাকতে পারে
- **Trail:** Edge পুনরাবৃত্তি হয় না
- **Path:** সাধারণত vertex পুনরাবৃত্তি হয় না
- **Cycle:** শুরু ও শেষ vertex একই
- **Connected Graph:** যেকোনো দুই vertex-এর মধ্যে path আছে
- **Connected Component:** Maximal connected subgraph
- **Strongly Connected Digraph:** প্রতিটি vertex থেকে অন্য প্রতিটি vertex-এ directed path আছে

## ৬. Complete Graph

n vertex-এর undirected complete graph-কে `K_n` বলা হয়।

প্রতিটি distinct pair-এর মধ্যে একটি edge থাকে।

```text
Number of edges in K_n = n(n - 1) / 2
```

Directed simple complete graph-এ দুই direction আলাদা edge হিসেবে ধরলে:

```text
Number of directed edges = n(n - 1)
```

## ৭. Bipartite Graph

Vertex set-কে দুইটি disjoint set-এ ভাগ করা যায় এবং একই set-এর দুই vertex-এর মধ্যে edge থাকে না।

গুরুত্বপূর্ণ property:

```text
A graph is bipartite if and only if it has no odd-length cycle.
```

Complete Bipartite Graph `K_m,n`-এ edge সংখ্যা:

```text
Edges = m × n
```

## ৮. Graph Representation

### Adjacency Matrix

n vertex-এর জন্য n × n matrix।

```text
Matrix[u][v] = 1    edge থাকলে
Matrix[u][v] = 0    edge না থাকলে
```

Weighted graph-এ 1-এর বদলে weight রাখা যায়।

#### সুবিধা

- Edge existence check O(1)
- Dense graph-এর জন্য উপযোগী
- Implementation সহজ

#### সীমাবদ্ধতা

- Space O(V²)
- Sparse graph-এ অনেক zero entry

### Adjacency List

প্রতিটি vertex-এর সঙ্গে তার adjacent vertex-এর list রাখা হয়।

#### সুবিধা

- Space O(V + E)
- Sparse graph-এর জন্য ভালো
- Neighbour traversal efficient

#### সীমাবদ্ধতা

- Edge existence check degree-এর ওপর নির্ভর করতে পারে
- Matrix-এর মতো সরাসরি O(1) নাও হতে পারে

## ৯. Sparse বনাম Dense Graph

- **Sparse Graph:** Edge সংখ্যা V²-এর তুলনায় অনেক কম
- **Dense Graph:** সম্ভাব্য edge-এর বড় অংশ উপস্থিত

সাধারণভাবে:

```text
Sparse graph -> Adjacency List
Dense graph  -> Adjacency Matrix
```

## ১০. Common Mistakes

- Undirected edge-কে দুইটি আলাদা edge হিসেবে count করা
- Self-loop degree-তে 1 যোগ করা
- Directed graph-এ degree-এর বদলে in-degree/out-degree ভুল করা
- Matrix space O(E) ধরা
- Bipartite graph-এ triangle থাকতে পারে মনে করা

## ১১. Exam Tips

- Undirected degree sum = 2E
- Directed in-degree sum = E
- Complete undirected edges = n(n−1)/2
- Adjacency Matrix = O(V²)
- Adjacency List = O(V+E)
- Odd cycle থাকলে Bipartite নয়

---

# MCQ Practice: Graph Fundamentals

## প্রশ্ন 401 | Topic: Data Structure > Graph > Basic Definition | Difficulty: Easy | Type: Theory

Q. একটি Graph `G = (V, E)`-এ `V` এবং `E` কী নির্দেশ করে?

A) Value এবং Expression  
B) Vertex set এবং Edge set  
C) Variable এবং Equation  
D) Vector এবং Element

**সঠিক উত্তর: B) Vertex set এবং Edge set**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Graph-এর মৌলিক mathematical representation-এ `V` node বা vertex-এর set এবং `E` connection বা edge-এর set।
- **A option কেন ভুল:** এগুলো programming expression-এর term; graph definition নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Variable ও Equation graph-এর formal pair নয়।
- **D option কেন ভুল:** Vector ও Element ভিন্ন mathematical concept।
- **Related Concept:** Directed graph-এ edge ordered pair; undirected graph-এ unordered pair হিসেবে ধরা হয়।
- **মনে রাখার টিপস:** Graph = Vertices + Edges।

---

## প্রশ্ন 402 | Topic: Data Structure > Graph > Handshaking Lemma | Difficulty: Medium | Type: Calculation

Q. একটি undirected graph-এ vertex-গুলোর degree যথাক্রমে 3, 2, 2, 1, 2। Graph-টিতে মোট edge কতটি?

A) 4  
B) 5  
C) 8  
D) 10

**সঠিক উত্তর: B) 5**

### গাণিতিক বিশ্লেষণ

#### Formula

```text
Sum of degrees = 2 × Number of edges

E = Sum of degrees / 2
```

#### Given Data

```text
Degrees = 3, 2, 2, 1, 2
```

#### Step-by-step Calculation

```text
Degree sum = 3 + 2 + 2 + 1 + 2
           = 10

Number of edges = 10 / 2
                = 5
```

#### Final Answer

```text
Total edges = 5
```

### Option বিশ্লেষণ

- **A) 4:** Degree sum ভুলভাবে 8 ধরা হয়েছে।
- **B) 5:** এটি সঠিক উত্তর।
- **C) 8:** কিছু degree যোগ করে division বাদ দেওয়া হয়েছে।
- **D) 10:** Degree sum-কে সরাসরি edge count ধরা হয়েছে।
- **Related Concept:** Undirected graph-এর প্রতিটি edge দুই vertex-এর degree-তে একবার করে অবদান রাখে।
- **মনে রাখার টিপস:** Degree যোগ করে সবসময় 2 দিয়ে ভাগ করুন।

---

## প্রশ্ন 403 | Topic: Data Structure > Graph > Directed Degree | Difficulty: Medium | Type: Theory

Q. Directed Graph-এ সব vertex-এর out-degree-এর যোগফল কোনটির সমান?

A) Vertex-এর সংখ্যা  
B) Directed edge-এর সংখ্যা  
C) Connected component-এর সংখ্যা  
D) Edge-এর দ্বিগুণ

**সঠিক উত্তর: B) Directed edge-এর সংখ্যা**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি directed edge ঠিক একটি source vertex থেকে বের হয়; তাই out-degree sum-এ একবার count হয়।
- **A option কেন ভুল:** Vertex count edge distribution নির্ধারণ করে না।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Component count-এর সঙ্গে degree sum-এর এমন relation নেই।
- **D option কেন ভুল:** Undirected degree sum 2E; directed out-degree sum E।
- **Related Concept:** সব in-degree-এর যোগফলও E।
- **মনে রাখার টিপস:** Directed graph-এ In sum = Out sum = E।

---

## প্রশ্ন 404 | Topic: Data Structure > Graph > Adjacency Matrix Storage | Difficulty: Medium | Type: Calculation

Q. ৮টি vertex-এর একটি graph Adjacency Matrix দিয়ে represent করলে matrix-এ মোট কতটি cell থাকবে?

A) 64  
B) 16  
C) 56  
D) 8

**সঠিক উত্তর: A) 64**

### গাণিতিক বিশ্লেষণ

#### Formula

```text
Adjacency Matrix cells = V × V
```

#### Given Data

```text
V = 8
```

#### Calculation

```text
Cells = 8 × 8
      = 64
```

#### Final Answer

```text
Total matrix cells = 64
```

### Option বিশ্লেষণ

- **A) 64:** এটি সঠিক উত্তর।
- **B) 16:** `2V` করা হয়েছে।
- **C) 56:** Self-loop diagonal বাদ দিয়ে `V(V−1)` করা হয়েছে; কিন্তু matrix-এর cell সংখ্যা 64।
- **D) 8:** শুধু vertex count নেওয়া হয়েছে।
- **Related Concept:** Edge কম হলেও matrix space O(V²)।
- **মনে রাখার টিপস:** Matrix dimension V by V।

---

## প্রশ্ন 405 | Topic: Data Structure > Graph > Sparse Representation | Difficulty: Medium | Type: Scenario

Q. ১,০০,০০০ vertex কিন্তু মাত্র ২,০০,০০০ edge-যুক্ত graph-এর জন্য কোন representation সাধারণত memory-efficient?

A) Adjacency List  
B) Full Adjacency Matrix  
C) V × V Boolean table বাধ্যতামূলক  
D) শুধু Incidence Matrix

**সঠিক উত্তর: A) Adjacency List**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Edge সংখ্যা V²-এর তুলনায় খুব কম; Adjacency List O(V+E) space নেয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Matrix প্রায় 10^10 cell চাইবে, যা অপ্রয়োজনীয়।
- **C option কেন ভুল:** Graph representation-এর জন্য matrix বাধ্যতামূলক নয়।
- **D option কেন ভুল:** Incidence Matrix-ও বড় হতে পারে এবং সাধারণ neighbour traversal-এর জন্য কম সুবিধাজনক।
- **Related Concept:** Sparse graph-এ list, dense graph-এ matrix বেশি উপযোগী।
- **মনে রাখার টিপস:** Edge কম হলে List ভাবুন।

---

## প্রশ্ন 406 | Topic: Data Structure > Graph > Bipartite Edge Count | Difficulty: Medium | Type: Calculation

Q. Complete Bipartite Graph `K_4,5`-এ edge সংখ্যা কত?

A) 9  
B) 10  
C) 16  
D) 20

**সঠিক উত্তর: D) 20**

### গাণিতিক বিশ্লেষণ

#### Formula

```text
Edges in K_m,n = m × n
```

#### Given Data

```text
m = 4
n = 5
```

#### Calculation

```text
Edges = 4 × 5
      = 20
```

#### Final Answer

```text
Total edges = 20
```

### Option বিশ্লেষণ

- **A) 9:** দুই partition-এর vertex count যোগ করা হয়েছে।
- **B) 10:** একটি partition-এর combination ধরা হয়েছে।
- **C) 16:** 4² করা হয়েছে।
- **D) 20:** এটি সঠিক উত্তর।
- **Related Concept:** একই partition-এর vertex-গুলোর মধ্যে edge থাকে না।
- **মনে রাখার টিপস:** Complete bipartite-এ left-এর প্রত্যেকে right-এর প্রত্যেকের সঙ্গে যুক্ত।

---

## প্রশ্ন 407 | Topic: Data Structure > Graph > Bipartite Property | Difficulty: Easy | Type: Theory

Q. নিচের কোন graph কখনো Bipartite হতে পারে না?

A) Tree  
B) Even cycle  
C) Odd cycle  
D) Path graph

**সঠিক উত্তর: C) Odd cycle**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Odd cycle-কে দুই color দিয়ে adjacent vertex ভিন্ন color রেখে color করা যায় না।
- **A option কেন ভুল:** প্রতিটি Tree bipartite।
- **B option কেন ভুল:** Even cycle দুই set-এ ভাগ করা যায়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Path graph-ও bipartite।
- **Related Concept:** Bipartite graph-এর equivalent test হলো 2-colorability।
- **মনে রাখার টিপস:** Odd cycle দেখলেই Not Bipartite।

---

## প্রশ্ন 408 | Topic: Data Structure > Graph > Complete Graph Edge Count | Difficulty: Hard | Type: Calculation

Q. ১০টি vertex-এর একটি simple undirected complete graph-এ edge সংখ্যা কত?

A) 45  
B) 90  
C) 100  
D) 50

**সঠিক উত্তর: A) 45**

### গাণিতিক বিশ্লেষণ

#### Formula

```text
Edges in K_n = n(n - 1) / 2
```

#### Given Data

```text
n = 10
```

#### Substitution and Calculation

```text
Edges = 10(10 - 1) / 2
      = 10 × 9 / 2
      = 90 / 2
      = 45
```

#### Final Answer

```text
Total edges = 45
```

### Option বিশ্লেষণ

- **A) 45:** এটি সঠিক উত্তর।
- **B) 90:** A→B এবং B→A-কে আলাদা edge ধরা হয়েছে।
- **C) 100:** n² করা হয়েছে।
- **D) 50:** n²/2 আনুমানিকভাবে করা হয়েছে।
- **Related Concept:** Complete graph-এর প্রতিটি vertex-এর degree n−1।
- **মনে রাখার টিপস:** Undirected pair count = combination nC2।

---

## প্রশ্ন 409 | Topic: Data Structure > Graph > Self-loop Degree | Difficulty: Easy | Type: Theory

Q. Undirected graph-এ একটি self-loop সংশ্লিষ্ট vertex-এর degree-তে কত যোগ করে?

A) 0  
B) 1  
C) 2  
D) Graph অনুযায়ী 3

**সঠিক উত্তর: C) 2**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Self-loop-এর দুই endpoint একই vertex-এ incident; degree count-এ দুইবার অবদান রাখে।
- **A option কেন ভুল:** Loop vertex-এর সঙ্গে incident।
- **B option কেন ভুল:** Edge count-এ এক হলেও degree contribution দুই।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Standard undirected degree rule-এ 2।
- **Related Concept:** Handshaking Lemma self-loop থাকলেও degree contribution 2 ধরলে কাজ করে।
- **মনে রাখার টিপস:** Loop এক edge, কিন্তু degree দুই।

---

## প্রশ্ন 410 | Topic: Data Structure > Graph > Adjacency List Entry Count | Difficulty: Hard | Type: Calculation

Q. একটি simple undirected graph-এ ৭টি edge আছে। Adjacency List-গুলোর সব neighbour entry মিলিয়ে মোট কতটি entry থাকবে?

A) 7  
B) 14  
C) 21  
D) 49

**সঠিক উত্তর: B) 14**

### গাণিতিক বিশ্লেষণ

#### Rule

```text
Undirected edge (u, v):
u-এর list-এ v একবার
v-এর list-এ u একবার

Total adjacency entries = 2E
```

#### Given Data

```text
E = 7
```

#### Calculation

```text
Entries = 2 × 7
        = 14
```

#### Final Answer

```text
Total neighbour entries = 14
```

### Option বিশ্লেষণ

- **A) 7:** প্রতিটি edge-এর একটি endpoint entry count করা হয়েছে।
- **B) 14:** এটি সঠিক উত্তর।
- **C) 21:** প্রতি edge তিন entry ধরা হয়েছে।
- **D) 49:** E² করা হয়েছে।
- **Related Concept:** Directed graph-এ outgoing adjacency list হলে total entry সাধারণত E।
- **মনে রাখার টিপস:** Undirected list-এ প্রতিটি edge দুইবার লেখা হয়।

---

# Chapter Theory 31: BFS and DFS

## ১. Breadth-First Search

`BFS` source vertex থেকে level-by-level graph traverse করে।

প্রধান data structure:

```text
Queue
```

Algorithm outline:

```text
1. Source-কে visited mark
2. Queue-তে source enqueue
3. Queue empty না হওয়া পর্যন্ত:
   a. Front vertex dequeue
   b. তার unvisited neighbour-কে visited mark
   c. Neighbour-কে enqueue
```

## ২. BFS-এর ব্যবহার

- Unweighted graph-এ shortest path by edge count
- Level order exploration
- Connected component
- Bipartite checking
- Network broadcasting
- Minimum move problem

## ৩. Depth-First Search

`DFS` একটি path যত গভীর সম্ভব অনুসরণ করে, তারপর backtrack করে।

প্রধান implementation:

- Recursion
- Explicit Stack

Algorithm outline:

```text
DFS(u):
    visited[u] = true
    for each neighbour v of u:
        if not visited[v]:
            DFS(v)
```

## ৪. DFS-এর ব্যবহার

- Cycle detection
- Topological sorting
- Connected component
- Strongly connected component
- Backtracking
- Maze traversal
- Articulation point ও bridge-এর advanced algorithm

## ৫. Time Complexity

Adjacency List ব্যবহার করলে:

```text
BFS = O(V + E)
DFS = O(V + E)
```

Adjacency Matrix ব্যবহার করলে neighbour scan:

```text
BFS = O(V²)
DFS = O(V²)
```

## ৬. Traversal Order

BFS/DFS order নির্ভর করতে পারে:

- Source vertex
- Neighbour ordering
- Representation
- Tie-breaking rule

তাই প্রশ্নে alphabetical বা numeric neighbour order দেওয়া থাকলে সেটি অনুসরণ করতে হবে।

## ৭. BFS Shortest Path

Unweighted graph-এ BFS প্রথমবার কোনো vertex discover করলে যে distance assign করে, সেটিই source থেকে minimum edge count।

```text
distance[source] = 0
distance[child]  = distance[parent] + 1
```

## ৮. DFS Edge Behavior

Directed graph-এর DFS-এ:

- Tree edge
- Back edge
- Forward edge
- Cross edge

Back edge directed graph-এ cycle নির্দেশ করতে পারে।

## ৯. Common Mistakes

- BFS-এ Stack ব্যবহার করা
- Vertex dequeue-এর সময় visited mark করে duplicate enqueue তৈরি করা
- Weighted graph-এর shortest path-এ BFS সবসময় ব্যবহার করা
- DFS order unique মনে করা
- Disconnected graph-এ শুধু একটি source থেকে সব vertex visit হবে ভাবা

## ১০. Exam Tips

- BFS → Queue → Level order
- DFS → Stack/Recursion → Deep exploration
- List representation → O(V+E)
- Matrix representation → O(V²)
- Unweighted shortest path → BFS
- Topological sort → DFS বা Kahn’s Queue algorithm

---

# MCQ Practice: BFS and DFS

## প্রশ্ন 411 | Topic: Algorithm > BFS > Primary Data Structure | Difficulty: Easy | Type: Theory

Q. Standard iterative BFS-এ কোন data structure traversal frontier পরিচালনা করে?

A) Priority Queue বাধ্যতামূলক  
B) Stack  
C) Queue  
D) Binary Search Tree

**সঠিক উত্তর: C) Queue**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** FIFO order একই level-এর আগে discovered vertex আগে process করে।
- **A option কেন ভুল:** Weighted shortest path-এর কিছু algorithm priority queue ব্যবহার করে; BFS নয়।
- **B option কেন ভুল:** Stack DFS-style traversal দেয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** BST traversal frontier-এর standard structure নয়।
- **Related Concept:** Multi-source BFS-এ একাধিক source শুরুতেই queue-তে দেওয়া যায়।
- **মনে রাখার টিপস:** Breadth বা level ধরে যেতে Queue।

---

## প্রশ্ন 412 | Topic: Algorithm > BFS > Traversal Trace | Difficulty: Hard | Type: Tracing

Q. নিচের undirected graph-এ neighbour alphabetical order-এ process করা হবে। `A` থেকে BFS traversal কোনটি?

```text
A: B, C
B: A, D, E
C: A, F
D: B
E: B, F
F: C, E
```

A) `A, B, D, E, F, C`  
B) `A, B, C, D, E, F`  
C) `A, C, F, E, B, D`  
D) `A, B, D, E, C, F`

**সঠিক উত্তর: B) `A, B, C, D, E, F`**

### ধাপে ধাপে BFS Trace

```text
Start:
Visited = {A}
Queue   = [A]
Output  = []

Dequeue A:
Output  = [A]
Enqueue B, C
Queue   = [B, C]

Dequeue B:
Output  = [A, B]
A visited; enqueue D, E
Queue   = [C, D, E]

Dequeue C:
Output  = [A, B, C]
A visited; enqueue F
Queue   = [D, E, F]

Dequeue D:
Output  = [A, B, C, D]
Queue   = [E, F]

Dequeue E:
Output  = [A, B, C, D, E]
F already discovered
Queue   = [F]

Dequeue F:
Output  = [A, B, C, D, E, F]
```

#### Final Answer

```text
BFS order = A, B, C, D, E, F
```

### Option বিশ্লেষণ

- **A:** B-এর child-গুলো C-এর আগে process করে DFS-সদৃশ order করা হয়েছে।
- **B:** এটি সঠিক উত্তর।
- **C:** C path ধরে গভীরে যাওয়া হয়েছে।
- **D:** Queue FIFO order ভাঙা হয়েছে।
- **Related Concept:** Mark visited at enqueue/discovery time to avoid duplicate queue entries।
- **মনে রাখার টিপস:** Queue state প্রতিটি dequeue-এর পরে লিখুন।

---

## প্রশ্ন 413 | Topic: Algorithm > BFS > Shortest Path | Difficulty: Easy | Type: Theory

Q. BFS কোন ক্ষেত্রে source থেকে shortest path নিশ্চিতভাবে বের করতে পারে?

A) Unweighted graph বা equal-weight edge graph  
B) Arbitrary negative-weight graph  
C) শুধু complete weighted graph  
D) সব weighted graph

**সঠিক উত্তর: A) Unweighted graph বা equal-weight edge graph**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** BFS level number minimum edge count নির্দেশ করে; সব edge cost সমান হলে এটিই minimum cost।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Negative weight-এর জন্য Bellman-Ford-এর মতো algorithm প্রয়োজন।
- **C option কেন ভুল:** Complete হওয়া নয়, equal edge cost গুরুত্বপূর্ণ।
- **D option কেন ভুল:** ভিন্ন weight থাকলে কম edge path-এর cost বেশি হতে পারে।
- **Related Concept:** Weight শুধু 0 ও 1 হলে 0–1 BFS ব্যবহার করা যায়।
- **মনে রাখার টিপস:** BFS shortest path = Unweighted।

---

## প্রশ্ন 414 | Topic: Algorithm > BFS > Distance Calculation | Difficulty: Medium | Type: Calculation

Q. BFS tree-তে source `S`-এর distance 0। `A` হলো `S`-এর child, `B` হলো `A`-এর child এবং `C` হলো `B`-এর child। `S` থেকে `C`-এর minimum edge distance কত?

A) 3  
B) 2  
C) 4  
D) 1

**সঠিক উত্তর: A) 3**

### গাণিতিক বিশ্লেষণ

#### Path

```text
S -> A -> B -> C
```

#### Edge Count

```text
S to A = 1 edge
A to B = 1 edge
B to C = 1 edge
-----------------
Total  = 3 edges
```

#### Distance Levels

```text
distance[S] = 0
distance[A] = 1
distance[B] = 2
distance[C] = 3
```

#### Final Answer

```text
Minimum edge distance = 3
```

### Option বিশ্লেষণ

- **A) 3:** এটি সঠিক উত্তর।
- **B) 2:** Vertex transition-এর একটি edge বাদ গেছে।
- **C) 4:** Source vertex-কে edge হিসেবে count করা হয়েছে।
- **D) 1:** শুধু শেষ parent-child edge নেওয়া হয়েছে।
- **Related Concept:** Path length edge count দিয়ে মাপা হয়, vertex count দিয়ে নয়।
- **মনে রাখার টিপস:** 4টি path vertex হলে edge সাধারণত 3টি।

---

## প্রশ্ন 415 | Topic: Algorithm > DFS > Primary Structure | Difficulty: Hard | Type: Theory

Q. Recursive DFS-এর implicit data structure কোনটি?

A) Queue  
B) Heap  
C) Hash Table  
D) Call Stack

**সঠিক উত্তর: D) Call Stack**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি recursive call stack frame তৈরি করে; backtracking call return-এর মাধ্যমে ঘটে।
- **A option কেন ভুল:** Queue BFS-এর জন্য।
- **B option কেন ভুল:** Heap priority management-এর জন্য।
- **C option কেন ভুল:** Visited set hash table হতে পারে, কিন্তু traversal control call stack।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Recursive DFS explicit stack দিয়েও implement করা যায়।
- **মনে রাখার টিপস:** DFS গভীরে যায়, তাই Stack।

---

## প্রশ্ন 416 | Topic: Algorithm > DFS > Traversal Order | Difficulty: Medium | Type: Theory

Q. একই graph ও একই start vertex-এর DFS traversal order ভিন্ন হতে পারে কেন?

A) DFS random number বাধ্যতামূলকভাবে ব্যবহার করে  
B) Graph-এর edge count প্রতি run-এ বদলায়  
C) DFS vertex visit করে না  
D) Neighbour processing order ভিন্ন হতে পারে

**সঠিক উত্তর: D) Neighbour processing order ভিন্ন হতে পারে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একাধিক unvisited neighbour থাকলে কোনটি আগে নেওয়া হবে, তার ওপর DFS tree ও order নির্ভর করে।
- **A option কেন ভুল:** Randomization বাধ্যতামূলক নয়।
- **B option কেন ভুল:** একই graph-এর edge count অপরিবর্তিত।
- **C option কেন ভুল:** DFS vertex visit করে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Exam-এ alphabetical বা ascending order উল্লেখ থাকলে তা অনুসরণ করতে হয়।
- **মনে রাখার টিপস:** Traversal order জানতে neighbour-order খুঁজুন।

---

# Chapter Theory 32: Tree and Binary Search Tree

## ১. Tree-এর মূল ধারণা

Tree হলো connected acyclic undirected graph।

n node-এর একটি tree-তে:

```text
Number of edges = n - 1
```

যেকোনো দুই node-এর মধ্যে exactly one simple path থাকে।

## ২. Rooted Tree Terminology

- **Root:** সর্বোচ্চ node
- **Parent:** একটি node-এর সরাসরি পূর্ববর্তী node
- **Child:** সরাসরি পরবর্তী node
- **Sibling:** একই parent-এর child
- **Leaf:** কোনো child নেই
- **Internal Node:** অন্তত একটি child আছে
- **Ancestor:** উপরের path-এর node
- **Descendant:** নিচের subtree-এর node
- **Depth:** Root থেকে node পর্যন্ত edge সংখ্যা
- **Height of Node:** Node থেকে deepest leaf পর্যন্ত longest edge count
- **Height of Tree:** Root-এর height

Height convention কিছু বইয়ে node count দিয়ে দেওয়া হয়। প্রশ্নে convention উল্লেখ করা না থাকলে edge-based বা level-based context পরীক্ষা করতে হবে।

## ৩. Binary Tree

প্রতিটি node-এর সর্বোচ্চ দুইটি child:

- Left child
- Right child

## ৪. Full, Complete এবং Perfect Binary Tree

### Full Binary Tree

প্রতিটি node-এর child সংখ্যা 0 অথবা 2।

### Complete Binary Tree

সব level পূর্ণ, শুধু শেষ level অসম্পূর্ণ হতে পারে; শেষ level বাম থেকে পূরণ হয়।

### Perfect Binary Tree

সব internal node-এর দুই child এবং সব leaf একই level-এ।

Edge-based height h হলে perfect tree:

```text
Total nodes = 2^(h + 1) - 1
Leaf nodes  = 2^h
```

## ৫. Binary Tree Traversal

### Preorder

```text
Root -> Left -> Right
```

### Inorder

```text
Left -> Root -> Right
```

### Postorder

```text
Left -> Right -> Root
```

### Level Order

Level-by-level; Queue ব্যবহার করে।

## ৬. Binary Search Tree

BST property:

```text
Left subtree keys  < Node key
Right subtree keys > Node key
```

Duplicate handling implementation policy অনুযায়ী নির্ধারিত।

### Operation Complexity

```text
Average search/insert/delete = O(log n)
Worst case                  = O(n)
```

Sorted input ordinary BST-কে skewed linked-list-এর মতো করতে পারে।

## ৭. BST Deletion

### Leaf node

সরাসরি remove।

### One-child node

Node-এর parent-কে child-এর সঙ্গে যুক্ত করা।

### Two-child node

সাধারণত replace করা হয়:

- Inorder successor — right subtree-এর minimum
- Inorder predecessor — left subtree-এর maximum

## ৮. Tree Representation

Binary tree node:

```c
struct Node {
    int key;
    struct Node *left;
    struct Node *right;
};
```

Array representation complete binary tree ও heap-এর জন্য সুবিধাজনক।

1-based indexing:

```text
Left child  = 2i
Right child = 2i + 1
Parent      = floor(i / 2)
```

0-based indexing:

```text
Left child  = 2i + 1
Right child = 2i + 2
Parent      = floor((i - 1) / 2)
```

## Common Mistakes

- Complete ও Full একই মনে করা
- Height ও node count convention গুলিয়ে ফেলা
- BST inorder sorted হয়—এই property ভুলে যাওয়া
- Two-child deletion-এ arbitrary node নেওয়া
- Tree edge count n মনে করা; আসলে n−1

## Exam Tips

- Tree = Connected + Acyclic
- n nodes → n−1 edges
- BST inorder → Sorted
- Preorder root first
- Postorder root last
- Complete tree array-friendly
- Skewed BST worst-case O(n)

---

# MCQ Practice: Tree and BST

## প্রশ্ন 417 | Topic: Data Structure > Tree > Edge Count | Difficulty: Easy | Type: Calculation

Q. একটি Tree-তে ২৫টি node থাকলে edge সংখ্যা কত?

A) 24  
B) 25  
C) 26  
D) 50

**সঠিক উত্তর: A) 24**

### গাণিতিক বিশ্লেষণ

#### Formula

```text
Edges in a tree = Number of nodes - 1
```

#### Given Data

```text
Nodes = 25
```

#### Calculation

```text
Edges = 25 - 1
      = 24
```

#### Final Answer

```text
Total edges = 24
```

### Option বিশ্লেষণ

- **A) 24:** এটি সঠিক উত্তর।
- **B) 25:** Node count-কে edge count ধরা হয়েছে।
- **C) 26:** এক যোগ করা হয়েছে।
- **D) 50:** Degree contribution-এর সঙ্গে গুলিয়ে ফেলা হয়েছে।
- **Related Concept:** n node ও n−1 edge-এর connected undirected graph অবশ্যই tree।
- **মনে রাখার টিপস:** Tree edge সবসময় node-এর এক কম।

---

## প্রশ্ন 418 | Topic: Data Structure > Binary Tree > Complete Tree | Difficulty: Medium | Type: Theory

Q. Complete Binary Tree-এর সঠিক বৈশিষ্ট্য কোনটি?

A) প্রতিটি node-এর ঠিক দুইটি child  
B) শেষ level ছাড়া সব level পূর্ণ এবং শেষ level বাম থেকে পূরণ হয়  
C) সব leaf ভিন্ন level-এ  
D) Inorder traversal সবসময় descending

**সঠিক উত্তর: B) শেষ level ছাড়া সব level পূর্ণ এবং শেষ level বাম থেকে পূরণ হয়**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Complete tree shape constraint level filling-এর ওপর ভিত্তি করে।
- **A option কেন ভুল:** এটি perfect/full-এর সঙ্গে মিলে যেতে পারে; complete tree-তে one-child node থাকতে পারে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Complete tree-তে leaf সাধারণত শেষ দুই level-এ থাকতে পারে।
- **D option কেন ভুল:** Traversal order key property-এর ওপর নির্ভর করে।
- **Related Concept:** Binary Heap একটি Complete Binary Tree।
- **মনে রাখার টিপস:** Complete মানে শেষ level বাম থেকে compact।

---

## প্রশ্ন 419 | Topic: Data Structure > Binary Tree > Traversal | Difficulty: Medium | Type: Tracing

Q. নিচের binary tree-এর Preorder traversal কোনটি?

```text
        A
       / \
      B   C
     / \   \
    D   E   F
```

A) `D, B, E, A, C, F`  
B) `D, E, B, F, C, A`  
C) `A, B, D, E, C, F`  
D) `A, C, F, B, E, D`

**সঠিক উত্তর: C) `A, B, D, E, C, F`**

### Traversal Rule

```text
Preorder = Root -> Left -> Right
```

### Step-by-step Trace

```text
Visit root A

Left subtree of A:
Visit B
Visit D
Visit E

Right subtree of A:
Visit C
Visit F
```

#### Final Answer

```text
Preorder = A, B, D, E, C, F
```

### Option বিশ্লেষণ

- **A:** এটি Inorder।
- **B:** এটি Postorder।
- **C:** এটি সঠিক উত্তর।
- **D:** Right subtree আগে নেওয়া হয়েছে।
- **Related Concept:** Preorder tree copy ও prefix-like serialization-এ ব্যবহৃত হতে পারে।
- **মনে রাখার টিপস:** Pre = Root আগে।

---

## প্রশ্ন 420 | Topic: Data Structure > BST > Inorder Property | Difficulty: Medium | Type: Theory

Q. Distinct key-যুক্ত Binary Search Tree-এর Inorder traversal কী দেয়?

A) Ascending sorted key sequence  
B) সবসময় descending sequence  
C) Level-order sequence  
D) Random sequence

**সঠিক উত্তর: A) Ascending sorted key sequence**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Inorder প্রথমে smaller left subtree, তারপর root, পরে larger right subtree visit করে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Reverse inorder descending দেয়।
- **C option কেন ভুল:** Level order Queue দিয়ে হয়।
- **D option কেন ভুল:** BST property deterministic sorted order দেয়।
- **Related Concept:** BST validate করতে inorder sequence strictly increasing কি না পরীক্ষা করা যায়।
- **মনে রাখার টিপস:** BST + Inorder = Sorted।

---

## প্রশ্ন 421 | Topic: Data Structure > BST > Insertion Trace | Difficulty: Medium | Type: Tracing

Q. Empty BST-তে ক্রমানুসারে `50, 30, 70, 20, 40` insert করলে `40` কোন node-এর child হবে?

A) 50-এর right child  
B) 20-এর right child  
C) 70-এর left child  
D) 30-এর right child

**সঠিক উত্তর: D) 30-এর right child**

### ধাপে ধাপে Insertion Trace

```text
Insert 50:
50 becomes root

Insert 30:
30 < 50
30 becomes left child of 50

Insert 70:
70 > 50
70 becomes right child of 50

Insert 20:
20 < 50
20 < 30
20 becomes left child of 30

Insert 40:
40 < 50
40 > 30
40 becomes right child of 30
```

#### Final Tree

```text
       50
      /  \
    30    70
   /  \
 20   40
```

#### Final Answer

```text
40 is the right child of 30
```

### Option বিশ্লেষণ

- **A:** 40 < 50, তাই right নয়।
- **B:** 40 > 20 হলেও search path-এ 20-এ যেতে হয় না।
- **C:** 40 < 70, কিন্তু root থেকে প্রথমে left subtree-এ যায়।
- **D:** এটি সঠিক উত্তর।
- **Related Concept:** BST insertion leaf position-এ হয়।
- **মনে রাখার টিপস:** প্রতিটি node-এ ছোট হলে left, বড় হলে right।

---

## প্রশ্ন 422 | Topic: Data Structure > BST > Worst Case | Difficulty: Medium | Type: Theory

Q. Ordinary BST-তে sorted ascending key insert করলে worst-case search `O(n)` হওয়ার কারণ কী?

A) Tree সবসময় complete হয়  
B) Tree একদিকে skewed chain হয়ে যেতে পারে  
C) প্রতিটি node দুই child পায়  
D) Hash collision ঘটে

**সঠিক উত্তর: B) Tree একদিকে skewed chain হয়ে যেতে পারে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি নতুন key আগের key-এর right child হলে height n−1 হয়।
- **A option কেন ভুল:** Sorted insertion complete tree তৈরি করে না।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** বরং অধিকাংশ node-এর একটি child থাকে।
- **D option কেন ভুল:** Hashing ব্যবহৃত হচ্ছে না।
- **Related Concept:** AVL ও Red-Black Tree height balance বজায় রাখে।
- **মনে রাখার টিপস:** Sorted data ordinary BST-এর শত্রু হতে পারে।

---

## প্রশ্ন 423 | Topic: Data Structure > Binary Tree > Perfect Tree Node Count | Difficulty: Easy | Type: Calculation

Q. Edge-based height 4-এর একটি Perfect Binary Tree-তে মোট node কতটি?

A) 15  
B) 16  
C) 31  
D) 32

**সঠিক উত্তর: C) 31**

### গাণিতিক বিশ্লেষণ

#### Formula

```text
Total nodes = 2^(h + 1) - 1
```

#### Given Data

```text
h = 4
```

#### Calculation

```text
Total nodes = 2^(4 + 1) - 1
            = 2^5 - 1
            = 32 - 1
            = 31
```

#### Final Answer

```text
Total nodes = 31
```

### Option বিশ্লেষণ

- **A) 15:** Height 3-এর perfect tree count।
- **B) 16:** শুধু last-level node count নেওয়া হয়েছে।
- **C) 31:** এটি সঠিক উত্তর।
- **D) 32:** Formula-এর `−1` বাদ দেওয়া হয়েছে।
- **Related Concept:** Height 4 হলে leaf count 2^4 = 16।
- **মনে রাখার টিপস:** Perfect total = next power of two minus one।

---

## প্রশ্ন 424 | Topic: Data Structure > Tree > Leaf Node | Difficulty: Hard | Type: Theory

Q. Rooted Tree-তে Leaf Node বলতে কী বোঝায়?

A) যে node-এর parent নেই  
B) যে node-এর degree সবসময় 2  
C) যে node root-এর child  
D) যে node-এর কোনো child নেই

**সঠিক উত্তর: D) যে node-এর কোনো child নেই**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Leaf বা terminal node-এর child count zero।
- **A option কেন ভুল:** এটি root-এর বৈশিষ্ট্য।
- **B option কেন ভুল:** Binary tree leaf-এর child zero।
- **C option কেন ভুল:** Root-এর child internal বা leaf—দুটিই হতে পারে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** একটি single-node tree-তে root একই সঙ্গে leaf।
- **মনে রাখার টিপস:** Leaf-এর নিচে আর branch নেই।

---

## প্রশ্ন 425 | Topic: Data Structure > Full Binary Tree > Leaf Relation | Difficulty: Easy | Type: Calculation

Q. একটি non-empty Full Binary Tree-তে internal node-এর সংখ্যা 12 হলে leaf node-এর সংখ্যা কত?

A) 11  
B) 12  
C) 24  
D) 13

**সঠিক উত্তর: D) 13**

### গাণিতিক বিশ্লেষণ

#### Property

Full Binary Tree-তে:

```text
Leaf nodes = Internal nodes + 1
```

#### Given Data

```text
Internal nodes = 12
```

#### Calculation

```text
Leaf nodes = 12 + 1
           = 13
```

#### Final Answer

```text
Leaf nodes = 13
```

### Option বিশ্লেষণ

- **A) 11:** এক বিয়োগ করা হয়েছে।
- **B) 12:** Leaf ও internal সমান ধরা হয়েছে।
- **C) 24:** Internal node দ্বিগুণ করা হয়েছে।
- **D) 13:** এটি সঠিক উত্তর।
- **Related Concept:** Full tree-তে total nodes = 2I + 1।
- **মনে রাখার টিপস:** Full Binary Tree-তে Leaf এক বেশি।

---

## প্রশ্ন 426 | Topic: Data Structure > Binary Tree > Level Order | Difficulty: Medium | Type: Theory

Q. Binary Tree-এর Level-order traversal implement করতে কোন data structure সবচেয়ে উপযুক্ত?

A) Recursion-only Stack  
B) Hash collision chain  
C) Queue  
D) Priority Heap বাধ্যতামূলক

**সঠিক উত্তর: C) Queue**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Parent visit-এর পরে তার child-গুলো FIFO queue-তে রেখে level-by-level process করা হয়।
- **A option কেন ভুল:** Stack depth-first order দেয়।
- **B option কেন ভুল:** Hash chain traversal structure নয়।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Level order-এর জন্য priority প্রয়োজন নেই।
- **Related Concept:** Level-order traversal আসলে tree-এর BFS।
- **মনে রাখার টিপস:** Level-by-level = Queue।

---

## প্রশ্ন 427 | Topic: Data Structure > Binary Tree > Array Index | Difficulty: Medium | Type: Calculation

Q. 1-based array representation-এ index 7-এ থাকা node-এর left child ও right child index কত?

A) 7 এবং 8  
B) 8 এবং 9  
C) 14 এবং 15  
D) 13 এবং 14

**সঠিক উত্তর: C) 14 এবং 15**

### গাণিতিক বিশ্লেষণ

#### Formula for 1-based indexing

```text
Left child  = 2i
Right child = 2i + 1
```

#### Given Data

```text
i = 7
```

#### Calculation

```text
Left child  = 2 × 7
            = 14

Right child = 2 × 7 + 1
            = 15
```

#### Final Answer

```text
Left index  = 14
Right index = 15
```

### Option বিশ্লেষণ

- **A:** শুধু এক করে বাড়ানো হয়েছে।
- **B:** 0-based child formula ভুলভাবে প্রয়োগ করা হয়েছে।
- **C:** এটি সঠিক উত্তর।
- **D:** Parent formula-এর মতো ভুল।
- **Related Concept:** 0-based হলে left=2i+1, right=2i+2।
- **মনে রাখার টিপস:** Index convention প্রথমে শনাক্ত করুন।

---

## প্রশ্ন 428 | Topic: Data Structure > BST > Two-child Deletion | Difficulty: Medium | Type: Theory

Q. BST-এর দুই child-যুক্ত node delete করতে সাধারণত replacement হিসেবে কোনটি ব্যবহার করা হয়?

A) যেকোনো random leaf  
B) Inorder successor বা Inorder predecessor  
C) Root সবসময়  
D) সর্বোচ্চ depth-এর যেকোনো node

**সঠিক উত্তর: B) Inorder successor বা Inorder predecessor**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** এরা deleted key-এর order position বজায় রেখে BST property রক্ষা করে।
- **A option কেন ভুল:** Random leaf order relation নষ্ট করতে পারে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Root replacement বাধ্যতামূলক নয়।
- **D option কেন ভুল:** Depth order property নিশ্চিত করে না।
- **Related Concept:** Successor = right subtree-এর minimum।
- **মনে রাখার টিপস:** Two child delete → Next larger বা next smaller key।

---

## প্রশ্ন 429 | Topic: Data Structure > Tree > Height Bound | Difficulty: Easy | Type: Theory

Q. n node-এর একটি skewed Binary Tree-এর edge-based maximum height কত হতে পারে?

A) `log₂ n`  
B) `n - 1`  
C) `n + 1`  
D) `2n`

**সঠিক উত্তর: B) `n - 1`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** প্রতিটি node-এর এক child থাকলে root থেকে deepest node পর্যন্ত n−1 edge।
- **A option কেন ভুল:** Balanced tree height logarithmic।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Edge count node count-এর চেয়ে এক কম।
- **D option কেন ভুল:** একটি simple root-to-leaf path-এ এত edge সম্ভব নয়।
- **Related Concept:** Skewed BST operation O(n)।
- **মনে রাখার টিপস:** Chain-এ n node মানে n−1 links।

---

## প্রশ্ন 430 | Topic: Data Structure > BST > Search Decision | Difficulty: Medium | Type: Theory

Q. BST-তে target key current node-এর key-এর চেয়ে ছোট হলে search কোনদিকে এগোয়?

A) Parent-এর দিকে  
B) সব child-এর দিকে একসঙ্গে  
C) Right subtree  
D) Left subtree

**সঠিক উত্তর: D) Left subtree**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** BST invariant অনুযায়ী current key-এর চেয়ে ছোট key left subtree-তে থাকে।
- **A option কেন ভুল:** Search root থেকে descendant দিকে যায়।
- **B option কেন ভুল:** BST comparison একটি subtree eliminate করে।
- **C option কেন ভুল:** Right subtree-তে বড় key থাকে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** এই elimination balanced BST-তে logarithmic search দেয়।
- **মনে রাখার টিপস:** Smaller left, larger right।

---

# Chapter Theory 33: AVL Tree

## ১. AVL Tree কী

AVL হলো self-balancing Binary Search Tree।

প্রতিটি node-এর `Balance Factor`:

```text
BF = Height(left subtree) - Height(right subtree)
```

Valid AVL node-এর জন্য:

```text
BF ∈ {-1, 0, +1}
```

কোনো insertion বা deletion-এর পরে BF এই range-এর বাইরে গেলে rotation প্রয়োজন।

## ২. Rotation Case

### LL Case

Insertion unbalanced node-এর left child-এর left subtree-তে।

সমাধান:

```text
Single Right Rotation
```

### RR Case

Insertion right child-এর right subtree-তে।

সমাধান:

```text
Single Left Rotation
```

### LR Case

Insertion left child-এর right subtree-তে।

সমাধান:

```text
Left rotation on left child
Then right rotation on unbalanced node
```

### RL Case

Insertion right child-এর left subtree-তে।

সমাধান:

```text
Right rotation on right child
Then left rotation on unbalanced node
```

## ৩. AVL Complexity

Height O(log n), তাই:

```text
Search = O(log n)
Insert = O(log n)
Delete = O(log n)
```

Rotation নিজে O(1), কিন্তু search path ও height update O(log n)।

## ৪. AVL বনাম Ordinary BST

AVL:

- বেশি strictly balanced
- Search দ্রুত ও predictable
- Update-এ rotation overhead

Ordinary BST:

- Implementation সহজ
- Worst-case skewed O(n)
- Balance guarantee নেই

## ৫. Common Mistakes

- BF formula উল্টো করা
- LL case-এ left rotation করা
- LR case-এ এক rotation যথেষ্ট মনে করা
- Rotation-এর পরে BST order যাচাই না করা
- Height convention বদলে result গুলিয়ে ফেলা

## ৬. Exam Tips

- LL → Right rotate
- RR → Left rotate
- LR → Left then Right
- RL → Right then Left
- AVL BF শুধু −1, 0, +1
- Rotation local, search path logarithmic

---

# MCQ Practice: AVL Tree

## প্রশ্ন 431 | Topic: Data Structure > AVL Tree > Balance Factor | Difficulty: Hard | Type: Theory

Q. AVL Tree-তে একটি balanced node-এর গ্রহণযোগ্য Balance Factor কোন set-এর মধ্যে থাকে?

A) `{0, 1, 2}`  
B) `{-2, -1, 0}`  
C) যেকোনো integer  
D) `{-1, 0, +1}`

**সঠিক উত্তর: D) `{-1, 0, +1}`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Left ও right subtree height difference সর্বোচ্চ 1 হতে পারে।
- **A option কেন ভুল:** +2 unbalanced।
- **B option কেন ভুল:** −2 unbalanced।
- **C option কেন ভুল:** AVL strict height balance বজায় রাখে।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** BF = left height − right height।
- **মনে রাখার টিপস:** AVL balance range তিনটি value: −1, 0, +1।

---

## প্রশ্ন 432 | Topic: Data Structure > AVL Tree > LL Rotation | Difficulty: Medium | Type: Tracing

Q. Empty AVL Tree-তে ক্রমানুসারে `30, 20, 10` insert করলে কোন rotation প্রয়োজন এবং নতুন root কী হবে?

A) Left Rotation; root 20  
B) LR Rotation; root 10  
C) Right Rotation; root 20  
D) RL Rotation; root 30

**সঠিক উত্তর: C) Right Rotation; root 20**

### ধাপে ধাপে Insertion

```text
Insert 30:

30

Insert 20:

   30
  /
20

Insert 10:

    30
   /
 20
 /
10
```

Node 30-এ LL imbalance হয়েছে।

#### Rotation

```text
Right rotate at 30
```

#### Final Tree

```text
   20
  /  \
10   30
```

#### Final Answer

```text
Rotation = Single Right Rotation
New root = 20
```

### Option বিশ্লেষণ

- **A:** Left rotation RR case-এর জন্য।
- **B:** Insertion left-left path-এ; LR নয়।
- **C:** এটি সঠিক উত্তর।
- **D:** RL case নয়।
- **Related Concept:** Median key 20 rotation-এর পরে subtree root হয়।
- **মনে রাখার টিপস:** LL imbalance-কে ডানদিকে rotate করুন।

---

## প্রশ্ন 433 | Topic: Data Structure > AVL Tree > RR Case | Difficulty: Medium | Type: Theory

Q. AVL Tree-তে RR imbalance ঠিক করতে কোন rotation ব্যবহার করা হয়?

A) Single Right Rotation  
B) Right-Left Double Rotation  
C) Single Left Rotation  
D) Left-Right Double Rotation

**সঠিক উত্তর: C) Single Left Rotation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Right subtree-এর right side heavy হলে unbalanced node-কে left rotate করা হয়।
- **A option কেন ভুল:** এটি LL case-এর জন্য।
- **B option কেন ভুল:** এটি RL case।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** এটি LR case।
- **Related Concept:** `10, 20, 30` insertion RR case।
- **মনে রাখার টিপস:** RR heavy → Left rotate।

---

## প্রশ্ন 434 | Topic: Data Structure > AVL Tree > Balance Factor Calculation | Difficulty: Medium | Type: Calculation

Q. একটি node-এর left subtree height 4 এবং right subtree height 2। `BF = left height − right height` হলে Balance Factor কত এবং node balanced কি না?

A) BF = −2, balanced  
B) BF = 2, balanced  
C) BF = −2, unbalanced  
D) BF = 2, unbalanced

**সঠিক উত্তর: D) BF = 2, unbalanced**

### গাণিতিক বিশ্লেষণ

#### Formula

```text
BF = Height(left) - Height(right)
```

#### Given Data

```text
Left height  = 4
Right height = 2
```

#### Calculation

```text
BF = 4 - 2
   = 2
```

AVL valid range:

```text
-1, 0, +1
```

`BF = 2` valid range-এর বাইরে।

#### Final Answer

```text
Balance Factor = 2
Node status    = Unbalanced
```

### Option বিশ্লেষণ

- **A:** Formula উল্টো এবং balanced status ভুল।
- **B:** BF ঠিক, কিন্তু +2 balanced নয়।
- **C:** Sign ভুল; status ঠিক।
- **D:** এটি সঠিক উত্তর।
- **Related Concept:** Positive BF left-heavy।
- **মনে রাখার টিপস:** Absolute BF > 1 হলে rotation দরকার।

---

## প্রশ্ন 435 | Topic: Data Structure > AVL Tree > LR Case | Difficulty: Hard | Type: Theory

Q. AVL Tree-তে LR imbalance সমাধানের সঠিক rotation sequence কোনটি?

A) Unbalanced node-এ শুধু Left Rotation  
B) Left child-এ Left Rotation, তারপর unbalanced node-এ Right Rotation  
C) Right child-এ Right Rotation, তারপর Left Rotation  
D) শুধু Right Rotation

**সঠিক উত্তর: B) Left child-এ Left Rotation, তারপর unbalanced node-এ Right Rotation**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Left subtree-এর right branch heavy; প্রথমে এটিকে LL shape-এ convert করে পরে right rotate করা হয়।
- **A option কেন ভুল:** Single left rotation LR imbalance ঠিক করে না।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** এটি RL case-এর sequence।
- **D option কেন ভুল:** Pure LL case হলে single right যথেষ্ট।
- **Related Concept:** `30, 10, 20` insertion LR case।
- **মনে রাখার টিপস:** LR নামের order: Left rotation, তারপর Right rotation।

---

## প্রশ্ন 436 | Topic: Data Structure > AVL Tree > RL Insertion Trace | Difficulty: Medium | Type: Scenario

Q. Empty AVL Tree-তে `10, 30, 20` insert করলে final root কোনটি?

A) 10  
B) 30  
C) Rotation প্রয়োজন নেই  
D) 20

**সঠিক উত্তর: D) 20**

### ধাপে ধাপে Insertion

```text
Insert 10:

10

Insert 30:

10
  \
  30

Insert 20:

10
  \
  30
 /
20
```

Node 10-এ Right-Left বা RL imbalance।

#### Rotation Sequence

```text
1. Right rotate at 30
2. Left rotate at 10
```

#### Final Tree

```text
   20
  /  \
10   30
```

#### Final Answer

```text
Final root = 20
```

### Option বিশ্লেষণ

- **A:** Rotation না করলে root 10 থাকত, কিন্তু tree unbalanced।
- **B:** শুধু প্রথম rotation-এর ভুল interpretation।
- **C:** Root 10-এর balance factor −2।
- **D:** এটি সঠিক উত্তর।
- **Related Concept:** Three-key AVL insertion-এর পরে median key প্রায়ই local root হয়।
- **মনে রাখার টিপস:** 10,30,20 pattern → RL → middle key root।

---

## প্রশ্ন 437 | Topic: Data Structure > AVL Tree > Complexity | Difficulty: Medium | Type: Theory

Q. AVL Tree-এর worst-case search complexity কত?

A) `O(1)`  
B) `O(n)`  
C) `O(n log n)`  
D) `O(log n)`

**সঠিক উত্তর: D) `O(log n)`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** AVL height logarithmicভাবে bounded।
- **A option কেন ভুল:** Root ছাড়া arbitrary key constant time নয়।
- **B option কেন ভুল:** Ordinary skewed BST-তে O(n), AVL-এ balance guarantee আছে।
- **C option কেন ভুল:** এক search-এর complexity নয়।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Insert/delete-ও search pathসহ O(log n)।
- **মনে রাখার টিপস:** Balanced BST মানে logarithmic height।

---

## প্রশ্ন 438 | Topic: Data Structure > AVL Tree > Height Comparison | Difficulty: Easy | Type: Calculation

Q. একটি perfectly balanced binary search tree-তে 31টি node আছে। Edge-based height কত?

A) 4  
B) 5  
C) 15  
D) 30

**সঠিক উত্তর: A) 4**

### গাণিতিক বিশ্লেষণ

Perfect tree formula:

```text
Nodes = 2^(h + 1) - 1
```

Given:

```text
31 = 2^(h + 1) - 1
```

#### Calculation

```text
31 + 1 = 2^(h + 1)
32     = 2^(h + 1)
32     = 2^5

h + 1 = 5
h     = 4
```

#### Final Answer

```text
Edge-based height = 4
```

### Option বিশ্লেষণ

- **A) 4:** এটি সঠিক উত্তর।
- **B) 5:** Level count-কে edge height ধরা হয়েছে।
- **C) 15:** Node count-এর অর্ধেকের কাছাকাছি ভুল।
- **D) 30:** Skewed tree height ধরা হয়েছে।
- **Related Concept:** Height convention পরীক্ষা করা জরুরি; level count এখানে 5।
- **মনে রাখার টিপস:** 31 = 2^5−1, তাই edge height 4।

---

## প্রশ্ন 439 | Topic: Data Structure > AVL Tree > Rotation Cost | Difficulty: Hard | Type: Theory

Q. একটি single AVL rotation-এর নিজস্ব pointer-update cost সাধারণত কত?

A) `O(log n)`  
B) `O(n)`  
C) `O(1)`  
D) `O(n²)`

**সঠিক উত্তর: C) `O(1)`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Rotation একটি local constant সংখ্যক node ও pointer update করে।
- **A option কেন ভুল:** Insert operation মোট O(log n), কিন্তু এক rotation local O(1)।
- **B option কেন ভুল:** পুরো tree traverse লাগে না।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** Nested traversal নেই।
- **Related Concept:** Height update path-এর কারণে পুরো insert/delete logarithmic।
- **মনে রাখার টিপস:** Rotation ছোট local surgery।

---

## প্রশ্ন 440 | Topic: Data Structure > AVL Tree > AVL vs BST | Difficulty: Medium | Type: Theory

Q. Ordinary BST-এর তুলনায় AVL Tree-এর প্রধান trade-off কোনটি?

A) AVL search ধীর এবং update free  
B) AVL কোনো key compare করে না  
C) AVL দ্রুত ও bounded search দেয়, কিন্তু update-এ rotation overhead থাকতে পারে  
D) AVL শুধু sorted linked list

**সঠিক উত্তর: C) AVL দ্রুত ও bounded search দেয়, কিন্তু update-এ rotation overhead থাকতে পারে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Strict balance search height কম রাখে; insertion/deletion-এ balance factor ও rotation maintain করতে হয়।
- **A option কেন ভুল:** Search সাধারণত AVL-এ বেশি predictable।
- **B option কেন ভুল:** AVL একটি BST; comparison ব্যবহার করে।
- **C option:** এটি সঠিক উত্তর।
- **D option কেন ভুল:** AVL tree structure।
- **Related Concept:** Read-heavy workload-এ AVL উপযোগী হতে পারে।
- **মনে রাখার টিপস:** Better search balance-এর বিনিময়ে update maintenance।

---

# Chapter Theory 34: Hashing

## ১. Hashing-এর মূল ধারণা

Hashing key-কে একটি table index-এ map করে।

```text
index = h(key)
```

ভালো hash function:

- দ্রুত compute হয়
- Key-গুলো table-এ uniformভাবে ছড়ায়
- Collision কমায়
- Deterministic

## ২. Collision

দুইটি ভিন্ন key একই index পেলে collision হয়।

```text
h(k1) = h(k2), যেখানে k1 != k2
```

Collision পুরোপুরি এড়ানো সাধারণত সম্ভব নয়; resolution method প্রয়োজন।

## ৩. Load Factor

```text
Load Factor α = Number of stored keys / Table size
```

### Separate Chaining

- প্রতিটি slot-এ list/bucket
- α 1-এর বেশি হতে পারে
- Average search প্রায় O(1+α), ভালো hashing assumption-এ

### Open Addressing

সব key table-এর slot-এ থাকে।

- সাধারণত α < 1
- Empty slot না থাকলে insertion অসম্ভব

## ৪. Linear Probing

```text
h_i(k) = (h(k) + i) mod m
```

Sequence:

```text
h, h+1, h+2, ...
```

সমস্যা:

- Primary clustering

## ৫. Quadratic Probing

একটি common form:

```text
h_i(k) = (h(k) + i²) mod m
```

Primary clustering কমায়, কিন্তু secondary clustering থাকতে পারে।

## ৬. Double Hashing

```text
h_i(k) = (h1(k) + i × h2(k)) mod m
```

ভালো coverage-এর জন্য step size ও table size coprime হওয়া দরকার।

## ৭. Separate Chaining

একই hash slot-এর key-গুলো linked list বা অন্য bucket structure-এ রাখা হয়।

সুবিধা:

- Deletion সহজ
- Table full হলেও bucket বাড়তে পারে
- α > 1 সম্ভব

সীমাবদ্ধতা:

- Extra pointer/storage
- Cache locality কম হতে পারে

## ৮. Static এবং Dynamic Hashing

### Static Hashing

Bucket সংখ্যা fixed। Data বাড়লে performance কমতে পারে।

### Dynamic Hashing

Data size-এর সঙ্গে bucket structure expand/shrink করতে পারে।

উদাহরণ:

- Extendible Hashing
- Linear Hashing

## ৯. Hashing বনাম Ordered Index

Hashing:

- Exact-match search-এ দ্রুত
- Range query-তে দুর্বল
- Sorted traversal দেয় না

B+ Tree/Ordered Index:

- Exact ও range—দুই query সমর্থন করে
- Ordered traversal
- Disk index-এর জন্য কার্যকর

## ১০. Common Mistakes

- Collision মানেই duplicate key মনে করা
- Load factor formula উল্টো করা
- Linear probing-এ modulo বাদ দেওয়া
- Open addressing-এ deleted slot handling ভুল করা
- Hashing দিয়ে efficient range query আশা করা

## ১১. Exam Tips

- Collision: different keys, same index
- α = n/m
- Linear probe: +1 steps
- Quadratic probe: +i²
- Double hash: second hash step
- Exact lookup → Hashing
- Range query → B+ Tree/Ordered index

---

# MCQ Practice: Hashing

## প্রশ্ন 441 | Topic: Data Structure > Hashing > Collision | Difficulty: Hard | Type: Theory

Q. Hash Collision কখন ঘটে?

A) দুটি ভিন্ন key একই table index-এ map করলে  
B) একই key একই index-এ map করলে  
C) Table size prime হলে  
D) Load factor zero হলে

**সঠিক উত্তর: A) দুটি ভিন্ন key একই table index-এ map করলে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Hash function অনেক key-space-কে সীমিত slot-space-এ map করে; ভিন্ন key একই slot পেতে পারে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Deterministic hash-এ একই key একই index পাওয়া স্বাভাবিক; এটি collision-এর সংজ্ঞা নয়।
- **C option কেন ভুল:** Prime size collision কমাতে সাহায্য করতে পারে, কিন্তু collision define করে না।
- **D option কেন ভুল:** Empty table-এ stored-key collision নেই।
- **Related Concept:** Pigeonhole Principle অনুযায়ী key-space slot-এর চেয়ে বড় হলে collision সম্ভব।
- **মনে রাখার টিপস:** Different key, same home slot।

---

## প্রশ্ন 442 | Topic: Data Structure > Hashing > Hash Index | Difficulty: Hard | Type: Calculation

Q. Hash table size 11 এবং `h(k) = k mod 11`। Key `83`-এর home index কত?

A) 5  
B) 7  
C) 6  
D) 8

**সঠিক উত্তর: C) 6**

### গাণিতিক বিশ্লেষণ

#### Formula

```text
h(k) = k mod m
```

#### Given Data

```text
k = 83
m = 11
```

#### Calculation

```text
83 ÷ 11 = 7 remainder 6

83 mod 11 = 6
```

#### Final Answer

```text
Home index = 6
```

### Option বিশ্লেষণ

- **A) 5:** Remainder ভুল।
- **B) 7:** Quotient-কে index ধরা হয়েছে।
- **C) 6:** এটি সঠিক উত্তর।
- **D) 8:** Key-এর tens digit ব্যবহার করা হয়েছে।
- **Related Concept:** Valid table index 0 থেকে 10।
- **মনে রাখার টিপস:** Modulo-তে quotient নয়, remainder নিন।

---

## প্রশ্ন 443 | Topic: Data Structure > Hashing > Load Factor | Difficulty: Easy | Type: Theory

Q. Hash table-এর Load Factor-এর standard formula কোনটি?

A) `α = stored keys / table slots`  
B) `α = table slots / stored keys`  
C) `α = collisions × slots`  
D) `α = keys + slots`

**সঠিক উত্তর: A) `α = stored keys / table slots`**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Table কতটা occupied বা loaded তা n/m ratio দিয়ে মাপা হয়।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Formula উল্টো।
- **C option কেন ভুল:** Collision count load factor-এর সরাসরি numerator নয়।
- **D option কেন ভুল:** Sum occupancy ratio দেয় না।
- **Related Concept:** Open addressing-এ α অবশ্যই 1-এর কম বা সমান।
- **মনে রাখার টিপস:** Items divided by capacity।

---

## প্রশ্ন 444 | Topic: Data Structure > Hashing > Linear Probing | Difficulty: Hard | Type: Tracing

Q. Table size 10, `h(k) = k mod 10` এবং Linear Probing ব্যবহৃত হচ্ছে। ক্রমানুসারে `23, 43, 13` insert করলে key `13` কোন index-এ থাকবে?

A) 5  
B) 3  
C) 4  
D) 6

**সঠিক উত্তর: A) 5**

### ধাপে ধাপে Probe Trace

#### Key 23

```text
h(23) = 23 mod 10
      = 3

Index 3 empty
23 stored at 3
```

#### Key 43

```text
h(43) = 3

Index 3 occupied by 23
Probe index 4
Index 4 empty
43 stored at 4
```

#### Key 13

```text
h(13) = 3

Index 3 occupied
Index 4 occupied
Probe index 5
Index 5 empty

13 stored at 5
```

#### Final Answer

```text
Key 13 index = 5
```

### Option বিশ্লেষণ

- **A) 5:** এটি সঠিক উত্তর।
- **B) 3:** Home slot collision উপেক্ষা করা হয়েছে।
- **C) 4:** দ্বিতীয় key-এর অবস্থান নেওয়া হয়েছে।
- **D) 6:** একটি অতিরিক্ত probe করা হয়েছে।
- **Related Concept:** Consecutive occupied block Primary Clustering তৈরি করে।
- **মনে রাখার টিপস:** Linear probing-এ এক slot করে সামনে যান।

---

## প্রশ্ন 445 | Topic: Data Structure > Hashing > Primary Clustering | Difficulty: Medium | Type: Theory

Q. Primary Clustering সমস্যা কোন collision resolution method-এর সঙ্গে সবচেয়ে বেশি সম্পর্কিত?

A) Separate Chaining  
B) Linear Probing  
C) Perfect Hashing  
D) B+ Tree indexing

**সঠিক উত্তর: B) Linear Probing**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Consecutive occupied slot-এর cluster তৈরি হলে নতুন colliding key cluster-এর শেষে যোগ হয় এবং cluster বড় হয়।
- **A option কেন ভুল:** Chaining slot-ভিত্তিক linked bucket ব্যবহার করে।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Perfect hashing collision-free target করতে পারে।
- **D option কেন ভুল:** এটি ordered tree index।
- **Related Concept:** Quadratic probing primary clustering কমায়।
- **মনে রাখার টিপস:** Linear step cluster-কে line-এর মতো বড় করে।

---

## প্রশ্ন 446 | Topic: Data Structure > Hashing > Quadratic Probing | Difficulty: Medium | Type: Calculation

Q. Table size 11, home index 4 এবং Quadratic Probing formula `(4 + i²) mod 11`, যেখানে প্রথম collision-এর পরে `i = 1`। প্রথম তিনটি probe index কী?

A) 4, 5, 6  
B) 5, 8, 2  
C) 5, 9, 3  
D) 4, 8, 9

**সঠিক উত্তর: B) 5, 8, 2**

### গাণিতিক বিশ্লেষণ

#### Formula

```text
Probe(i) = (4 + i²) mod 11
```

#### First Probe: i = 1

```text
(4 + 1²) mod 11
= 5 mod 11
= 5
```

#### Second Probe: i = 2

```text
(4 + 2²) mod 11
= (4 + 4) mod 11
= 8
```

#### Third Probe: i = 3

```text
(4 + 3²) mod 11
= (4 + 9) mod 11
= 13 mod 11
= 2
```

#### Final Answer

```text
Probe sequence = 5, 8, 2
```

### Option বিশ্লেষণ

- **A:** Linear probing করা হয়েছে।
- **B:** এটি সঠিক উত্তর।
- **C:** Square calculation ও modulo ভুল।
- **D:** Home index-কে প্রথম collision probe হিসেবে পুনরায় নেওয়া হয়েছে।
- **Related Concept:** Quadratic sequence সব slot visit করবে কি না table size ও formula-এর ওপর নির্ভর করে।
- **মনে রাখার টিপস:** i-এর square নিন, তারপর modulo।

---

## প্রশ্ন 447 | Topic: Data Structure > Hashing > Separate Chaining | Difficulty: Easy | Type: Theory

Q. Separate Chaining-এ collision হওয়া key-গুলো সাধারণত কোথায় রাখা হয়?

A) অন্য একটি sorted array বাধ্যতামূলকভাবে  
B) সংশ্লিষ্ট table slot-এর bucket বা linked chain-এ  
C) CPU register-এ  
D) Table-এর বাইরে ফেলে দেওয়া হয়

**সঠিক উত্তর: B) সংশ্লিষ্ট table slot-এর bucket বা linked chain-এ**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** একই hash index পাওয়া key-গুলো একটি collection-এ সংরক্ষিত হয়।
- **A option কেন ভুল:** Linked list, dynamic array বা tree bucket হতে পারে; sorted array বাধ্যতামূলক নয়।
- **B option:** এটি সঠিক উত্তর।
- **C option কেন ভুল:** Persistent hash storage register-এ হয় না।
- **D option কেন ভুল:** Collision key হারানো যায় না।
- **Related Concept:** Long chain search performance কমায়।
- **মনে রাখার টিপস:** Same slot, separate chain।

---

## প্রশ্ন 448 | Topic: Data Structure > Hashing > Load Factor Calculation | Difficulty: Hard | Type: Calculation

Q. 50-slot hash table-এ 35টি key stored আছে। Load Factor কত?

A) 0.70  
B) 1.43  
C) 0.50  
D) 0.35

**সঠিক উত্তর: A) 0.70**

### গাণিতিক বিশ্লেষণ

#### Formula

```text
Load Factor α = Number of keys / Number of slots
```

#### Given Data

```text
Keys  = 35
Slots = 50
```

#### Calculation

```text
α = 35 / 50
  = 0.70
```

Percentage হিসেবে:

```text
0.70 × 100 = 70%
```

#### Final Answer

```text
Load Factor = 0.70
```

### Option বিশ্লেষণ

- **A) 0.70:** এটি সঠিক উত্তর।
- **B) 1.43:** Formula উল্টো `50/35` করা হয়েছে।
- **C) 0.50:** Slot count-এর অর্ধেক নেওয়া হয়েছে।
- **D) 0.35:** Key count-কে 100 দিয়ে ভাগ করা হয়েছে।
- **Related Concept:** Open addressing-এ α বাড়লে probe length সাধারণত বাড়ে।
- **মনে রাখার টিপস:** Stored items ÷ total slots।

---

## প্রশ্ন 449 | Topic: Data Structure > Hashing > Range Query | Difficulty: Medium | Type: Theory

Q. অনেক range query যেমন “key 100 থেকে 500-এর মধ্যে” চালাতে কোন structure সাধারণত Hash Table-এর চেয়ে বেশি উপযোগী?

A) B+ Tree বা ordered index  
B) Unordered Hash Table  
C) Stack  
D) Circular Queue

**সঠিক উত্তর: A) B+ Tree বা ordered index**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** Ordered index starting key খুঁজে sequentially range traverse করতে পারে।
- **A option:** এটি সঠিক উত্তর।
- **B option কেন ভুল:** Hashing order সংরক্ষণ করে না।
- **C option কেন ভুল:** Stack key-range indexing structure নয়।
- **D option কেন ভুল:** Queue FIFO processing দেয়।
- **Related Concept:** Exact equality lookup-এ Hash Table সাধারণত খুব দ্রুত।
- **মনে রাখার টিপস:** Exact → Hash; Range → Ordered Tree।

---

## প্রশ্ন 450 | Topic: Data Structure > Hashing > Double Hashing | Difficulty: Easy | Type: Theory

Q. Double Hashing-এর probe sequence-এর প্রধান বৈশিষ্ট্য কী?

A) প্রতিবার fixed `+1` ব্যবহার করে  
B) কোনো দ্বিতীয় function লাগে না  
C) সব collision chain-এ রাখে  
D) দ্বিতীয় hash function probe step size নির্ধারণ করে

**সঠিক উত্তর: D) দ্বিতীয় hash function probe step size নির্ধারণ করে**

### বিস্তারিত বিশ্লেষণ

- **সঠিক উত্তর কেন:** `h2(k)` key-specific step তৈরি করে, ফলে clustering কমতে পারে।
- **A option কেন ভুল:** এটি Linear Probing।
- **B option কেন ভুল:** Double Hashing-এর নামই দুই hash function থেকে।
- **C option কেন ভুল:** এটি Separate Chaining।
- **D option:** এটি সঠিক উত্তর।
- **Related Concept:** Step size ও table size coprime হলে বেশি slot cover করা যায়।
- **মনে রাখার টিপস:** First hash home slot, second hash jump size।

---

# Batch Quality Summary

## Question Count

```text
Question Range          = 401–450
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

- Graph terminology
- Directed ও Undirected Graph
- Weighted Graph
- Degree, In-degree ও Out-degree
- Handshaking Lemma
- Path, Cycle ও Connectivity
- Complete Graph
- Bipartite Graph
- Adjacency Matrix
- Adjacency List
- Sparse বনাম Dense Graph
- BFS
- DFS
- BFS shortest path
- BFS/DFS complexity
- Tree terminology
- Full, Complete ও Perfect Binary Tree
- Preorder, Inorder, Postorder ও Level-order
- Binary Search Tree
- BST insertion, search ও deletion
- Tree array representation
- AVL Balance Factor
- LL, RR, LR ও RL Rotation
- AVL complexity
- Hash function
- Collision
- Load Factor
- Linear Probing
- Quadratic Probing
- Double Hashing
- Separate Chaining
- Static ও Dynamic Hashing
- Hashing বনাম ordered index

## Math and Tracing Coverage

```text
Degree-sum edge count             : Included
Adjacency Matrix storage          : Included
Complete/Bipartite edge count     : Included
Adjacency List entry count        : Included
BFS queue trace                   : Included
BFS distance                      : Included
Tree edge count                   : Included
Tree traversal                    : Included
BST insertion                     : Included
Perfect tree node count           : Included
Full tree leaf relation           : Included
Array child-index calculation     : Included
AVL rotation trace                : Included
Balance Factor calculation        : Included
AVL height calculation            : Included
Hash index calculation            : Included
Linear probe trace                : Included
Quadratic probe sequence          : Included
Load Factor calculation           : Included
```

## Quality Checks

```text
Numbering continuity       : Passed
Question total             : Passed
Difficulty distribution    : Passed
Answer balance             : Passed
Syllabus relevance         : Passed
Calculation verification   : Passed
Plain-text math alignment  : Passed
Raw LaTeX issue            : Removed
Bangla explanation         : Passed
Technical keywords         : Preserved
Duplicate option check     : Passed
```

---

## Next Coverage

পরবর্তী Batch 11 — Question 451–500:

- B-Tree এবং B+ Tree
- Shortest Path
- Dijkstra
- Bellman-Ford
- Floyd-Warshall
- Minimum Spanning Tree
- Kruskal এবং Prim
- Topological Sorting
- Greedy Strategy
- Fractional Knapsack
- Activity Selection
- Huffman Encoding
