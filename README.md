#include <Servo.h>

Servo myServo;

int sensorPin = 2;
int servoPin = 5;
int lastState = HIGH;

void setup() {
  pinMode(sensorPin, INPUT_PULLUP);
  myServo.attach(servoPin);
  myServo.write(90);
}

void loop() {
  int val = digitalRead(sensorPin);

  if (val == LOW && lastState == HIGH) {
    myServo.write(0);
  }

  if (val == HIGH && lastState == LOW) {
    myServo.write(180);
  }

  lastState = val;
  delay(50);
}# rain_detector.ino
Add rain detector Arduino code
