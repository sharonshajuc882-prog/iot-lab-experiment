# N-LED Blinking using ESP32

## Aim
To interface multiple LEDs (N LEDs) with the ESP32 development board and make them blink in a sequential/pattern manner using GPIO pins.

## Objective
- To understand how to control multiple GPIO pins simultaneously on the ESP32.
- To learn how to use arrays and loops in an Arduino sketch to manage multiple output pins efficiently.
- To create a sequential blinking (chasing) pattern across multiple LEDs.
- To understand timing control using the `delay()` function for multiple outputs.

## Components Required
| Component              | Quantity |
|--------------------------|----------|
| ESP32 development board  | 1        |
| LEDs                      | N (e.g., 4) |
| Resistors (220Ω)          | N        |
| Breadboard                | 1        |
| Jumper wires               | N + 1    |
| Micro-USB cable            | 1        |

## Circuit Diagram
- Connect the anode (long leg) of each LED to a separate GPIO pin on the ESP32 (e.g., GPIO 2, 4, 5, 18 for 4 LEDs), each through a 220Ω resistor.
- Connect the cathode (short leg) of each LED to the **GND** pin of the ESP32 (common ground).

## Program (Arduino Sketch)
```cpp
const int ledPins[] = {2, 4, 5, 18};   // GPIO pins connected to LEDs
const int numLeds = sizeof(ledPins) / sizeof(ledPins[0]);

void setup() {
  for (int i = 0; i < numLeds; i++) {
    pinMode(ledPins[i], OUTPUT);
    digitalWrite(ledPins[i], LOW);
  }
}

void loop() {
  for (int i = 0; i < numLeds; i++) {
    digitalWrite(ledPins[i], HIGH); // Turn ON current LED
    delay(300);                     // Wait
    digitalWrite(ledPins[i], LOW);  // Turn OFF current LED
  }
}
```

## Procedure
1. Connect N LEDs to separate GPIO pins on the ESP32 as per the circuit diagram, each with a current-limiting resistor.
2. Open the Arduino IDE and write/paste the above program, updating the `ledPins[]` array to match your wiring.
3. Select the correct ESP32 board and COM port from the **Tools** menu.
4. Upload the program to the ESP32 (press **BOOT** if prompted).
5. Observe the LEDs blinking one after another in a sequential pattern.

## Result
Multiple LEDs (N LEDs) were successfully interfaced with the ESP32 and made to blink sequentially using an array of GPIO pins with the `digitalWrite()` and `delay()` functions, demonstrating multi-pin digital output control on the ESP32.
