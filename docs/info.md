<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->
# How it works
how_it_works: |
  This 2-bit full adder circuit implements binary addition using cascaded logic gates. It takes five inputs:
  - A1, A0: First 2-bit binary number
  - B1, B0: Second 2-bit binary number  
  - Cin: Carry-in from previous addition stage
  
  The circuit produces three outputs:
  - Sum1, Sum0: Result of A + B + Cin (2-bit sum)
  - Cout: Carry-out to next stage (0 or 1)
  
  The logic implementation uses two cascaded 1-bit full adders:
  - Stage 1 (LSB): Adds A0, B0, Cin to produce Sum0 and Carry1
  - Stage 2 (MSB): Adds A1, B1, Carry1 to produce Sum1 and Cout
  
  Boolean equations:
  Sum0 = A0 ⊕ B0 ⊕ Cin
  Carry1 = (A0·B0) + (Cin·(A0⊕B0))
  Sum1 = A1 ⊕ B1 ⊕ Carry1
  Cout = (A1·B1) + (Carry1·(A1⊕B1))
  
  This 2-bit building block can be cascaded to create larger multi-bit adders for arithmetic operations in processors, calculators, and digital systems.

# How to test
how_to_test: |
  To test the 2-bit full adder circuit:
  
  1. Apply input combinations to A0, A1, B0, B1, and Cin using push buttons or switches
  2. Observe the Sum0, Sum1, and Cout outputs on LEDs or a logic analyzer
  3. Verify truth table (partial example):
  
  | A1 | A0 | B1 | B0 | Cin | Sum1 | Sum0 | Cout |
  |----|----|----|----|-----|------|------|------|
  | 0  | 0  | 0  | 0  | 0   | 0    | 0    | 0    |
  | 0  | 0  | 0  | 0  | 1   | 0    | 1    | 0    |
  | 0  | 0  | 0  | 1  | 0   | 0    | 1    | 0    |
  | 0  | 0  | 0  | 1  | 1   | 1    | 0    | 0    |
  | 0  | 1  | 0  | 1  | 0   | 1    | 0    | 0    |
  | 1  | 0  | 0  | 1  | 0   | 1    | 1    | 0    |
  | 1  | 0  | 1  | 0  | 0   | 0    | 0    | 1    |
  | 1  | 1  | 1  | 1  | 1   | 1    | 1    | 1    |
  
  4. Test cascaded operation by connecting Cout to Cin of another 2-bit full adder to form a 4-bit adder
  5. Use a clock signal to test dynamic behavior if applicable

# External hardware
external_hardware:
  - "5x Push buttons or DIP switches for inputs (A0, A1, B0, B1, Cin)"
  - "3x LEDs with current-limiting resistors (220-330Ω) for outputs (Sum0, Sum1, Cout)"
  - "Breadboard and jumper wires for prototyping"
  - "5V power supply or USB power source"
  - "Optional: Additional full adder ICs for multi-bit testing (74HC283 for 4-bit adder)"

# Language and framework
language:
  - "Verilog"
  - "Wokwi schematic"

# Tags for discovery
tags:
  - "2-bit adder"
  - "full adder"
  - "arithmetic"
  - "logic gates"
  - "binary addition"
  - "digital circuit"
  - "carry chain"
  - "ALU building block"
  - "Tiny Tapeout"
  - "combinational logic"
  - "XOR"
  - "AND"
  - "OR"

# Clock information
clock:
  frequency: "none (combinational logic)"

# Pin mapping (customize based on your actual pin assignments)
pin_mapping:
  - "Input A0: Pin 1"
  - "Input A1: Pin 2"
  - "Input B0: Pin 3"
  - "Input B1: Pin 4"
  - "Input Cin: Pin 5"
  - "Output Sum0: Pin 6"
  - "Output Sum1: Pin 7"
  - "Output Cout: Pin 8"

# Power requirements
power:
  voltage: "3.3V - 5V"
  current: "< 15mA"

# Applications
applications:
  - "Multi-bit adder circuits (cascade multiple 2-bit adders)"
  - "Arithmetic Logic Units (ALUs)"
  - "Digital counters"
  - "Microprocessor design"
  - "Educational tool for binary arithmetic"
