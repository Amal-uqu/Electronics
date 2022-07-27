# Electronics Task
## After creating the circuit for stepper motor 
<img width="602" alt="stepperMotor" src="https://user-images.githubusercontent.com/108195103/181306565-096507f0-59e6-44f7-8663-99c602f2cc54.png">

## I ran the following code:

#include <Stepper.h>
const int stepsPerRevolution = 200;  
Stepper myStepper(stepsPerRevolution, 8, 9, 10, 11);
int stepCount = 0;  
void setup() {
}
void loop() {
  int sensorReading = analogRead(A0);
  int motorSpeed = map(sensorReading, 0, 1023, 0, 100);
  if (motorSpeed > 0) {
    myStepper.setSpeed(motorSpeed);
    myStepper.step(stepsPerRevolution / 100);
  }
}
