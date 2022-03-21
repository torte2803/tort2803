int rot = D6;
int grün = D7;
int TMP36 = A0;
int motor = D8;
int t=500;
int sensorwert;
int temperatur = 0;
void setup() {

pinMode(rot, OUTPUT);
pinMode(grün, OUTPUT);
pinMode(motor, OUTPUT);
  // put your setup code here, to run once:

}

void loop() {
sensorwert=analogRead(TMP36); 
temperatur= map(sensorwert, 0, 410, -50, 150);
delay(t);
Serial.print(temperatur);
Serial.println(" Grad Celsius");

if (temperatur <20)
{
digitalWrite(rot, HIGH);
delay(1000);
digitalWrite(rot, LOW);
}
else if (temperatur >20.1 && < 24.9)
{
digitalWrite(grün, HIGH);
delay(1000);
digitalWrite(grün, LOW);
}
else
{
digitalWrite(motor, HIGH);
delay(1000);
digitalWrite(motor, LOW);
}


  // put your main code here, to run repeatedly:

}
