# GitHub Pages – Deep Links (con index y 404)

Esta versión agrega **`index.html`** en la raíz (evita 404) y **`404.html`** (redirige al inicio).

## Importante sobre la URL
- Si el repo se llama **`<usuario>.github.io`** ⇒ tu sitio se publica en `https://<usuario>.github.io/` (raíz del dominio). **Esto es lo recomendado** para App/Universal Links, porque `.well-known` queda en el root del host.
- Si usas un repo cualquiera (p. ej., `github-pages-deeplink-virtual_ask`) ⇒ se publica en `https://<usuario>.github.io/<repo>/`. En ese caso **NO** sirve para App Links porque los endpoints quedarían en `https://<host>/<repo>/.well-known/...` (no en el root).
- Alternativa: configura un **dominio o subdominio propio** apuntado a ese repo de proyecto; así `.well-known` queda en el root de ese dominio.

## Certificados Android
- `package_name`: `com.example.virtual_ask`
- Debug SHA-256: `E3:DA:49:28:CC:49:A4:B4:73:7D:54:09:4F:81:9A:A8:44:98:F9:7F:07:DB:3F:17:89:E5:87:27:F5:00:12:AF`
- Release SHA-256: `REEMPLAZAR_CON_SHA256_RELEASE` (reemplazar)

## iOS
- `appID`: `TEAMID.com.example.virtualAsk` (reemplaza `TEAMID`)
- Archivos `apple-app-site-association` en raíz y en `/.well-known/`.

## Workflow (Actions)
- `.github/workflows/pages.yml` despliega el contenido estático desde la **raíz** del repo.

