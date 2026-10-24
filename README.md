# Tea Green Theme

Un tema de color para Visual Studio Code con variantes clara y oscura. Tea Green combina tonos crema, matcha y verde bosque para una experiencia tranquila y legible.

![Version](https://img.shields.io/badge/version-1.0.1-AFC49A)
![Licencia MIT](https://img.shields.io/badge/licencia-MIT-4F7256)

## Temas

| Tema | Apariencia |
| --- | --- |
| **Tea Green Light** | Fondo crema `#F7F8F1`, superficies claras y acentos verde bosque. |
| **Tea Green Dark** | Fondo verde profundo `#111A13`, superficies `#19241B` y acento matcha `#C2D7A3`. |

Ambas variantes incluyen colores para el editor, la barra lateral, pestañas, paneles, terminal, controles y decoraciones de Git. El resaltado semántico se aplica cuando el servidor de lenguaje correspondiente lo proporciona.

## Vistas previas

### Tea Green Light

![Vista previa de Tea Green Light en Visual Studio Code](./screenshots/tea-green-light.png)

### Tea Green Dark

![Vista previa de Tea Green Dark en Visual Studio Code](./screenshots/tea-green-dark.png)

## Instalación

### Desde el Marketplace

Busca **Tea Green Theme** en la vista Extensions de VS Code, o instálalo desde una terminal:

```sh
code --install-extension ricra.tea-green-theme
```

### Desde un archivo VSIX

Descarga el `.vsix` de la versión que quieras instalar y ejecuta:

```sh
code --install-extension ricra.tea-green-theme-1.0.1.vsix
```

## Activar un tema

1. Abre la paleta de comandos con `Ctrl+Shift+P` (`Cmd+Shift+P` en macOS).
2. Ejecuta **Preferences: Color Theme**.
3. Elige **Tea Green Light** o **Tea Green Dark**.

## Paleta

| Token | Claro | Oscuro |
| --- | --- | --- |
| Fondo del editor | `#F7F8F1` | `#111A13` |
| Superficie | `#FFFFFF` | `#19241B` |
| Superficie secundaria | `#EEF2E8` | `#222F24` |
| Texto principal | `#1E2A21` | `#F1F5EB` |
| Texto secundario | `#5E6E5F` | `#B5C0B2` |
| Acento | `#294635` | `#C2D7A3` |

Los colores están diseñados para mantener una jerarquía coherente entre las dos variantes. El contraste puede variar según el lenguaje, las extensiones y los colores de sintaxis que estas aporten; el tema no representa una certificación WCAG.

## Tipografía

El tema cambia colores, no fuentes. Si quieres personalizar la tipografía, configura `editor.fontFamily` en los ajustes de VS Code con una fuente monoespaciada instalada en tu sistema.

## Publicar una versión

El identificador de publicador configurado es `ricra`. Para publicar, ese publicador debe existir en Visual Studio Marketplace y estar asociado a tu cuenta:

```sh
npx @vscode/vsce login ricra
npx @vscode/vsce publish
```

Antes de publicar, incrementa `version` en `package.json`. Para crear un paquete local sin publicarlo:

```sh
npx @vscode/vsce package
```

Consulta la [guía oficial para publicar extensiones](https://code.visualstudio.com/api/working-with-extensions/publishing-extension) para crear el publicador y configurar las credenciales.

## Licencia

Distribuido bajo la licencia [MIT](./LICENSE).
