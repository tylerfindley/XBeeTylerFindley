# XBeeTylerFindley
This code is for communication between two XBees 

#include <SoftwareSerial.h>

SoftwareSerial XBee(4, 3); // RX, TX

void setup()
{
  
  XBee.begin(9600);
  Serial.begin(9600);
}

void loop()
{
  if (Serial.available())
  { //  out to XBee
    XBee.write(Serial.read());
  }
  if (XBee.available())
  { // send it out to serial monitor
    Serial.write(XBee.read());
  }
}
