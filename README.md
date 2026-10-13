# Proyecto Lumen

Presentación estratégica y documentación del proyecto Lumen. Este repositorio contiene un Canvas de modelo de negocio en HTML y material visual de referencia de M-4; no incluye el proyecto ejecutable del videojuego ni un backend.

## Contenido

- `models/canvas/proyecto_lumen_business_model_canvas.html`: Canvas interactivo, escena 3D y resumen de alcance.
- `assets/documentation/resources/M4_turnaround.png`: referencia visual de M-4 y alternativa de la escena 3D.
- `assets/vendor/three.module.js` y `assets/vendor/three.core.js`: Three.js 0.180.0, con su licencia MIT.
- `docs/architecture/m4toraound-architecture.html`: diagrama interactivo generado con Archify.
- `docs/architecture/README.md`: explicación de arquitectura, flujo y límites confirmados.
- `.archify/m4toraound-architecture-local.json`: fuente del diagrama.

## Ejecutar

Desde la raíz del repositorio, ejecuta `python -m http.server 8000` y abre `http://localhost:8000/models/canvas/proyecto_lumen_business_model_canvas.html` en un navegador moderno. Se usa HTTP para cargar el módulo local de Three.js. Google Fonts requiere conexión; se usan fuentes de sistema como alternativa. Si WebGL no está disponible, la escena muestra la imagen local de M-4. No se requiere un servidor de aplicaciones ni instalar paquetes.

El botón **Imprimir** usa el diálogo nativo del navegador; desde allí se puede guardar como PDF.

## Alcance

El material del proyecto describe un RPG isométrico de exploración y puzles de reparación protagonizado por M-4 y PIP en una metrópolis robótica abandonada, con un conflicto alrededor de CORE. Los segmentos, canales, ingresos, socios y costos del Canvas se presentan como hipótesis por validar. Las métricas de wishlists, descargas y playtests de la versión anterior no tenían fuentes verificables y se retiraron.

No hay código de Unity, Node/Express, API, base de datos, autenticación, Steam, Itch.io, PWA o analítica en este repositorio. Su mención en el Canvas anterior no demuestra que estén implementados.

## Dependencias

No hay gestor de paquetes ni proceso de compilación configurados. Three.js 0.180.0 está incluido localmente para la escena WebGL. Manrope y DM Mono se solicitan a Google Fonts. La impresión y exportación a PDF usan el navegador; no se añade una biblioteca PDF.
