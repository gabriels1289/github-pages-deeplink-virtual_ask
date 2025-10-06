# GitHub Pages – App/Universal Links (Virtual Ask)

Incluye **dos fingerprints** en `assetlinks.json` para admitir builds de *debug* y *release*:

- **Debug** (`com.example.virtual_ask`):  
  `E3:DA:49:28:CC:49:A4:B4:73:7D:54:09:4F:81:9A:A8:44:98:F9:7F:07:DB:3F:17:89:E5:87:27:F5:00:12:AF`
- **Release** (placeholder, reemplazar cuando tengas tu keystore de release):  
  `REEMPLAZAR_CON_SHA256_RELEASE`

> En producción, el fingerprint que debe validar es el de **release**. Mantener el de debug facilita pruebas locales/QA.

## Archivos
- `.nojekyll`
- `/.well-known/assetlinks.json` (con dos SHA-256)
- `/apple-app-site-association` y `/.well-known/apple-app-site-association` (`TEAMID.com.example.virtualAsk`)
- `/invite/index.html` (fallback `virtualask://invite?...`)

## Publicación
1. Repo: **<tu-usuario>.github.io**
2. Sube todo a la raíz del branch publicado (usualmente `main`).
3. Settings → Pages → Source: `main` (root).
4. Verifica endpoints públicos:
   - `https://<tu-usuario>.github.io/.well-known/assetlinks.json`
   - `https://<tu-usuario>.github.io/apple-app-site-association`
   - `https://<tu-usuario>.github.io/.well-known/apple-app-site-association`

## Nota
- Cuando tengas el **SHA-256 de release**, reemplaza `REEMPLAZAR_CON_SHA256_RELEASE` por el hash real.
- Puedes conservar el fingerprint de debug para pruebas, o removerlo cuando publiques en producción.
