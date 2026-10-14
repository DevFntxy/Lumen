# 🤖 LUMEN // Diagrama de Secuencia de Pantallas Móviles

Un visualizador interactivo y suite de arquitectura UX/UI diseñado con estética **Cyberpunk HUD** para mapear, analizar y documentar el flujo de navegación de **13 pantallas móviles** del videojuego / companion app **LUMEN**.

---

## 📐 Descripción General

Este archivo es una aplicación **single-file** (`LUMEN_Diagrama_frecuencia_pantallas.html`) desarrollada en HTML5, CSS3 y Vanilla JavaScript. Proporciona una interfaz interactiva tipo *Heads-Up Display* (HUD) que permite a diseñadores UX/UI, desarrolladores y arquitectos de software visualizar la arquitectura de navegación, transiciones, eventos de disparo (triggers) y especificaciones del flujo de la aplicación.

---

## ✨ Características Principales

1. **Diagrama de Nodos Interactivo (Canvas SVG)**:
   - Visualización por capas (*Tiers*) temporales y funcionales.
   - Renderizado dinámico de flechas con curvas de Bézier mediante SVG para mostrar la dirección de navegación.
   - Resaltado dinámico de rutas al interactuar con los botones disparadores (*triggers*).

2. **Matriz de Secuencia UX (Tabla)**:
   - Vista detallada en formato tabla con el mapa completo de transiciones: Pantalla Origen $\rightarrow$ Acción Disparadora $\rightarrow$ Pantalla Destino + Notas de UX/Lore.

3. **Modo Recorrido Guiado (Walkthrough Simulator)**:
   - Asistente flotante paso a paso que realiza un tour guiado a través del flujo principal de usuario, desplazando la vista y enfocando la pantalla activa.

4. **Filtros por Categoría**:
   - Permite aislar y examinar secciones específicas: `INICIO (1)`, `AUTH (3)`, `HUB (2)`, `PROGRESO (2)`, `CÓDEX (4)`, `AJUSTES (1)`.

5. **Integración con Archify AI**:
   - Generador automático de prompts estructurados en JSON listos para copiar o descargar como `LUMEN_Screens_Sequence_Config.json`, optimizados para alimentar agentes de IA y herramientas de documentación técnica.

6. **Renderizado de Wireframes en Canvas 2D**:
   - Esquemas gráficos dibujados mediante `<canvas>` como vista previa de respaldo cuando las imágenes de pantallas reales no están disponibles.

---

## 📂 Estructura de Pantallas (13 Nodos)

El sistema organiza las 13 pantallas en 6 capas funcionales (*Tiers*):

| ID | Nombre de Pantalla | Categoría | Pantalla(s) Destino Principales |
| :--- | :--- | :--- | :--- |
| **SCR-13** | Splash / Loading Screen | Inicio | `SCR-01` |
| **SCR-01** | Account Login | Autenticación | `SCR-04`, `SCR-02`, `SCR-03` |
| **SCR-02** | Account Registration | Autenticación | `SCR-01`, `SCR-04` |
| **SCR-03** | Password Recovery | Autenticación | `SCR-01` |
| **SCR-04** | Home Dashboard | Hub Central | `SCR-05`, `SCR-06`, `SCR-07`, `SCR-08` |
| **SCR-05** | User Profile & Account | Hub Central | `SCR-01`, `SCR-12` |
| **SCR-06** | Game Progress & Mission | Progreso | `SCR-04` |
| **SCR-07** | Achievements List | Progreso | `SCR-04` |
| **SCR-08** | Codex Main Index | Códex | `SCR-09`, `SCR-10`, `SCR-11` |
| **SCR-09** | Character Codex | Códex | `SCR-08` |
| **SCR-10** | Enemy & Boss Codex | Códex | `SCR-08` |
| **SCR-11** | Memory Fragments | Códex | `SCR-08` |
| **SCR-12** | App Settings & Audio | Ajustes | `SCR-05` |

---

## 🖼️ Configuración de Assets de Imagen

El archivo está preparado para vincular capturas/diseños reales en la carpeta de recursos. Para personalizar o reemplazar las imágenes de cada pantalla:

1. Coloca tus imágenes dentro de la ruta relativa del proyecto `/assets/pantallas/`.
2. Actualiza los atributos `src` en los elementos `<img>` dentro del HTML:

```html
<!-- Ejemplo para SCR-01 -->
<img id="img-SCR-01" src="/assets/pantallas/login_screen.png" alt="Login Screen">
```

> **Nota:** Si una imagen no carga o la ruta no existe, el sistema muestra el nombre y la estructura wireframe gráfica dibuja en el fondo.

---

## 🚀 Instrucciones de Uso y Despliegue

### Requisitos Previos
- Un navegador web moderno (Google Chrome, Mozilla Firefox, Microsoft Edge, Safari).
- Conexión a Internet (para cargar tipografías de Google Fonts e íconos de FontAwesome).

### Ejecución
1. Clona o descarga el repositorio en tu equipo.
2. Abre el archivo `LUMEN_Diagrama_frecuencia_pantallas.html` directamente en tu navegador (doble clic o mediante servidor local como Live Server en VS Code).

### Atajos / Acciones Útiles
- **Filtrar Pantallas**: Haz clic en los botones de la barra superior para aislar categorías.
- **Cambiar Modo de Vista**: Usa los botones centralizados para alternar entre **Diagrama**, **Matriz de Secuencia** y **Archify Prompt**.
- **Iniciar Recorrido**: Haz clic en `MODO RECORRIDO` para iniciar la guía paso a paso.
- **Recargar Imágenes**: Si actualizas los archivos en disco, haz clic en el botón `RECARGAR IMÁGENES`.

---

## 🛠️ Tecnologías Utilizadas

- **HTML5 & CSS3**: Estructura semántica, variables CSS (`:root`), Flexbox, CSS Grid y efectos Neón Cyberpunk.
- **JavaScript (Vanilla)**: Manipulación del DOM, cálculo de coordenadas para vectores SVG, manejo de modal/walkthrough y generador de JSON.
- **Librerías Externas (CDN)**:
  - FontAwesome 6.4.0 (Iconografía).
  - Google Fonts (*Orbitron*, *Rajdhani*, *JetBrains Mono*).

---

## 📝 Licencia y Créditos

Desarrollado para el proyecto **LUMEN Architecture // Serie Robótica (2026)**. Compatible con editores visuales y agentes IA de especificación de software (Archify Agent).