# Función RPA  
**Nombre de la función:** Función de generación de reporte de ejecución – GF_DownloadEmailAttachments  
**Objetivo de la función:** Automatizar la descarga de archivos adjuntos desde correos electrónicos entrantes, según filtros configurables como remitente, asunto, fecha o tipo de archivo, permitiendo su integración en flujos RPA que requieren procesamiento posterior de documentos.  
**Desarrollado por:** Synthetics Solutions  
**Fecha de creación:** Diciembre 2023  

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
En el marco de la automatización de procesos empresariales, muchas tareas requieren la recepción y procesamiento de información enviada por correo electrónico. La función GF_DownloadEmailAttachments fue diseñada como un componente reutilizable para automatizar la descarga de archivos adjuntos desde cuentas de correo, aplicando filtros como remitente, asunto, tipo de archivo o fecha. Esta funcionalidad es esencial en flujos RPA donde los datos llegan por email y deben integrarse automáticamente al proceso sin intervención manual. Al centralizar esta lógica en una función estándar, se optimiza la eficiencia operativa, se mejora la trazabilidad documental y se asegura la disponibilidad oportuna de la información requerida para otros módulos automatizados.  

## 2 Objetivos  
### a. Objetivo General  
- Automatizar la descarga estructurada de archivos adjuntos desde correos electrónicos, aplicando filtros personalizables, para integrarlos oportunamente en flujos RPA que requieren procesamiento de documentos o datos recibidos por email.  

### b. Objetivos Específicos  
- Detectar y acceder automáticamente a correos entrantes con archivos adjuntos relevantes.  
- Filtrar correos según criterios como remitente, asunto, fecha o tipo de archivo.  
- Descargar los archivos adjuntos en una carpeta predeterminada para su posterior uso.  
- Integrar la función de forma reutilizable en diferentes procesos automatizados.  
- Garantizar trazabilidad mediante registro de archivos descargados y errores (si los hay).  

## 3 Alcance  
La función GF_DownloadEmailAttachments aplica a bots desarrollados en plataformas como Automation Anywhere 360 y Rocketbot, integrándose en etapas donde se requiere obtener información desde correos electrónicos entrantes. Su alcance comprende la conexión con cuentas de correo compatibles (como Outlook o IMAP), el filtrado de mensajes según criterios definidos (fecha, remitente, asunto, etc.), la descarga de archivos adjuntos y su almacenamiento en rutas específicas del bot. Esta función puede ser reutilizada en múltiples procesos automatizados que dependan de documentos recibidos por correo, asegurando eficiencia, trazabilidad y reducción de intervención manual.  

## 4 Arquitectura de contexto  
### a. Contexto general  
- La función GF_DownloadEmailAttachments se enmarca en la necesidad de establecer un mecanismo confiable y reutilizable para la descarga automática de archivos adjuntos recibidos por correo electrónico. Su propósito es facilitar la captura de documentos clave desde bandejas de entrada corporativas, reducir la dependencia de intervenciones manuales, y asegurar que los datos necesarios para el proceso automatizado estén disponibles en el momento oportuno y en las rutas correctas del bot.  

### b. Componentes principales  
- Plataforma RPA: Automation Anywhere / Rocketbot, Control Room / Workspace, Bot Creator, Bot Runner.  
- Fuente de datos: Servidor de correo electrónico (Outlook, Exchange, Gmail, IMAP, etc.), Archivos adjuntos del correo.  
- Parámetros de entrada: Remitente, Asunto o palabras clave, Fecha de envío, Ruta destino, Extensiones permitidas.  
- Resultado de salida: Archivos descargados, Confirmación o mensaje de error.  
- Manejo de errores y trazabilidad: Validación de conexión, control de errores, registro en logs.  

## 5 Diagrama de despliegue  
Componentes clave: Bot principal, Función RPA, Parámetros, Máquina virtual, Servidor de correo, Ruta destino.  

## 6 Diagrama de componentes  
Pasos secuenciales: Validación parámetros, Conexión servidor, Búsqueda mensajes, Descarga adjuntos, Almacenamiento, Retorno y logging.  

## 7 Tecnologías utilizadas  
- Automation Anywhere 360  
- Rocketbot  
- SQL Server  

## 8 Flujo del proceso  
- Lectura parámetros, validación, conexión al servidor, búsqueda y filtrado, descarga, almacenamiento, retorno de resultado, registro en logs.  

## 9 Resultados obtenidos  
- Automatización descarga de adjuntos, reducción de errores, mejora operativa, trazabilidad incrementada, reutilización flexible.  

## 10 Confidencialidad  
Este documento no contiene información confidencial. Su propósito es mostrar la experiencia de Synthetics Solutions.  

## 11 Contacto  
- Correo: Synthetic.solutions5@gmail.com  
