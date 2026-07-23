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

# Lesson 3 Digital Inputs/Outputs

## Key Ideas
- Digital devices only have two positions: completely ON or completely OFF.
- The number 1 means electricity is flowing, and 0 means it is stopped.24 
- Volts DC is the most common electricity type used because it is safe.
- Sinking and sourcing describe the direction that the electricity flows through wires.

## Step 1
- The input scans all physical inputs. 
- Once a button is pressed, two metal pieces close, once they close eletricity can now flow through sending a  eletrical signal to the PLC. 
- PLC registers this as either a 1 or a 0. 

## Step 2
- PLC reads the frozen table. 
- It determines what actions to take and excutes the program. 
- Eletricity is sent through either a internal relay (mechanical) or a transistor (eletrical) to route power. 
- The final decisions are written down in a output table as a 1 or 0.

## Step 3 
- Output scan sends out the eletrical signal to mechanical equipment. 
- Power flows from PLC to connected machine parts. 
- If solenoid valve needs to close, PLC will remove eletricity from the area, forcing the valve to close. 

Example: 
- Push buttons (Input)
- Limit switches (Input)
- Proximity switches (Input)
- Pilot lights (Output)
- Solenoid valves (Output)
- Motor starters (Output)

## My own explanation
- Digital inputs and outputs are like the fingers of a machine. First, a digital input is pressed, and a eletrical signal is sent to the PLC, registering it as either a 1 or a 0. PLC reads through the frozen data and determines a action, sending or diverting away eletricity to a output, and a mechanical action occurs. 

# Lesson 4 Analog Inputs/Outputs

## Key Ideas
- Analog devices do not rely on 1s and 0s, instead they rely on a smooth range of changing values.
- Instead of 1s and 0s, analog uses multi-digit numbers to determine how high or low a signal is. 
- A eletrical current is used to send a analog signal, and measured in miliamps (mA). 
- Voltage signals ranging from 0 to 10, however they suffer from eletrical noise and limited range. 

## Step 1
- An analog sensor measures a real-world condition like temperature or pressure.
- The sensor turns that physical measurement into a continuous stream of electrical current between 4 mA and 20 mA .
- Electrical signal is sent straight into the PLC's analog input module.
- The PLC takes this incoming electrical data and matches it to a scale inside its memory.

## Step 2
- The PLC program reads the exact number from the scaled data table rather than just seeing a standard true or false bit.
- It evaluates the number against the written instructions from the operator to figure out the exact percentage or level needed.
- The CPU calculates a complex math formula to decide how wide to open a valve or how fast to spin a motor.
- It writes a specific target value onto the output card, preparing to change the physical machine's power.

## Step 3 
- The analog output card translates the internal code back into a matching electrical signal.
- The PLC pushes a variable current out through the terminal wires to the field device.
- This power tells the output equipment exactly how much it needs to adjust.
- The machine part holds a steady position halfway or partway open based on that continuous voltage or current.

Example: 
- Temperature sensors (Input) 
- Flow transducers (Input) Weight load cells (Input) 
- RTDs and Thermocouples (Input) Control valves set to 30% or 70% (Output) 
- Variable Frequency Drives for motor speed (Output) 

## My own explanation
- Analog inputs/outputs operate as a dimmer rather than a set switch. Firstly, the analog sensor sends a small eletrical current to the PLC, that way it can show exact measurements it needs. Then, the PLC reads the exact live measurement for the machine, compares it with written instructions, and completes a math operation. After finding the final value, the PLC sends out a matching small eletrical current to control things precisely. 

