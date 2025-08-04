
# Synthetics Solutions - Proyecto RPA: Gestión de documentos – API Rest SharePoint

## Cliente / Industria  
Sector salud – Operaciones

## Desarrollado por  
Synthetics Solutions

## Fecha de creación  
Abril 2022

---

## Contenido  
1. Introducción
2. Objetivos
3. Alcance
4. Flujo del proceso
5. Diseño de solución
6. Tecnologías utilizadas
7. Resultados obtenidos
8. Conclusiones estratégicas
9. Confidencialidad
10. Contacto

---

## 1. Introducción  
En el marco de los esfuerzos por optimizar procesos operativos dentro del área de Operaciones de una empresa del Sector Salud, se desarrolló un proyecto de Automatización Robótica de Procesos (RPA, por sus siglas en inglés) utilizando Python como herramienta de desarrollo y API REST de Microsoft Graph como mecanismo de integración con SharePoint.  
El objetivo principal fue disminuir el tiempo del proceso de gestión masiva de documentos comerciales en SharePoint, una actividad altamente operativa, que se realiza a nivel nacional en todas las regiones de la empresa.  
La gestión de documentos consiste en identificar los elementos de la lista (clientes) de SharePoint que se encuentran en estado de “validación documental” para validar y completar la lista de chequeo de documentos requeridos por el área de auditoría médica.  
Mediante la automatización de este proceso se busca no solo mejorar la eficiencia operativa, sino también garantizar la precisión y consistencia de la documentación necesaria, reduciendo los errores humanos y los tiempos de espera.  
Este documento resume los aspectos clave del proyecto, incluyendo el alcance del proceso automatizado, las actividades ejecutadas por el bot, los beneficios obtenidos y los resultados alcanzados tras su implementación.

---

## 2. Objetivos

### Objetivo General  
Desarrollar e implementar una solución RPA para la gestión automatizada de documentos en SharePoint, que permita identificar, validar y completar la lista de chequeo de documentos requeridos por el área de auditoría médica, mejorando la eficiencia operativa, garantizando precisión y trazabilidad en el proceso.

### Objetivos Específicos  
- Automatizar la identificación y clasificación de los documentos en estado de “validación documental” en SharePoint, según las necesidades del área de auditoría médica.  
- Desarrollar una lógica de validación automatizada que permita comparar los documentos entregados con la lista de chequeo establecida por el área de auditoría médica, asegurando el cumplimiento de los requisitos.  
- Reducir el tiempo dedicado a la validación y seguimiento de los documentos, alcanzando una eficiencia operativa superior y asegurando una mayor cobertura de la gestión documental.  
- Implementar alertas automáticas para notificar a los usuarios cuando los documentos estén incompletos o no cumplan con los requisitos establecidos, facilitando la toma de decisiones oportunas.  
- Integrar la solución con las herramientas y sistemas internos del cliente, como SharePoint, para garantizar la trazabilidad, acceso y gestión de los resultados de forma centralizada.  
- Entregar documentación técnica detallada, guías de usuario y proporcionar soporte durante las fases de pruebas y puesta en producción para asegurar la correcta implementación y operación del asistente RPA.

---

## 3. Alcance  
La automatización desarrollada en Python ejecuta las siguientes actividades:  
- Identificación de documentos en validación: El bot localiza los documentos marcados como “validación documental” en SharePoint.  
- Lectura de parámetros de validación: El bot extrae los criterios y reglas de validación establecidos por el área de auditoría médica.  
- Extracción de documentos: El bot accede a SharePoint y descarga los documentos correspondientes para su validación.  
- Validación de documentos: El bot verifica que los documentos cumplan con los requisitos establecidos.  
- Actualización de estado de documentos: El bot marca los documentos validados y notifica inconsistencias.  
- Generación de reportes: El bot genera reportes automáticos con los resultados de la validación.

---

## 4. Flujo del proceso  
- Lectura de parámetros de entrada (Excel / base de datos)  
- Consumo de API para obtener el listado de ID de clientes  
- Inserción de datos en base de datos para estructuración  
- Consumo de API para descargar los documentos adjuntos de cada cliente  
- Gestión de documentos y validación de completitud  
- Consumo de API para cargue masivo de documentos a nueva lista de SharePoint  
- Registro de logs y resultados en el sistema

---

## 5. Diseño de solución  

| Nombre componente        | Tipo         |  
|-------------------------|--------------|  
| Main_DocumentsManagment | Orquestador  |  
| ConfigVars              | Función      |  
| Notifications           | Función      |  
| Exceptions              | Función      |  
| Logging                 | Función      |  
| ST1_GetDocuments        | Tarea        |  
| ST2_ProcessDocuments    | Tarea        |  
| ST3_GenerateReports     | Tarea        |  

---

## 6. Tecnologías utilizadas  
- API REST Microsoft Graph  
- SharePoint Online  
- Python 3.1  
- Microsoft Excel  
- SQL Server  

---

## 7. Resultados obtenidos  
- Desarrollo de un asistente que valida más de 12.000 documentos mensuales en un tiempo promedio de 20 minutos.  
- Reducción del tiempo de ejecución del proceso en más de un 90%.  
- Minimización de errores manuales, gracias a la ejecución sistemática de reglas de negocio.  
- Trazabilidad y auditoría mejorada, mediante el registro de datos en bases estructuradas.  
- Liberación de carga operativa al personal operativo, permitiéndoles enfocarse en tareas analíticas y estratégicas.

---

## 8. Conclusiones estratégicas  
- La automatización mejoró la precisión y trazabilidad de la gestión documental, liberando tiempo para que los equipos internos se enfoquen en tareas estratégicas.  
- Synthetic Solution jugó un papel clave en agilizar la implementación del proyecto, proporcionando experiencia técnica en la automatización y validación de documentos.  
- Este caso demuestra cómo la tercerización especializada en RPA puede aportar valor tangible a proyectos liderados internamente, acelerando resultados y garantizando sostenibilidad técnica.

---

## 9. Confidencialidad  
Este documento ha sido elaborado con fines de divulgación técnica y comercial. Se han tratado los datos sensibles bajo la normativa de confidencialidad de la organización. No se expone información personal o confidencial de terceros.

---

## 10. Contacto  
Synthetic.solutions5@gmail.com
