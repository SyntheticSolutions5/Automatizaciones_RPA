# Función RPA  
**Nombre de la función:** Función de generación de reporte de ejecución – GF_AzureDownloader  
**Objetivo de la función:** Automatizar la descarga de archivos desde contenedores de Azure Blob Storage en flujos RPA, utilizando credenciales seguras y parámetros configurables como el nombre del contenedor, el nombre del archivo (blob) y la ruta de destino local. Esta función permite integrar datos alojados en la nube directamente en procesos automatizados, facilitando la interoperabilidad entre sistemas, la actualización de información y la reducción de tareas manuales relacionadas con la gestión de archivos remotos.  
**Desarrollado por:** Synthetics Solutions  
**Fecha de creación:** Febrero 2025  

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
En el marco de la automatización de procesos empresariales, muchas tareas requieren la integración con servicios de almacenamiento en la nube. La función GF_AzureDownloader surge como un componente reutilizable para automatizar la descarga de archivos desde Azure Blob Storage, permitiendo que bots RPA accedan de forma segura y estructurada a documentos almacenados en contenedores de Azure. Esta función centraliza la lógica de conexión, autenticación, descarga y validación de archivos, mejorando la eficiencia operativa, reduciendo el trabajo manual y garantizando la disponibilidad oportuna de la información en los flujos automatizados.  

## 2. Objetivos  
**Objetivo General:**  
- Automatizar la descarga de archivos desde contenedores de Azure Blob Storage dentro de flujos RPA, garantizando el acceso seguro, controlado y estructurado a documentos almacenados en la nube para su posterior procesamiento automatizado.  

**Objetivos Específicos:**  
- Establecer conexión segura con Azure Storage utilizando credenciales, tokens SAS o claves de acceso.  
- Descargar archivos específicos a partir de parámetros como nombre del contenedor, ruta dentro del blob o nombre del archivo.  
- Almacenar los archivos descargados en rutas locales definidas por el bot.  
- Reutilizar la lógica de conexión y descarga en múltiples bots sin necesidad de modificaciones.  
- Registrar eventos, errores y archivos descargados para trazabilidad y monitoreo.  

## 3. Alcance  
La función GF_AzureDownloader aplica a bots desarrollados en plataformas como Automation Anywhere 360 y Rocketbot, integrándose en etapas donde se requiere descargar archivos desde almacenamiento en la nube de Azure Blob Storage. Su alcance incluye la conexión segura a contenedores de Azure mediante claves de acceso, tokens SAS o credenciales gestionadas, la búsqueda de archivos por ruta o nombre, y la descarga automatizada hacia carpetas locales o compartidas. Esta función puede ser reutilizada en múltiples procesos que dependan de insumos alojados en la nube, asegurando eficiencia, seguridad en el acceso y trazabilidad en la gestión de archivos distribuidos.  

## 4. Arquitectura de contexto  
### a. Contexto general  
La función GF_AzureDownloader responde a la necesidad de establecer un componente confiable y reutilizable para la descarga automática de archivos desde Azure Blob Storage dentro de flujos RPA. Su propósito es facilitar el acceso a recursos alojados en la nube mediante autenticación segura (como SAS Token o claves de cuenta), rutas dinámicas y control de errores. Centralizar esta lógica en una función única permite mejorar la trazabilidad, reducir esfuerzos manuales y estandarizar la integración con almacenamiento en la nube de Microsoft Azure.  

### b. Componentes principales  
- **Plataforma RPA:**  
  - Automation Anywhere / Rocketbot: plataformas donde se integra y ejecuta la función.  
  - Control Room / Workspace: orquestan la ejecución del bot que contiene la función.  
  - Bot Creator (Desarrollo): entorno donde se desarrolla y actualiza la lógica de generación del reporte.  
  - Bot Runner: instancia donde se ejecuta la función junto al flujo principal del bot.  

- **Fuente de datos:**  
  - Azure Blob Storage: contenedor en la nube donde se alojan los archivos.  
  - Credenciales Azure: token SAS, claves de acceso, o identidades gestionadas (MSI).  

