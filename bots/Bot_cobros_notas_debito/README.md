
# Synthetics Solutions - Proyecto RPA: Automatización de Cobro de Comisiones Notas Débito

## Cliente / Industria  
Bancario – Financiero - Captaciones

## Desarrollado por  
Synthetics Solutions

## Fecha de creación  
Agosto 2023

---

## Contenido  
1. Introducción
2. Objetivos
3. Alcance
4. Arquitectura del proceso
5. Tecnologías utilizadas
6. Resultados obtenidos
7. Lecciones aprendidas
8. Confidencialidad
9. Contacto

---

## 1. Introducción  
Como parte de las estrategias de eficiencia operativa lideradas por el equipo de Finanzas del Banco, se identificó una tarea crítica y recurrente que presentaba alta dependencia de la intervención manual: la aplicación de notas débito para el cobro de comisiones asociadas a operaciones financieras diversas, registradas y gestionadas por el área de Contabilidad.  
El procedimiento, hasta entonces manual, implicaba revisar grandes volúmenes de registros, consolidar información dispersa en múltiples formatos, aplicar reglas de cálculo heterogéneas y finalmente generar los archivos para aplicación en sistemas como Taylor Financiero (AS400). Estas actividades no solo eran intensivas en tiempo, sino que estaban sujetas a errores humanos, duplicidades, omisiones y poca trazabilidad.  
A través de esta automatización basada en Automation Anywhere 360, se logró estructurar un flujo desatendido, robusto y auditable que garantiza una aplicación precisa, masiva y documentada de comisiones mediante notas débito. Este documento describe los componentes clave del proceso automatizado, su arquitectura, lógica técnica y resultados obtenidos.

---

## 2. Objetivos

### Objetivo general  
Desarrollar e implementar un asistente RPA que automatice integralmente el proceso de cobro de comisiones por medio de notas débito, incluyendo validación de insumos, cálculo de valores, interacción con AS400, control de errores y reportería centralizada.

### Objetivos específicos  
- Validar insumos provenientes de reportes contables en SharePoint y cargarlos a la base RPA.  
- Filtrar, consolidar y estandarizar los valores a cobrar, aplicando reglas y fórmulas específicas.  
- Ejecutar la aplicación masiva de notas débito en AS400, por cliente y tipo de cobro.  
- Generar reportes detallados por cada jornada de ejecución (archivos Excel y PDF).  
- Clasificar las transacciones entre exitosas, con error, repetidas o con saldos insuficientes.  
- Generar automáticamente el formato Tapalote para fines de control contable y legal.  
- Enviar notificaciones automáticas con los resultados a los responsables del proceso.

---

## 3. Alcance

### Procesos incluidos  
- Validación y limpieza del archivo de entrada con movimientos a cobrar.  
- Carga a la tabla B12_CobroNotaDebito los registros a procesar.  
- Cálculo de valores: comisión, IVA, y "cuatro por mil" por separado.  
- Verificación de saldos antes de ejecutar el cobro.  
- Aplicación de la nota débito en Taylor Financiero mediante terminal AS400.  
- Registro de cada transacción con su estado y código de respuesta.  
- Generación de reportes automáticos (resultado + Tapalote).  
- Limpieza y archivado de datos procesados.

### Procesos fuera de alcance  
- Validación jurídica de cada cobro.  
- Procesamiento de insumos no estructurados o manualmente editados.  
- Gestión de errores originados por caída de sistemas externos (AS400, SharePoint).  
- Reintentos automáticos fuera del flujo de ejecución diario.  
- Cálculo de tarifas no establecidas en las plantillas base.

---

## 4. Arquitectura del proceso  

| Componente       | Descripción Técnica                                                        |
|------------------|---------------------------------------------------------------------------|
| Entradas         | Reporte de movimientos (Excel) bajo estructura predeterminada.            |
| Procesamiento    | Validación, transformación de datos, cálculos, segmentación por tipo de comisión. |
| Base de Datos    | SQL Server – Tablas para trazabilidad, históricos y configuración.         |
| Sistemas externos| AS400 (Taylor Financiero) – Aplicación de notas débito vía terminal.       |
| Salidas          | Archivos Excel, PDF, Tapalote, registros en tablas RPA.                    |
| Orquestación     | Automation Anywhere Control Room.                                          |

---

## 5. Tecnologías utilizadas  
- Automation Anywhere 360 – Herramienta de desarrollo  
- SQL Server – Almacenamiento estructurado de registros, configuraciones y trazabilidad.  
- Microsoft Excel – Insumos, reportes y plantillas como Tapalote.  
- AS400 (Taylor Financiero)

---

## 6. Resultados obtenidos  
- Ejecución diaria confiable: El proceso se ejecuta diariamente sin intervención, asegurando cumplimiento oportuno y sin rezagos.  
- +95% de efectividad en cobros: Los valores calculados y ejecutados concuerdan con las reglas contables, aumentando la precisión operativa.  
- Reducción de errores humanos: Eliminación de errores por digitación, fórmulas erradas o saldos mal interpretados.  
- Estandarización contable: Todos los movimientos quedan reflejados en los documentos Tapalote y en BD.  
- Tiempo de procesamiento reducido: El ciclo completo de cobro, antes de hasta 6 horas cada semana, actualmente su duración es de 15 minutos diarios (dependiendo la cantidad de registros).  
- Auditoría trazable: Cada movimiento queda registrado en tablas con estado, código de error, timestamp y responsable técnico.  
- Cumplimiento normativo: El cálculo de retenciones, IVA y cargos adicionales se apega a la normatividad vigente.

---

## 7. Lecciones aprendidas  
- Revisión previa del insumo: Pequeñas diferencias en los títulos de columnas o formatos pueden detener la ejecución. Se debe garantizar una estructura 100% estandarizada.  
- Separación de cálculos intermedios: Incluir el “cuatro por mil” tanto para comisión como para IVA evitó inconsistencias y permitió transparencia en auditoría.  
- Manejo de errores en AS400: La navegación por terminal es sensible a cambios en el layout, por lo que el manejo de excepciones y reintentos es crucial.  
- Uso del formato Tapalote como cierre del proceso: Este documento consolidado permite control fiscal, financiero y contable de cada ejecución.  
- Control de duplicidad en base de datos: Asegurar que un cliente no sea cobrado más de una vez ante reinicios del bot.  
- Automatización resiliente: Aunque el bot es desatendido, los mensajes de error o ejecución fallida son enviados por correo para intervención humana rápida.

---

## 8. Confidencialidad  
Este documento ha sido elaborado con fines de divulgación técnica y comercial. Se han tratado los datos sensibles bajo la normativa de confidencialidad de la organización. No se expone información personal o confidencial de terceros.

## 9. Contacto  
Synthetic.solutions5@gmail.com
