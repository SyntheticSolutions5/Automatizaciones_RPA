# Función RPA  
**Nombre de la función:** Función de generación de reporte de ejecución – GF_WorkdayUtils  
**Objetivo de la función:** Determinar si una fecha es día hábil, identificar el último y primer día hábil del mes, y obtener la fecha hábil anterior en caso de días no laborables, para facilitar decisiones en procesos automatizados.  
**Desarrollado por:** Synthetics Solutions  
**Fecha de creación:** Agosto 2024  

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
En el contexto de la automatización de procesos empresariales, muchas tareas requieren lógica avanzada para determinar fechas válidas de operación. La función GF_WorkdayUtils surge como una solución reutilizable para gestionar condiciones relacionadas con días hábiles y no hábiles, como festivos o fines de semana. Esta función permite validar si una fecha es laborable, identificar el primer y último día hábil del mes, y determinar el día hábil anterior en caso de ser necesario. Al centralizar esta lógica en un componente común, se mejora la precisión de los procesos automatizados, se reduce la duplicidad de código y se facilita la toma de decisiones basadas en calendario laboral.  

## 2 Objetivos  
### a. Objetivo General  
- Automatizar el análisis y validación de fechas laborales en procesos RPA, permitiendo identificar días hábiles, festivos y fechas clave del calendario operativo para optimizar la ejecución de tareas automatizadas.  

### b. Objetivos Específicos  
- Determinar si una fecha es día hábil o festivo.  
- Obtener el primer y último día hábil de un mes dado.  
- Calcular el día hábil anterior en caso de que una fecha no sea laborable.  
- Centralizar la lógica de validación de fechas en una única función reutilizable.  
- Mejorar la precisión y eficiencia de los bots que dependen de condiciones de calendario.  

## 3 Alcance  
La función GF_WorkdayUtils aplica a bots desarrollados en plataformas como Automation Anywhere 360 y Rocketbot, integrándose en etapas donde se requiere validar condiciones relacionadas con días hábiles. Su alcance incluye la verificación de si una fecha es laborable, la identificación del primer y último día hábil del mes, y el cálculo del día hábil anterior a una fecha dada. Esta función puede ser reutilizada en diversos procesos que dependan del calendario operativo, asegurando coherencia, eficiencia y precisión en la toma de decisiones relacionadas con fechas clave.  

## 4 Arquitectura de contexto  
### a. Contexto general  
- La función GF_WorkdayUtils se enmarca en la necesidad de establecer un mecanismo confiable y reutilizable para la validación y consulta de días hábiles dentro del calendario operativo de una organización. Su propósito es determinar si una fecha es laborable, encontrar el día hábil anterior o posterior, y calcular los primeros y últimos días hábiles del mes, facilitando la programación lógica de bots RPA dependientes de fechas clave.  

### b. Componentes principales  
- Plataforma RPA  
  - Automation Anywhere / Rocketbot: plataformas donde se integra y ejecuta la función.  
  - Control Room / Workspace: orquestan la ejecución del bot que contiene la función.  
  - Bot Creator (Desarrollo): entorno donde se desarrolla y actualiza la lógica de generación del reporte.  
  - Bot Runner: instancia donde se ejecuta la función junto al flujo principal del bot.  
- Fuente de datos  
  - Base de datos SQL Server: contiene la tabla de festivos oficial y calendario laboral.  
  - Parámetros del bot: incluyen fecha actual, mes, empresa, etc.  
- Parámetros de entrada  
  - Fecha a evaluar  
  - Tabla de festivos  
  - Tipo de operación requerida (último día hábil, siguiente día hábil, etc.)  
- Resultado de salida  
  - Fecha hábil calculada  
  - Indicador de si la fecha actual es hábil o no  
- Manejo de errores y trazabilidad  
  - Validación de existencia de la tabla de festivos  
  - Control de errores por fechas inválidas o rangos fuera de calendario  
  - Retorno de mensajes en caso de fallos, para tratamiento centralizado en el bot  

## 5 Diagrama de despliegue  
Representa la infraestructura lógica en la que se ejecuta la función GF_WorkdayUtils, mostrando los componentes involucrados y sus interacciones dentro del ecosistema RPA.  
Componentes clave:  
- Bot principal (Main)  
- Función RPA  
- Parámetros de entrada  
- Máquina virtual (Runner)  
- Servidor de base de datos (SQL Server)  

## 6 Diagrama de componentes  
Este diagrama representa la estructura interna de la función GF_WorkdayUtils, dividida en pasos secuenciales que encapsulan la lógica de evaluación de días hábiles, considerando parámetros de entrada, fechas actuales y festivos registrados.  
| Nombre componente               | Tipo                |  
|-------------------------------|---------------------|  
| STEP 00 – Validación de parámetros | Script / Validación  |  
| STEP 01 – Obtención de fecha actual | Script / Consulta   |  
| STEP 02 – Verificación de festivo | Script / Consulta lógica |  
| STEP 03 – Cálculo de días hábiles | Script / Consulta lógica |  
| STEP 04 – Retorno de resultados | Script / Finalización |  

## 7 Tecnologías utilizadas  
- Automation Anywhere 360  
- Rocketbot  
- SQL Server  

## 8 Flujo del proceso  
- Lectura de parámetros desde el diccionario de variables  
- Validación del formato de fecha y campos obligatorios  
- Consulta de la fecha actual y comparación con días festivos  
- Identificación del último día hábil anterior (si aplica)  
- Cálculo del primer y último día hábil del mes  
- Retorno de fechas calculadas al flujo principal del bot  
- Registro de resultados para trazabilidad y validación  

## 9 Resultados obtenidos  
- Automatización del cálculo de días hábiles y festivos en procesos RPA  
- Eliminación de errores manuales en la validación de fechas críticas  
- Mejora en la planificación operativa gracias a información precisa sobre días laborables  
- Reducción del tiempo de desarrollo al reutilizar una función estandarizada  
- Integración flexible en múltiples bots, sin necesidad de ajustes por proceso  

## 10 Confidencialidad  
Este documento no contiene información confidencial. Su propósito es mostrar la experiencia de Synthetics Solutions.  

## 11 Contacto  
- Correo: Synthetic.solutions5@gmail.com  

