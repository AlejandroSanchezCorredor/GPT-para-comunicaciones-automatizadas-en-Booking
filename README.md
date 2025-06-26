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

### 🛠Tecnologías Usadas

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
* ⚙**API Serverless**: Conexión entre el frontend, el backend y los modelos.
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
* Automatización efectiva de más del **90% de las consultas simuladas**.
* Infraestructura serverless desplegada correctamente en entorno AWS.
* Reducción estimada de tiempo de gestión en un **70%** para escenarios con múltiples propiedades.

---

### Conclusiones y Futuras Mejoras

* Se comprobó que los modelos GPT son muy útiles en la automatización de atención al cliente.
* La arquitectura serverless permite escalar fácilmente sin costes fijos elevados.
* Próximas mejoras:

  * Integración con la API oficial de Booking (si es accesible)
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
📦 booking-gpt-bot
├── src/
│   ├── scraping/
│   ├── api/
│   ├── prompts/
│   └── model/
├── serverless.yml
├── .env
└── README.md
```
