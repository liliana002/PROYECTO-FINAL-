# PROYECTO-FINAL-
## 1.SISTEMA DE DOMOTICA HOSPITALARIA: PREVENCION DE CAIDAS Y MONITOREO CONTINUO.
Este proyecto es un prototipo de sistema de domótica hospitalaria, el sistema monitorea variables ambientales y de seguridad en una habitación de paciente hospitalario, utilizando un ESP32 con MicroPython, donde Incluye sensores para temperatura/humedad (DHT22), peso/caídas (HX711), luz (LDR), proximidad (HC-SR04) y botón de pánico, actuadores incluyen ventilador, luz, servo para puerta y buzzer para alertas, el control se realiza vía bot de Telegram y una API web local.
El sistema alerta en tiempo real sobre condiciones críticas como la temperatura alta, caídas, y permite configuración remota.

### 2. CONDICIONES
- ESP32 con Wifi activado 
- Microphyton instalado en el ESP32.
- Librerias machines, network, time, etc.
- conexion wifi, configuracion de SSID Y PASWORD (boot.py)

### 3. COMO CORRERLO
3.1 INSTALACION EN ESP32
- Se conecta el ESP32 al pc via USB.
- Instalamos Thonny el cual nos permitira subir los archivos al ESP32.
- Verificar que el Wifi este configurado en boot.py

##3.2 EJECUTAR
- Reinicia el ESP32 o ejecuta manualmente el archivo main.py desde Thonny
- Verifica la conexión observando la consola serial donde se mostrará la Dirección IP asignada.
- Una vez conectado, accede a la interfaz web en: "http://[IP_DEL_ESP32]:8080"
- Endpoints disponibles, consultar main.py para lista como 
/estado (Estado general del sistema)  /sensores (Lecturas de sensores en tiempo real).
- En Telegram, inicia el bot con `/start` para autorizarte y ver comandos como /ingresar (acceso al sistema), /estado (consultar estado actaul), /set temp_max28 (configurar temperatura maxima).

##3.3 PRUEBAS INCIALES 
- Verifica conexión WiFi en consola.
- Envía comandos vía Telegram y observa alertas.
- Simula sensores, presiona botón de pánico y verifica actuadores como el boton de panico.

- ## 4. ESTRUCTURA
- `main.py`: Script principal que integra todos los modulos del sistema.
- `config_sistema.py`: Configuración central, umbrales, Telegram.
- `boot.py`: inicia automaticamente el wifi y servicios.
  
- Sensores: `sensor_dht.py`: Sensor de temperatura y humedad
- `sensor_hx711.py`: Sensor de peso.
- `sensor_ldr.py`: Sensor de luz ambiental.
- `sensor_proximidad.py`: Sensor de presencia
- `boton_panico.py`: Botón de emergencia
  
- Actuadores: `actuador_luz.py`: Control de iluminación.
- `actuador_puerta.py`: Control de apertura/cierre de puerta.
- `buzzer.py`: Control de alarma sonora.
- 
- Comunicaicon : `bot_telegram.py`: bot completo de telegram.
-  `boot.py`: wifi



  









