# Función RPA  
**Nombre de la función:** Función de generación de reporte de ejecución – GF_FileConverter  
**Objetivo de la función:** Convertir archivos entre distintos formatos estructurados (como Excel, CSV, JSON, XML), según los parámetros definidos, con el fin de facilitar la interoperabilidad de datos y su procesamiento automatizado en flujos RPA.  
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
En el contexto de la automatización de procesos empresariales, es común la necesidad de manipular y transformar archivos entre distintos formatos estructurados como parte del flujo de datos. La función GF_FileConverter surge como una solución reutilizable que permite convertir archivos entre extensiones como Excel (.xlsx), CSV, JSON y XML, entre otros. Su implementación facilita la interoperabilidad entre sistemas, reduce los errores manuales en la manipulación de datos y estandariza los formatos de entrada y salida requeridos por otros módulos o plataformas. Al centralizar esta lógica en un componente único, se mejora la eficiencia operativa y se garantiza consistencia en la transformación de archivos dentro de procesos RPA.  

## 2 Objetivos  
### a. Objetivo General  
- Automatizar la conversión estructurada de archivos entre diferentes formatos (como Excel, CSV, JSON y XML) en procesos RPA, garantizando compatibilidad, estandarización y eficiencia en el tratamiento de datos entre sistemas.  

### b. Objetivos Específicos  
- Convertir archivos de entrada de un formato a otro según los parámetros definidos.  
- Soportar múltiples tipos de archivo (XLSX, CSV, JSON, XML, TXT, entre otros).  
- Centralizar la lógica de transformación en una función reutilizable.  
- Validar la estructura y contenido del archivo antes de la conversión.  
- Optimizar la interoperabilidad entre sistemas que requieren distintos formatos de datos.  

## 3 Alcance  
La función GF_FileConverter aplica a bots desarrollados en plataformas como Automation Anywhere 360 y Rocketbot, integrándose en etapas donde se requiere transformar archivos entre distintos formatos estructurados. Su alcance incluye la conversión de archivos como XLSX, CSV, JSON, XML y TXT, según parámetros definidos por el proceso. Esta función puede ser reutilizada en múltiples flujos que necesiten interoperabilidad entre sistemas, garantizando consistencia, estandarización y automatización eficiente del tratamiento de datos.  

## 4 Arquitectura de contexto  
### a. Contexto general  
- La función GF_FileConverter se enmarca en la necesidad de establecer un mecanismo confiable y reutilizable para la conversión automatizada de archivos entre distintos formatos (XLSX, CSV, JSON, XML, TXT, entre otros). Su propósito es facilitar la interoperabilidad entre sistemas, estandarizar la estructura de datos de entrada y salida, y permitir que los bots RPA operen con múltiples fuentes de información sin necesidad de codificación redundante.  

### b. Componentes principales  
- Plataforma RPA:  
  - Automation Anywhere / Rocketbot: plataformas donde se integra y ejecuta la función.  
  - Control Room / Workspace: orquestan la ejecución del bot que contiene la función.  
  - Bot Creator (Desarrollo): entorno donde se desarrolla y actualiza la lógica de generación del reporte.  
  - Bot Runner: instancia donde se ejecuta la función junto al flujo principal del bot.  
- Fuente de datos:  
  - Archivos fuente: ubicados en carpetas locales o compartidas, en formatos estructurados como XLSX, CSV, JSON, XML o TXT.  
  - Parámetros del bot: definen ruta del archivo, formato origen, formato destino y estructura deseada.  
- Parámetros de entrada:  
  - Ruta del archivo fuente  
  - Formato de origen  
  - Formato de destino  
  - Opciones adicionales de transformación (codificación, delimitadores, estructura)  
- Resultado de salida:  
  - Archivo convertido en el formato solicitado  
  - Confirmación de éxito o mensaje de error  
- Manejo de errores y trazabilidad:  
  - Validación de existencia del archivo origen y permisos de acceso  
  - Control de errores por formato inválido, incompatibilidades o rutas no accesibles  
  - Registro de mensajes de error o éxito en logs centralizados para trazabilidad del proceso  

## 5 Diagrama de despliegue  
Representa la infraestructura lógica en la que se ejecuta la función GF_WorkdayUtils, mostrando los componentes involucrados y sus interacciones dentro del ecosistema RPA.  
Componentes clave:  
- Bot principal (Main)  
- Función RPA  
- Parámetros de entrada  
- Máquina virtual (Runner)  
- Servidor de archivos / Base de datos  

## 6 Diagrama de componentes  
Este diagrama representa la estructura interna de la función GF_FileConverter, dividida en pasos secuenciales que encapsulan la lógica de conversión entre formatos de archivo, considerando parámetros de entrada, validaciones de formato y ejecución del proceso.  
| Nombre componente            | Tipo         |  
|-----------------------------|--------------|  
| STEP 00 – Validación de parámetros | Script / Validación |  
| STEP 01 – Detección del formato origen | Script / Análisis |  
| STEP 02 – Conversión de contenido | Script / Procesamiento |  
| STEP 03 – Exportación al nuevo formato | Script / Escritura |  
| STEP 04 – Retorno y logging | Script / Finalización |  

## 7 Tecnologías utilizadas  
- Automation Anywhere 360  
- Rocketbot  
- SQL Server  

## 8 Flujo del proceso  
- Lectura de parámetros desde el diccionario de variables  
- Validación de formato de archivo de entrada y salida  
- Verificación de existencia del archivo fuente  
- Carga del archivo original (XLSX, CSV, JSON, XML, etc.)  
- Conversión de datos al formato de destino especificado  
- Guardado del archivo convertido en la ruta de salida  
- Retorno del resultado y mensaje de estado al bot  
- Registro en log para trazabilidad de la conversión  

## 9 Resultados obtenidos  
- Automatización del proceso de conversión entre múltiples formatos de archivo (XLSX, CSV, JSON, XML, TXT, etc.)  
- Reducción de errores humanos en la manipulación y transformación de archivos  
- Aumento en la eficiencia operativa al eliminar tareas manuales repetitivas  
- Estandarización del tratamiento de datos entre distintos sistemas o etapas del proceso  
- Flexibilidad para reutilizar la función en diferentes bots y flujos sin necesidad de modificaciones estructurales  

## 10 Confidencialidad  
Este documento no contiene información confidencial. Su propósito es mostrar la experiencia de Synthetics Solutions.  

## 11 Contacto  
- Correo: Synthetic.solutions5@gmail.com  
