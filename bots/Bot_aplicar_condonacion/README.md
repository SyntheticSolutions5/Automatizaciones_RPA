# Synthetics Solutions - Proyecto RPA: Automatización de Aplicar Condonación de Carteras

## Cliente / Industria  
Bancario – Financiero – Crédito y Cartera

## Desarrollado por  
Synthetics Solutions

## Fecha de creación  
Agosto 2024

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
9 Contacto

---

## 1. Introducción  
Este documento describe la solución de automatización implementada para el proceso de Aplicación de Condonaciones de cartera del Banco, mediante el uso de tecnologías RPA, específicamente con Automation Anywhere 360 y la integración con sistemas como Taylor Financiero (AS400) y bases de datos corporativas en SQL Server.  
La automatización surge como respuesta a la necesidad de digitalizar y agilizar la gestión de actas de condonación, eliminar los errores derivados de la intervención humana, y asegurar el cumplimiento de las políticas contables y normativas en el proceso de cancelación de obligaciones por cliente.  
Esta automatización, desarrollada como un asistente desatendido, opera diariamente sobre archivos compartidos en red, realizando validaciones, cargues, creación de conceptos contables, ejecución en sistemas legacy, generación de reportes y comunicaciones automáticas a las partes interesadas.

---

## 2. Objetivos

### Objetivo general  
Diseñar e implementar un asistente RPA robusto y auditable que automatice de forma integral el ciclo de recepción, validación, creación y aplicación de condonaciones, permitiendo cumplir de manera eficiente con las solicitudes de los analistas de cartera y garantizando la trazabilidad y conformidad operativa.

### Objetivos específicos  
- Validar la estructura y contenido de los insumos de condonaciones enviados por los analistas.  
- Cargar los registros a la base de datos RPA para su posterior procesamiento.  
- Crear tres conceptos contables específicos en Taylor Financiero: CONDOPYG, CONDONA y COFINOCA.  
- Aplicar la condonación en función de los valores autorizados para cada cliente y obligación.  
- Generar reportes detallados de ejecución y estado por registro, en formatos Excel y PDF.  
- Enviar notificaciones automáticas al equipo funcional y de soporte sobre el estado del proceso.  
- Gestionar excepciones operativas de manera controlada, con logs y alertas inmediatas.

---

## 3. Alcance

### Procesos incluidos  
- Validación y cargue de insumos desde carpeta compartida.  
- Conexión y operación en Taylor AS400 para creación de conceptos y condonaciones.  
- Validación cruzada entre insumo y obligaciones vigentes en el sistema financiero.  
- Aplicación de reglas de negocio para condonación total o parcial.  
- Registro de ejecución y observaciones en base de datos SQL Server.  
- Generación de reportes operativos y Tapalote.  
- Envío de reportes automáticos por correo a las partes interesadas.

### Procesos fuera de alcance  
- Aprobación de solicitudes de condonación (fase previa).  
- Validación jurídica de los documentos enviados.  
- Corrección de errores en insumos mal diligenciados.  
- Procesos específicos en SAT o TARCRED (incluidos en versiones anteriores, no en esta automatización).  
- Creación de usuarios o mantenimiento del sistema Taylor.

---

## 4. Arquitectura del proceso  

| Componente       | Descripción                                                             |
|------------------|-------------------------------------------------------------------------|
| Entradas         | Archivos Excel con actas de condonación desde carpeta compartida.       |
| Procesamiento    | Validación, cargue en DB, ejecución en Taylor AS400, actualización de estados. |
| Bases de datos   | SQL Server – Tablas de staging, configuración, ejecución y seguimiento.  |
| Aplicaciones externas | Taylor Financiero (AS400), Excel 365.                              |
| Salidas          | Reporte de ejecución (Excel y PDF), Tapalote PDF, logs de ejecución.     |
| Orquestación     | Automation Anywhere Control Room.                                       |

---

## 5. Tecnologías utilizadas  
- Automation Anywhere 360 – Herramienta de desarrollo  
- SQL Server – Almacenamiento estructurado de registros, configuraciones y trazabilidad.  
- Microsoft Excel – Insumos, reportes y plantillas como Tapalote.  
- AS400 (Taylor Financiero)

---

## 6. Resultados obtenidos  
- Procesamiento automatizado 100% de las actas válidas, con reglas específicas por cliente y concepto.  
- Reducción del tiempo de ejecución: de 3 minutos por cada usuario para aplicar esta condonación a 50 segundos por usuario realizando el proceso por medio del Bot.  
- +97% de efectividad en procesamiento, incluyendo validaciones y aplicación en AS400.  
- Minimización de errores humanos: especialmente en digitación y validación de montos.  
- Auditoría completa: mediante reportes, logs, campos de estado y observaciones.  
- Estandarización del flujo: desde insumos hasta entregables contables.

---

## 7. Lecciones aprendidas  
- Validaciones tempranas del insumo (estructura, columnas, formato) evitan bloqueos posteriores en producción.  
- Manejo de excepciones centralizado: permite trazabilidad en tiempo real y evita reinicios innecesarios del flujo completo.  
- Separación modular por HU: garantiza claridad en fases y permite reinicios parciales ante errores.  
- Integración con base de datos configurable: facilitó el mantenimiento y parametrización sin tocar el código del Bot.  
- Uso de Tapalote: asegura cierre operativo legal, útil para controles internos y auditorías.  
- Control de versiones del bot: permitió incorporar nuevas funcionalidades como cancelación de tarjetas y generación en PDF sin afectar estabilidad previa.

---

## 8. Confidencialidad  
Este documento ha sido elaborado con fines de divulgación técnica y comercial. Se han tratado los datos sensibles bajo la normativa de confidencialidad de la organización. No se expone información personal o confidencial de terceros.

---

## 9. Contacto  
Synthetic.solutions5@gmail.com
