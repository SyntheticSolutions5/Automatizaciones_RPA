
# Synthetics Solutions - Proyecto RPA: Conciliación de cuentas contables

## Cliente / Industria  
Bancario – Financiero - Contable

## Desarrollado por  
Synthetics Solutions

## Fecha de creación  
Marzo 2024

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
En el marco de los esfuerzos por optimizar procesos operativos dentro del área de Finanzas y Contabilidad, se desarrolló un proyecto de Automatización Robótica de Procesos (RPA, por sus siglas en inglés) utilizando la plataforma Automation Anywhere. El objetivo principal fue automatizar el proceso de conciliación de cuentas contables, una actividad crítica que tradicionalmente demandaba una alta carga operativa, consumo significativo de tiempo y propensión a errores manuales.  
La conciliación contable consiste en comparar y validar la correspondencia entre diferentes registros financieros, con el fin de garantizar la integridad y precisión de la información contable. Mediante la automatización de este proceso, se busca no solo mejorar la eficiencia operativa, sino también asegurar un mayor control sobre los datos y facilitar la trazabilidad de las partidas conciliadas.  
Este documento resume los aspectos clave del proyecto, incluyendo el alcance del proceso automatizado, las actividades ejecutadas por el bot, los beneficios obtenidos y los resultados alcanzados tras su implementación.

---

## 2. Objetivos  

### Objetivo General  
Automatizar el proceso de conciliación contable mediante el uso de tecnología RPA en Automation Anywhere, con el fin de reducir tiempos operativos, mejorar la exactitud de la información y aumentar la eficiencia en el análisis y gestión de partidas contables.

### Objetivos Específicos  
- Estandarizar y digitalizar la lectura de parámetros necesarios para ejecutar las conciliaciones contables.  
- Automatizar la descarga de reportes desde los sistemas fuente (ERP u otras plataformas contables).  
- Integrar los datos en una base de datos estructurada para su posterior procesamiento y análisis.  
- Actualizar automáticamente las plantillas de conciliación aplicando reglas de negocio definidas.  
- Generar reportes de conciliación con los resultados clasificados (partidas conciliadas, no conciliadas, observaciones).  
- Aumentar la trazabilidad y control del proceso mediante registros automáticos y estructurados.  
- Disminuir el riesgo de errores manuales y liberar tiempo del personal contable para tareas de mayor valor agregado.

---

## 3. Alcance  
El bot desarrollado en Automation Anywhere ejecuta de manera autónoma las siguientes actividades:  
- Lectura de parámetros de conciliación: El bot identifica y lee los parámetros necesarios para realizar la conciliación, como rangos de fechas, cuentas específicas, criterios de comparación, entre otros.  
- Descarga de reportes contables: Accede a las fuentes de información relevantes (ERP, sistemas contables o archivos compartidos) y descarga los reportes necesarios para el análisis de conciliación.  
- Interacción con base de datos: Los datos descargados son transformados y cargados en una base de datos estructurada, optimizando el manejo, consulta y trazabilidad de la información.  
- Actualización de plantillas de conciliación: Utilizando las reglas definidas por el negocio, el bot actualiza automáticamente las plantillas de conciliación, aplicando filtros, fórmulas y agrupaciones requeridas.  
- Generación de reportes finales: Se generan reportes automáticos con los resultados de la conciliación, incluyendo partidas conciliadas, no conciliadas y observaciones, listos para ser revisados por el equipo contable.

---

## 4. Arquitectura de contexto  

### Contexto general  
El proyecto se enmarca en la automatización del proceso de conciliación contable, que requiere interacción con diferentes fuentes de información (ERP, reportes financieros, bases de datos), procesamiento estructurado de datos y generación de reportes.

### Componentes principales  
- Plataforma RPA: Automation Anywhere  
  - Control Room: Gestiona el orquestamiento de los bots, asignación de tareas y monitoreo de ejecuciones.  
  - Bot Runner: Ejecuta el bot de conciliación de forma programada o bajo demanda.  
  - Bot Creator (Desarrollo): Entorno donde se desarrolló y mantiene el bot.  
