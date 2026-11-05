## ## Experiment 2 — ESP32 Switch Controlled LED

**Aim:** To interface a push-button switch with ESP32 GPIO and control an LED based on switch input.

**Components Required:**

| Component | Quantity |
|-----------|----------|
| ESP32 Development Board | 1 |
| LED (Red / Green) | 1 |
| Resistor 220Ω | 1 |
| Push-Button Switch | 1 |
| Breadboard | 1 |
| Jumper Wires | 5 |
| USB Cable | 1 |

**Circuit Connections:**

| ESP32 Pin | Component |
|-----------|-----------|
| GPIO2 | LED Anode (+) via 220Ω resistor |
| GND | LED Cathode (−) |
| GPIO4 | Push-button terminal 1 |
| GND | Push-button terminal 2 |

```
ESP32 GPIO4 ──── Button ──── GND      (Input, Internal Pull-Up)
ESP32 GPIO2 ──── 220Ω ──── LED(+) ──── LED(−) ──── GND
```

**Code:**
```cpp
#define LED_PIN    2
#define BUTTON_PIN 4

void setup() {
  pinMode(LED_PIN, OUTPUT);
  pinMode(BUTTON_PIN, INPUT_PULLUP);  // Internal pull-up enabled
}

void loop() {
  int buttonState = digitalRead(BUTTON_PIN);

  if (buttonState == LOW) {       // Button pressed (pulled to GND)
    digitalWrite(LED_PIN, HIGH);  // LED ON
  } else {
    digitalWrite(LED_PIN, LOW);   // LED OFF
  }
}
```

**Procedure:**
1. Connect the LED to GPIO2 through a 220Ω resistor. Connect LED cathode to GND.
2. Connect one terminal of the push-button to GPIO4 and the other terminal to GND.
3. Open Arduino IDE, select the correct board and port.
4. Upload the code.
5. Press and hold the push-button and observe the LED. Release and observe.

**Result:** The LED turns ON when the push-button is pressed and turns OFF when released, confirming successful GPIO digital input reading and output control on the ESP32.


**Aim:** To interface a push-button switch with ESP32 GPIO and control an LED based on switch input.

**Components Required:**

| Component | Quantity |
|-----------|----------|
| ESP32 Development Board | 1 |
| LED (Red / Green) | 1 |
| Resistor 220Ω | 1 |
| Push-Button Switch | 1 |
| Breadboard | 1 |
| Jumper Wires | 5 |
| USB Cable | 1 |

**Circuit Connections:**

| ESP32 Pin | Component |
|-----------|-----------|
| GPIO2 | LED Anode (+) via 220Ω resistor |
| GND | LED Cathode (−) |
| GPIO4 | Push-button terminal 1 |
| GND | Push-button terminal 2 |

```
ESP32 GPIO4 ──── Button ──── GND      (Input, Internal Pull-Up)
ESP32 GPIO2 ──── 220Ω ──── LED(+) ──── LED(−) ──── GND
```

**Code:**
```cpp
#define LED_PIN    2
#define BUTTON_PIN 4

void setup() {
  pinMode(LED_PIN, OUTPUT);
  pinMode(BUTTON_PIN, INPUT_PULLUP);  // Internal pull-up enabled
}

void loop() {
  int buttonState = digitalRead(BUTTON_PIN);

  if (buttonState == LOW) {       // Button pressed (pulled to GND)
    digitalWrite(LED_PIN, HIGH);  // LED ON
  } else {
    digitalWrite(LED_PIN, LOW);   // LED OFF
  }
}
```

**Procedure:**
1. Connect the LED to GPIO2 through a 220Ω resistor. Connect LED cathode to GND.
2. Connect one terminal of the push-button to GPIO4 and the other terminal to GND.
3. Open Arduino IDE, select the correct board and port.
4. Upload the code.
5. Press and hold the push-button and observe the LED. Release and observe.

**Result:** The LED turns ON when the push-button is pressed and turns OFF when released, confirming successful GPIO digital input reading and output control on the ESP32.
