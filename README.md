STM32F1 Logic Analyzer
A lightweight, high-speed logic analyzer implementation for STM32F1 microcontrollers (Blue Pill board) that captures digital signal changes on 4 channels.
Features

4-channel digital capture on pins PB12-PB15
High-speed sampling with microsecond-precision timestamps
200 sample buffer (configurable)
Serial communication at 115200 baud for data transmission
Edge detection - captures only pin state changes for efficient memory usage
Simple protocol for interfacing with visualization software (Processing, Python, etc.)

Hardware Requirements

STM32F1 board (e.g., Blue Pill - STM32F103C8T6)
Requires Arduino_STM32 core

Pin Configuration

Input Channels: PB12, PB13, PB14, PB15 (with internal pull-up resistors)
Status LED: PB1

How It Works
The analyzer continuously monitors the 4 input pins and records:

Which pin(s) changed state
Precise timestamp of each change (microseconds)

Data is transmitted via USB serial when the buffer fills, then waits for a 'G' (Go) command to start the next capture cycle.
Communication Protocol
Data format sent over serial:
S
<initial_state>:<sample_count>
<changed_pins>:<timestamp_us>
<changed_pins>:<timestamp_us>
...
Use Cases

Digital protocol analysis (SPI, I2C, UART, etc.)
Timing verification
Debug embedded systems
Educational purposes
