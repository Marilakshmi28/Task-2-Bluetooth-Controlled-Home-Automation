COMPANY:CODTECH IT SOLUTIONS
NAME:MARILAKSHMI S
INTERN ID:CT04DH848
DOMAIN:EMBEDDED SYSTEMS
DURATION:4 WEEKS
# Task-2-Bluetooth-Controlled-Home-Automation
Simulated Bluetooth-controlled home automation system using Arduino UNO and Serial Monitor in Tinkercad.
This project simulates a Bluetooth-controlled smart home automation system using Arduino UNO. Since HC-05 is not available in Tinkercad, the Serial Monitor is used to simulate Bluetooth commands (A, B, C, D) to control devices like lights and fans (represented by LEDs).

Components Used:
- Arduino UNO  
- 2 × LEDs  
- 2 × 220Ω Resistors  
- Jumper Wires  
- Serial Monitor (Bluetooth simulation)

Circuit Description:
- LED1 positive (long leg) → Pin 8 (through 220Ω resistor)  
- LED2 positive (long leg) → Pin 9 (through 220Ω resistor)  
- Both LED negative legs → GND  

This simulates a 2-device home automation system (e.g., light & fan).

Working Logic:
The user types commands in the Serial Monitor (like Bluetooth input):

`A` Turn ON LED1 
`B` Turn OFF LED1 
`C` Turn ON LED2 
`D` Turn OFF LED2 

Arduino Code:
char data = 0;

void setup() {
  Serial.begin(9600);
  pinMode(8, OUTPUT);
  pinMode(9, OUTPUT);
}

void loop() {
  if (Serial.available()) {
    data = Serial.read();
    if (data == 'A') digitalWrite(8, HIGH);
    if (data == 'B') digitalWrite(8, LOW);
    if (data == 'C') digitalWrite(9, HIGH);
    if (data == 'D') digitalWrite(9, LOW);
  }
}
