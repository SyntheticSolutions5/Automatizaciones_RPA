# Función RPA  
**Nombre de la función:** Función de generación de reporte de ejecución – GF_APIUtils  
**Objetivo de la función:** Automatizar el consumo de servicios web (APIs REST o SOAP) desde flujos RPA, permitiendo la integración con sistemas externos mediante solicitudes HTTP estructuradas (GET, POST, PUT, DELETE), el manejo de autenticaciones, y el procesamiento de respuestas para ser utilizadas en procesos automatizados.  
**Desarrollado por:** Synthetics Solutions  
**Fecha de creación:** Julio 2024  

---

## Contenido  
1. Introducción  
2. Objetivos  
3. Alcance  
4. Arquitectura de contexto  
5. Diagrama de despliegue  
6. Diagrama de componentes  
7. Tecnologías utilizadas  
8. Flujo del proceso  
9. Resultados obtenidos  
10. Confidencialidad  
11. Contacto  

---

## 1. Introducción  
En el contexto de la automatización de procesos empresariales, es cada vez más común la necesidad de integrar bots RPA con sistemas externos mediante servicios web. La función GF_APIUtils surge como una solución reutilizable para consumir APIs REST o SOAP desde flujos automatizados, permitiendo enviar y recibir datos estructurados mediante solicitudes HTTP. Esta función permite centralizar la lógica de conexión, autenticación, envío de parámetros y manejo de respuestas, facilitando la interoperabilidad entre sistemas, mejorando la eficiencia operativa y asegurando la estandarización de las integraciones API dentro del ecosistema RPA.  

## 2. Objetivos  
**Objetivo General:**  
- Automatizar el consumo de servicios API (REST o SOAP) desde flujos RPA, permitiendo la integración dinámica con sistemas externos mediante solicitudes HTTP estructuradas, autenticación segura y manejo estandarizado de respuestas.  

**Objetivos Específicos:**  
- Realizar solicitudes GET, POST, PUT o DELETE según el tipo de operación requerida.  
- Soportar autenticación mediante tokens, API keys o credenciales básicas.  
- Enviar y recibir datos en formatos estructurados como JSON o XML.  
- Centralizar la lógica de consumo API en una función reutilizable y parametrizable.  
- Registrar resultados, errores y tiempos de respuesta para trazabilidad y monitoreo.  

## 3. Alcance  
La función GF_APIUtils aplica a bots desarrollados en plataformas como Automation Anywhere 360 y Rocketbot, integrándose en etapas donde se requiere interactuar con servicios externos mediante API REST o SOAP. Su alcance abarca la configuración de solicitudes HTTP (GET, POST, PUT, DELETE), el manejo de autenticación (API keys, tokens, credenciales), el envío y recepción de datos en formatos como JSON o XML, y el procesamiento automatizado de las respuestas. Esta función puede ser reutilizada en múltiples procesos automatizados que requieran integración con sistemas externos, garantizando conectividad estandarizada, trazabilidad y eficiencia operativa.  

## 4. Arquitectura de contexto  
### a. Contexto general  
La función GF_APIUtils se enmarca en la necesidad de establecer un componente confiable y reutilizable para el consumo automatizado de APIs dentro de flujos RPA. Su propósito es permitir la integración con sistemas externos mediante solicitudes HTTP estructuradas, facilitando el intercambio de información, la consulta de servicios y el envío de datos sin intervención manual. Al centralizar esta lógica en una única función, se mejora la escalabilidad, se reduce la duplicidad de código y se estandariza la forma en que los bots interactúan con APIs.  

### b. Componentes principales  
- **Plataforma RPA:**  
  - Automation Anywhere / Rocketbot: plataformas donde se integra y ejecuta la función.  
  - Control Room / Workspace: orquestan la ejecución del bot que contiene la función.  
  - Bot Creator (Desarrollo): entorno donde se desarrolla y actualiza la lógica de generación del reporte.  
  - Bot Runner: instancia donde se ejecuta la función junto al flujo principal del bot.  

