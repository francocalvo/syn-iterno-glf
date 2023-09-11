# Construcción de DWH en Synapse 54Cuatro

Vamos usar como datos el modelo de LEGO Catalog Database.

## Tareas

- [ ] Registrarse en Rebricable API.
- [ ] Conseguir permisos de Synapse para mi, Lau y Gaby
- [ ] Migrar dos tablas CONFIG_CARGAS y BITACORA_CARGAS a tabla Delta.

## Arquitectura

Las herramientas que vamos a utilizar dentro de Synapse son: ADF Pipelines,
notebooks, Azure Data Lake Storage Gen2 (ADLS), pools serverless de SQL y
tablas Delta.

### Ventajas de Delta

- Delta es un formato de **almacenamiento**, no un formato de archivo.
- Permite transacciones ACID.
- Permite operaciones de update, insert y merge.

### Orquestración

Vamos a utilizar los pipelines para generar cargas genéricas. Tenemos que
dividir tres tipos de situaciones: cargas iniciales, cargas incrementales y
cargas totales.

Para configurar las cargas que se van a utilizar, vamos a tomar la parte
de tablas Delta para guardar la configuración.

# Documentación de DWH Libertad

1. Conexiones y linked services.
2. Tablas de configuración dentro de pool dedicado de SQL.
