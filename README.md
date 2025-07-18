# 🚦 Arduino Traffic Light Controller
![Circuit Preview](./circuit.png)

Interactive Arduino circuit simulation demonstrating multi-input control with LED outputs

## 🔗 Live Demo
[View on Tinkercad](https://www.tinkercad.com/things/6bm4NatIbXI)

## 💻 Arduino Code
```cpp
void setup() {
  pinMode(7, INPUT);   // Button 1 input
  pinMode(4, INPUT);   // Button 2 input
  pinMode(2, INPUT);   // Button 3 input
  pinMode(13, OUTPUT); // LED 1 output
  pinMode(12, OUTPUT); // LED 2 output
  pinMode(8, OUTPUT);  // LED 3 output
}

void loop() {
  if(digitalRead(7) == HIGH) {
    digitalWrite(13, HIGH); // Activate LED 1
    delay(1000);
    digitalWrite(13, LOW);
    delay(1000);
  }
  else if(digitalRead(4) == HIGH) {
    digitalWrite(12, HIGH); // Activate LED 2
    delay(1000);
    digitalWrite(12, LOW);
    delay(1000);
  }
  else if(digitalRead(2) == HIGH) {
    digitalWrite(8, HIGH);  // Activate LED 3
    delay(1000);
    digitalWrite(8, LOW);
    delay(1000);
  }
  else {
    // Turn off all LEDs
    digitalWrite(13, LOW);
    digitalWrite(12, LOW);
    digitalWrite(8, LOW);
  }
}
```
# 🛠 Components

| Component          | Purpose                  |
|--------------------|--------------------------|
| Arduino UNO        | Main controller          |
| LED (x3)           | Visual output indicators |
| Push Button (x3)   | Digital input controls   |
| 220Ω Resistor (x3) | LED current limiting     |

## 🎯 How It Works

- **Button Mapping**:
  - `Button 1 (Pin 7)` → `LED 1 (Pin 13)`
  - `Button 2 (Pin 4)` → `LED 2 (Pin 12)`
  - `Button 3 (Pin 2)` → `LED 3 (Pin 8)`

- **Behavior**:
  - Pressing any button makes its corresponding LED blink at 1-second intervals
  - All LEDs automatically turn off when no buttons are pressed
  - Only one LED can be active at a time (mutually exclusive control)
