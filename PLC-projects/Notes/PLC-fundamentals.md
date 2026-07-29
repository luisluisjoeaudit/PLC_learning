Notes will be in the following format: 

What is it?
Why is it used in industry?
Where would I see it?
How does it connect to a PLC?

# Unit 1 
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

# Unit 2 
# Lesson 1 Timers

## Key Ideas
- Timers allow a PLC program to delay actions, control step durations, or track total operating runtimes. 
- Industrial systems rely on timers to synchronize multiple moving parts and prevent alarm chatter 
- Every timer uses an internal memory block containing a specific preset target time and an accumulated value. 
- Most modern control software utilizes standardized IEC timer function blocks for program development. 

## Step 1
- The upstream logic conditions on the ladder rung switch from a false state to a true state.
- Power reaches the timer input, activating the block's internal enable (EN) bit flag.
- The timer block begins tracking live elapsed time using its configured baseline time unit.
- The active timing (TT) bit stays true while the clock numbers climb toward the setpoint.

## Step 2
- The accumulated counting value successfully climbs up until it matches the preset target value.
- The clock stops counting, dropping the timing bit and triggering the block's done (DN) bit.
- The true done bit passes electrical power forward down the rung to activate downstream code.
- Turning off the upstream input instantly drops the tracking values back down to zero.

## Variants
- Special off-delay (TOF) configurations turn the done bit on immediately before starting the clock
- Retentive timers (RTO) save their current counted value even if the incoming power drops out. 
- Programmers must fire a dedicated reset instruction to clear a retentive timer back to zero.
- Advanced tasks cascade multiple timer units together to alternate fluid pumps or mixing valves sequentiall.

## My own explanation
- Timers are used to caculate tasks before excuting the task. In short, when a condition is true, power is directed to the Timer. The timer begans counting down until it hits a preset value, and from there it turns a switch and changes a value to either a "1" or a "0". The PLC detects this and determines a way to excute a task. 

# Lesson 2 Counters

## Key Ideas
-  Counters do not track clock time, instead they count physical pulses or event triggers. 
- Industrial systems rely on counters to track production volume, pack boxes, or limit machine.  cycles.
- Every counter uses an internal memory block containing a specific preset target value and an accumulated count.
- Most modern control software utilizes standardized IEC counter function blocks (CTU, CTD, or CTUD).

## Step 1
- A proximity sensor or limit switch detects a physical part moving down the production line.
- The sensor transitions from a false state to a true state, creating a rising edge pulse.
- This sharp incoming pulse reaches the counter input, activating the block's counting logic.
- The counter block increments or decrements its live internal value by exactly one count.

## Step 2
- The accumulated counting value successfully moves up or down until it matches the preset target value.
- The block stops tracking the target and instantly updates its internal done (DN or Q) bit flag.
- This value change turns a virtual switch inside the PLC memory from a "0" to a "1".
- The true bit passes electrical power forward down the ladder rung to trigger the next execution task.

## Variants
- Special count-down (CTD) configurations subtract numbers from the current total every time a sensor trips.
- Bi-directional counters (CTUD) use two separate inputs to count up for entries and count down for exits.
- Unlike basic timers, standard counters hold their accumulated numbers tightly even if the rung loses power.
- Programmers must fire a dedicated reset (RST) instruction to clear the accumulated value back to zero.

## Reset (RES)Memory Retention: 

Counters hold onto their accumulated numbers tightly even if the incoming rung power drops out.

Instruction Trigger: 
- Programmers must use a separate, dedicated Reset (RES) instruction block to clear the internal memory.

 State Change:
 - Activating the reset block instantly forces the accumulated value back to zero and drops the done bit from a "1" back to a "0"

## Shared Memory Tag:
 A Count-Up (CTU) and a Count-Down (CTD) block can be paired together by assigning them the exact same name or tag in the software code.
 
 Shared Values:
 -  Paired blocks share the exact same preset value, accumulated value, and done bit output behind the scenes.
 
 Bidirectional Tracking: 
 - Tripping the CTU input adds 1 to the shared total, while tripping the CTD input subtracts 1 from that same total, allowing the PLC to track entries and exits seamlessly.


