# Auditoría de Infraestructura Cloud - TechNova

Este repositorio contiene la auditoría técnica realizada sobre el catálogo de servidores de **TechNova Cloud**. El objetivo es extraer información crítica de seguridad, mantenimiento y eficiencia energética utilizando consultas **XPath**.

## Archivos del Proyecto

* `CatalogoCloud.xml`: Base de datos de la infraestructura en formato XML.
* `auditoria_Gonzalez_Penha_Diego.xbook`: Notebook de VS Code con las misiones de auditoría y las consultas XPath ejecutadas.

## Misiones de Auditoría

A continuación se detallan las consultas realizadas:

### 1. Mapeo de Seguridad (París)
**Objetivo:** Identificar puertos abiertos en el centro de datos de París.
* **Consulta:** `/catalogo_cloud/centro_datos[@ubicacion='Paris']//servicio/@puerto`

### 2. Auditoría de Mantenimiento
**Objetivo:** Verificar la versión del Sistema Operativo del servidor de base de datos (`srv-db-01`).
* **Consulta:** `//servidor[@id='srv-db-01']/software/so/@version`

### 3. Inventario de Alta Capacidad
**Objetivo:** Listar discos con capacidad igual o superior a 8 TB.
* **Consulta:** `//disco[@capacidad_tb >= 8]`

### 4. Eficiencia Energética
**Objetivo:** Localizar el primer servidor en estado "apagado" para revisión de consumo.
* **Consulta:** `(//servidor[@estado='apagado'])[1]`

### 5. Desafío Auditor Senior
**Objetivo:** Identificar la arquitectura de CPU de servidores que disponen de GPU.
* **Consulta:** `//servidor[hardware/gpu]/hardware/cpu/@arquitectura`
