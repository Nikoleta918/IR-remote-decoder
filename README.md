# 🔦 IR Remote-Controlled LEDs with Arduino

This Arduino project allows you to control two LEDs using an IR remote. It uses an IR receiver to detect signals and turns LEDs on or off based on specific remote control buttons.

## 📦 Components Used

- Arduino board (Uno, Nano, etc.)
- 2x LEDs
- 2x Resistors (220–330 ohms)
- IR Receiver (e.g., VS1838B)
- IR Remote Control
- Breadboard and jumper wires

## 🧾 Description

The IR receiver reads signals from a remote control and matches specific hexadecimal codes to trigger actions:

- LED on pin **6** turns **ON** when button with code `0xE718FF00` is pressed  
- LED on pin **6** turns **OFF** with code `0xAD52FF00`  
- LED on pin **5** turns **ON** with code `0xA55AFF00`  
- LED on pin **5** turns **OFF** with code `0xF708FF00`

You can monitor raw IR codes via the serial monitor to map new buttons.

## 📥 How to Use

### 1. Connect Components
- IR receiver output pin to **D3**
- LED 1 anode to **D6** (with a resistor in series)
- LED 2 anode to **D5** (with a resistor in series)
- Common grounds between all components

### 2. Upload the Code
Make sure you have the **IRremote** library installed. You can install it via Library Manager in the Arduino IDE.

### 3. Use the Remote
Press the mapped buttons to control each LED. You can also print new codes to the Serial Monitor by uncommenting this line:

```cpp
// Serial.println(IR.decodedIRData.decodedRawData, HEX);
