
# Synthetics Solutions - Proyecto RPA: Firma de PDF de contratos - API REST de Microsoft Graph

## Cliente / Industria  
Sector salud – Operaciones

## Desarrollado por  
Synthetics Solutions

## Fecha de creación  
Abril 2024

---

## Contenido  
1 Introducción
2 Objetivos
3 Alcance
4 Flujo del proceso
5 Diseño de solución
6 Tecnologías utilizadas
7 Resultados obtenidos
8 Conclusiones estratégicas
9 Confidencialidad
10 Contacto

---

## 1. Introducción  
Con el objetivo de mejorar la eficiencia operativa en el área de Operaciones de una empresa del Sector Salud, se implementó un proyecto de Automatización Robótica de Procesos (RPA) utilizando Python como herramienta principal de desarrollo y API REST de Microsoft Graph para la integración con SharePoint.  
La firma de contratos consiste en identificar el tipo de contrato de prestación de servicios, para extraer la información de los usuarios y, de acuerdo con los parámetros, insertar la firma del líder comercial asociado a la oficina dueña del contrato.  
Mediante la automatización de este proceso se busca no solo mejorar la eficiencia operativa, sino también garantizar la precisión y consistencia de la documentación necesaria, reduciendo los errores humanos y los tiempos de espera.  
Este documento resume los aspectos clave del proyecto, incluyendo el alcance del proceso automatizado, las actividades ejecutadas por el bot, los beneficios obtenidos y los resultados alcanzados tras su implementación.

---

## 2. Objetivos

### Objetivo General  
Desarrollar e implementar una solución RPA para la automatización del proceso de firma de contratos en PDF en el sector salud, utilizando Python y la API REST de Microsoft Graph para integrarse con SharePoint, mejorando la eficiencia operativa y garantizando la precisión y consistencia de la documentación.

### Objetivos Específicos  
- Automatizar la identificación del tipo de contrato de prestación de servicios en SharePoint, con el fin de extraer la información de los usuarios de manera eficiente y precisa.  
- Desarrollar un proceso automatizado para insertar la firma del líder comercial asociado a la oficina dueña del contrato, de acuerdo con los parámetros establecidos, garantizando la correcta inclusión de la firma en los documentos.  
- Reducir el tiempo dedicado al proceso de firma de contratos, mejorando la eficiencia operativa y reduciendo los errores humanos en la validación y gestión de los documentos.

---

## 3. Alcance  
La automatización desarrollada en Python ejecuta las siguientes actividades para la gestión de la firma de contratos en PDF:  
- Identificación de contratos: El bot localiza los contratos de prestación de servicios almacenados en un sitio de SharePoint que requieren ser firmados, según los parámetros establecidos en el sistema.  
- Lectura de parámetros de firma: El bot extrae los criterios y reglas asociadas al contrato, como la oficina responsable y el líder comercial asignado para la firma.  
- Extracción de información de contratos: El bot accede a SharePoint, descarga los contratos correspondientes y extrae la información de los usuarios relacionada con cada uno de los documentos.  
- Inserción de firma: El bot inserta automáticamente la firma del líder comercial correspondiente al contrato, basándose en los parámetros extraídos, asegurando la correcta inclusión de la firma en el documento PDF.  
- Actualización de estado de contratos: El bot actualiza el estado de los contratos en SharePoint, marcando los documentos firmados y notificando cualquier inconsistencia o error en el proceso.  
- Generación de reportes: El bot genera reportes automáticos con los resultados de la firma de los contratos, detallando los documentos firmados y aquellos con algún tipo de error o inconsistencia.

---

## 4. Flujo del proceso  
- Lectura de parámetros de entrada (Excel / SharePoint)  
- Consumo de API para obtener el listado de contratos pendientes  
- Extracción de datos para la firma  
- Inserción de datos en la estructura de contratos  
- Gestión de documentos y validación de parámetros  
- Inserción de firma en los contratos  
- Actualización de estado de contratos  
- Generación de reportes y registro de logs

---

## 5. Diseño de solución  

| Nombre componente           | Tipo        |  
|----------------------------|-------------|  
| Main_SignContracts          | Orquestador |  
| ConfigVars                 | Función     |  
| Notifications              | Función     |  
| Exceptions                 | Función     |  
| Logging                    | Función     |  
| ST1_DownloadContractsSharePoint | Tarea   |  
| ST2_ClassifySignContracts  | Tarea       |  
| ST3_UpdateContractsSharePoint | Tarea    |  
| ST4_GenerateReports        | Tarea       |  

---

## 6. Tecnologías utilizadas  
- API REST Microsoft Graph  
- SharePoint Online  
- Python 3.1  
- Microsoft Excel  
- SQL Server  

---

## 7. Resultados obtenidos  
- Desarrollo de un asistente que valida más de 1.000 contratos mensuales en un tiempo promedio de 5 minutos.  
- Reducción del tiempo de ejecución del proceso en más de un 98%.  
- Minimización de errores manuales, gracias a la ejecución sistemática de reglas de negocio.  
- Trazabilidad y auditoría mejorada, mediante el registro de datos en bases estructuradas.  
- Liberación de carga operativa al personal operativo, permitiéndoles enfocarse en tareas analíticas y estratégicas.

---

## 8. Conclusiones estratégicas  
- La automatización mejoró la precisión y trazabilidad de la gestión documental, liberando tiempo para que los equipos internos se enfoquen en tareas estratégicas.  
- Synthetics Solutions jugó un papel clave en agilizar la implementación del proyecto, proporcionando experiencia técnica en la automatización y validación de documentos.  
- Este caso demuestra cómo la tercerización especializada en RPA puede aportar valor tangible a proyectos liderados internamente, acelerando resultados y garantizando sostenibilidad técnica.

---

## 9. Confidencialidad  
Este documento ha sido elaborado con fines de divulgación técnica y comercial. Se han tratado los datos sensibles bajo la normativa de confidencialidad de la organización. No se expone información personal o confidencial de terceros.

---

## 10. Contacto  
Synthetic.solutions5@gmail.com
