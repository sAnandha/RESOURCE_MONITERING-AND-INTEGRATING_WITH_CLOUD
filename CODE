/************************************************************************************

 *  My Channel: ASKME_EDITS 
 
 *  
 *  *********************************************************************************
 *  Preferences--> Aditional boards Manager URLs : 
 *  For ESP32:
 *  https://dl.espressif.com/dl/package_esp32_index.json
 *  
 *  *********************************************************************************/


/* Fill-in your Template ID (only if using Blynk.Cloud) */

#define BLYNK_TEMPLATE_ID "TMPL3I0Sv898t"
#define BLYNK_TEMPLATE_NAME "WATER LEVEL MONITER"

#define BLYNK_AUTH_TOKEN "_C5qtqNL6lsNBCMPTrbGCSHDXE7Kc2CJ"


#include <DHT.h>

#define BLYNK_PRINT Serial
#include <WiFi.h>
#include <WiFiClient.h>
#include <BlynkSimpleEsp32.h>

#define trig 27   // Trig pin
#define echo 26   // Echo Pin 
// Comment this out to disable prints and save space

char ssid[] = "";  // type your wifi name
char pass[] = "";  // type your wifi password
int tankdepth =100 ;   // Change 1 according to your tank depth


BlynkTimer timer;


char auth[] = BLYNK_AUTH_TOKEN;
#define DHTPIN 14 //Connect Out pin to D2 in NODE MCU
#define DHTTYPE DHT11  
DHT dht(DHTPIN, DHTTYPE);
void sendSensor()
{
  float h = dht.readHumidity();
  float t = dht.readTemperature(); // or dht.readTemperature(true) for Fahrenheit

  if (isnan(h) || isnan(t)) {
    Serial.println("Failed to read from DHT sensor!");
    return;
  }
  // You can send any value at any time.
  // Please don't send more that 10 values per second.
    Blynk.virtualWrite(V4, t);
    Blynk.virtualWrite(V5, h);
    Serial.print("Temperature : ");
    Serial.print(t);
    Serial.print("    Humidity : ");
    Serial.println(h);
}
void PGM()
{
  digitalWrite(trig, LOW);
  delayMicroseconds(2);
  digitalWrite(trig, HIGH);
  delayMicroseconds(10);
  digitalWrite(trig, LOW);
  long t = pulseIn(echo, HIGH);
  long cm = t / 29 / 2;
  Serial.println(cm);
  long level= tankdepth-cm;
  if (level<0)
  level=0;
  level = map(level,0,tankdepth-3,0,100);
  Blynk.virtualWrite(V1, level);
  Blynk.virtualWrite(V2,"Tank Water LeveL");
  Blynk.virtualWrite(V3,"     in %");

  
}

 
void setup()
{
  pinMode(trig, OUTPUT);
  pinMode(echo, INPUT);
  Serial.begin(115200);
  Blynk.begin(auth, ssid, pass);
  dht.begin();
  timer.setInterval(10L, PGM);
  timer.setInterval(100L,sendSensor);
  pinMode(2,OUTPUT);
  digitalWrite(2,HIGH);
  
}

void loop()
{
 
  Blynk.run();
  timer.run();
  }
