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

## Qué hace

- **Enlaces seguros**: copia el guardado a la nube, verifica la copia y recién entonces deja el enlace; si algo falla, deshace todo y el original queda donde estaba.
- **Linux y Windows con la misma nube**: cada juego guarda una ruta por sistema, y en Linux reconoce los prefijos de Proton (Steam) y de Heroic, y deduce la ruta de un sistema a partir de la del otro.
- **Rutas recomendadas**: al agregar un juego, sugiere dónde guarda las partidas (la base se descarga desde la app la primera vez).
- **Conflictos**: si hay guardados locales y en la nube, elegís con cuáles quedarte; lo otro queda como respaldo.
- **Idioma**: español o inglés, o el del sistema.

## Actualización automática

La app busca versiones nuevas al arrancar (también desde Configuración → Buscar actualizaciones), verifica el SHA256 y se reinicia actualizada: el AppImage se reemplaza en su lugar y en Windows se ejecuta el instalador en silencio. Después de actualizar, ofrece abrir el changelog de la versión nueva.

## Requisitos

- Windows 11: WebView2 (viene con el sistema).
- La carpeta de la nube tiene que estar disponible.

## Créditos

- **Rutas recomendadas**: los datos son de [PCGamingWiki](https://www.pcgamingwiki.com/), publicados bajo la licencia [CC BY-NC-SA 3.0](https://creativecommons.org/licenses/by-nc-sa/3.0/) (ver [sus condiciones](https://www.pcgamingwiki.com/wiki/PCGamingWiki:Copyrights)), y llegan a la app a través del [Ludusavi Manifest](https://github.com/mtkennerly/ludusavi-manifest) de Matthew T. Kennerly (licencia MIT), que los compila. CloudSaves no incluye esos datos: cada instalación los descarga del Ludusavi Manifest cuando se lo pide. Si falta un juego o una ruta está mal, la forma de corregirlo es editar PCGamingWiki.
- **[Wails](https://wails.io/)** (Lea Anthony y colaboradores, licencia MIT): el framework de la app.
- **Bibliotecas**: [godbus/dbus](https://github.com/godbus/dbus) (BSD-2-Clause), [golang.org/x/sys](https://pkg.go.dev/golang.org/x/sys) y [golang.org/x/text](https://pkg.go.dev/golang.org/x/text) (BSD-3-Clause), [yaml.v3](https://github.com/go-yaml/yaml) (MIT y Apache-2.0).
- **AppImage**: incluye GTK, WebKitGTK y sus dependencias, que se distribuyen bajo sus propias licencias (principalmente LGPL).

Cada versión incluye `THIRD_PARTY_LICENSES-linux.txt` y `THIRD_PARTY_LICENSES-windows.txt`, con la lista completa de componentes de terceros, sus licencias y, para las bibliotecas del AppImage, el enlace a su código fuente.
