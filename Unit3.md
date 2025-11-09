**Design and Analysis of Algorithms**

**ASSIGNMENT-03**

\-By Dhruv Popli

04513302723

CSE-5A

**SECTION A - Short Theory \[15 Marks\]**

**1) DP essentials**

**\- List the three ingredients of DP and one-line purpose of each. \[2\]\[1\]**

1) DP essentials include 3 ingredients that are-

- Optimal substructure - Breaks problem into smaller optimal subproblems.
- Overlapping subproblems - Reuses already-solved subproblems.
- Memorization/tabulation - Stores and reuses computed results to avoid recomputation.

**2) DP vs D&C**

**\- State two differences focusing on subproblem overlap and reuse; give one example for each. \[2\]\[1\]**

2) DP vs D&C

- DP: overlapping subproblems, results reused → _e.g._, Fibonacci.
- D&C: disjoint subproblems, no reuse → _e.g._, Merge Sort.

**3) Principle of optimality**

**\- Define it in one sentence and name any one problem satisfying it. \[3\]\[4\]**

Principle of optimality  
An optimal solution contains optimal solutions to its subproblems.  
Example: Shortest Path (Floyd-Warshall).

**4) Memoization**

**\- Define memoization and contrast with tabulation in one line each. \[1\]**

Memoization  
Top-down: store results of recursive calls.  
Tabulation: bottom-up: fill DP table iteratively.

**5) Branch and Bound idea**

**\- Define BnB and the role of bounding in pruning in two lines. \[5\]\[6\]**

Branch and Bound  
Systematically explores state space using bounds.  
Bounding prunes branches whose best possible value ≤ current best.

**SECTION B - Algorithms & Recurrences \[15 Marks\]**

- **Matrix Chain Multiplication (A₁:5×4, A₂:4×6, A₃:6×2, A₄:2×7)  
    a) Write m\[i,j\] recurrence and base case (no derivation). \[4\]\[7\]\[8\]**

a)Base: m\[i,i\] = 0

Recurrence: m\[i,j\] = min_{i≤k<j} (m\[i,k\] + m\[k+1,j\] + p_{i−1}·p_k·p_j)  
**b) State the minimum scalar multiplications (number only). \[8\]\[4\]**

b) Minimum scalar multiplications = 158

- **Longest Common Subsequence (X="ABCDGH", Y="AEDFHR")  
    a) Write the LCS(i,j) recurrence and base. \[1\]**

Base: LCS(i,0)=LCS(0,j)=0

Recurrence:

if X\[i\]=Y\[j\]: LCS(i,j)=1+LCS(i−1,j−1)

else: LCS(i,j)=max(LCS(i−1,j), LCS(i,j−1))

**b) Give the LCS length (number only). \[1\]**

b) LCS length = 3

- **Optimal Binary Search Tree (keys: 10,20,30; p: 0.4,0.3,0.3; assume q=0)**
  - **Write w\[i,j\] and e\[i,j\] DP formulations with base. \[1\]**

Base: e\[i,i−1\]=w\[i,i−1\]=0

w\[i,j\]=w\[i,j−1\]+p_j

e\[i,j\]=min_{r=i..j}(e\[i,r−1\]+e\[r+1,j\]+w\[i,j\])

- 1. **State the minimum expected search cost (number only). \[1\]**

b) **Minimum expected search cost = 1.9**

- **0/1 Knapsack - Branch & Bound (W=5; w={2,3,4,5}, p={3,4,5,6})**
  - **Write the fractional upper bound formula used for pruning. \[6\]\[9\]\[5\]**

UB = v + (W−w) \* (p_next / w_next) // fractional upper bound

- 1. **Show level-0 and level-1 nodes (include/exclude first item) with (v,w,ub) only. \[5\]\[6\]**

Level-0: (v=0, w=0, ub=10.0)

Level-1 Include: (v=3, w=2, ub=9.0)

Level-1 Exclude: (v=0, w=0, ub=10.0)

- **TSP - Dynamic Programming (Held-Karp; 4 cities, example D given)**
  - **Write the C\[S,j\] recurrence and final answer expression. \[1\]**

C\[S,j\] = min_{k∈S−{j}} (C\[S−{j},k\] + D\[k\]\[j\])

Final: min_{j≠1} (C\[{all},j\] + D\[j\]\[1\])

- 1. **Initialize base entries C\[{k},k\] for k=2..4 (numbers only for the given D). \[1\]**

C\[{2},2\]=D\[1\]\[2\], C\[{3},3\]=D\[1\]\[3\], C\[{4},4\]=D\[1\]\[4\]
