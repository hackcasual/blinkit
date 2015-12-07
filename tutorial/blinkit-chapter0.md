# Bling Development Kit

## The Basics

### Getting Started

#### Install Arduino
#### Install Teensyduino
#### Install BDK
#### Configure the board

### Blink
We need to start somewhere, let's blink an LED!

```c++
#define LED_PIN 13

void setup()
{
  pinMode(LED_PIN, OUTPUT);
}

void loop()
{
  digitalWrite(LED_PIN, 1);
  delay(500);
  digitalWrite(LED_PIN, 0);
  delay(500);
}
```
###### Your first sketch (blink.ino)

### Hello World

```c++
void setup()
{
  Serial.begin(9600);
}

void loop()
{
  Serial.println("Hello world!");
  delay(1000);
}
```
###### Hello sketch (serialhello.ino)

#### Debugging
Use the serial printing to find out when the *secret* value equals 0xDEADBEEF

```c++
void setup()
{
  Serial.begin(9600);
  // Wait for the computer to connect
  delay(10000);

  int secret = 0x230D9557;

  // How many iterations until secret equals 0xDEADBEEF?
  for (int i = 0; i < 1000000; i++) {
    secret *= 1337;
  }
}

void loop()
{

}
```
