
# Synthetics Solutions - Proyecto RPA: Automatización de Emisión de Documentos Soporte DIAN

## Cliente / Industria  
Cooperativa del sector financiero – Unidad Financiera e Impuestos

## Desarrollado por  
Synthetics Solutions

## Fecha de creación  
Diciembre 2022

---

## Contenido  
1. Introducción
2. Objetivos
3. Alcance
4. Tecnologías utilizadas
5. Resultados obtenidos
6. Conclusiones estratégicas
7. Confidencialidad
8. Contacto

---

## 1. Introducción  
Este documento describe el desarrollo e implementación de un asistente RPA orientado a la generación automatizada de documentos soporte en formato XML requeridos por la Dirección de Impuestos y Aduanas Nacionales (DIAN). La necesidad surgió en un contexto crítico: el cliente había acumulado cerca de 25.000 documentos pendientes por emitir, producto de la falta de claridad normativa y la alta complejidad operativa del proceso, lo que ponía en riesgo el cumplimiento fiscal antes del cierre de año. El proceso original era completamente manual, demandando aproximadamente 30 minutos por registro, sin lineamientos claros y sin una herramienta eficiente para estandarizar la generación y envío. El asistente fue desarrollado como proyecto de emergencia en menos de un mes, incluyendo el diseño del flujo completo, la lógica para construir hasta 15 tipos distintos de documentos soporte, su cifrado en Código16, y su transmisión automatizada vía FTP a un proveedor autorizado, garantizando así el cumplimiento normativo en tiempo récord.

---

## 2. Objetivos

### Objetivo General  
Automatizar la emisión de documentos soporte en formato XML exigidos por la DIAN, mediante el uso de tecnología RPA en Automation Anywhere, con el fin de garantizar el cumplimiento tributario, reducir tiempos operativos y estandarizar el proceso de generación, cifrado y envío de documentos.

### Objetivos Específicos  
- Diseñar e implementar un flujo automatizado para la construcción de múltiples tipos de documentos soporte con estructuras XML diferenciadas.  
- Interpretar condiciones específicas del insumo estructurado entregado por el cliente para aplicar reglas de negocio.  
- Cifrar cada documento emitido utilizando el esquema Código16 requerido por el proveedor.  
- Transmitir de forma segura los archivos generados vía FTP a un tercero autorizado para su entrega ante la DIAN.  
- Registrar trazabilidad detallada de cada ejecución en un repositorio compartido.  
- Disminuir significativamente la intervención manual y el riesgo de errores humanos en la emisión documental.  
- Apoyar el diseño del proceso normativo ante la falta de lineamientos claros por parte de los entes fiscales.  

---

## 3. Alcance  
El asistente automatiza la generación masiva de documentos soporte exigidos por la DIAN, a partir de un archivo estructurado con múltiples registros. Para cada uno, aplica reglas específicas que determinan cuál de los 15 tipos de documentos construir, genera el archivo XML correspondiente con su estructura particular, realiza su cifrado en Código16 y lo transmite vía FTP a un proveedor externo. El proceso excluye la integración con sistemas contables o ERP, y se apoya en almacenamiento compartido para trazabilidad. También contempló la definición operativa del proceso, ya que este era completamente nuevo para la organización.

---

## 4. Tecnologías utilizadas  
- Automation Anywhere  
- Python  
- Estructuras XML personalizadas  
- Codificación Código16  
- Servidor FTP seguro  

---

## 5. Resultados obtenidos  
- Generación y envío completo de 25.000 documentos soporte en menos de un mes  
- Eliminación de riesgo tributario al cumplir con el cierre fiscal antes de la fecha límite  
- Ahorro operativo significativo: de 30 minutos por registro a segundos por ejecución automatizada  
- Asistente activo y reutilizable para futuras emisiones  
- Proyecto destacado por su respuesta rápida, innovación técnica y criticidad operativa  
- Presentado en concurso nacional de innovación organizado por la DIAN  

---

## 6. Conclusiones estratégicas  
- Generación y envío completo de 25.000 documentos soporte en menos de un mes  
- Eliminación de riesgo tributario al cumplir con el cierre fiscal antes de la fecha límite  
- Ahorro operativo significativo: de 30 minutos por registro a segundos por ejecución automatizada  
- Asistente activo y reutilizable para futuras emisiones  
- Proyecto destacado por su respuesta rápida, innovación técnica y criticidad operativa  
- Presentado en concurso nacional de innovación organizado por la DIAN  

---

## 7. Confidencialidad  
Este documento ha sido elaborado con fines de divulgación técnica y comercial. Se han tratado los datos sensibles bajo la normativa de confidencialidad de la organización. No se expone información personal o confidencial de terceros.

---

## 8. Contacto  
Synthetic.solutions5@gmail.com
