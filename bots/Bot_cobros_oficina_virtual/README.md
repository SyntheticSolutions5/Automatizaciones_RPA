
# Synthetics Solutions - Proyecto RPA: Automatización de Cobro de Comisiones Oficina Virtual  

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
En el marco de la estrategia de transformación digital impulsada por el Banco, se identificó la necesidad de automatizar el proceso de cobro de comisiones por el uso de la Oficina Virtual Empresarial. Esta iniciativa responde a una problemática operativa frecuente: la baja efectividad en la recuperación de las comisiones correspondientes al uso del servicio, derivada principalmente de la falta de fondos en las cuentas de los clientes y la ausencia de validaciones retroactivas de meses anteriores.  
El proceso anteriormente manual, repetitivo y propenso a errores, representaba un cuello de botella para las áreas financieras, con una tasa efectiva de recaudo inferior al 25%. A través de la implementación de esta automatización basada en la plataforma Automation Anywhere 360, se logró transformar una operación crítica en un flujo digital trazable, escalable y resiliente. Este documento describe con detalle el diseño, funcionamiento y resultados de dicha automatización.  

---

## 2. Objetivos  

### Objetivo general:
Automatizar de forma desatendida el proceso completo de cobro por uso de Oficina Virtual Empresarial para clientes del Banco, incluyendo validaciones, cálculos de comisión e IVA, gestión de excepciones, aplicación de notas débito en Taylor Financiero, y generación de reportes diarios y mensuales.  

### Objetivos específicos:
- Validar la existencia de insumos mensuales en SharePoint y cargarlos a la base de datos RPA.  
- Calcular tarifas según tipo de cliente (asociado/no asociado) y convenios exonerados (PAEF).  
- Integrar con AS400 (Taylor Financiero) para aplicar notas débito de comisión e IVA por cliente.  
- Generar y distribuir automáticamente reportes diarios y mensuales a stakeholders.  
- Asegurar trazabilidad, control de excepciones y cumplimiento de requisitos técnicos y de seguridad.  
- Incrementar la eficiencia operativa del proceso, aumentando la tasa efectiva de recaudo.  

---

## 3. Alcance  
**Procesos incluidos:**  
- Validación de insumos en SharePoint.  
- Carga de datos a tablas RPA (DetalleConvenios, OtrosConvenios, EstadosCuentas, PAEF).  
- Determinación dinámica de tarifas aplicables.  
- Cálculo de comisión e IVA y validación de saldo.  
- Aplicación de cobros en Taylor Financiero.  
- Registro en base de datos de transacciones exitosas y fallidas.  
- Generación de reportes en Excel y PDF.  
- Diligenciamiento automático del formato Tapalote.  

**Procesos fuera de alcance:**  
- Gestión manual de insumos inconsistentes o incompletos.  
- Validaciones jurídicas sobre convenios.  
- Procesamiento de cuentas sin convenio vigente o sin información estructurada.  
- Reintentos por errores operativos externos a la plataforma (caídas de AS400, bloqueo de usuario).  

---

## 4. Arquitectura del proceso  

| Componente      | Descripción Técnica                                                 |
|-----------------|-------------------------------------------------------------------|
| Entradas (Excel)| Archivo "Maestro de Convenios", archivo "PAEF/PAP", estructura predefinida. |
| Procesamiento   | Validaciones, cálculos financieros, carga a BD, conexión con Taylor Financiero (AS400). |
| Salidas         | Reportes en Excel y PDF, actualizaciones en BD RPA, notificaciones automáticas. |
| Ejecución       | Programada en Control Room A360                                   |  

---

## 5. Tecnologías utilizadas  
- Automation Anywhere 360 – Herramienta de desarrollo  
- SQL Server – Almacenamiento estructurado de registros, configuraciones y trazabilidad  
- Microsoft Excel – Insumos, reportes y plantillas como Tapalote  
- SharePoint – Fuente de insumos oficiales para procesamiento  
- AS400 (Taylor Financiero)  

---

## 6. Resultados obtenidos  
- Reducción del tiempo operativo: de jornadas manuales de hasta 16 horas semanales a una ejecución automatizada de aproximadamente 20 minutos diarios (dependiendo cantidad de registros por procesar).  
- Incremento de cobertura de cobros: se validan todas las cuentas activas con retroactividad de hasta 2 meses, ampliando la base efectiva de recaudo.  
- Estandarización de reportes: los reportes se generan en formatos uniformes y son almacenados en rutas definidas para fácil auditoría.  
- Mejora en la trazabilidad y control: cada etapa del proceso se registra en tablas dedicadas, con trazabilidad de errores y logs detallados por HU.  
- Minimización de errores manuales: los cálculos de IVA y comisión, así como los cruces con PAEF, se realizan con lógica programática validada.  
- Integración robusta con Taylor Financiero: el Bot utiliza la interfaz de terminal AS400 con lógica de reintentos y validación de mensajes transaccionales.  

---

## 7. Lecciones aprendidas  
- Validación anticipada de accesos y permisos (SharePoint, AS400, BD): clave para evitar fallos en tiempo de ejecución.  
- Importancia de centralizar las configuraciones en una tabla control de variables: facilita el mantenimiento, despliegue y trazabilidad.  
- Estrategia de cobro parcial: permitió aprovechar saldos menores en cuentas, optimizando el recaudo sin perder oportunidades.  
- Estándar de nomenclatura y estructura de carpetas: simplifica la navegación, respaldo y auditoría del proceso.  
- Uso del módulo de terminal de A360: requiere precisión en el uso de coma decimal y navegación por comandos tipo sendText.  
- Automatización de Tapalote: permitió cerrar el proceso con documentación formal sin intervención humana.  

---

## 8. Confidencialidad  
Este documento ha sido elaborado con fines de divulgación técnica y comercial. Se han tratado los datos sensibles bajo la normativa de confidencialidad de la organización. No se expone información personal o confidencial de terceros.

---

## 9. Contacto  
Synthetic.solutions5@gmail.com
