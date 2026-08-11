# Solar-Powered Multipurpose Agricultural Robot

An eco-friendly, automated, solar-powered multipurpose agricultural robot designed for grass cutting, weed management, and pesticide/fertilizer spraying. Powered by an embedded microcontroller platform with RF wireless control.

---

## Project Overview
Manual weeding and pesticide spraying are labor-intensive, time-consuming, and expose farmers to harmful chemicals. This project offers an autonomous/semi-autonomous solution powered by renewable solar energy to perform multiple agricultural operations efficiently.

* **Primary Functions:** Automated Grass/Weed Cutting & Liquid Fertilizer/Pesticide Spraying
* **Power Source:** Solar Panel with 12V Rechargeable Battery Bank
* **Control Mechanism:** RF Wireless Remote Control


## Output Video (Drive Link) https://drive.google.com/drive/folders/1UrtmDWfcxmb_RIvFFaM8GJsbhqjNVdmK?usp=drive_link
---

##Key Features
* **Solar Energy Harvesting:** Roof-mounted solar panel continuously recharges the onboard 12V battery for uninterrupted field operation.
* **Dual Functionality:** 
  * Front-mounted rotating blade cutter motor for grass/weed trimming.
  * Onboard fluid container with 12V pump for targeted fertilizer spraying.
* **RF Wireless Navigation:** Controlled remotely using RF communication for safe operation away from hazardous chemicals.
* **Modular Mechanical Design:** Sturdy 4-wheel drive chassis built to handle uneven agricultural terrain.

---

## Hardware & Circuit Components

### **Electronic Components (As per Circuit Schematic)**
* **Microcontroller:** ATmega8 / 8051 Architecture
* **Power Management:**
  * 12V Solar Panel & 12V Battery (`BAT1`)
  * LM7805 Voltage Regulator (`U2`) for 5V DC logic supply
  * Filtering Capacitors ($1000\mu\text{F}$, $100\text{nF}$, $27\text{pF}$ crystal caps)
* **Actuators & Motor Drivers:**
  * Base Wheel Drive Motors (Left & Right wheel drive via Motor Driver 1)
  * Cutter Motor & Shaft Mechanism (via Motor Driver 2)
  * 12V Liquid Spray Pump driven via **IRF540 MOSFET** (`Q1`)
* **Wireless Communication:** RF Receiver Module
* **Clock Source:** External Crystal Oscillator with loading capacitors

---

## Circuit Working & Block Description

1. **Power Supply Unit:** 12V Solar Panel charges the 12V battery. The LM7805 regulator steps down 12V to 5V to power the microcontroller and RF Receiver.
2. **Control Processing:** The RF Receiver captures directional and operational signals from the transmitter remote and passes them to the ATmega8 microcontroller.
3. **Locomotion:** The microcontroller commands Motor Driver 1 to drive the base wheels (forward, reverse, left, right).
4. **Cutter & Pump Actuation:** 
   * Motor Driver 2 controls the front cutter blade motor.
   * An IRF540 MOSFET acts as an electronic switch to trigger the 12V fluid pump for spraying operations.

---

## How to Build & Run

### **1. Hardware Assembly**
1. Assemble the 4-wheel robot chassis and mount the cutter motor at the front arm.
2. Mount the liquid container, 12V spray pump, and tubing nozzle.
3. Fix the solar panel on the top frame above the main battery and PCB enclosure.

### **2. Software & Firmware Setup**
1. Open your embedded C IDE (e.g., Keil uVision / Atmel Studio).
2. Compile the embedded C code for RF signal decoding and motor control outputs.
3. Flash the hex file onto the microcontroller using an ISP programmer.

---

## Project Visuals
* **Hardware Prototype:** Solar Panel top-mount, 4-wheel drive base, front cutter, and fluid reservoir.
* **Circuit Diagram:** Complete schematic with RF module, ATmega8, LM7805, Motor Drivers, and MOSFET switching pump control.
