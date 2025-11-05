**[ASSIGNMENT-3]{.underline}**

**[SECTION A -- Short Theory \[15 Marks\]]{.underline}**

**QUES 1). DP essentials**

-   **List the three ingredients of DP and one-line purpose of each.**

The three ingredients of Dynamic Programming (DP) and their purposes
are:

1.  Optimal Substructure -- The problem can be broken down into smaller
    subproblems whose optimal solutions can be combined to form the
    overall optimal solution.

2.  Overlapping Subproblems -- The same subproblems recur multiple
    times, allowing reuse of their solutions instead of recomputing.

3.  Memoization / Tabulation -- To store the results of subproblems
    (either top-down or bottom-up) and avoid redundant calculations,
    improving efficiency.

**QUES 2). DP vs D&C**

-   **State two differences focusing on subproblem overlap and reuse;
    give one example for each. \[2\]\[1\]**

> Two differences:

1.  Subproblem overlap:

-   *DP:* Subproblems overlap and are reused.

-   *D&C:* Subproblems are independent and non-overlapping.

2.  Reuse of results:

-   *DP:* Stores and reuses results of subproblems.

-   *D&C:* Does not store results; recomputes when needed.

**[Examples:]{.underline}**

-   *DP:* Fibonacci series

-   *D&C:* Merge Sort

**QUES 3).Principle of optimality**

-   **Define it in one sentence and name any one problem satisfying it.
    \> \[3\]\[4\]**

> [Definition:]{.underline}\
> A problem satisfies the principle of optimality if an optimal solution
> can be constructed from optimal solutions of its subproblems.
>
> [Example:**\
> **]{.underline}Shortest path problem (e.g., Dijkstra's algorithm).

**QUES 4).Memoization**

-   **Define memoization and contrast with tabulation in one line each.
    \[1\]**

> [Definition:**\
> **]{.underline}Memoization is a top-down approach where results of
> recursive subproblems are stored to avoid recomputation.
>
> [Contrast with Tabulation:**\
> **]{.underline}Tabulation is a bottom-up approach where subproblems
> are solved iteratively and stored in a table.

**QUES 5).Branch and Bound idea**

-   **Define BnB and the role of bounding in pruning in two lines. \>
    \[5\]\[6\]**

> [Definition:**\
> **]{.underline}Branch and Bound (BnB) is an optimization technique
> that systematically explores solution branches and uses bounds to
> eliminate unpromising branches.
>
> [Role of Bounding in Pruning:**\
> **]{.underline}Bounding estimates the best possible solution in a
> branch; if it cannot improve the current best, the branch is pruned.

**[SECTION B -- Algorithms & Recurrences \[15 Marks\]]{.underline}**

**QUES 6).Matrix Chain Multiplication (A₁:5×4, A₂:4×6, A₃:6×2, A₄:2×7)\
a) Write m\[i,j\] recurrence and base case (no derivation).
\[4\]\[7\]\[8\]**

m\[i, j\] = min { m\[i, k\] + m\[k + 1, j\] + p\[i - 1\] × p\[k\] ×
p\[j\] }, for i ≤ k \< j\
Base Case: m\[i, i\] = 0

**b) State the minimum scalar multiplications (number only).
\[8\]\[4\]**

158

**QUES 7).Longest Common Subsequence (X=\"ABCDGH\", Y=\"AEDFHR\")\
a) Write the LCS(i,j) recurrence and base. \[1\]**

LCS(i, j) = 0 if i = 0 or j = 0\
If X\[i\] = Y\[j\] ⇒ LCS(i, j) = LCS(i -- 1, j -- 1) + 1\
Else LCS(i, j) = max { LCS(i -- 1, j), LCS(i, j -- 1) }

**b) Give the LCS length (number only). \[1\]**

> 3

**QUES 8).Optimal Binary Search Tree (keys: 10,20,30; p: 0.4,0.3,0.3;
assume q=0)\
a) Write w\[i,j\] and e\[i,j\] DP formulations with base. \[1\]**

w\[i, j\] = Σ p\[t\] for t = i to j; w\[i, i -- 1\] = 0\
e\[i, j\] = min { e\[i, r -- 1\] + e\[r + 1, j\] } + w\[i, j\]\
Base Case: e\[i, i -- 1\] = 0

**b) State the minimum expected search cost (number only). \[1\]**

> **1.7**

**QUES 9).0/1 Knapsack -- Branch & Bound (W=5; w={2,3,4,5},
p={3,4,5,6})\
a) Write the fractional upper bound formula used for pruning.
\[6\]\[9\]\[5\]**

> ub = v + Σ (profit of full items) + \[(W -- current_weight -- Σ
> weights of full items) / weight_next\] × profit_next

**b) Show level-0 and level-1 nodes (include/exclude first item) with
(v,w,ub) only. \[5\]\[6\]**

-   Level 0 (root): (0, 0, 7)

-   Level 1 (include item 1): (3, 2, 7)

-   Level 1 (exclude item 1): (0, 0, 6.5)

**QUES 10).TSP -- Dynamic Programming (Held--Karp; 4 cities, example D
given)\
a) Write the C\[S,j\] recurrence and final answer expression. \[1\]**

C\[S, j\] = min { C\[S -- {j}, i\] + d\[i, j\] } for i ∈ S, i ≠ j\
Final Answer: min { C\[{2,...,n}, j\] + d\[j, 1\] } for j = 2 to n

**b) Initialize base entries C\[{k},k\] for k=2..4 (numbers only for the
given D). \[1\]**

C\[{2}, 2\] = d\[1, 2\]\
C\[{3}, 3\] = d\[1, 3\]\
C\[{4}, 4\] = d\[1, 4\]