## My own explanation
- Counters "count" how many items there are using sensors, unlike a Timer which times everything automatically. The Counter first detects the object, it changes the accumulated value by 1. When it reaches a preset value, the Counter sends out a value of either "1" or a "0" to the PLC. From there, the PLC decides what the following action should be pursued. 

# Unit 3 
# Analog Inputs and Signals

## What is an Analog Signal?

- An analog signal is a continuous signal that can have many different values.
- Unlike digital signals (ON/OFF), analog signals represent changing measurements.
- PLCs use analog signals to measure real-world conditions.

Examples:
- Temperature
- Pressure
- Flow
- Level
- Speed

---

## Digital vs Analog Signals

### Digital Signal
- Only has two states:
  - ON (1)
  - OFF (0)

Examples:
- Push buttons
- Limit switches
- Proximity sensors

### Analog Signal
- Has a range of values.
- Represents a measurement.

Examples:
- Temperature = 0°C to 100°C
- Pressure = 0 psi to 100 psi
- Level = 0% to 100%

---

## Common Industrial Analog Signals

### 4-20 mA

- The most common industrial analog signal.
- Used because it is reliable over long distances.
- The PLC reads the current value and converts it into a measurement.

Example:

4 mA = 0%
12 mA = 50%
20 mA = 100%

---

## How Analog Inputs Work

Process:

Sensor → Analog Signal → PLC Analog Input → PLC Program → Output

Example:

Temperature transmitter:
1. Measures temperature.
2. Sends a 4-20 mA signal.
3. PLC reads the signal.
4. PLC controls a heater or fan.

---

## Analog Input vs Digital Input

Digital Input:
- Receives ON/OFF information.
- Example: Is the button pressed?

Analog Input:
- Receives measurement values.
- Example: What is the tank level?

# Proximity Sensors

## What is a Proximity Sensor?

- A proximity sensor is an industrial sensor that detects the presence of an object without physical contact.
- It sends a signal to a PLC when an object is detected.
- It is commonly used in automation systems for object detection, positioning, counting, and safety.

Basic operation:

Object detected
        ↓
Sensor output changes state
        ↓
PLC input receives signal
        ↓
PLC logic controls output

Example:
A conveyor detects a metal part:
- Sensor detects the part.
- PLC receives an ON signal.
- PLC stops the conveyor or activates another process.

---

# Types of Proximity Sensors

## 1. Inductive Proximity Sensor

### What does it detect?
- Detects metal objects only.
- Commonly detects:
  - Steel
  - Aluminum
  - Copper

### How does it work?
- Creates an electromagnetic field.
- When a metal object enters the sensing range, it changes the field.
- The sensor detects this change and switches its output.

### Advantages:
- No physical contact required.
- Very durable.
- Works well in dirty industrial environments.
- Long operating life.

### Limitations:
- Only detects metal objects.
- Shorter sensing distance compared to some other sensors.

### Industrial examples:
- Detecting metal parts on conveyors.
- Checking if a machine component is in position.
- Counting metal products.

---

# 2. Capacitive Proximity Sensor

### What does it detect?
- Detects many different materials:
  - Plastic
  - Wood
  - Glass
  - Liquids
  - Metal

### How does it work?
- Creates an electric field.
- When an object enters the sensing area, it changes the capacitance.
- The sensor detects the change and switches output.

### Advantages:
- Detects many materials.
- Can detect objects through some non-metal containers.

### Limitations:
- More sensitive to environmental conditions.
- Can detect unwanted materials if not adjusted properly.

### Industrial examples:
- Detecting liquid levels inside containers.
- Detecting plastic products.
- Detecting materials in packaging systems.

---

# Sensor Outputs

Most industrial proximity sensors provide a digital signal:

ON = Object detected
OFF = No object detected

This connects to a PLC digital input.

Example:

Sensor Output:
OFF → PLC Input = 0
ON → PLC Input = 1

---

# Wiring to PLC

Typical connection:

24V Power Supply
        ↓
Proximity Sensor
        ↓
PLC Digital Input

The PLC reads whether the sensor is ON or OFF and executes ladder logic.

---

# Proximity Sensor vs Push Button

Push Button:
- Human gives the signal.
- Requires physical interaction.

Proximity Sensor:
- Machine automatically detects objects.
- Used for automation.

Example:

Before:
Operator presses button → Conveyor starts

After:
Sensor detects object → PLC starts/stops conveyor automatically
