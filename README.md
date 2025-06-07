# Practica-ESP32-con-DHT11

En este repositorio se mostrara como programar un ESP32 con un sensor DHT11, con el cual obtendremos las magnitudes de temperatura y humedad.

## Introducción 

La placa ESP32 la empleamos para adquirir los datos provenientes del DHT11 (temperatura y humedad en porcentaje) respecto al entorno. 

Esta practica se realizo empleando un simulador: [WOKWI](www.wokwi.com) la cual nos permite simular los elementos y el codigo.

#Material necesario

Para realizar esta practica se necesito
- [WOKWI](www.wokwi.com)
- Una tarjeta ESP32 (para adquisicion de datos)
- Sensor DHT11 (para recolectar los datos del entorno)

#Instrucciones
1. Abrir la terminal del codigo:

```
#include "DHTesp.h"

const int DHT_PIN = 15;
DHTesp dhtSensor;


void setup() {

  Serial.begin(115200);
  dhtSensor.setup(DHT_PIN, DHTesp::DHT22);
}

void loop() {

  TempAndHumidity  data = dhtSensor.getTempAndHumidity();
  Serial.println("Temp: " + String(data.temperature, 1) + "°C");
  Serial.println("Humidity: " + String(data.humidity, 1) + "%");
  Serial.println("---");
  delay(1000);
}
```
2. Instalar la libreria de DHT senson library for ESPx, en la siguiente imagen se muestra la libreria seleccionada.

![](https://github.com/HV202506/Practica-ESP32-con-DHT11/blob/main/DHT%20sensor%20library%20for%20ESPx.png?raw=true)


3. Hacer las concexiones del DHT11 con el ESP32 tal cual se muestra la siguiente imagen.

![](https://github.com/HV202506/Practica-ESP32-con-DHT11/blob/main/Elementos%20ESP32%20y%20DHT11.png?raw=true))

#Intrucciones de operación
1. Iniciar la simulación.
2. Observar los datos del monitor serial.
3. Colorar la temperatura y humedad dando doble click en el sensor DHT11 (temperatura y humedad).

#Resultados

Una vez realizados los pasos anteriores deberas visualizar la temperatura y la humedad del entorno tal como se muestra en la siguiente imagen. 

![](https://github.com/user-attachments/assets/eb7bd133-741a-45b8-b340-1e4558ba4116)


#Créditos
Desarrollado por Ing. Héctor Angel Vega Rodríguez
