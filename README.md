# CloudSaves

App de escritorio para **Linux y Windows 11** que sincroniza los guardados de los juegos con una carpeta en la nube: mueve el archivo o la carpeta de guardado a la nube y deja un enlace en su lugar, así el juego no nota la diferencia. En otra máquina o sistema, restaurar vuelve a crear los enlaces a partir del registro.

Acá solo se publican los binarios; el código no está en este repositorio.

## Descargas

| Sistema | Archivo |
|---|---|
| Linux (x86-64) | `cloud.saves.linux-amd64.AppImage` |
| Windows 11 (x86-64) | `cloud.saves.windows-amd64-installer.exe` |

Cada uno viene con su checksum: `SHA256SUMS-linux` y `SHA256SUMS-windows`.

- **Linux**: se instala con Shelly (`shelly install appimage`) o se marca como ejecutable y se corre. El AppImage trae GTK y WebKit adentro.
- **Windows**: se ejecuta el instalador (instala por usuario, sin UAC).

## Actualización automática

La app busca versiones nuevas al arrancar (también desde Configuración → Buscar actualizaciones), verifica el SHA256 y se reinicia actualizada: el AppImage se reemplaza en su lugar y en Windows se ejecuta el instalador en silencio.

## Requisitos

- Windows 11: WebView2 (viene con el sistema).
- La carpeta de la nube tiene que estar disponible.
