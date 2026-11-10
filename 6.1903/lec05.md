> risc-v calling convention

a0-a7 (x10-x17) function arguments
a0, a1 function return values

risc-v stack (lifo)
* grows down: higher address to lower address
* sp: register pointing to top of stack
	* top would be lowest address with value
![[Pasted image 20261101201920.png]]
* procedures should leave stack as they found it 

![[Pasted image 20261101202134.png]]

caller saved (aN, tN, ra)
* callee can use freely
	* since the caller will save any register values it will need
* caller doesnt know what registers the callee will use
	* so they assume all of them will be used
* knowing caller needs a caller saved register
	* before calling the procedure: save the register's value on the stack
	* after returning from the procedure: restore the old value from the stack before next using the register

callee saved (sN, sp)
* preserved across a procedure call
	* so the caller can assume that the register's value will be the same before and after the procedure call
* callee using a callee-saved register:
	* before use: save to stack
	* after use: restore from stack before return to caller
	* sp should be reset to og value