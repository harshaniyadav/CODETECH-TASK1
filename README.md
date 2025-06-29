# CODETECH-TASK1
 Circuit Diagram Description
Components Needed:

Arduino Uno (or similar)
16x2 LCD (using 6 digital pins)
Push button
10kΩ resistor (optional for pull-down, but not needed if using INPUT_PULLUP)
Breadboard and jumper wires
Connections:

LCD:

RS → Pin 12
E → Pin 11
D4 → Pin 5
D5 → Pin 4
D6 → Pin 3
D7 → Pin 2
VSS → GND
VDD → 5V
V0 → Center pin of 10k potentiometer (ends to 5V and GND) for contrast
RW → GND
A (backlight) → 5V (with suitable resistor)
K (backlight) → GND
Button:

One side to GND
Other side to Pin 7
(Use INPUT_PULLUP in code to avoid needing an external pull-down resistor)
Diagram:

Code
   +5V ---[LCD VDD]-------+
   |                     [LCD A]---(220Ω)---+5V
  [LCD K]---GND
  [LCD VSS, RW]---GND
  [LCD RS]---Pin 12
  [LCD E ]---Pin 11
  [LCD D4]---Pin 5
  [LCD D5]---Pin 4
  [LCD D6]---Pin 3
  [LCD D7]---Pin 2
  [LCD V0]---Potentiometer middle (ends: 5V and GND)
  
  [Button leg 1]---GND
  [Button leg 2]---Pin 7 (digital input, uses internal pull-up)
3. Debouncing Explanation
Mechanical push buttons can "bounce" when pressed, causing multiple quick on/off signals. The code above uses a debounce routine: after detecting a state change, it waits 50 ms to see if the state is stable before counting the press.

4. Result
Each time the button is pressed, the counter increments by 1.
The count displays on both the LCD and the Serial Monitor.
Debouncing ensures accurate counting.
