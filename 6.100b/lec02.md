> solving knapsack problems
# exponential
* 0/1 knapsack problem is inherently exponential
* $2^n$ combinations for n items

# decision trees

![[Screenshot 2026-09-23 at 2.05.25 AM.png]]

### binary tree
* solving knapsack
* generate all leaves of the tree
* remove any leaves that dont meet constraint
* find the best remaining leaf
* left-first, depth-first enumeration
* brute force was $O(n2^n)$; decision tree is $O(2^n)$
	* we can reduce this further by identifying bad choices early in the process
	* will allow us to avoid creating parts of tree without valid sol

![[Screenshot 2026-09-23 at 2.16.48 AM.png]]


# greedy strategy
* repeatedly choosing the "best" remaining item
* "best" ?
	* can mean anything, most valuable, lowest cost, highest value per unit, etc.
* good news, fast
* bad news, wrong answer
	* might be impossible to get correct answer w greedy
	* answer likely still reasonable, just not optimal

![[Screenshot 2026-09-23 at 2.19.35 AM.png]]

# dynamic programming
### fib num ex
* we often waste time solving things we already know

![[Screenshot 2026-09-23 at 2.22.41 AM.png]]![[Screenshot 2026-09-23 at 2.22.54 AM.png]]
### memoization
* the idea of creating a table to record what we've done
	* before actually computing fib(n), check if its already in table
	* add to table if not

![[Screenshot 2026-09-23 at 2.25.12 AM.png]]

* memoization is top-down
	* start from problem to be solved, the biggest problem
	* ***add entries*** to memo ***as you solve*** new sub-problems

### tabular
* bottom-up
* ***pre-allocate memo table*** for all possible sub-problems
* populate the table systematically, from smallest problem

![[Screenshot 2026-09-23 at 2.27.08 AM.png]]

# tabularization vs. memoization
* if original problem requires all subproblems to be solved, tabular better
* tabular easier to implement
* tabular usually faster
	* no overhead for recursion
	* pre-allocated fixed size list
* if only some subproblems need to be solved to solve the original problem, memoization better
	* more efficient because subproblems are solved lazily, or only perform the computations that are needed

# dynamic programming cont.
* will help problems w following characteristics:
1. optimal substructure:
	* a globally optimal sol can be found by combining optimal sols to local subproblems
	* i.e. for x>1, fib(x) = fib(x-1) + fib(x-2)
2. overlapping subproblems:
	* finding an optimal solution involves solving the same subproblem multiple times
	* i.e. compute fib(x) many times