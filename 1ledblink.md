# LED Blinking using ESP32

## Aim
To interface an LED with the ESP32 development board and make it blink at a fixed time interval using a simple program.

## Objective
- To understand the basic working of the ESP32 board and its GPIO pins.
- To learn how to write and upload a program (sketch) to the ESP32 using the Arduino IDE.
- To control an LED (ON/OFF) using the `digitalWrite()` function.
- To understand the use of the `delay()` function for timing control.

## Components Required
| Component            | Quantity |
|-----------------------|----------|
| ESP32 development board | 1        |
| LED                    | 1        |
| Resistor (220Ω)        | 1        |
| Breadboard             | 1        |
| Jumper wires           | 2        |
| Micro-USB cable        | 1        |

## Circuit Diagram
- Connect the anode (long leg) of the LED to GPIO pin **2** of the ESP32 through a 220Ω resistor.
  (GPIO 2 is connected to the onboard LED on most ESP32 dev boards, so an external LED is optional.)
- Connect the cathode (short leg) of the LED to the **GND** pin of the ESP32.

## Arduino IDE Setup for ESP32
1. Open Arduino IDE → **File** → **Preferences**.
2. In "Additional Boards Manager URLs", add:
   `https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json`
3. Go to **Tools** → **Board** → **Boards Manager**, search "esp32", and install it.
4. Select **Tools** → **Board** → your ESP32 board (e.g., "ESP32 Dev Module").
5. Select the correct **COM Port**.

## Program (Arduino Sketch)
```cpp
#define LED_PIN 2  // Onboard/external LED pin

void setup() {
  pinMode(LED_PIN, OUTPUT); // Set GPIO pin as output
}

void loop() {
  digitalWrite(LED_PIN, HIGH); // Turn LED ON
  delay(1000);                  // Wait for 1 second
  digitalWrite(LED_PIN, LOW);  // Turn LED OFF
  delay(1000);                  // Wait for 1 second
}
```

## Procedure
1. Connect the circuit as per the circuit diagram (skip external wiring if using the onboard LED).
2. Open the Arduino IDE and write/paste the above program.
3. Select the correct ESP32 board and COM port from the **Tools** menu.
4. Click **Upload** and press the **BOOT** button on the ESP32 if prompted, to start flashing.
5. Observe the LED blinking at 1-second intervals.

## Result
The LED was successfully interfaced with the ESP32, and it was made to blink at a fixed interval of 1 second using the `digitalWrite()` and `delay()` functions, demonstrating the basic digital output control capability of the ESP32 development board.

