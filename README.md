# Panalink OTA

Repositorio exclusivo para distribuir actualizaciones oficiales de Panalink.

## Publicación manual

Los APK se generan y firman fuera de GitHub, GitHub no compila la aplicación.

Para cada versión:

1. Generar el APK Release firmado.
2. Obtener el `versionCode` y `versionName` reales.
3. Calcular SHA-256 del APK:
   `sha256sum Panalink-vX.Y.Z.apk`
4. Crear un GitHub Release con una etiqueta `vX.Y.Z`.
5. Subir el APK como asset del Release.
6. Generar `manifest.json` con la URL del asset, SHA-256 y datos de versión.
7. Subir `manifest.json` como asset del mismo Release.

La aplicación consume el manifiesto desde:

`https://github.com/Andresaguiar22/panalink-ota/releases/latest/download/manifest.json`

## Seguridad

El SHA-256 debe corresponder exactamente al APK publicado. La aplicación además debe verificar la identidad del paquete, la firma del APK y el `versionCode` antes de instalar.

La clave privada de firma de Panalink nunca debe almacenarse en este repositorio.

## Estructura de un Release

Cada Release debe contener como mínimo:

- `Panalink-vX.Y.Z.apk`
- `manifest.json`

No se deben subir APK al historial normal de Git. Los APK se publican como assets de GitHub Releases.