- Fuentes de datos  
  - ERP / Sistema Contable: Sistema origen de los reportes contables utilizados para la conciliación.  
  - Archivos Excel / CSV: Reportes descargados manual o automáticamente desde portales o carpetas compartidas.  
  - Parámetros de Entrada: Plantillas de configuración con las reglas de conciliación, fechas, cuentas, criterios, etc.  
- Base de datos  
  - Motor de base de datos - SQL Server: Repositorio para almacenar los datos extraídos de los reportes y organizar las partidas contables para facilitar la conciliación.  
  - Facilita consultas dinámicas, depuración de errores y auditoría del proceso.  
- Plantillas de conciliación  
  - Plantillas Excel con fórmulas y formatos predefinidos: Utilizadas para reflejar los resultados del cruce contable.  
  - Actualizadas por el bot en cada ejecución según los resultados obtenidos.  
- Reportes finales  
  - Reportes en Excel generados automáticamente, con partidas conciliadas, no conciliadas, observaciones y resumen ejecutivo.

---

## 5. Diagrama de despliegue  
Muestra dónde se ejecutan los componentes del bot y cómo se comunican entre sí (infraestructura lógica).  
Componentes clave:  
- Bot RPA  
- Máquina virtual  
- Servidor de base de datos SQL Server  
- ERP o sistema fuente  
- Carpeta compartida  

---

## 6. Diagrama de componentes  
Muestra la estructura interna del bot, dividido en módulos o scripts/componentes.

| Nombre componente  | Tipo         |  
|-------------------|--------------|  
| Main              | Orquestador  |  
| ConfigVars        | Función      |  
| Notifications     | Función      |  
| Exceptions        | Función      |  
| Logging           | Función      |  
| B01_GetParamsFiles | Tarea        |  
| B02_DownloadErpReports | Tarea    |  
| B03_InsertData    | Tarea        |  
| B04_ProcessData   | Tarea        |  
| B05_UpdateTemplates | Tarea      |  
| B06_GenerateFinalReports | Tarea  |  

Relaciones:  
- Main → inicializa y contiene la lógica principal para manejo del flujo del proceso.  
- B01_GetParamsFiles → Obtiene los parámetros  
- B02_DownloadErpReports → Descarga los reportes desde el ERP  
- B03_InsertData → Inserta los datos de los reportes en SQL Server  
- B04_ProcessData → Realiza la conciliación  
- B05_UpdateTemplates → Actualiza las plantillas de conciliación  
- B06_GenerateFinalReports → Genera los reportes finales  
- ConfigVars → configura un diccionario de variables utilizadas en el proceso  
- Notifications → envía correos electrónicos de inicio, fin y novedades  
- Exceptions → gestiona los errores controlados y no controlados  
- Logging → registra la trazabilidad de la ejecución en archivos planos de log  

---

## 7. Tecnologías utilizadas  
- Automation Anywhere 360  
- Python 3.1  
- SQL Server  

---

## 8. Flujo del proceso  
- Lectura de parámetros de entrada (Excel / base de datos)  
- Acceso y descarga de reportes desde el ERP o sistema fuente  
- Inserción de datos en base de datos para estructuración  
- Ejecución de lógica de conciliación (cruce de partidas)  
- Actualización de plantillas de conciliación (Excel)  
- Generación y almacenamiento de reportes  
- Registro de logs y resultados en el sistema  

---

## 9. Resultados obtenidos  
- Reducción del tiempo de ejecución del proceso de conciliación en más de un 95%.  
- Minimización de errores manuales, gracias a la ejecución sistemática de reglas de negocio.  
- Trazabilidad y auditoría mejorada, mediante el registro de datos en bases estructuradas.  
- Liberación de carga operativa al personal contable, permitiéndoles enfocarse en tareas analíticas y estratégicas.

---

## 10. Confidencialidad  
Este documento ha sido elaborado con fines de divulgación técnica y comercial. Se han tratado los datos sensibles bajo la normativa de confidencialidad de la organización. No se expone información personal o confidencial de terceros.

---

## 11. Contacto  
Synthetic.solutions5@gmail.com
