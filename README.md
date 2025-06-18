# 🧪 Electrical Engineering Test Challenge: STM32 CAN Communication & LED Acknowledgement

## 🎯 Objective
Design and implement a two-board system using STM32 microcontrollers (STM32G4 series) to communicate over the CAN bus, triggered by a button and acknowledged by an LED.

---

## 🛠️ System Overview

- **Microcontroller**: STM32G431CBT6
- **Power Supply**: 12V
- **CAN Transceiver**: External or integrated
- **Pin Mapping**:
  - **Onboard LED**: GPIOB, Pin 11
  - **Button Input**: GPIOB, Pin 6
  - **CAN RX**: GPIOA, Pin 11
  - **CAN TX**: GPIOA, Pin 12

---

## 📋 Requirements

### ✅ Board 1 (Sender)
- Use external button on **PB6** with interrupt.
- On button press, start sending CAN packets every **25 ms**.
- Each packet must include a unique identifier (e.g. a counter).
- Use **interrupt-based transmission**, not polling.

### ✅ Board 2 (Receiver)
- Listen for incoming CAN messages.
- On receipt:
  - Send back an ACK packet.
  - Blink onboard LED (PB11) once.

### ✅ Both Boards
- Use consistent CAN baudrate and message structure.
- ACK message must reflect original message (e.g. echo ID or counter).
- Implement basic debounce or protection against interrupt flooding.

---

## 💡 Implementation Notes

- HAL, LL, or bare-metal STM32 code is acceptable.
- CAN bitrate must be appropriate for 12V systems.
- Use **interrupts**, not polling, wherever applicable.
- You may simulate button presses if hardware is unavailable.

---

## 📦 Deliverables

1. **Firmware Source Code** for both boards.
2. **Schematics** (block or detailed) for setup.
3. **Short Documentation** (1–2 pages):
   - Pin mapping
   - CAN message format
   - Flow/state diagrams
4. **Optional**: Logic analyzer/oscilloscope traces of CAN exchange.

---

## 🏅 Bonus Points

- Use of **FreeRTOS** for task management.
- CAN error detection (e.g., NACK, timeouts).
- LED feedback pattern for success/failure differentiation.

---
