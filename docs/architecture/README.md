# Arquitectura documentada

## Resumen

La entrega comprobable es un sitio estático. `models/canvas/proyecto_lumen_business_model_canvas.html` concentra la estructura, los estilos y el comportamiento de presentación. El navegador renderiza las nueve tarjetas, el diálogo informativo, la escena Three.js y el documento imprimible. No hay capa de servidor ni almacenamiento del producto en este repositorio.

El diagrama interactivo está en [m4toraound-architecture.html](m4toraound-architecture.html); la especificación fuente está en [m4toraound-architecture-local.json](../../.archify/m4toraound-architecture-local.json).

## Componentes y responsabilidades

| Componente | Responsabilidad | Evidencia |
| --- | --- | --- |
| Página Canvas | Premisa, nueve bloques, detalles expandibles, navegación e impresión. | `models/canvas/proyecto_lumen_business_model_canvas.html` |
| Escena M-4 | Geometría, materiales, iluminación y rotación por arrastre en tiempo de ejecución. | Módulo Three.js de la página |
| Three.js 0.180.0 | Renderizado WebGL; archivos locales con licencia MIT. | `assets/vendor/three.module.js` y `three.core.js` |
| Referencia de M-4 | Imagen local de respaldo si falla WebGL o la carga de módulos. | `assets/documentation/resources/M4_turnaround.png` |
| Google Fonts | Manrope y DM Mono, con fuentes de sistema como alternativa. | Hoja de estilos de la página |
| Archify | Genera el HTML autónomo para explorar el diagrama de arquitectura. | `.archify/m4toraound-architecture-local.json` |

## Flujo principal

1. La persona abre la página a través de un servidor HTTP estático.
2. El navegador presenta la página y sus nueve bloques.
3. La escena crea geometría 3D con Three.js local. Si falla WebGL o el módulo, se conserva visible la imagen local.
4. La impresión llama al diálogo nativo del navegador, que puede guardar el documento como PDF.

La escena no consulta servicios del juego ni guarda datos. No hay un flujo de frontend a backend o de persistencia que se pueda documentar como existente.

## Decisiones y límites

- Se conserva una página HTML porque el repositorio original no tenía framework, gestor de paquetes, proceso de compilación o servidor de aplicaciones.
- Three.js 0.180.0 se incluye en `assets/vendor/` con la licencia MIT. El navegador necesita servir la página por HTTP para permitir la carga del módulo local.
- Google Fonts sigue siendo una dependencia externa opcional; las fuentes de sistema sirven de alternativa.
- El turnaround de M-4 se usa como respaldo visual, no se presenta como el modelo 3D.
- `prefers-reduced-motion` detiene el balanceo automático. La rotación manual continúa disponible.
- La impresión usa CSS de impresión y el navegador; no se implementa una función de generación PDF propia.
- El Canvas original mencionaba Unity, Node/Express, API, Steam, Itch.io, FMOD, comunidad y métricas de playtests. No hay módulos, configuración o fuentes de datos que confirmen esas afirmaciones aquí; no se dibujan como arquitectura existente.

## Modelo estratégico

La premisa descrita es una aventura de rol isométrica, de exploración y puzles de reparación, con M-4, PIP, una ciudad robótica abandonada y CORE. Los nueve bloques están presentes. Los segmentos, canales, relaciones, alianzas, actividades, recursos, costos e ingresos son hipótesis o propuestas: el repositorio no incluye datos de mercado, equipo, presupuesto, publicación o pruebas que los confirmen.

## Verificación de Archify

Archify CLI estuvo disponible en la instalación local de la skill. La especificación se validó con el perfil `showcase`: 9 de 9 comprobaciones, cero errores de composición y cero advertencias. `deliver` generó un HTML autónomo. `visual-check` pasó en Chrome en 1440×900, 1600×1000, 1920×1080 y 2048×1320, con tema claro y oscuro. Esta comprobación es del diagrama de arquitectura.

## Evolución recomendada

- Añadir el repositorio del juego o artefactos ejecutables para documentar motor, subsistemas, infraestructura e integraciones reales.
- Validar público, canales, estrategia de publicación y presupuesto con investigación o decisiones del equipo.
- Si el proyecto se convierte en una aplicación mayor, versionar y revisar las dependencias estáticas y su distribución.
