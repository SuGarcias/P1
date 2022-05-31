
#### Oriol Garcia Vila
# INFORME PRÀCTICA 1: BLINK
___ 
### Part 1:

1. Codi utilitzat:
~~~cpp 
#include <Arduino.h>

#define LED 16

void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
pinMode(LED,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
  digitalWrite(LED,HIGH);
  Serial.println("PUT ON");
  delay(1000);
  Serial.println("PUT OFF");
  digitalWrite(LED,LOW);
  delay(1000);
} 
~~~

  2. Diagrama de flux:
```mermaid
sequenceDiagram
Programa ->> Programa: Repetir
  Programa -->> ESP32: Encender Led;
    ESP32->>Puerto serie:"Put ON"
      note right of Puerto serie: Put ON;
  Programa-> ESP32: Espera 500 ms;
  Programa-->> ESP32: Apagar Led;
    ESP32->>Puerto serie:"Put OFF"
      note right of Puerto serie: Put OFF;
  Programa-> ESP32: Espera 500 ms; 
  Programa ->> Programa: Repetir
```


3. Diagram de Tiempos:

![](time_diagram1.png) 

> Imágen del osciloscopio, ON, 500ms, OFF


### Temps lliure del procesador:
- El temps lliure del porcessador és el delay de 500 ms entre el LED ON i LED OFF






