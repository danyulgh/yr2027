> dynamic programming

# memo knapsack implementation
![[Screenshot 2026-09-23 at 2.34.57 AM.png]]
![[Screenshot 2026-09-23 at 2.43.27 AM.png]]

* definitely faster that decision tree
* runtime points can be scattered / have peaks because our generated tests can cause us to be unlucky and not reap benefits of dp 
* so we should always run multiple trials and look at average result

	# tabular knapsack implementation
![[Screenshot 2026-09-23 at 3.08.14 AM.png]]![[Screenshot 2026-09-23 at 3.08.23 AM.png]]
* tabular smoother since it will always fill out the table, not based on luck
	* tabular faster since it uses iteration rather than recursion
# but i thought knapsack was exponential
* it is, but in the actual size of the input
	* i.e. the number of bits need to represent the input
	* this is pseudo-polynomial time

# tabular with floats
* size of table depends on # of possible combinations of weights below capacity, so we scale and round (introduce conservative approx error)
![[Screenshot 2026-09-23 at 3.18.23 AM.png]]