# Función RPA  
**Nombre de la función:** Función de Configuración de Variables – GF_ConfigVars  
**Objetivo de la función:** Configurar de forma automática y estandarizada las variables necesarias para la ejecución de bots RPA, garantizando trazabilidad y compatibilidad entre entornos.  
**Desarrollado por:** Synthetics Solutions  
**Fecha de creación:** Enero 2024  

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
En el marco de los esfuerzos por optimizar procesos operativos dentro de entornos empresariales complejos, surge la necesidad de automatizar tareas repetitivas que antes eran ejecutadas de forma manual. La función GF_ConfigVars fue diseñada con el objetivo de establecer un mecanismo confiable y reutilizable para configurar dinámicamente las variables requeridas por los bots RPA, garantizando precisión, trazabilidad y adaptabilidad a distintos entornos de ejecución.  

## 2 Objetivos  
### a. Objetivo General  
- Automatizar la configuración de variables necesarias para la ejecución controlada y trazable de bots RPA, desde entornos centralizados.  

### b. Objetivos Específicos  
- Minimizar errores por variables mal configuradas o ausentes.  
- Adaptarse automáticamente a entornos de desarrollo o producción.  
- Extraer datos de configuración desde bases de datos centralizadas.  
- Permitir trazabilidad de errores en la configuración inicial.  
- Reutilizar la lógica de configuración en múltiples procesos RPA.  

## 3 Alcance  
La función GF_ConfigVars aplica a bots desarrollados en plataformas como Automation Anywhere 360 y Rocketbot. Su alcance incluye validación de entorno, consulta a tablas de configuración, carga automática de variables a un diccionario, creación de carpetas de logs y retorno de resultados con control de errores.  

## 4 Arquitectura de contexto  
### a. Contexto general  
- La función GF_ConfigVars se enmarca en la automatización de la configuración de variables de entorno para bots RPA. Su propósito es identificar el entorno de ejecución (desarrollo o producción), extraer desde una base de datos los parámetros necesarios y construir un diccionario reutilizable que centraliza toda la información que necesita el bot para operar correctamente.  

### b. Componentes principales  
- Plataforma RPA  
  - Automation Anywhere / Rocketbot: plataformas donde se integra y ejecuta la función.  
  - Control Room / Workspace: orquestan la ejecución del bot que contiene la función.  
  - Bot Creator (Desarrollo): entorno donde se desarrolla y actualiza la lógica de configuración.  
  - Bot Runner: instancia donde se ejecuta la función junto al resto del bot.  
- Fuente de datos  
  - SQL Server: contiene las tablas de configuración con variables parametrizadas por bot y entorno.  
  - Tablas auxiliares: permiten identificar el nombre del bot, empresa asociada o entorno dinámico.  
- Parámetros de entrada  
  - Nombre de la tarea principal  
  - Tabla de configuración personalizada  
  - Variables de control  
- Diccionario de salida  
  - Contiene todas las variables leídas y organizadas en pares clave-valor.  
  - Incluye información de entorno, rutas, empresa, trazabilidad, etc.  
- Manejo de errores y trazabilidad  
  - Variables de control que permiten capturar fallos en tiempo de ejecución.  
  - Si la tabla no existe o hay errores de conexión, estos se devuelven al bot para tratamiento centralizado.  

## 5 Diagrama de despliegue  
Representa la infraestructura lógica en la que se ejecuta la función GF_ConfigVars, mostrando los componentes involucrados y sus interacciones dentro del ecosistema RPA.  
Componentes clave:  
- Función RPA  
- Máquina virtual  
- Servidor de base de datos (SQL Server)  
- Carpetas compartidas  
- Parámetros de Entrada  

## 6 Diagrama de componentes  
Muestra la estructura interna del bot, dividido en módulos o scripts/componentes.  

| Nombre componente             | Tipo             |  
|------------------------------|------------------|  
| STEP 00 – Validación inicial  | Script / Validación |  
| STEP 01 – Validación del entorno | Script / Consulta   |  
| STEP 02 – Configuración del diccionario | Script / Procesamiento |  
| STEP 03 – Consulta de nombre del bot | Script / Consulta auxiliar |  
| STEP 04 – Cierre y retorno    | Script / Finalización |  

## 7 Tecnologías utilizadas  
- Automation Anywhere 360  
- Rocketbot  
- SQL Server  

## 8 Flujo del proceso  
- Lectura de parámetros de entrada  
- Validación del entorno de ejecución  
- Consulta a la base de datos de configuración  
- Construcción del diccionario de variables  
- Consulta auxiliar del nombre del bot  
- Creación de carpetas de logs si no existen  
- Retorno de resultados  

## 9 Resultados obtenidos  
- Reducción del tiempo de configuración de variables en más de un 98%.  
- Eliminación de errores manuales en la carga de parámetros del bot.  
- Mejora en la trazabilidad y auditoría mediante registros automáticos.  
- Estandarización de la configuración en todos los procesos del CoE RPA.  
- Mayor agilidad para el mantenimiento y despliegue de nuevos bots  

## 10 Confidencialidad  
Este documento no contiene información confidencial. Su propósito es mostrar la experiencia de Synthetics Solutions.  

## 11 Contacto  
- Correo: Synthetic.solutions5@gmail.com  
