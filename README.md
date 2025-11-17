# Arduino Home Theater Automation
Automate your entire home theater setup with an Arduino-controlled IR blaster, relay modules, and sensor feedback. This project lets you power on/off devices, switch inputs, dim lights, and more — all with a single automated sequence.

## Features
- One-button theater startup sequence  
- IR remote emulation for TVs, receivers, LED strips, etc.  
- Relay control for lights and power toggles  
- Optional sensors for environment or power-state detection  
- Fully customizable device timings and sequences  

## Hardware Used
- Arduino (Uno / Nano / Mega)  
- IR LED + IR Receiver  
- Relay module (1–4 channel)  
- Optional:
  - Light sensor (LDR)
  - Power detection module
  - LED strip or ambient lighting
  - Servo (for physical button automation)

## Software / Libraries
Install these Arduino libraries:
- IRremote  
- EEPROM (optional)

## Project Structure
arduino-home-theater-automation/
│
├── src/
│ ├── main.ino # Main logic
│ ├── ir_codes.h # IR code storage
│ └── sequences.h # Startup/shutdown sequences
│
└── README.md
## Usage
1. Upload `main.ino` to your Arduino.  
2. Fill `ir_codes.h` with your learned IR codes.  
3. Edit `sequences.h` to define your automation steps.  
4. Trigger with a button or Serial command.

## Example Automation Code
```cpp
void startTheater() {
    sendIR(TV_POWER);
    delay(500);

    sendIR(AVR_POWER);
    delay(800);

    sendIR(HDMI_SWITCH_INPUT1);
    delay(500);

    activateRelay(LED_STRIP, ON);
}
