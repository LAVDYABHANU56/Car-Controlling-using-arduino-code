# Car Controlling using arduino code
# Arduino code will be transferred to ESP8266 and it will connected to a motor drive in order control the car.All the runtime commands are provided in the code.
// Define motor control pins
const int motorA1 = D1; // IN1
const int motorA2 = D2; // IN2
const int motorB1 = D5; // IN3
const int motorB2 = D6; // IN4
const int enableA = D7; // ENA
const int enableB = D3  ; // ENB

void setup() {
  // Set motor control pins as outputs
  pinMode(motorA1, OUTPUT);
  pinMode(motorA2, OUTPUT);
  pinMode(motorB1, OUTPUT);
  pinMode(motorB2, OUTPUT);
  
  // Set enable pins as outputs
  pinMode(enableA, OUTPUT);
  pinMode(enableB, OUTPUT);

  // Set initial speed
  analogWrite(enableA, 255); // Full speed for Motor A
  analogWrite(enableB, 255); // Full speed for Motor B
}

void loop() {
  // Move Motor A forward
  digitalWrite(motorA1, LOW);
  digitalWrite(motorA2, HIGH);
  
  // Move Motor B forward
  digitalWrite(motorB1, HIGH);
  digitalWrite(motorB2, LOW);
  delay(2000); // Move forward for 2 seconds

  // Stop Motor A
  digitalWrite(motorA1, LOW);
  digitalWrite(motorA2, LOW);
  
  // Stop Motor B
  digitalWrite(motorB1, LOW);
  digitalWrite(motorB2, LOW);
  delay(1000); // Stop for 1 second

  // Move Motor A backward
  digitalWrite(motorA1, HIGH);
  digitalWrite(motorA2, LOW );
  
  // Move Motor B backward
  digitalWrite(motorB1, LOW);
  digitalWrite(motorB2, HIGH);
  delay(2000); // Move backward for 2 seconds

  // Stop both motors
  digitalWrite(motorA1, LOW);
  digitalWrite(motorA2, LOW);
  digitalWrite(motorB1, LOW);
  digitalWrite(motorB2, LOW);
  delay(1000); // Stop for 1 second
}
