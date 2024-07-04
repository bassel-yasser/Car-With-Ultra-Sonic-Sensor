# Obstacle Avoiding Robot Car

This project guides you through building an obstacle avoiding robot car using Arduino Uno and various components.

## Components Needed

- Arduino Uno
- L293D Motor Driver Shield
- Micro Servo
- Ultrasonic Sensor Module
- 4 x Geared DC Motors & Wheels
- 9-12V Battery Pack
  - A 9V block battery usually can't produce enough current to drive the four motors. Rechargeable battery packs for RC cars tend to work best for this project.
- 8 x M3 x 15mm Socket Head Screws
- Ribbon Cable
- Header Pins

## Building the Robot Car

### Motor Driver Shield
The motor control is managed through an L293D motor driver shield, using two L293D driver chips and a shift register. The shield also includes power breakout pins, connectors for two servos, and a breakout for IO pin 2.

#### Soldering
- Solder female pin headers to the power pins at the bottom of the shield.
- Solder a pin header for pin 2 in the breakout hole.
- Solder pin 13 directly onto the back (top) of the shield’s pins.

### Ultrasonic Sensor
The ultrasonic sensor uses sound waves to measure the distance to an object by timing the pulse's return.

Formula: `Distance = Pulse Time x Speed of Sound in Air / 2`

### DC Motors and Wheels
Attach a short power lead to each motor with pins to screw into the shield's terminals.

### Chassis
The car chassis can be 3D printed. The design includes:
- Top and bottom chassis sections
- Holder for the ultrasonic sensor

### Assembly Steps
1. **Servo and Ultrasonic Sensor:**
   - Glue the servo with the ribbon cable facing the back of the car.
   - Glue the ultrasonic sensor into its housing, ensuring space around the pins.
   - Glue the servo arm to the bottom of the holder, then attach it to the servo.

2. **Motors:**
   - Glue each motor to the bottom chassis plate, keeping wiring accessible.
   - Place a rechargeable battery between the motors if used.
   - Secure the top chassis plate with screws.

3. **Arduino and Shield:**
   - Screw the Arduino to the top chassis plate.
   - Plug the motor driver shield into the Arduino.
   - Connect motors to the shield’s terminals (front motors to front terminals, back motors to back terminals).

4. **Wire Management:**
   - Glue wires away from the wheels to prevent tangling.
   - Plug the servo into the servo 1 header pins on the shield with the signal wire facing inwards.

5. **Power Connections:**
   - Connect a power cable from the battery to the power terminals.
   - Avoid connecting both the battery to the motor shield and a power supply to the Arduino simultaneously to prevent damage.

6. **Sensor Connections:**
   - Connect the ultrasonic sensor: ground and Vcc to ground and 5V pins, trigger pin to pin 2, and echo pin to pin 13 on the shield.

7. **Finishing Up:**
   - Attach the wheels to the geared motors.

  Setting Up The Obstacle Avoiding Robot Car

Wheel Rotation:

Ensure all wheels turn in the forward direction when the car starts moving. If any wheel turns in the wrong direction, swap the motor leads in the terminals.
Servo Movement:

Ensure the servo moves left first and then right when detecting an object. Adjust if the servo signal direction is reversed.
Straight Line Adjustment:

If the car pulls left or right, adjust the motorOffset variable. Increase or decrease the offset based on the direction the car pulls.
Turning Adjustment:

Allow the car to detect an object and turn. Adjust the turning times in the switch statement if the car doesn't turn approximately 90 degrees.
Tight Spaces:

The car will turn around and drive back out if it drives into a tight space.
The obstacle avoiding robot car runs well on both carpeted and tiled surfaces. Adjust motor speed for carpeted areas if needed.

Future Improvements
In future versions, the ultrasonic sensor will move left and right during forward movement to detect objects slightly off-center. This will help the robot avoid gradual obstacles and prevent it from getting stuck.
