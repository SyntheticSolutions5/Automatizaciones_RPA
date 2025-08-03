
# Synthetics Solutions - Proyecto RPA: Automatización de Punteo y Activación de Vinculaciones

## Cliente / Industria  
Cooperativa – Área de vinculación

## Desarrollado por  
Synthetics Solutions

## Fecha de creación  
Marzo 2023

---

## Contenido  
1 Introducción
2 Objetivos
3 Alcance
4 Arquitectura del proceso
5 Tecnologías utilizadas
6 Resultados obtenidos
7 Lecciones aprendidas
8 Confidencialidad

---

## 1. Introducción  
Este documento describe el desarrollo de un Bot RPA orientado a la automatización del proceso de Punteo y Activación de Vinculaciones en el aplicativo web de la cooperativa, con el objetivo de optimizar el flujo operativo relacionado con la actualización de estados de tareas y activación de vinculaciones en la Cooperativa.

---

## 2. Objetivos

### Objetivo general  
- Automatizar el proceso de punteo y activación de vinculaciones utilizando tecnología RPA Automation Anywhere 360, reduciendo los tiempos operativos y errores humanos, mejorando la trazabilidad, eficiencia y cumplimiento regulatorio en la vinculación de nuevos asociados.

### Objetivos específicos  
- Validar y actualizar automáticamente el estado de tareas de “Punteo” a “Verificación” en aplicativo web de la Cooperativa.  
- Descargar y procesar la plantilla “Evidente” desde SharePoint (carpeta del cliente).  
- Activar vinculaciones según reglas de negocio definidas.  
- Generar y enviar reportes automáticos con los resultados del proceso.  
- Registrar logs de ejecución y errores para trazabilidad.

---

## 3. Alcance

### Procesos incluidos  
- Actualización de estados de tareas en aplicativo web de la Cooperativa.  
- Descarga, transformación y cargue de plantillas a Base de Datos desde SharePoint.  
- Activación de vinculaciones con validación de condiciones.  
- Generación y envío automático de reportes de resultados.

### Procesos fuera de alcance del Bot  
- Modificación manual de las plantillas por parte del Bot.  
- Validaciones que requieran intervención humana o interpretación subjetiva.  
- Procesamiento de plantillas con errores estructurales no corregidos.

---

## 4. Arquitectura del proceso  
- **Entradas:** Plantilla “Evidente” (Excel) desde SharePoint, estados de tareas “punteo” se descargan desde Aplicativo de la Cooperativa.  
- **Procesamiento:** Validación y actualización de estados, carga de datos, aplicación de reglas de activación.  
- **Salidas:** Reportes de tareas actualizadas, activaciones exitosas y fallidas, archivos de log.

---

## 5. Tecnologías utilizadas  
- Automation Anywhere 360  
- SQL Server  
- Excel  
- Aplicaciones Web

---

## 6. Resultados obtenidos  
- Reducción del tiempo de ejecución por operación (de 2:15 min a 45 segundos).  
- Automatización de más del 90% del proceso, con intervención solo ante errores.  
- Generación de reportes estandarizados y con trazabilidad completa.  
- Mejora en la calidad de la información cargada a aplicativos y Base de Datos.  
- Liberación de recursos humanos operativos.

---

## 7. Lecciones aprendidas  
- Es fundamental contar con plantillas estandarizadas y limpias antes de la ejecución.  
- La validación temprana de accesos y rutas compartidas evita detenciones del Bot.  
- La trazabilidad por logs permitió detectar errores específicos de estructura o red.  
- Automatizar la reportería facilita el seguimiento por parte de los analistas del proceso.

---

## 8. Confidencialidad  
Este documento ha sido elaborado con fines de divulgación técnica y comercial. Se han tratado los datos sensibles bajo la normativa de confidencialidad de la organización. No se expone información personal o confidencial de terceros.

---

## Contacto  
Synthetic.solution@gmail.com
