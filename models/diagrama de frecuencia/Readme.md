# 🤖 LUMEN // Diagrama de Secuencia de Pantallas Móviles

Un visualizador interactivo y catálogo de arquitectura UX/UI diseñado con estética **Cyberpunk HUD** para mapear, analizar y documentar el flujo de navegación de **22 pantallas móviles** del videojuego / companion app **LUMEN**.

---

## 📐 Descripción General

Este archivo es una aplicación interactiva (`DiagramaDeSketchesLumen.html`) desarrollada en HTML5, CSS3 y Vanilla JavaScript. Proporciona una interfaz tipo *Heads-Up Display* (HUD) que permite a diseñadores UX/UI, desarrolladores y arquitectos de software visualizar la arquitectura de navegación, bocetos reales a mano alzada en cuadrícula isométrica, transiciones, eventos de disparo (triggers) y especificaciones del flujo de la aplicación.

---

## ✨ Características Principales

1. **Visor de Sketches Reales**:
   - Catálogo completo con las 22 ilustraciones a mano alzada ubicadas en `assets/pantallas/`.
   - Efecto de perspectiva y rotación orgánica de bocetos.
   - Píldoras de etiquetas dinámicas (`ACCESO`, `SEGURIDAD`, `CARGA`, `INICIO`, `PERFIL`, `AJUSTES`, `EQUIPO`, `HABILIDADES`, `MISIONES`, `AVANCE`, `RÁNKINGS`, `CÓDEX`, `SISTEMA`).

2. **Modal de Inspección Detallada**:
   - Vista ampliada de alta fidelidad del sketch seleccionado.
   - Metadatos de ingeniería de software: ID, rol de usuario, disparador, acción principal y flujo de salida interactivo.
   - Botón guiado de "Seguir ruta principal" y navegación por teclado (← / → / Esc).

3. **Filtros por Rol y Búsqueda en Vivo**:
   - Filtros instantáneos: `Todas (22)`, `Shared (10)` y `Jugador (12)`.
   - Búsqueda en tiempo real por ID, nombre de pantalla o categoría temática.

---

## 📂 Estructura de Pantallas (22 Bocetos Reales)

El sistema organiza las 22 pantallas en 5 fases funcionales:

| ID | Nombre de Pantalla | Categoría | Rol | Archivo de Boceto | Destino(s) Principal(es) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **SCR-01** | Splash / Onboarding | Autenticación | Shared | `splash_screen.png` | `SCR-18`, `SCR-02` |
| **SCR-18** | Pantalla de Carga | Carga | Shared | `loading_screen.png` | `SCR-05`, `SCR-12` |
| **SCR-02** | Inicio de Sesión | Autenticación | Shared | `login_screen.png` | `SCR-05`, `SCR-03`, `SCR-04`, `SCR-19` |
| **SCR-03** | Registro de Cuenta | Autenticación | Shared | `register_screen.png` | `SCR-05`, `SCR-02` |
| **SCR-04** | Recuperación de Contraseña | Autenticación | Shared | `password_recovery_screen.png` | `SCR-02` |
| **SCR-19** | Bloqueo de Cuenta | Seguridad | Shared | `lock_account_screen.png` | `SCR-20`, `SCR-02` |
| **SCR-20** | Desbloqueo de Cuenta (OTP) | Seguridad | Shared | `unlock_account_screen.png` | `SCR-02`, `SCR-05` |
| **SCR-05** | Home / Dashboard | Dashboard | Jugador | `home_screen.png` | `SCR-14`, `SCR-15`, `SCR-07`, `SCR-06`, `SCR-08`, `SCR-17` |
| **SCR-06** | Perfil de Usuario | Perfil | Jugador | `profile_screen.png` | `SCR-13`, `SCR-05` |
| **SCR-13** | Configuración General | Configuración | Shared | `settings_screen.png` | `SCR-06`, `SCR-21`, `SCR-22`, `SCR-05` |
| **SCR-14** | Inventario y Equipamiento | Inventario | Jugador | `inventory_screen.png` | `SCR-16`, `SCR-05` |
| **SCR-16** | Árbol de Habilidades | Habilidades | Jugador | `skill_tree_screen.png` | `SCR-14`, `SCR-15`, `SCR-05` |
| **SCR-15** | Registro de Misiones | Misiones | Jugador | `quest_log_screen.png` | `SCR-07`, `SCR-12`, `SCR-05` |
| **SCR-07** | Progreso de Partida | Progreso | Jugador | `progress_user_screen.png` | `SCR-12`, `SCR-17`, `SCR-10` |
| **SCR-12** | Mapa de Zonas y Progreso | Progreso | Jugador | `zone_progress_map_screen.png` | `SCR-07`, `SCR-15`, `SCR-05` |
| **SCR-17** | Tabla de Clasificación | Social | Jugador | `leaderboard_screen.png` | `SCR-10`, `SCR-05` |
| **SCR-08** | Códex de Personajes | Códex | Jugador | `character_codex_screen.png` | `SCR-09`, `SCR-11`, `SCR-10` |
| **SCR-09** | Códex de Enemigos y Jefes | Códex | Jugador | `enemy_and_boss_codex_screen.png` | `SCR-11`, `SCR-08` |
| **SCR-10** | Logros / Achievements | Progreso | Jugador | `achievements_list_screen.png` | `SCR-11`, `SCR-07`, `SCR-05` |
| **SCR-11** | Fragmentos de Memoria | Códex | Jugador | `memory_fragments_screen.png` | `SCR-08`, `SCR-05` |
| **SCR-21** | Información del Software | Sistema | Shared | `about_software_screen.png` | `SCR-13`, `SCR-22`, `SCR-05` |
| **SCR-22** | Acerca del Equipo y Estudio | Sistema | Shared | `about_team_screen.png` | `SCR-21`, `SCR-13`, `SCR-05` |

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