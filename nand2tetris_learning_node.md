#Nand2Tetris Learning node

## Why do I want to learn it?


---
## Chapter 1 Boolean Functions And Gate Logic

###1.1 boolean logic  
Looking at these laws, remember me of my boolean logic teacher: A tiny lady wearing a large glass...

*Commutative Laws*

* (x And y) = (y And x)
* (x Or y) = (y Or x)

*Associative Laws*

* (x And (y And z)) = ((x And y) And z)
* (x Or (y Or z)) = ((x Or y) Or z)

*Distributive Laws*

* (x And (y Or z)) = ((x And y) Or (x And z))
* (x Or (y And z)) = ((x And z) Or (x And z))

*De Morgan Laws*

* Not(x And y) = Not(x) Or Not(y)
* Not(x Or y) = Not(x) And Not(y)

###1.2 boolean functions synthesis

How to get boolean expression from truth table. Write the boolean expression for the row that equals 1. Then Or these expressions. 
**Any boolean expression can be represented using an expression containing AND OR NOT operations. **


**Any boolean function can be represented using an expression containing AND , NOT operations. **

Proof:


x OR y = NOT(NOT(x) AND (NOT(y))) 


####what is nand. 

Nand(x,x) = NOT(x)

Nand(x,y) = NOT(x AND y)

**Any boolean function can be represented using an expression containing NAND operations. **

Proof:

Not(x) = (x NAND x)

(x AND y) = NOT(x NAND y)

It is important because it is the theorem basis for computer. 


###1.3 Logic Gate

NADN gate, AND gate, OR gate, NOT gate.

Gate interface: it is a unique way to describe what the gate to.

Gate implements: the ways to make the interface to be true. There are many ways to do it.

### 1.4 HDL

Use NOT gate, AND gate and OR gate to generate any chip.

Implementation:
PARTS:

Not (in=a, out=nota)

Not (in=b, out=notb)

And (a=a, b=notb, out=aAndNotb)

...

*Just use the privious out as in of the gate.*

**HDL is a functional/declarative language.**

Before using a chip, you must know its interface.
like:

Not(in=, out=)
And(a=, b=, out=)

Common HDLs:

* VHDL
* Verilog

###1.5 Hardware Simulation

**How to use the hardware simulation**

* Interactive
* Script-based
* With/without output and compare files

**Test Script**

	load Xor.hdl,
	output-file Xor.out,
	output-list a b out;

	set a 0, set b 0, eval, output;
	
**difference between ',' and ';'.**
When we debug the code, the simulator will stop at ';', not at ','.

### 1.6 Multi-bit Buses

Bus is a array of bits.

For example: a 16-bit adder, its inputs are two 16-bits buses.

	CHIP Add16 {
		IN first[16], second[16];
		OUT out[16];
		
		PARTS:
		
	}

Sub-buses
	
	IN lsb[8], msb[8],..
	
	Add16(a[0..7]=lsb, a[8..15]=msb, b=.., out=...);
	

This is the interface declaration for a chip: IN c, Bus1[16], Bus2[16]; OUT out, out2[16]

* Add16(a=Bus1[0..15], b=Bus2[0..15], out[0..14]=out2[0..14]);
* Add16(a=true, b=false, out=out2);
* Add(a=c, b=Bus2[7], out=out);

The above are correct.

* Add16(a=Bus1[0..15], b=Bus2[0..15], out=out2[0..14]);
* Add16(a=c, b=Bus2[0..15], out=out2);

The above are wrong.

###About Mux

In hdl, we can not use if statement as easy as other software programming lauguage. Luckly, we have Mux, Mux4Way, Mux8Way. After we figure out how to implement Mux4Way and Mux8Way with Mux, we know how to translate 'if' to Mux. 

### writting hdl
**Tips**:
*when you refer to a Not gate in your code, the system looks for it, and the order it performs a search is such that the system prefers files in the same directory over the built-in definitions*


###2.1 Binary Numbers

* how to convert decial number to binary number
* how to convert binary number to decial number

### 2.





