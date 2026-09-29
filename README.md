# Manga Froggy updates

Repositorio público propuesto para distribuir **metadatos de actualización de la app**.
`public/stable/manifest.json` y `public/stable/manifest.sig` se publicarán en GitHub
Pages después de firmarlos y verificarlos en el PC local. El cliente verifica la firma
Ed25519 **incluida** en `manifest.json`; `.sig` es solo una copia legible de esa firma.

Cada APK irá como asset versionado de GitHub Releases, nunca en Pages ni en Git.
Una versión y su tag se consideran inmutables: si cambia cualquier byte, se publica
otra versión y otro `versionCode`. El manifest apunta al asset exacto con tag versionado,
sin usar `/latest/`.

Este repositorio no contiene código fuente principal, claves privadas, keystores,
contraseñas, tokens, copias de seguridad ni datos de usuarios. La firma Ed25519 se
genera localmente; el workflow de Pages solo publica los bytes ya firmados y se
ejecuta manualmente tras revisar cada cambio.

El canal INTERNAL queda sin publicar en esta primera fase. Cuando se decida usarlo,
puede añadirse `public/internal/manifest.json` con su propia clave de confianza.

**Estado:** la Release pública `v1.1.0` contiene
`manga-froggy-1.1.0-code2.apk`; Pages sirve el manifest estable firmado.
El repositorio se mantiene separado del código principal de Manga Froggy.
