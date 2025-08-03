# Función RPA  
**Nombre de la función:** Función de generación de reporte de ejecución – GF_ExecutionReport  
**Objetivo de la función:** Generar automáticamente un resumen estructurado de la ejecución de un bot, incluyendo tiempo total, módulos ejecutados, errores, resultados obtenidos y detalles relevantes para trazabilidad.  
**Desarrollado por:** Synthetics Solutions  
**Fecha de creación:** Febrero 2024  

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
En el marco de la automatización de procesos empresariales y la necesidad creciente de garantizar trazabilidad operativa, surge la importancia de registrar de manera estructurada cada ejecución realizada por los bots RPA. La función GF_ExecutionReport fue diseñada con el propósito de centralizar y automatizar la generación de reportes de ejecución, consolidando información clave como tiempos, resultados, errores y módulos ejecutados. Esta función aporta valor al permitir el monitoreo, la auditoría y la mejora continua de los procesos automatizados, asegurando transparencia y control en cada ciclo de ejecución.  

## 2 Objetivos  
### a. Objetivo General  
- Automatizar la generación y almacenamiento de reportes de ejecución de bots RPA, consolidando información clave para su trazabilidad y análisis posterior.  

### b. Objetivos Específicos  
- Registrar de forma estructurada los datos más relevantes de cada ejecución de bot.  
- Centralizar la información de resultados, errores y tiempos en una base de datos.  
- Facilitar la trazabilidad y el monitoreo de procesos automatizados.  
- Estandarizar el formato de reporte en todos los bots del CoE RPA.  
- Reutilizar la función en diferentes flujos de bots sin modificaciones estructurales.  

## 3 Alcance  
La función GF_ExecutionReport aplica a bots desarrollados en plataformas como Automation Anywhere 360 y Rocketbot, integrándose en la etapa final del flujo de ejecución. Su alcance comprende la recolección de datos relevantes desde el diccionario de variables del bot, la validación de información crítica, la estructuración del registro de ejecución y su almacenamiento en una base de datos centralizada. Esta función garantiza la generación uniforme de reportes para todos los procesos automatizados, contribuyendo a la trazabilidad, monitoreo y análisis del desempeño de los bots.  

## 4 Arquitectura de contexto  
### a. Contexto general  
- La función GF_ExecutionReport se enmarca en la necesidad de generar reportes estandarizados sobre la ejecución de bots RPA. Su propósito es consolidar, estructurar y almacenar información clave como fecha de ejecución, duración, estado, errores y observaciones, permitiendo trazabilidad operativa desde entornos centralizados.  

### b. Componentes principales  
- Plataforma RPA  
  - Automation Anywhere / Rocketbot: plataformas donde se integra y ejecuta la función.  
  - Control Room / Workspace: orquestan la ejecución del bot que contiene la función.  
  - Bot Creator (Desarrollo): entorno donde se desarrolla y actualiza la lógica de generación del reporte.  
  - Bot Runner: instancia donde se ejecuta la función junto al flujo principal del bot.  
- Fuente de datos  
  - Diccionario de variables: contiene la información generada durante la ejecución del bot.  
  - Variables internas: capturadas y actualizadas en tiempo real dentro del flujo del proceso.  
- Parámetros de entrada  
  - Nombre del bot  
  - Fecha y hora de inicio y fin  
  - Duración total de la ejecución  
  - Estado final (Éxito / Error)  
  - Observaciones o mensajes de error  
- Registro estructurado en base de datos  
  - Inserta los datos en la tabla de ejecución dentro de SQL Server.  
  - Cada campo se corresponde con una columna estructurada para trazabilidad.  
- Manejo de errores y trazabilidad  
  - Si falta información clave o ocurre un error de inserción, este se captura y se retorna al log del bot.  
  - La función permite validar campos requeridos y asegurar consistencia del registro.  

## 5 Diagrama de despliegue  
Representa la infraestructura lógica en la que se ejecuta la función GF_ExecutionReport, mostrando los componentes involucrados y sus interacciones dentro del ecosistema RPA.  
Componentes clave:  
- Función RPA  
- Máquina virtual  
- Servidor de base de datos (SQL Server)  
- Parámetros de entrada  
- Bot principal (Main)  

## 6 Diagrama de componentes  
Muestra la estructura interna del bot, dividido en módulos o scripts/componentes.  
| Nombre componente            | Tipo              |  
|-----------------------------|-------------------|  
| STEP 00 – Validación de entrada | Script / Validación |  
| STEP 01 – Construcción de campos | Script / Procesamiento |  
| STEP 02 – Ensamblado del registro | Script / Preparación |  
| STEP 03 – Inserción en base de datos | Script / Escritura |  
| STEP 04 – Retorno y logging   | Script / Finalización |  

## 7 Tecnologías utilizadas  
- Automation Anywhere 360  
- Rocketbot  
- SQL Server  

## 8 Flujo del proceso  
- Lectura de parámetros de entrada  
- Validación de campos requeridos  
- Construcción del registro de ejecución  
- Inserción del registro en la base de datos  
- Retorno de resultado (éxito o error)  
- Registro en log del sistema  

## 9 Resultados obtenidos  
- Estandarización del registro de ejecución de bots RPA desde un componente reutilizable.  
- Trazabilidad mejorada mediante almacenamiento centralizado de métricas de ejecución.  
- Reducción de errores humanos en la documentación de resultados.  
- Mejora en la auditoría operativa con reportes sistemáticos y estructurados.  
- Agilidad para identificar fallos, tiempos muertos y puntos críticos del flujo.  

## 10 Confidencialidad  
Este documento no contiene información confidencial. Su propósito es mostrar la experiencia de Synthetics Solutions.  

## 11 Contacto  
- Correo: Synthetic.solutions5@gmail.com  

