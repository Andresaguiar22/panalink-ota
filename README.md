# PanaLink

**PanaLink** es una aplicación de mensajería, momentos (historias y publicaciones) y comunidad
para Android: chat en tiempo real, reels, salas de voz, transmisiones en vivo, GIFs y stickers.

Este repositorio distribuye las **actualizaciones oficiales** de la app (canal OTA).

## 📲 Descargar PanaLink

- **Página de descarga:** https://andresaguiar22.github.io/descargar.html
- **Última versión (APK):** https://github.com/Andresaguiar22/panalink-ota/releases/latest
- **Todas las versiones:** https://github.com/Andresaguiar22/panalink-ota/releases

### Instalación (APK directo)

PanaLink no se distribuye por Google Play; se instala como APK.

1. Abre el enlace de descarga desde tu teléfono Android.
2. Si el sistema lo pide, activa *«Instalar apps de origen desconocido»* para tu navegador o
   gestor de archivos.
3. Abre el archivo `Panalink-vX.Y.Z.apk` descargado y pulsa **Instalar**.

**Requisitos:** Android 7.0 (Nougat) o superior.

> La app incluye actualización automática (OTA): cuando hay una versión nueva, PanaLink avisa
> dentro de la propia aplicación.

## 🔐 Seguridad

- Descarga **siempre** desde este repositorio o desde el sitio oficial.
- Verifica el `sha256` del APK si quieres asegurarte de su integridad (cada release lo publica).
- La clave privada de firma de PanaLink **nunca** se almacena en este repositorio.

## 🛠️ Publicación manual (mantenedor)

Los APK se generan y firman fuera de GitHub; GitHub no compila la aplicación.

Para cada versión:

1. Generar el APK Release firmado.
2. Obtener el `versionCode` y `versionName` reales.
3. Calcular SHA-256 del APK: `sha256sum Panalink-vX.Y.Z.apk`.
4. Crear un GitHub Release con una etiqueta `vX.Y.Z`.
5. Subir el APK como asset del Release.
6. Generar `manifest.json` con la URL del asset, SHA-256 y datos de versión.
7. Subir `manifest.json` como asset del mismo Release.

La aplicación consume el manifiesto desde:

`https://github.com/Andresaguiar22/panalink-ota/releases/latest/download/manifest.json`

El SHA-256 del `manifest.json` debe corresponder exactamente al APK publicado. La app además
verifica la identidad del paquete, la firma del APK y el `versionCode` antes de instalar.

### Estructura de un Release

Cada Release debe contener como mínimo:

- `Panalink-vX.Y.Z.apk`
- `manifest.json`

No se suben APK al historial normal de Git: se publican como assets de GitHub Releases.
