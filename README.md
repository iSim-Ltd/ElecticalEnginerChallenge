# Electrical Engineering Test Challenge: STM32 CAN Communication & LED Acknowledgement

## Objective
Design and implement a two-board system using STM32 microcontrollers (STM32G4 series) to communicate over the CAN bus, triggered by a button and acknowledged by an LED.

---

## System Overview

- **Microcontroller**: STM32G431CBT6
- **Power Supply**: 12V
- **CAN Transceiver**: External
- **Pin Mapping**:
  - **LED**: GPIOB, Pin 11
  - **Button Input**: GPIOB, Pin 2
  - **CAN RX**: GPIOA, Pin 11
  - **CAN TX**: GPIOA, Pin 12

---

## Requirements

### Board 1 (Sender)
- Listen for incoming CAN messages on address 0x1
- Use external button on **PB6** with interrupt.
- On button press, send a single CAN message
  - Send to address 0x2
- On receipt:
  - Blink LED once.  


### Board 2 (Receiver)
- Listen for incoming CAN messages on address 0x2
- On receipt:
  - Send back a message to address 0x1.
  - Blink LED once.  

### Both Boards
- Use consistent CAN baudrate and message structure.

---

## Implementation Notes

- HAL, LL, or bare-metal STM32 code is acceptable.
- Use **interrupts**, not polling, wherever applicable.

---

## Deliverables

1. **Firmware Source Code** for both boards.
2. **Schematics** (block or detailed) for setup.
3. **Short Documentation** (1–2 pages):
   - Pin mapping
   - CAN message format
   - Flow/state diagrams

---

## Bonus Points

- Implement basic debounce or protection against interrupt flooding.
- Use of a WS2812B LED on GPIOA, Pin 0 alongside the basic LED

---

