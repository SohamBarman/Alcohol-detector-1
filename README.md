 const int alcoholSensorPin = A0;  // Analog pin for alcohol sensor
const int motorPin = 9;          // Pin to control the car motor
const int A= 11;  
void setup() {
    pinMode(A,OUTPUT);
  pinMode(alcoholSensorPin, INPUT);
  pinMode(motorPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int alcoholValue = analogRead(alcoholSensorPin);

  // Convert analog reading to voltage (0-5V)
  float voltage = alcoholValue * (5.0 / 1023.0);

  // Check if alcohol concentration is above a thresholdzz
  if (voltage > 2.5) {
    stopCar();
    Serial.println("Alcohol detected! Car stopped.");
  } else {
    moveCarForward();
    Serial.println("No alcohol detected. Car moving.");
  }
}

void stopCar() {
  digitalWrite(motorPin, LOW);  // Stop the car
    digitalWrite(A,HIGH);
}

void moveCarForward() {
  digitalWrite(motorPin, HIGH);  // Move the car forward
    digitalWrite(A,LOW);
}
