registers
* physically big
* placed next/in cpu for quick access
* cpu has limited cpu
* so only 32 registers in risc-v

memory
* very many of them 
	* 100's of thousands in esp32
	* billions in computer
* packed so tight so bytes cannot be accessed easily
* sram
	* for cache
	* 10-20x physically smaller than register
* dram
	* general memory
	* 100+x physically smaller than register

![[Pasted image 20261109232724.png]]

dram
* this is what ppl refer to when they say they have '16gb of ram'
* crazy high bit density in chips
* bits so tiny that bits leak from material imperfections
* and bits cannot hold binary value for more than 100ms at room temp
* and so tiny and use so few electrons to store bit that reading the bit destroys the bit in the process
	* so every bit is read and rewritten every 64ms on avg at room temp
	* "refresh" ^ 
	* idea of re-remembering fast enough it overcomes forgetting/losing bit
* so dram is always doing something
	* has to re-remember first before giving requested info
	* this is why memory accesses can be variable

![[Pasted image 20261109234037.png]]