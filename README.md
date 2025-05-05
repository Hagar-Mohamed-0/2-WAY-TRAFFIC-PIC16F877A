🚦 2-Way Traffic Light Controller using PIC16F877A
This project implements a 2-way traffic light controller using the PIC16F877A microcontroller. The system simulates real-world traffic signal operation at a crossroad, using LEDs to represent traffic lights and a 7-segment display for countdown timers. It also supports manual control via start/stop buttons and an alternate display mode for maintenance or testing.

📌 Features
Simulates 2-way traffic control: Direction A and Direction B

Uses LEDs to represent RED, YELLOW, and GREEN traffic signals

Displays countdown timer on a 7-segment display

Manual start/stop control using input buttons

Alternate mode toggle for LED flashing pattern

🧰 Hardware Requirements
PIC16F877A microcontroller

20 MHz Crystal Oscillator

6 x LEDs (Red, Yellow, Green for each direction)

7-Segment display (Common cathode)

Resistors (220Ω – 330Ω)

Tactile Push Buttons (Start, Stop, Mode)

Breadboard or PCB

5V regulated power supply

💻 Software Requirements
MPLAB X IDE

XC8 Compiler

(Optional) Proteus for simulation

⚙️ Microcontroller Pin Configuration
Port	Pin	Usage
RC0	IN	Start Button
RC1	IN	Stop Button
RC2	IN	Mode Toggle Button (while stopped)
RD0	OUT	Red Light
RD1	OUT	Secondary Red/Yellow Control
RD2	OUT	Yellow Light
RD3	OUT	Green Light (Direction A)
RD4	OUT	Yellow Light (Direction A)
RD5	OUT	Green Light (Direction B)
RD7	OUT	Power Indicator / LED Master Enable
RB0–RB7	OUT	7-Segment Display Output

🧠 Working Principle
The program continuously monitors the START (RC0) and STOP (RC1) buttons. If START is pressed and STOP is not, it initiates the traffic light cycle:

Direction A:

Green ON (RD3), Yellow (RD2), Red for B (RD0)

Countdown displayed using num15 on 7-segment

Direction A:

Yellow ON (RD4)

Countdown using num3

Direction B:

Green ON (RD5), Red for A (RD0)

Countdown using num20

The STOP button (RC1) interrupts the cycle, entering idle mode. In this state, pressing the mode button (RC2) toggles between two LED display patterns for testing or maintenance.

