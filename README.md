# ALU with Seven-Segment Display Decoder

This repository contains the project of a Logic/Arithmetic Unit (ALU) coupled with a binary decoder for a seven-segment display. The ALU is capable of performing various logical and arithmetic operations selected through a selector. The project was developed using block diagrams, exclusively utilizing basic logic gates such as AND, OR, XOR, etc.

## Project Description
The ALU performs the following operations based on the 3-bit selector:</br>
| S2 | S1 | S0 | Operation       |
|----|----|----|-----------------|
| 0  | 0  | 0  | F = A + B       |
| 0  | 0  | 1  | F = A - B       |
| 0  | 1  | 0  | F = MIN(A,B)    |
| 0  | 1  | 1  | F = MAX(A,B)    |
| 1  | 0  | 0  | F = A > B       |
| 1  | 0  | 1  | F = A <= B      |
| 1  | 1  | 0  |  F = \|A\|      |
| 1  | 1  | 1  | F = A << 2      |

#### ALU Inputs:
1. Two 5-bit vectors A and B (1 bit for sign) representing operands. Numbers can be positive or negative binary values (two's complement).
2. A 3-bit vector S representing the operation selector according to the table above.

#### ALU Outputs:
1. A 5-bit vector F representing the operation result (for operations returning a vector).
An overflow LED (Light Emitting Diode) indicating overflow (for operations that might generate overflow).
2. A status LED indicating status (for operations returning a boolean).
3. A LED indicating negative result (on when negative, off when positive).

### Seven-Segment Display Decoder
The ALU project is coupled with a decoder for the seven-segment display, allowing the display of operation results.


#### Decoder Inputs:
A 5-bit vector representing a positive or negative binary number (two's complement).

#### Decoder Outputs:
Two 7-bit vectors representing the two seven-segment displays.


### FPGA Configuration
The project is further enhanced if successfully implemented on an FPGA. ALU inputs and outputs can be mapped as follows:

- Input A and B: Mapped to the FPGA's 10 DIP switches.
- Input S: Mapped to FPGA buttons.
- Outputs F, overflow, status, and negative result: Mapped to the FPGA's seven-segment displays and LEDs.

## Contributors
This project was developed by **Saulo Roberto dos Santos** and **Guilherme** as part of the coursework for Sistemas Digitais.
