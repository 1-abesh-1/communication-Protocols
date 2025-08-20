# UART Communication Protocol

## Overview
UART (**Universal Asynchronous Receiver/Transmitter**) is one of the simplest communication protocols used in embedded systems. Unlike I²C and SPI, UART does not require a clock line. Instead, it sends data asynchronously using only **two wires**:  
- **TX (Transmit)**  
- **RX (Receive)**  

It is widely used for debugging, connecting microcontrollers to PCs, or communication between two devices.

---

## UART Communication Lines
1. **TX (Transmit)** → Sends data out.  
2. **RX (Receive)** → Receives data in.  
3. **GND** → Common ground reference between devices.  

Optional control lines exist (RTS, CTS for hardware flow control), but in most embedded applications only TX and RX are used.

---

## How UART Works
UART sends data **bit by bit** in a structured frame without a clock signal. Both devices must **agree on the baud rate** (bits per second) beforehand.

### UART Frame Structure:
1. **Idle State** → Line stays HIGH when nothing is transmitted.  
2. **Start Bit** → A LOW signal indicates the start of transmission.  
3. **Data Bits** → Typically 5–9 bits (commonly 8 bits).  
4. **Parity Bit (optional)** → Error checking mechanism.  
5. **Stop Bit(s)** → One or two HIGH bits to signal the end of data.  

---

## Baud Rate
The **baud rate** defines how fast the data is transmitted (e.g., 9600, 115200 bps).  
Both devices must be configured with the same baud rate; otherwise, data will be corrupted.

---

## Advantages of UART
- Simple and widely used.  
- Requires only **two wires** (TX & RX).  
- Full-duplex communication (send and receive simultaneously).  

## Limitations
- Point-to-point communication only (no multi-device support like I²C or SPI).  
- Maximum distance and speed are limited.  
- Both devices must have the same baud rate.  

---

## UART Protocol Diagram
![UART Protocol](https://cdn-bpgea.nitrocdn.com/zuCVBxhMWfcaYgPVpbHfeZtJIxVXpbeO/assets/images/optimized/rev-12fffc9/tritekbattery.com/wp-content/uploads/2023/07/uart-communication-protocol.jpg)

---
