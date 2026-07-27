# PLC Project 1 – Delayed Start Light with Safety Interlock

## Overview

This project is the first step in my PLC programming journey using CODESYS.

The goal is to understand the fundamentals of PLC programming by creating a simple program where pressing a push button energizes an output to turn on a light.

---

## Skills Practiced

- PLC Fundamentals
- Ladder Logic
- Normally Open Contact
- Output Coil
- PLC Scan Cycle

---

## Learning Objectives

- Understand how PLC inputs and outputs work
- Learn how Ladder Logic executes
- Create my first functioning PLC program
- Document my progress professionally

---

## Future Improvements

- Add a Stop button (complete)
- Add a latch circuit (complete)
- Add timers (complete)
- Convert the project to a Factory I/O simulation (complete)

---

## PLC Project 1 – Delayed Start Light with Safety Interlock

Objective

Design a ladder logic program in CODESYS that controls a light using a Start push button, Stop push button, Safety Switch, and a 5-second ON-delay timer. The program should use an internal latch so the Start button only needs to be pressed once.

Components Used

Inputs

- Start Push Button (NO)
- Stop Push Button (NC)
- Safety Switch (NO)

Internal Memory

- Run_Latch

- Function Block

- TON (On Delay Timer)

Output

- Light

## Program Logic

1. Pressing the Start button sets the Run_Latch memory bit.
2. Run_Latch remains TRUE after the Start button is released.
3. If the Stop button is pressed, Run_Latch resets.
4. When Run_Latch and Safety Switch are TRUE, the TON timer begins counting.
5. After 5 seconds, the timer's Q output becomes TRUE.
6. The Light output turns ON.

## What I learned

- Difference between Normally Open and Normally Closed contacts.
- Series contacts create AND logic.
- Parallel branches create OR logic.
- TON timers delay an output instead of immediately energizing it.
- nternal memory bits are used instead of output coils for latching.
- Ladder logic executes from left to right and the PLC scans continuously.

## Problems Encountered


- Problem 1

I initially didn't understand how to create a second contact in series.

Solution

Learned how ladder logic is constructed and how contacts are placed one after another.

- Problem 2

I didn't understand how TON worked.

I originally thought the timer directly delayed electricity.

Solution

Learned that TON waits until its preset time has elapsed before its Q output becomes TRUE.

- Problem 3

I didn't understand why the Stop button should use a Normally Closed contact.

Solution

Learned that industrial stop buttons are normally closed because the circuit remains complete until the button is pressed.

## Reflection

This project introduced me to the fundamentals of PLC programming using ladder logic. At first, I focused mainly on making the circuit work, but I later realized that a working program is not always the best design. My original solution latched the Light output directly, which required holding the Start button until the timer finished. After redesigning the program with an internal Run_Latch memory bit, I better understood how industrial PLC programs separate machine state, timing, and outputs into multiple rungs. This project also improved my understanding of timers, parallel branches, normally closed contacts, and troubleshooting ladder logic. Going forward, I want to build programs that are not only functional but also easier to maintain and troubleshoot.

![alt text](image.png)