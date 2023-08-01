## CONFIGURACION
- Tener configurado Arduino IDE.
- Contar con el sensor DHT11.
- Tener la configuración de conexión entre la ESP32CAM y la computadora (con el sensor FTDI).
- Tener activados los contenedores de mqtt.

## PASOS
- Clonar el código del repositorio de GitHub para la aplicación del sensor DHT11, el link es: https://github.com/codigo-iot/esp32cam-mqtt-json-no-bloqueante/tree/main
- Colocar los datos de tu red de internet (ssid = nombre de la red; Password = contraseña de la red).
- Colocar el nombre de la ip del servidor mqtt (puede encontrarse con el comando "$ ifconfig", en la sección enp0s3.
- Cargar el código a la ESP32CAM.
- Ver el funcionamiento del sensor de temperatura y humedad.
- Acceder, mediante la terminal, a la base de datos de la siguiente forma:

---
### MQTT
##### Instalación local
- $ mosquitto_sub -h localhost -t codigoIoT/esp32/dht

#### Docker Compose
- $ docker exec -it id_contenedor mosquitto_sub -h localhost -t codigoIoT/esp32/dht

---
### Confirmación de conexión
#### Instalación local
- $ mosquitto_sub -h localhost -t codigoIoT/esp32/msg

#### Docker Compose
- $ docker exec -it id_contenedor mosquitto_sub -h localhost -t codigoIoT/esp32/msg

---
De este modo ahora es posible ver los datos obtenidos por el sensor mediante la ip del server mqtt a través de la terminal.
