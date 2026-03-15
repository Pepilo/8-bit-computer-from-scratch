# 8-bit-computer-from-scratch
A fully functional 8-bit PC built from scratch, following Ben Eater’s detailed tutorials.

First step: Computer clock
![IMG_20251115_142136](https://github.com/user-attachments/assets/cd8cbdb0-df5f-4c2e-aacb-93ce8bf3f053)

![IMG_20251123_164757](https://github.com/user-attachments/assets/5ea3ef56-3fe9-4132-90be-db2066297c94)

![IMG_20251130_152106](https://github.com/user-attachments/assets/1f0e70e7-cd6b-4510-bf14-6c72ad86b126)

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

Second step: 8 bits memory
![IMG_20251214_152400](https://github.com/user-attachments/assets/55230b8b-679c-433b-a910-4d80642cb22b)

![IMG_20251221_194056](https://github.com/user-attachments/assets/0e70e7e1-8de7-4b74-ab5f-c4ca66091539)

Third step: ALU

![IMG_20260111_154433](https://github.com/user-attachments/assets/8a0a1b83-5c17-4dd1-81aa-a951f6330e2d)

![IMG_20260118_165912](https://github.com/user-attachments/assets/81d127c1-2add-4e14-bc1f-12efaa2d24d6)

![Image](https://github.com/user-attachments/assets/6fef71f3-03d6-4278-8208-bd6549a1ae3f)

Fourth step: RAM

![IMG_20260201_203752](https://github.com/user-attachments/assets/6cac95f6-754e-4f4e-bbca-e65715d4a5d6)







