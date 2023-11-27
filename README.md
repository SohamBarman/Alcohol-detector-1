# Alcohol-detector-1
int B=11; void setup (){ pinMode(A0,INPUT); pinMode(B,OUTPUT); } void loop(){ int A=digitalRead(A0); if (A==1){ digitalWrite(B,HIGH); delay(1000); } else  { digitalWrite(B,LOW); delay(1000); } }
