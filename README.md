# Booth algorithm
 Multiplication of two binary numbers can be implemented by

 
## Module Declaration:
The module named booth takes three inputs: M (the multiplicand), Q (the multiplier), and ans (the output which represents the product).
It also declares some internal registers and parameters used in the algorithm.

## Internal Registers:
shift: A 17-bit register used to hold the current state of the multiplication process, including the accumulator and the multiplier.
count: A 4-bit register used to count the number of iterations.
temp: An 8-bit register used to store temporary values during addition and subtraction operations.
M_reg: An 8-bit register to hold the value of the multiplicand.

## State Machine:
The state and next_state registers are used to define the current state and the next state of the finite state machine (FSM) that controls the algorithm's behavior.
The start, sub, add, ASSIGN, shift, and result parameters define the different states of the FSM.

## Clock Generator:
Generates a clock signal with a period of 10 time units.

## Initialization:
Sets initial values for M_reg, shift, state, and count.

## Sequential Blocks:
always @(posedge clk): Updates the state register on every positive edge of the clock.
always @(posedge clk): Increments the count register when in the start state.

## Combinational Block:
Determines the next state based on the current state and conditions (comparison of the multiplier's two least significant bits).
Performs addition, subtraction, and shifting operations based on the current state.

## Output Assignment:
Assigns the output ans to the 16 most significant bits of the shift register.