- **Fuente de datos:**  
  - APIs REST/SOAP: servicios externos que exponen endpoints para operaciones específicas.  
  - Cuerpo de la solicitud (Payload): datos enviados en formato JSON, XML, o texto plano.  

- **Parámetros de entrada:**  
  - URL del endpoint  
  - Método HTTP (GET, POST, PUT, DELETE)  
  - Cabeceras (Headers)  
  - Cuerpo del mensaje (si aplica)  
  - Tipo de autenticación (Bearer Token, API Key, Basic Auth, etc.)  

- **Resultado de salida:**  
  - Respuesta de la API (JSON, XML, texto, etc.)  
  - Código de estado HTTP (200, 400, 500, etc.)  
  - Datos extraídos o transformados para su uso en el flujo RPA.  

- **Manejo de errores y trazabilidad:**  
  - Validación de respuesta y código HTTP  
  - Gestión de reintentos ante fallos temporales (timeout, red, etc.)  
  - Registro de errores y respuestas en log centralizado para auditoría  
  - Control de excepciones por formato inválido, credenciales incorrectas o endpoint no disponible.  

## 5. Diagrama de despliegue  
Representa la infraestructura lógica en la que se ejecuta la función GF_APIUtils, mostrando los componentes involucrados y sus interacciones dentro del ecosistema RPA. Esta función se integra en flujos automatizados que requieren consumir servicios web externos (APIs), permitiendo el intercambio de datos entre plataformas.  

**Componentes clave:**  
- Bot principal (Main)  
- Función RPA  
- Parámetros de entrada  
- Máquina virtual (Runner)  
- Servidor o Servicio API externo (REST/SOAP)  
- Servidor de archivos / Base de datos  

## 6. Diagrama de componentes  
Este diagrama representa la estructura interna de la función GF_APIUtils, dividida en pasos secuenciales que encapsulan la lógica de consumo de servicios API. Cada paso está organizado en scripts modulares para garantizar validación, ejecución segura y trazabilidad del proceso.  

| Nombre componente           | Tipo          |  
|----------------------------|---------------|  
| STEP 00 – Validación de parámetros  | Script / Validación |  
| STEP 01 – Construcción de solicitud HTTP | Script / Preparación |  
| STEP 02 – Envío de solicitud al API | Script / Comunicación |  
| STEP 03 – Procesamiento de la respuesta | Script / Análisis |  
| STEP 04 – Gestión de errores y reintentos | Script / Control |  
| STEP 05 – Retorno y logging | Script / Finalización |  

## 7. Tecnologías utilizadas  
- Automation Anywhere 360  
- Rocketbot  
- SQL Server  

## 8. Flujo del proceso  
- Lectura de parámetros desde el diccionario de variables (endpoint, método, headers, body, etc.).  
- Validación de parámetros obligatorios y formato de solicitud.  
- Construcción del cuerpo de la solicitud HTTP (GET, POST, PUT, DELETE).  
- Envío de la solicitud al servicio API utilizando cliente HTTP o librerías RPA.  
- Recepción y análisis de la respuesta del API (JSON, XML, etc.).  
- Manejo de errores, códigos de estado y reintentos automáticos (si aplica).  
- Devolución de los datos al bot en formato estructurado para su uso posterior.  
- Registro de eventos y resultados en logs para trazabilidad del consumo.  

## 9. Resultados obtenidos  
- Automatización del consumo de servicios API desde bots RPA, integrando datos externos de forma estructurada.  
- Reducción de errores humanos mediante la centralización de la lógica de conexión, autenticación y manejo de respuestas.  
- Interoperabilidad entre sistemas, facilitando la integración con aplicaciones internas o servicios de terceros.  
- Mejora en la trazabilidad operativa gracias al registro detallado de solicitudes, respuestas y errores.  
- Reutilización flexible de la función en múltiples bots, adaptándola fácilmente a diferentes endpoints o métodos.  

## 10. Confidencialidad  
Este documento no contiene información confidencial. Su propósito es mostrar la experiencia de Synthetics Solutions.  

## 11. Contacto  
- Correo: Synthetic.solutions5@gmail.com  