- **Parámetros de entrada:**  
  - Nombre del contenedor (container)  
  - Ruta del archivo (blob path)  
  - Ruta local de destino (descarga)  
  - Credenciales de acceso (SAS Token, Storage Key, Azure Identity, etc.).  

- **Resultado de salida:**  
  - Archivo descargado correctamente en la ruta local especificada  
  - Mensaje estructurado de éxito o error  
  - Registro de evento en logs del bot.  

- **Manejo de errores y trazabilidad:**  
  - Validación de existencia del contenedor y blob  
  - Control de errores por credenciales inválidas, blob inexistente o permisos insuficientes  
  - Manejo de timeouts o desconexiones temporales  
  - Registro en log central con detalles del intento, estado, ruta y resultado.  

## 5. Diagrama de despliegue  
Representa la infraestructura lógica en la que se ejecuta la función GF_AzureDownloader, mostrando los componentes involucrados y sus interacciones dentro del ecosistema RPA. Esta función se integra en flujos automatizados que requieren descargar archivos desde Azure Blob Storage, permitiendo la obtención segura de recursos almacenados en la nube para su procesamiento posterior.  

**Componentes clave:**  
- Bot principal (Main)  
- Función RPA  
- Parámetros de entrada  
- Máquina virtual (Runner)  
- Azure Blob Storage  
- Carpeta de destino local / red compartida  

## 6. Diagrama de componentes  
Este diagrama representa la estructura interna de la función GF_AzureDownloader, dividida en pasos secuenciales que encapsulan la lógica de conexión con Azure Blob Storage, descarga del archivo y registro del resultado. Cada paso está organizado en scripts modulares para garantizar validación, ejecución segura y trazabilidad del proceso.  

| Nombre componente           | Tipo          |  
|----------------------------|---------------|  
| STEP 00 – Validación de parámetros  | Script / Validación |  
| STEP 01 – Autenticación Azure (Token / Key) | Script / Seguridad |  
| STEP 02 – Conexión a Blob Storage | Script / Comunicación |  
| STEP 03 – Descarga del archivo | Script / Extracción |  
| STEP 04 – Guardado en destino local | Script / Escritura |  
| STEP 05 – Retorno y logging | Script / Finalización |  

## 7. Tecnologías utilizadas  
- Automation Anywhere 360  
- Rocketbot  
- SQL Server  

## 8. Flujo del proceso  
- Lectura de parámetros desde el diccionario de variables (container, ruta del archivo, claves de acceso, carpeta destino).  
- Validación de credenciales de Azure (Access Key o Token SAS) y existencia de parámetros obligatorios.  
- Establecimiento de conexión con Azure Blob Storage mediante librería o módulo RPA.  
- Búsqueda del archivo solicitado dentro del contenedor especificado.  
- Descarga del archivo desde Azure hacia la carpeta local o compartida configurada.  
- Verificación de éxito y validación de integridad (nombre, tamaño, formato).  
- Devolución del resultado al bot indicando éxito o detalles del error.  
- Registro del evento en logs para trazabilidad del proceso.  

## 9. Resultados obtenidos  
- Automatización de la descarga de archivos desde Azure Blob Storage dentro de flujos RPA, eliminando tareas manuales repetitivas.  
- Reducción de errores humanos al centralizar la lógica de autenticación, conexión y descarga.  
- Interoperabilidad eficiente con servicios en la nube, integrando datos almacenados en contenedores de Azure.  
- Mejora en la trazabilidad operativa mediante registros detallados de descargas, rutas y errores.  
- Reutilización flexible de la función en múltiples bots, adaptable a distintos contenedores, rutas y condiciones de descarga.  

## 10. Confidencialidad  
Este documento no contiene información confidencial. Su propósito es mostrar la experiencia de Synthetics Solutions.  

## 11. Contacto  
- Correo: Synthetic.solutions5@gmail.com  
