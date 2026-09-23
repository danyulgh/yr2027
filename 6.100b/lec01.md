> optimization models

# optimization models
* mathematical models that maximize or minimize some criterion, subject to constraints on solution
	* e.g. minimize money spent traveling from cambridge to nyc
	* e.g. constraint expected transit time < 5 hours

# exhaustive enumeration
* using the fact that there is a finite number of possible answers
	* discrete
* compute the all possible values
* choose the value that is maximized/minimized

# unimodal
* one optimal solution
* values strictly dec before the point
* values strictly inc after the point
	* (or vice versa)

![[Screenshot 2026-09-23 at 1.02.10 AM.png]]

# ternary search
* method of minimizing f(x) where x is in range of (l, r)
* ~binary search except...
	* split interval into thirds
	* discard third that cannot contain answer
* evaluate point at 1/3 and 2/3
	* if 1/3 more optimized, throw away right of 2/3 point
	* if 2/3 more optimized, throw away left of 1/3
* if 1/3 and 2/3 are sufficiently close, take average and call it a day

# calculus
* helps with continuous problems

# knapsack problems
* I have limited strength, so there is a maximum weight knapsack that I can carry
* You want to take more stuff than you can carry
* You have to choose what to take vs. leave behind
	* Optimizing the value of things to take
* 2 Variants
	* Continuous or fractional knapsack problem
		* Imagine gold dust
	* 0/1 knapsack problem
		* Imagine gold bars
		* More interesting
* formalized
	* item represented by a pair <value, weight>
	* knapsack can accommodate total weight \<w>
	* vector A of len n represents set of available items
	* vector T of len n indicated whether item is taken
		* T\[i] = 1, then A\[i] is taken

# brute force solution (knapsack)
* generate all possible combinations of items
	* get power set
* remove combinations w total units exceeding allowed weight
* choose any combination with largest value
* works because its a discrete problem