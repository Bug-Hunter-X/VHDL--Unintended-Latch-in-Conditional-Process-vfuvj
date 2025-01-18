# VHDL Unintended Latch Bug
This repository demonstrates a common VHDL coding error: an unintended latch created when a signal is assigned only within a conditional statement within a process. This can lead to unexpected behavior and simulation errors.

## The Bug
The `bug.vhdl` file contains a VHDL process where the `temp` signal is assigned only when a `rising_edge(clk)` is detected.  This is incorrect when using processes because this leads to an implicit latch for the `temp` signal. If there is not a matching assignment otherwise the signal will retain its previous value. This can lead to unexpected behavior and difficulty in debugging.

## The Solution
The `bugSolution.vhdl` file shows how to correct the issue by using an else statement to assign a default value when there is no rising edge of the clock, avoiding the unintended latch.

## How to Reproduce
1.  Simulate `bug.vhdl`. Note the unexpected behavior.
2.  Simulate `bugSolution.vhdl`. Observe the corrected behavior.
