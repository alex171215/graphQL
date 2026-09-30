# Bitácora - Laboratorio Semana 4 GraphQL

## 1. Comparación REST vs GraphQL
**Pregunta:** ¿Cuántas llamadas REST necesitarías para obtener "todos los productos, solo nombres, más el detalle de uno" y cómo se compara con GraphQL?

**Respuesta:**
- En **REST** se necesitarían al menos **2 llamadas**:
  1. `GET /api/v1/productos` para obtener la lista de todos los productos (lo cual devolvería todos los campos de cada producto, generando *overfetching* de datos innecesarios si solo queríamos los nombres).
  2. `GET /api/v1/productos/:id` para obtener el detalle de un producto específico.
- En **GraphQL**, todo esto se logra con **1 sola llamada**, y además únicamente pedimos los campos exactos que nos interesan (ej. solo el `nombre`), evitando el exceso de transferencia de datos.

## 2. Análisis del Paso 6 (Conexión a REST)
**Nota:** En el paso 6 se sustituyó la variable `catalogo` (que vivía en memoria dentro del resolver) por `HttpService` y `HttpModule`. La ventaja principal es que la definición de los métodos del resolver (`productos` y `productoPorId`) se mantuvo prácticamente igual para el cliente de GraphQL. Las *queries* no cambiaron en absoluto, lo único que se modificó fue la **fuente de datos** subyacente. Esto demuestra cómo GraphQL funciona como un excelente orquestador (o *gateway*) de APIs subyacentes.

## 3. Declaración de uso de IA
### Declaración de uso de IA
- **Herramienta(s):** Antigravity AI (Asistente de código)
- **Nivel de uso:** 3 (Borrador / Ejecución bajo supervisión)
- **Qué se le pidió:** Generar la base de código NestJS, configurar `@nestjs/graphql`, conectar el `HttpService` con la API pública, e implementar el reto del método `productosBaratos`.
- **Qué se modificó/verificó manualmente:** La IA ejecutó los pasos en orden, y el usuario revisó que la base de código cumpla con los requisitos del taller, que el puerto responda correctamente y que la bitácora cumpla las especificaciones.
