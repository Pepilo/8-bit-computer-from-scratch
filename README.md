# 8-bit-computer-from-scratch
A fully functional 8-bit PC built from scratch, following Ben Eater’s detailed tutorials.

# =========================
# STEP 1 — CLOCK MODULE
# =========================

The following image shows the clock module of the 8-bit computer project built on a breadboard. The clock is responsible for generating the timing signal that synchronizes all registers and logic in the system.

The circuit is based on two 555 timer ICs (NE555). One 555 is configured in astable mode, generating a continuous square wave clock signal. The clock frequency is adjustable using a potentiometer, allowing the computer to run slowly for debugging or faster for normal operation.

The second 555 timer is used in monostable mode to generate a clean, debounced pulse for manual clock stepping. A pushbutton allows stepping the computer one clock cycle at a time, which is extremely useful for observing and debugging individual instruction cycles.

![IMG_20251207_001350](https://github.com/user-attachments/assets/d202d96a-89cf-4df4-a0dc-701c47402aee)

A toggle switch selects between:

- Automatic clock mode (continuous oscillation)

- Manual step mode (one pulse per button press)

The logic section includes:

An inverter (74LS04)

AND gates (74LS08)

OR gates (74LS32)

These logic gates condition the clock signal and combine it with control signals (such as halt) to ensure clean and properly synchronized clock pulses are sent to the rest of the computer.

Two LEDs are used as visual indicators:

One shows the main clock signal.

The other indicates the inverted clock phase.

Resistors and capacitors around the 555 timers define the timing characteristics and provide proper signal conditioning. The circuit is powered through the breadboard power rails, distributing 5V and ground across the board.

This clock module is a critical foundation of the 8-bit computer, as every operation in the CPU depends on precise and reliable clock timing.

# =========================
# STEP 2 — MEMORY MODULE
# =========================

The image below shows the register and memory interface module of the 8-bit computer. This part of the system is responsible for temporarily storing data, holding instructions, and interfacing with the rest of the CPU, particularly the ALU.

Unlike a full RAM module, which will be implemented separately, this section focuses on the main working registers of the CPU.

![IMG_20251214_152400](https://github.com/user-attachments/assets/55230b8b-679c-433b-a910-4d80642cb22b)

The system is built around three key registers:

- Register A
This is one of the primary data registers. It stores 8-bit values and is directly connected to the ALU. During arithmetic or logic operations, Register A typically provides one of the operands and also receives the result from the ALU.

- Register B
This register also stores 8-bit values and serves as the second operand for the ALU. Data loaded into Register B is used together with Register A to perform operations such as addition or subtraction.

- Instruction Register (IR)
This is a special 8-bit register that holds the current instruction being executed. It is divided into two 4-bit parts:
The upper 4 bits (opcode) define the operation to perform.
The lower 4 bits (operand/address) represent either a value or a memory address, depending on the instruction.

The Instruction Register plays a central role in the fetch-decode-execute cycle. After an instruction is loaded, the opcode is sent to the control logic, which generates the appropriate control signals for the rest of the system.

Data is transferred between registers and other modules through a shared 8-bit bus. Control signals determine when each register loads data from the bus or places its contents onto it.

Each register is implemented using standard logic ICs and is connected to a row of LEDs. These LEDs provide a real-time visualization of the stored values, making it easier to debug and understand how data moves through the system.

The wiring between the breadboards carries the data bus, control lines, and power rails, ensuring proper synchronization with the clock module.

This module is a fundamental part of the CPU datapath. Register A and Register B enable arithmetic operations through the ALU, while the Instruction Register controls the behavior of the entire system by defining which operation is executed at each clock cycle.

![IMG_20251221_194056](https://github.com/user-attachments/assets/0e70e7e1-8de7-4b74-ab5f-c4ca66091539)

# =========================
# STEP 3 — ALU MODULE
# =========================

![Image](https://github.com/user-attachments/assets/6fef71f3-03d6-4278-8208-bd6549a1ae3f)

The image above shows the Arithmetic Logic Unit (ALU) of the 8-bit computer. This module is responsible for performing arithmetic operations on data coming from the CPU registers.

The ALU takes its inputs from Register A and Register B, which provide the two 8-bit operands required for computation. These values are fed into the ALU through dedicated wiring from the register module.

At the core of the ALU are binary adders (typically 74LS283 ICs), which perform 8-bit addition. The circuit is designed to also support subtraction by using two’s complement arithmetic. This is achieved by conditionally inverting the bits of Register B and adding 1, allowing the ALU to compute both:

Addition (A + B)
Subtraction (A − B)

A control signal determines whether the ALU operates in addition or subtraction mode. When subtraction is selected, XOR gates invert the bits of Register B, and the carry-in is set to 1 to complete the two’s complement operation.

The result of the computation is placed onto the shared 8-bit bus, where it can be loaded back into Register A or used by other parts of the system.

The ALU also generates status information:

Carry flag: Indicates an overflow from the most significant bit.
(Optionally) Zero flag: Can be derived to indicate when the result is zero.

A set of LEDs is connected to the ALU output, providing a real-time visual representation of the computed result. This is especially useful for debugging and understanding how operations are performed step by step.

The wiring between the breadboards distributes the operands, control signals (such as subtraction enable), and output lines. Proper synchronization with the clock ensures that operations occur at the correct time during each instruction cycle.

This ALU module is a central component of the CPU. It enables the computer to perform arithmetic operations, which are essential for executing programs and processing data.

# =========================
# STEP 4 — ALU MODULE
# =========================

![IMG_20260201_203752](https://github.com/user-attachments/assets/6cac95f6-754e-4f4e-bbca-e65715d4a5d6)

![IMG_20260329_151219](https://github.com/user-attachments/assets/394b5261-ed8f-4995-94aa-f9e3b86b0b3d)







