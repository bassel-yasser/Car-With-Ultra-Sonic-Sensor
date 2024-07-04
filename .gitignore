#include <AFMotor.h>    // Import library to control motor shield
#include <Servo.h>      // Import library to control the servo

AF_DCMotor rightBack(1);    // Create an object to control each motor
AF_DCMotor rightFront(2);
AF_DCMotor leftFront(3);
AF_DCMotor leftBack(4);
Servo servoLook;            // Create an object to control the servo

byte trig = 2;              // Assign the ultrasonic sensor pins
byte echo = 13;

byte maxDist = 150;         // Maximum sensing distance (Objects further than this distance are ignored)
byte stopDist = 50;         // Minimum distance from an object to stop in cm
float timeOut = 2 * (maxDist + 10) / 100 / 340 * 1000000; // Maximum time to wait for a return signal

byte motorSpeed = 55;       // The maximum motor speed
int motorOffset = 10;       // Factor to account for one side being more powerful
int turnSpeed = 50;         // Amount to add to motor speed when turning

void setup() {
  rightBack.setSpeed(motorSpeed);         // Set the motors to the motor speed
  rightFront.setSpeed(motorSpeed);
  leftFront.setSpeed(motorSpeed + motorOffset);
  leftBack.setSpeed(motorSpeed + motorOffset);
  rightBack.run(RELEASE);                 // Ensure all motors are stopped
  rightFront.run(RELEASE);
  leftFront.run(RELEASE);
  leftBack.run(RELEASE);
  servoLook.attach(10);                   // Assign the servo pin
  pinMode(trig, OUTPUT);                  // Assign ultrasonic sensor pin modes
  pinMode(echo, INPUT);
}

void loop() {
  servoLook.write(90);                    // Set the servo to look straight ahead
  delay(750);
  int distance = getDistance();           // Check that there are no objects ahead
  if (distance >= stopDist) {             // If there are no objects within the stopping distance, move forward
    moveForward();
  }
  while (distance >= stopDist) {          // Keep checking the object distance until it is within the minimum stopping distance
    distance = getDistance();
    delay(250);
  }
  stopMove();                             // Stop the motors
  int turnDir = checkDirection();         // Check the left and right object distances and get the turning instruction
  Serial.print(turnDir);
  switch (turnDir) {                      // Turn left, turn around or turn right depending on the instruction
    case 0:                               // Turn left
      turnLeft(400);
      break;
    case 1:                               // Turn around
      turnLeft(700);
      break;
    case 2:                               // Turn right
      turnRight(400);
      break;
  }
}

void accelerate() {
  // Function to accelerate the motors from 0 to full speed
  for (int i = 0; i < motorSpeed; i++) {
    // Accelerate code here
  }
}

int getDistance() {
  // Function to get the distance from the ultrasonic sensor
  // Distance measurement code here
}

void moveForward() {
  // Function to move the car forward
  // Move forward code here
}

void stopMove() {
  // Function to stop the car
  // Stop code here
}

int checkDirection() {
  // Function to check the direction
  // Check direction code here
}

void turnLeft(int duration) {
  // Function to turn the car left
  // Turn left code here
}

void turnRight(int duration) {
  // Function to turn the car right
  // Turn right code here
}
