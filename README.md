## GPT para Comunicaciones Automatizadas en Booking

Este proyecto consiste en el desarrollo de un sistema inteligente que automatiza las respuestas a clientes en plataformas como Booking.com utilizando modelos de lenguaje como **GPT-3** y **GPT-4**, con una arquitectura escalable y moderna basada en servicios serverless de **AWS**.

---

### Tabla de Contenidos

* [Motivación](#motivación)
* [Objetivos](#objetivos)
* [Tecnologías Usadas](#tecnologías-usadas)
* [Arquitectura](#arquitectura)
* [Componentes del Proyecto](#componentes-del-proyecto)
* [Pruebas Realizadas](#pruebas-realizadas)
* [Resultados](#resultados)
* [Conclusiones y Futuras Mejoras](#conclusiones-y-futuras-mejoras)

---

### Motivación

La gestión manual de las comunicaciones en Booking puede ser ineficiente y propensa a errores, especialmente para propietarios con muchas propiedades. Este proyecto busca **automatizar las respuestas a los clientes**, utilizando procesamiento de lenguaje natural para mejorar la experiencia del usuario y ahorrar tiempo a los propietarios.

---

### Objetivos

* Automatizar las respuestas a consultas frecuentes de clientes en Booking.
* Integrar modelos GPT para generar respuestas coherentes y personalizadas.
* Diseñar una arquitectura serverless escalable en AWS.
* Simular datos y escenarios reales para entrenamiento y pruebas.

---

### Tecnologías Usadas

* **Lenguaje y Frameworks**: Python, Node.js, Serverless Framework
* **Machine Learning**: GPT-3 y GPT-4 (OpenAI API)
* **Web Scraping**: Selenium
* **AWS Services**:

  * Lambda
  * DynamoDB
  * API Gateway
  * Cognito
  * SES (Simple Email Service)
  * S3 y ECR
* **Otros**: Docker, Faker (simulación de datos), Git

---

### Arquitectura

El sistema se despliega sobre una infraestructura completamente **serverless**:

* Las funciones Lambda ejecutan tareas como obtención de datos y generación de respuestas.
* DynamoDB almacena propiedades, reservas y conversaciones.
* API Gateway expone las funciones a través de endpoints REST.
* La API de OpenAI se consulta para generar las respuestas inteligentes.
* Interfaz simulada para representar el flujo conversacional con clientes.

![image](https://github.com/user-attachments/assets/98b447aa-3088-47f7-baeb-a88c48b92ef0)

---

### Componentes del Proyecto

* **Scraping de Booking**: Automatización para recolectar datos simulados de propiedades, reservas, etc.
* **Módulo GPT**: Manejo de prompts y respuestas personalizadas con GPT-4.
* **API Serverless**: Conexión entre el frontend, el backend y los modelos.
* **Base de datos NoSQL (DynamoDB)**: Estructura para almacenar información de usuarios, reservas y propiedades.
* **Frontend de prueba**: Interfaz para simular conversaciones y ver el modelo en acción.

---

### Pruebas Realizadas

Se realizaron múltiples pruebas con distintos enfoques de prompt y escenarios:

1. Respuesta a nuevas reservas
2. Respuesta a dudas sobre una propiedad
3. Reenvío de información de contacto
4. Preguntas de cancelación o reembolso

Cada prueba fue evaluada por claridad, coherencia y relevancia del modelo.

---

### Resultados

* Se alcanzó una calidad conversacional alta en las respuestas del modelo GPT.
* Infraestructura serverless desplegada correctamente en entorno AWS.
  
---

### Conclusiones y Futuras Mejoras

* Se comprobó que los modelos GPT son muy útiles en la automatización de atención al cliente.
* La arquitectura serverless permite escalar fácilmente sin costes fijos elevados.
* Próximas mejoras:

  * Integración con la API oficial de Booking (si es accesible en el futuro)
  * Añadir procesamiento multilenguaje real
  * Panel de control para propietarios

---

### Requisitos para Ejecutar

```bash
npm install
serverless deploy
```

Configura tus credenciales AWS y claves de la API de OpenAI en `.env`.

---

### Estructura del Repositorio

```bash
GPT-para-comunicaciones-automatizadas-en-Booking/
├── application/                # Backend principal: lógica de negocio, controladores y servicios
│   ├── controllers/            # Encapsula la lógica de rutas (endpoints)
│   ├── core/                   # Configuraciones centrales de la app
│   ├── functions/              # Funciones principales, incluidas las llamadas a GPT
│   ├── models/                 # Modelos de datos (ORM o estructuras para DynamoDB)
│   ├── services/               # Servicios auxiliares (p. ej., conexión con OpenAI, email, etc.)
│   └── configuration.py        # Parámetros de configuración general de la aplicación
│   └── handler.py              # Entrada principal del backend (Lambda handler)
│   └── __init__.py             # Inicialización del módulo Python
│
├── frontend/                  # Interfaz de usuario (Angular)
│   ├── src/                    # Código fuente de la aplicación frontend
│   ├── public/                 # Recursos estáticos
│   └── README.md               # Instrucciones del frontend
│
├── serverless_resources/       # Definición de recursos en AWS vía archivos YAML
│   ├── aws_s3.yml              # Configuración del bucket S3
│   ├── aws_cognito.yml         # Gestión de autenticación
│   ├── dynamodb.yml            # Definición de tablas NoSQL
│   ├── aws_route53.yml         # DNS para la app
│   ├── aws_acm_certificates.yml# Certificados SSL
│   ├── aws_cloudfront.yml      # Distribución CDN de CloudFront
│   └── app_security.yml        # Políticas y seguridad
│
├── Dockerfile.api              # Contenedor para el backend
├── Dockerfile.scheduler        # Contenedor para tareas programadas
├── Dockerfile.test             # Contenedor para pruebas del modelo GPT
│
├── serverless.yml              # Archivo principal para despliegue con Serverless Framework
├── requirements.txt            # Dependencias de Python para el backend
├── package.json                # Dependencias del frontend
├── README.md                   # Documentación general del proyecto

```
---

### Descripción de Carpetas

* **`application/`**: Contiene toda la lógica del backend, incluida la interacción con OpenAI, manejo de datos y configuración del entorno.
* **`frontend/`**: Proyecto Angular que permite simular la experiencia de un usuario en Booking conversando con un chatbot basado en GPT.
* **`serverless_resources/`**: Infraestructura como código (IaC), donde se definen recursos específicos de AWS como S3, DynamoDB, Cognito, etc., para un despliegue automatizado.
* **`Dockerfile.*`**: Imágenes personalizadas para cada parte del sistema. Esto permite entornos aislados para pruebas, API y procesos programados.
* **`serverless.yml`**: Define funciones Lambda, eventos, permisos y recursos para desplegar tu arquitectura sin servidor usando el Serverless Framework.

---


