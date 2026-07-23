# Lesson 1 - What is a PLC?

## Key Ideas

- PLC = Programmable Logic Controller.
- Used to automate industrial machines and processes.
- Reads inputs, executes a program, updates outputs repeatedly.

## Inputs
These are things like buttons, lasers, or temperature sensors. They tell the PLC what is happening (e.g., "A box just arrived on the conveyor belt").

Examples:
- Push button
- Limit switch
- Proximity sensor
- Pressure switch


## Outputs
After input sends information to the PLC, the CPU determines a action and the PLC sends electricity to motors, robot arms, or lights to make them move or turn on.
Examples:
- Pilot light
- Motor starter
- Solenoid valve
- Alarm

## Why industries use PLCs

- Reliable
- Easy to troubleshoot
- Can be reprogrammed
- Built for harsh environments

## My own explanation

A PLC is basically an industrial computer that continuously checks sensors and decides whether to turn devices on or off.


# Lesson 2 - PLC Scan Cycle

## Key Ideas
- The scan cycle for a PLC is a continous loop that machines use to keep themselves running. 
- It can repeat this process listed below many times per second. 
- It ensures that the machine runs in a safe, predictable manner. 

## Step 1
- The input will freeze time within a milisecond. During that time, the input checks the state of all input devices. 
- Once that is complete, the PLC writes a temporary table containing a 1 (ON) or a 0 (OFF) is listed for each input device. 
- It can prevent errors if a sensor suddenly flips ON or OFF while code is still processing within the PLC.

## Step 2
- Based on the frozen snapshot from the data in Step 1, the PLC reads one instruction at a time from start to finish to determine which action it should take. 
- It can read horizontalilly (top to bottom, left to right) or vertically (Up and down, moving left to right). 

## Step 3 
- Once the program finishes reading the logic, the PLC begans to update the output devices. It can either cut or send eletricity based on the 1s and 0s. 

Example: 
- A limit switch is physically activated. 
- The PLC records this as a 1 or a ON in the record table. 
- The program is excuted and instructions are sent to the output device to turn on a light. 
- A light turns on after eletricity was sent from the PLC. 



## Self Test
- Before the cycle begans again, the PLC runs a quick internal check and notes any hardware or software faults. If there are, it will not began the cycle. If there are none, it will began the cycle. 

## My own explanation
- The cycle is used to send information to and fro from the input, PLC, and finally to a output. The PLC gathers information from the input, stores it inside a table, and the PLC reads the table. After reading the table, the PLC can now send information to the output, and the output excutes. 
