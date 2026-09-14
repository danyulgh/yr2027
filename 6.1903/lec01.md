> what is information?

* information is anything that provides an answer to a question of some kind
* fundamental unit is the bit: one yes/no amount of info
* $n = log_2(m)$
	* n = number of bits
	* m = number of values
* 8 bits = byte
# representing information
* two primary entities in electronics:
	* voltage
	* current
* voltage
	* can be either static (fixed in time)
	* or dynamic (changing in time)
	* conveys meaning based on value
	* **ANALOG** systems interpret many values via voltage
	* **DIGITAL** systems where voltage is limited (almost always to two categories of values)
* analog
	* ex: voltage varying from 0 to 10V in 0.01V steps
		* theoretically, single voltage represents up to 1000 options
		* log2(1000) ~= 9.96 bits of info
* digital
	* ex: voltage is limited to "high" (5v to 10v) or "low" (0v to 10v)
		* theoretically, voltage represents 2 options
		* log2(2) = 1 bit of info
* on paper analog is better... but we use digital!
	* because there is noise!
		* if you get a reading of 2.01V, you don't know if its really 1.98V + 0.03V of noise
	* digital uses ranges so noise is not really a problem
		* more robust

# digital in electronics
* we set up a "contract"
	* this contract has all parts agree that
		* above a certain V amount is 1
		* below a certain V amount is 0
* potentially has a forbidden zone between high and low

# numbers
* just base 2
	* $smallest = 0$
	* $greatest = 2^N-1$
* dividing/multiplying by 2 are trivial
* overflow: operations produce results outside range output can represent
	* adding 1110 and 0111 and getting 10101 when limiting answer to 4 bits
* underflow: same thing but under range
* limiting output to N bits is the same as modular arithmetic 
	* specifically, $\%2^N$
* method of encoding to base 2:
	* find biggest power of 2 you can fit in number
	* subtract that power of 2 and repeat until leftover is 0
* decoding: 0b means binary
	* 0b10101 = 21 base10

# c: the language
* low-level compared to python
* very unsafe language compared to python
* python is written in C

| Python                      | C                        |
| --------------------------- | ------------------------ |
| interpreted - slower        | compiled - faster        |
| don't need to declare types | must declare types       |
| no pointers                 | pointers                 |
| automatic memory management | manual memory management |
# memory
* large chunk of electrical storage
* everything is stored digitally (in binary)
* each part of memory has an address affiliated with it
	* addresses go from low to high

# hexadecimal
* long strings of bits are tedious
* base16
* each 4 adjacent bits is a single hexadecimal digit
* 0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F

# organization
* we operate in a 32 bit system
* 1 byte = 8 bits = 2 hexadecimals 
* so memory is organized into 4 byte words

![[Screenshot 2026-09-14 at 10.27.27 AM.png]]

# c printf
* \#include <stdio.h> - gives access to printf()
* uses % for formatted printing

# c types
* int: 4 bytes
* float: 4 bytes
* char: 1 byte

# c goto
* goto keyword jumps to labeled locations
	* goto spot_1;
	* spot_1:

# c bitwise
* x << y; shift x left by y bits
	* multiply by $2^y$
* x >> y; shift x right by y bits
	* divide by $2^y$ 
* x & y; bitwise and x with y
* x | y; bitwise or x with y
* ~x; bitwise x
* x ^ y; bitwise xor x with y

# pointers
* a data type in C that "points" to other data
	* this is done via storing a memory address (called a "reference")
	* we can access what it points to it as need ("dereference")
* allow direct access and manipulation of memory
* variables that allow the computer to represent locations
* how to make one
	* declare what type of thing you're pointing to
	* add a * before the name for your pointer
	* then assign address of thing you want to pointer via &

![[Screenshot 2026-09-14 at 10.50.39 AM.png]]
# * operator
* "value-of at the given address operator"
* \*(&x) returns value of x
# & operator
* "address-of operator"
* to get access to a variable's spot in memory, you use the & operator
* will return where in memory a variable resides

![[Screenshot 2026-09-14 at 10.44.08 AM.png]]

# c arrays 
* size must be known at creation
* type of all elements must be the same
* array's variable is approximately(more like an unchangeable pointer)) the same as a pointer to the start of the array in memory