# Función RPA  
**Nombre de la función:** Función de generación de reporte de ejecución – GF_NotificationBots  
**Objetivo de la función:** Enviar correos automatizados al inicio, final o ante errores de ejecución de un bot RPA, usando plantillas HTML dinámicas y parámetros del proceso.  
**Desarrollado por:** Synthetics Solutions  
**Fecha de creación:** Marzo 2024  

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

## 1 Introducción  
En el marco de la automatización de procesos empresariales y la necesidad creciente de garantizar trazabilidad operativa y comunicación oportuna, surge la importancia de notificar los eventos relevantes durante la ejecución de bots RPA. La función GF_NotificationBots fue diseñada con el propósito de centralizar y automatizar el envío de notificaciones estructuradas por correo electrónico, consolidando información clave como el inicio, finalización, errores o alertas del proceso. Esta función aporta valor al permitir el monitoreo en tiempo real, la auditoría externa y la respuesta temprana ante incidentes, asegurando transparencia, control y continuidad operativa en cada ciclo de ejecución.  

## 2 Objetivos  
### a. Objetivo General  
- Automatizar el envío estructurado de notificaciones por correo electrónico durante la ejecución de bots RPA, consolidando información clave para la trazabilidad operativa y la atención oportuna de eventos.  

### b. Objetivos Específicos  
- Notificar de manera automática el inicio, finalización y errores durante la ejecución del bot.  
- Estandarizar el formato y contenido de los correos enviados por todos los bots del CoE RPA.  
- Facilitar el monitoreo en tiempo real de los procesos automatizados.  
- Incluir información relevante del proceso como tiempo de ejecución, estado, errores y observaciones.  
- Reutilizar la función en múltiples bots sin necesidad de modificaciones estructurales.  

## 3 Alcance  
La función GF_NotificationBots aplica a bots desarrollados en plataformas como Automation Anywhere 360 y Rocketbot, integrándose en distintas etapas del flujo de ejecución (inicio, error o finalización). Su alcance comprende la validación de variables clave, la construcción dinámica del cuerpo del mensaje, el uso de plantillas predefinidas y el envío automatizado de correos electrónicos con la información de ejecución. Esta función garantiza una comunicación uniforme, oportuna y estructurada en todos los procesos automatizados, facilitando el monitoreo, la trazabilidad y la gestión proactiva de eventos.  

## 4 Arquitectura de contexto  
### a. Contexto general  
- La función GF_NotificationBots se enmarca en la necesidad de establecer un mecanismo confiable y reutilizable para enviar notificaciones estructuradas por correo electrónico durante la ejecución de bots RPA. Su propósito es facilitar la trazabilidad, el monitoreo operativo y la respuesta oportuna ante eventos relevantes, centralizando la lógica de notificación en un único componente funcional.  

### b. Componentes principales  
- Plataforma RPA  
  - Automation Anywhere / Rocketbot: plataformas donde se integra y ejecuta la función.  
  - Control Room / Workspace: orquestan la ejecución del bot que contiene la función.  
  - Bot Creator (Desarrollo): entorno donde se desarrolla y actualiza la lógica de generación del reporte.  
  - Bot Runner: instancia donde se ejecuta la función junto al flujo principal del bot.  
- Fuente de datos  
  - Diccionario de variables: contiene la información necesaria para armar el mensaje.  
  - Plantillas HTML / texto plano: utilizadas como base para estructurar el contenido del correo.  
- Parámetros de entrada  
  - Nombre del bot o proceso  
  - Estado de ejecución (Inicio, Finalización, Error)  
  - Duración total  
  - Observaciones, mensajes de error o comentarios adicionales  
  - Lista de destinatarios y copia  
- Canal de salida  
  - Cliente SMTP o servidor de correo integrado  
  - Entrega de notificaciones vía correo electrónico a destinatarios definidos.  
- Manejo de errores y trazabilidad  
  - Captura de errores en el envío del correo o en la construcción del mensaje  
  - Registro de intentos fallidos y errores en archivo log o base de datos  
  - Validación de campos obligatorios antes del envío  

## 5 Diagrama de despliegue  
Representa la infraestructura lógica en la que se ejecuta la función GF_NotificationBots, mostrando los componentes involucrados y sus interacciones dentro del ecosistema RPA.  
Componentes clave:  
- Bot principal (Main)  
- Función RPA  
- Parámetros de entrada  
- Máquina virtual (Runner)  
- Servidor SMTP / Cliente de correo  

## 6 Diagrama de componentes  
Este diagrama representa la estructura interna de la función GF_NotificationBots, dividida en pasos secuenciales que encapsulan la lógica del proceso de notificación y registro de ejecución.  
| Nombre componente           | Tipo              |  
|----------------------------|-------------------|  
| STEP 00 – Validación de parámetros | Script / Validación |  
| STEP 01 – Construcción del mensaje | Script / Procesamiento |  
| STEP 02 – Aplicación de plantilla   | Script / Formateo    |  
| STEP 03 – Envío del correo          | Script / Comunicación |  
| STEP 04 – Retorno de estado         | Script / Finalización |  

## 7 Tecnologías utilizadas  
- Automation Anywhere 360  
- Rocketbot  
- SQL Server  

## 8 Flujo del proceso  
- Lectura de parámetros desde el diccionario de variables  
- Validación de campos requeridos para la notificación (destinatarios, asunto, mensaje)  
- Construcción del cuerpo del mensaje con base en la plantilla HTML  
- Aplicación de formato y reemplazo dinámico de campos  
- Envío del correo electrónico vía servidor SMTP o cliente de correo  
- Registro de resultado y retorno al flujo principal del bot  

## 9 Resultados obtenidos  
- Automatización del envío de notificaciones por correo al finalizar la ejecución de bots RPA.  
- Estandarización de los mensajes de notificación, utilizando una plantilla HTML reutilizable.  
- Reducción del trabajo manual en la generación y redacción de correos informativos.  
- Mayor trazabilidad y visibilidad operativa, al informar automáticamente el estado y los resultados del bot.  
- Mejora en la comunicación entre áreas, al garantizar que los stakeholders reciban reportes consistentes y oportunos.  

## 10 Confidencialidad  
Este documento no contiene información confidencial. Su propósito es mostrar la experiencia de Synthetics Solutions.  

## 11 Contacto  
- Correo: Synthetic.solutions5@gmail.com  
