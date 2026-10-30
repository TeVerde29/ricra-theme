# Ricra Theme — Colección de temas de color para Visual Studio Code

> Colección de temas de color para Visual Studio Code, con variantes clara, oscura y de alto contraste.

![Estado: activo](https://img.shields.io/badge/estado-activo-green)
![VS Code Theme](https://img.shields.io/badge/tema-VS%20Code-294635)
![Licencia: MIT](https://img.shields.io/badge/licencia-MIT-4F7256)

## Capturas

| Tea Green Light | Tea Green Dark |
|---|---|
| ![Vista previa de Tea Green Light en Visual Studio Code](./screenshots/tea-green-light.png) | ![Vista previa de Tea Green Dark en Visual Studio Code](./screenshots/tea-green-dark.png) |

Quien escribe código en Visual Studio Code elige entre los temas de Ricra Theme para editar archivos de texto, configuración y código fuente.

## Tabla de contenidos

- [Descripción](#descripción)
- [Descarga](#descarga)
- [Características principales](#características-principales)
- [Stack tecnológico](#stack-tecnológico)
- [Arquitectura](#arquitectura)
- [Instalación y uso](#instalación-y-uso)
- [Requisitos del sistema](#requisitos-del-sistema)
- [Formato de los archivos de tema](#formato-de-los-archivos-de-tema)
- [Buenas prácticas de uso](#buenas-prácticas-de-uso)
- [Notas de publicación](#notas-de-publicación)
- [Roadmap](#roadmap)
- [Licencia](#licencia)
- [Autor](#autor)

## Descripción

Ricra Theme es una extensión de Visual Studio Code que provee diez variantes de color: dos originales (Tea Green Light y Tea Green Dark) y ocho nuevas (Ricra Andromeda, Ricra GitHub Dark, Ricra One Dark Pro, Ricra Dracula, Ricra Tokyo Night, Ricra Night Owl, Ricra Ayu Mirage y Ricra Shades of Purple). Los archivos de tema viven en la carpeta `themes/`.

La idea de fondo es ofrecer una paleta inspirada en hojas de té verde, matcha, verde salvia y tonos crema para los temas Tea Green, y replicar estilos reconocibles como Andromeda, GitHub Dark, One Dark Pro, Dracula, Tokyo Night, Night Owl, Ayu Mirage y Shades of Purple para los temas Ricra. Los temas evitan verdes neón, fondos negros puros y excesos de glassmorphism.

Ambos archivos definen tres secciones: `colors` (interfaz de usuario: editor, sidebar, pestañas, terminal, botones, Git), `tokenColors` (sintaxis del editor mediante scopes de TextMate) y `semanticTokenColors` (tokens provistos por servidores de lenguaje LSP: clase, función, variable, parámetro, etc.). El resaltado semántico se activa cuando el servidor de lenguaje correspondiente lo proporciona.

## Descarga

| Capa | URL |
|---|---|
| Repositorio | https://github.com/TeVerde29/ricra-theme.git |
| Página del proyecto | https://github.com/TeVerde29/ricra-theme#readme |
| Reportar errores | https://github.com/TeVerde29/ricra-theme/issues |
| Paquete local | `ricra-theme-1.0.2.vsix` |

## Características principales

- **Diez variantes de tema:** `Tea Green Light` y `Tea Green Dark` (claro y oscuro originales), más ocho temas Ricra declarados en `package.json` bajo `contributes.themes`.
- **Colores de interfaz coherentes:** fondo, superficie, texto, bordes, foco y estados de éxito, advertencia, error e información comparten tokens entre variantes.
- **Colores de sintaxis:** `tokenColors` asigna colores a comentarios, cadenas, números, palabras clave, funciones, clases, variables, propiedades, etiquetas y atributos mediante scopes de TextMate.
- **Resaltado semántico:** `semanticTokenColors` cubre namespace, type, class, enum, interface, struct, typeParameter, parameter, variable, property, enumMember, event, function, method, macro, keyword, modifier, comment, string, number, regexp y operator.
- **Decoraciones de Git:** colores para recursos added, modified, deleted y untracked en el explorador de archivos.
- **Colores de terminal:** 16 colores ANSI (normal y brillante) definidos por tema.

## Stack tecnológico

| Capa | Tecnología | Función |
|---|---|---|
| Extensión | Visual Studio Code Theme API | Registro de temas de color |
| Motor de temas | JSON (VS Code Color Theme) | Definición de `colors`, `tokenColors` y `semanticTokenColors` |
| Motor mínimo | VS Code `^1.70.0` | Versión mínima del motor declarada en `engines` |
| Icono | `images/ricra-tea-green.png` | Imagen de la extensión en el Marketplace |

## Arquitectura

```
ricra-theme/
├── package.json                 # Manifiesto de la extensión (nombre, versión, publisher, temas)
├── README.md                    # Documentación
├── LICENSE                      # Licencia MIT
├── images/
│   └── ricra-tea-green.png      # Icono de la extensión
├── screenshots/
│   ├── tea-green-light.png      # Vista previa del tema claro
│   └── tea-green-dark.png       # Vista previa del tema oscuro
├── themes/
│   ├── tea-green-light.json     # Tema claro (uiTheme: vs)
│   ├── tea-green-dark.json      # Tema oscuro (uiTheme: vs-dark)
│   ├── ricra-andromeda.json     # Tema oscuro estilo Andromeda
│   ├── ricra-github-dark.json   # Tema oscuro estilo GitHub Dark
│   ├── ricra-one-dark-pro.json  # Tema oscuro estilo One Dark Pro
│   ├── ricra-dracula.json       # Tema oscuro estilo Dracula
│   ├── ricra-tokyo-night.json   # Tema oscuro estilo Tokyo Night
│   ├── ricra-night-owl.json     # Tema oscuro estilo Night Owl
│   ├── ricra-ayu-mirage.json    # Tema claro estilo Ayu Mirage
│   └── ricra-shades-of-purple.json # Tema oscuro estilo Shades of Purple
└── ricra-theme-1.0.2.vsix       # Paquete empaquetado de la versión 1.0.2
```

- **Temas declarados en `package.json`:** `contributes.themes` apunta a los 10 archivos JSON con sus respectivos `uiTheme` (`vs` para claro, `vs-dark` para oscuro).
- **Sin servidor propio:** es un tema de color estático; no hay backend, base de datos ni API.
- **Instalado vs desarrollo:** en desarrollo se editan los JSON directamente; en instalado se distribuye el `.vsix` generado con `vsce package`.

## Instalación y uso

1. Abre la paleta de comandos con `Ctrl+Shift+P` (`Cmd+Shift+P` en macOS).
2. Ejecuta **Preferences: Color Theme**.
3. Elige cualquiera de los diez temas disponibles.

### Desde un archivo VSIX

Descarga el `.vsix` de la versión que quieras instalar y ejecuta:

```sh
code --install-extension ricra-theme-1.0.2.vsix
```

### Flujo básico de uso

1. Abre un archivo de código (por ejemplo `package.json` o un archivo de código fuente).
2. Observa los colores aplicados según el tema activo.
3. Cambia de tema desde la paleta de comandos si necesitas pasar de modo claro a oscuro.

## Requisitos del sistema

| Componente | Requisito mínimo |
|---|---|
| Editor | Visual Studio Code `^1.70.0` |
| Sistema operativo | Windows, macOS o Linux (soportado por VS Code) |

## Formato de los archivos de tema

Cada tema es un archivo JSON con esta estructura:

```json
{
  "name": "Ricra Andromeda",
  "type": "dark",
  "colors": {
    "editor.background": "#23262E",
    "editor.foreground": "#D5CED9"
  },
  "tokenColors": [
    {
      "scope": ["comment"],
      "settings": { "foreground": "#A0A1A7CC", "fontStyle": "italic" }
    }
  ],
  "semanticTokenColors": {
    "function": "#FFE66D",
    "string": "#96E072"
  }
}
```

- `colors`: colorea la interfaz de VS Code (editor, sidebar, pestañas, terminal, botones, Git).
- `tokenColors`: colorea la sintaxis del editor según scopes de TextMate.
- `semanticTokenColors`: colorea según tokens semánticos de servidores de lenguaje (LSP).

## Buenas prácticas de uso

- Usa los temas claros (Tea Green Light, Ricra Ayu Mirage) en entornos con buena iluminación para reducir fatiga visual.
- Usa los temas oscuros en entornos con poca luz; sus fondos no son negros puros, lo que evita halos alrededor del texto.
- No edites los JSON del tema instalado directamente; modifica los archivos fuente y vuelve a empaquetar con `npx @vscode/vsce package`.
- El tema no controla tipografía; configura `editor.fontFamily` en los ajustes de VS Code con una fuente monoespaciada instalada en tu sistema si deseas personalizarla.

## Notas de publicación

1. Incrementa `version` en `package.json` (actual: `1.0.2`).
2. Ejecuta `npx @vscode/vsce login ricra` para autenticar el publicador.
3. Ejecuta `npx @vscode/vsce publish` para subir al Marketplace.
4. Para empaquetar localmente sin publicar: `npx @vscode/vsce package`.

## Roadmap

- Revisar contraste de scopes de sintaxis adicionales según retroalimentación de usuarios.
- Mantener compatibilidad con futuras versiones del motor de VS Code.

## Licencia

Este proyecto se distribuye bajo la licencia **MIT**. Consulta el archivo `LICENSE` para más detalles.

## Autor

---

**Pedro Giovanni Ricra Figueroa** — Ingeniería de Sistemas

[GitHub](https://github.com/TeVerde29) · [hikih020@gmail.com](mailto:hikih020@gmail.com)

---

Si este proyecto te resultó útil, considera darle una estrella en GitHub.
