
# Synthetics Solutions - Proyecto RPA: Automatización de Conciliaciones Bancarias

## Cliente / Industria  
Grupo Empresarial del sector cooperativo – Área Financiera

## Desarrollado por  
Synthetics Solutions

## Fecha de creación  
Junio 2024

---

## Contenido  
1. Introducción
2. Objetivos
3. Alcance
4. Tecnologías utilizadas
5. Resultados obtenidos
6. Confidencialidad
7. Contacto

---

## 1. Introducción  
Este documento describe el desarrollo e implementación de un asistente RPA encargado de automatizar el proceso de conciliación de cuentas por pagar en la cooperativa. Antes de la automatización, este proceso era completamente manual y lo ejecutaban seis analistas financieros. Cada día, los analistas descargaban reportes de tres plataformas distintas (Oracle Cloud, Cen Financiero y SharePoint) para realizar la validación de 13 cuentas, lo que representaba un desafío en términos de tiempo y precisión, ya que solo se validaba una pequeña parte de la facturación.  
El asistente, desarrollado y liderado por Synthetic Solution, permite la validación automática de todas las cuentas por pagar, realizando conciliaciones por tercero, documento, saldo, antigüedad de saldos y fecha. El bot compara los datos de las plataformas internas y alerta si alguna cuenta se encuentra descuadrada, notificando de inmediato a los responsables. Con esta solución, el tiempo de validación se redujo significativamente y se mejoró la confiabilidad y trazabilidad de las operaciones contables.

---

## 2. Objetivos

### Objetivo General  
Automatizar el proceso de conciliación contable de 13 cuentas por pagar mediante el uso de RPA en Automation Anywhere, con el fin de optimizar el tiempo operativo, mejorar la precisión en las conciliaciones y permitir una validación 100% del proceso en lugar de una muestra limitada.

### Objetivos Específicos  
- Extraer automáticamente los reportes contables de Oracle Cloud, Cen Financiero y SharePoint.  
- Realizar la conciliación de las 13 cuentas, abarcando validaciones por tercero, documento, saldo, antigüedad de saldos y fecha de imputación.  
- Establecer una holgura mínima de diferencia permitida en cada cuenta para determinar si hay descuadres.  
- Automatizar las notificaciones a los responsables de las cuentas descuadradas y generar reportes con el resultado de la conciliación.  
- Almacenar todos los resultados y logs en una carpeta compartida para su trazabilidad.  
- Optimizar la carga operativa del equipo humano, permitiendo que el proceso de conciliación sea ejecutado automáticamente cada madrugada.

---

## 3. Alcance  
El asistente RPA automatiza la conciliación diaria de 13 cuentas por pagar, extrayendo datos de tres plataformas internas: Oracle Cloud, Cen Financiero y SharePoint. El proceso incluye la validación completa del 100% de los datos, en lugar de un muestreo como se hacía previamente. El bot ejecuta las siguientes tareas:  
- Descarga automática de reportes de las plataformas especificadas.  
- Validación cruzada de datos de las tres plataformas, para verificar que los saldos, documentos y fechas coincidan correctamente.  
- Si un descuadre se encuentra fuera de la holgura mínima, el bot envía notificaciones automáticas a los analistas responsables de la cuenta.  
- Generación de reportes consolidados con resultados y detalles de las discrepancias detectadas.  
- Almacenamiento de los resultados y logs en una carpeta compartida en la organización para su trazabilidad.  
El proceso se ejecuta diariamente en la madrugada, asegurando que los analistas encuentren la conciliación lista cada mañana para su revisión y corrección si es necesario.

---

## 4. Tecnologías utilizadas  
- Automation Anywhere (RPA)  
- Python (Para procesamiento y validación de datos)  
- SQL Server (Base de datos para almacenamiento de resultados)  
- Microsoft Excel (Herramienta para la visualización de reportes y análisis de datos)  
- SharePoint (Almacenamiento y trazabilidad de logs y resultados)  

---

## 5. Resultados obtenidos  
- Validación 100% de los saldos de las 13 cuentas por pagar, eliminando el muestreo anterior.  
- Reducción significativa en el tiempo de conciliación: de varios días a solo unos minutos por ciclo.  
- Notificación automática a los responsables ante cualquier descuadre detectado, mejorando la respuesta ante inconsistencias.  
- Aumento de la precisión en la conciliación contable y disminución de errores humanos.  
- Automatización diaria del proceso, ejecutado a la madrugada para facilitar la revisión por parte de los analistas.  
- Reconocimiento interno al proyecto, mejorando la operativa financiera y el control contable dentro de la organización.

---

## 6. Confidencialidad  
Este documento ha sido elaborado con fines de divulgación técnica y comercial. Se han tratado los datos sensibles bajo la normativa de confidencialidad de la organización. No se expone información personal o confidencial de terceros.

---

## 7. Contacto  
Synthetic.solutions5@gmail.com
