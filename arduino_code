
#include <SoftwareSerial.h> // Comes with Arduino IDE

SoftwareSerial ble_sensor(7,6);

int micro_read = 2;
volatile int iter = 0;

void setup() {
  // put your setup code here, to run once:
  //Serial.begin(9600);
  // Start the serial connection to the MH-Z14
  ble_sensor.begin(9600);
  pinMode(micro_read,INPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
  bool val;
  
  val = digitalRead(micro_read);
  if (val){
    iter+=1;
    Serial.println(iter);
    
    ble_sensor.write(char(iter));
    delay(100);
    if (iter>255){
      iter = 0;
    }
  }
  delay(10);
}
