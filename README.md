# Sistema Inteligente de Productividad e IoT con ESP32

## Descripción

Este proyecto es una aplicación IoT enfocada en productividad, bienestar y automatización de pausas activas utilizando una ESP32, sensores ambientales y una aplicación web desarrollada en Flask.

El sistema permite monitorear variables del entorno, gestionar sesiones Pomodoro y mostrar recomendaciones inteligentes tanto en una interfaz web como en una pantalla TFT conectada a la ESP32.

La aplicación está dividida en dos partes principales:

* **Backend en Flask** encargado de la lógica del sistema, API REST y gestión del asistente.
* **Firmware para ESP32** encargado de la lectura de sensores, comunicación con el servidor y visualización en pantalla.

---

# Características Principales

## Backend Flask

* API REST para comunicación con la ESP32.
* Gestión de estados del entorno.
* Sistema Pomodoro:

  * Iniciar sesión
  * Pausar
  * Reanudar
  * Finalizar
  * Saltar fases
* Interfaz web responsive.
* Generación de recomendaciones y pausas activas.
* Manejo y limpieza inteligente de texto para pantallas LCD/TFT.
* Integración modular mediante Blueprints.

## ESP32

* Conexión WiFi.
* Comunicación HTTP con Flask.
* Lectura de sensores.
* Visualización de información en pantalla TFT.
* Manejo de actuadores.
* Actualización de estado en tiempo real.

---

# Arquitectura del Proyecto

```text
nuevocodigo/
│
├── backend/
│   ├── app.py
│   ├── requirements.txt
│   ├── routes/
│   ├── services/
│   ├── static/
│   ├── templates/
│   └── utils/
│
├── ESP32/
│   └── thecode/
│       ├── thecode.ino
│       ├── sensores.cpp
│       ├── pantalla.cpp
│       ├── actuadores.cpp
│       ├── flask_client.cpp
│       └── config.h
│
└── .venv/
```

---

# Tecnologías Utilizadas

## Backend

* Python
* Flask
* HTML5
* CSS3
* JavaScript

## Hardware

* ESP32
* Pantalla TFT LCD
* Sensores ambientales

---

# Funcionamiento General

1. La ESP32 se conecta a la red WiFi.
2. Los sensores capturan información del entorno.
3. La ESP32 envía datos al servidor Flask mediante HTTP.
4. Flask procesa la información.
5. El sistema genera estados y recomendaciones.
6. La interfaz web y la pantalla TFT muestran la información.
7. El usuario puede controlar sesiones Pomodoro desde la aplicación.

---

# Instalación del Backend

## 1. Clonar el repositorio

```bash
git clone <URL_DEL_REPOSITORIO>
cd nuevocodigo/backend
```

## 2. Crear entorno virtual

```bash
python -m venv venv
```

## 3. Activar entorno virtual

### Windows

```bash
venv\Scripts\activate
```

### Linux / Mac

```bash
source venv/bin/activate
```

## 4. Instalar dependencias

```bash
pip install -r requirements.txt
```

## 5. Ejecutar servidor

```bash
python app.py
```

Servidor disponible en:

```text
http://localhost:5000
```

---

# Configuración ESP32

## Requisitos

* Arduino IDE
* Librerías necesarias instaladas
* Drivers de la ESP32

## Configuración básica

Editar el archivo:

```text
ESP32/thecode/config.h
```

Configurar:

* SSID WiFi
* Contraseña WiFi
* Dirección IP del servidor Flask

---

# API REST

## Prefijo principal

```text
/api
```

## Ejemplos de endpoints

| Método | Endpoint                | Descripción           |
| ------ | ----------------------- | --------------------- |
| GET    | /api/status             | Estado del sistema    |
| POST   | /api/iot/registro       | Registro de datos IoT |
| POST   | /api/pomodoro/iniciar   | Iniciar Pomodoro      |
| POST   | /api/pomodoro/pausar    | Pausar Pomodoro       |
| POST   | /api/pomodoro/reanudar  | Reanudar Pomodoro     |
| POST   | /api/pomodoro/finalizar | Finalizar Pomodoro    |

---

# Interfaz Web

La interfaz web se encuentra en:

```text
backend/templates/index.html
```

Los archivos estáticos están organizados en:

```text
backend/static/
```

Incluye:

* Panel de estado
* Temporizador Pomodoro
* Recomendaciones
* Actualización dinámica

---

# Módulos Importantes

## Backend

### app.py

Punto de entrada principal del servidor Flask.

### routes/api.py

Contiene todos los endpoints de la API.

### services/

Lógica principal del sistema:

* Estado del entorno
* Asistente inteligente
* Sistema Pomodoro

## ESP32

### sensores.cpp

Lectura de sensores.

### pantalla.cpp

Control de pantalla TFT.

### actuadores.cpp

Manejo de actuadores.

### flask_client.cpp

Comunicación con el servidor Flask.

---

# Objetivo del Proyecto

El objetivo principal es crear un sistema inteligente de productividad que ayude al usuario a:

* Mejorar concentración
* Gestionar tiempos de trabajo
* Realizar pausas activas
* Monitorear condiciones ambientales
* Integrar hardware y software en tiempo real

---

# Posibles Mejoras Futuras

* Integración con base de datos
* Sistema de autenticación
* Dashboard avanzado
* Notificaciones móviles
* Machine Learning para recomendaciones
* Control remoto desde aplicación móvil
* Estadísticas de productividad


---

# Licencia

Este proyecto puede utilizarse con fines académicos y educativos.
