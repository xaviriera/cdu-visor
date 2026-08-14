# cdu-visor

Repositorio de **publicación** de los Visores del Inversor de las operaciones de
CdU de 0 a Éxito. Se sirve mediante GitHub Pages en `visor.tucambiodeuso.com`.

Este repositorio contiene **únicamente**:

- El visor (HTML/CSS/JS) tal cual se construye en el repositorio de origen.
- Sus imágenes.
- El `llavero.json` **cifrado** de cada operación.

**Nunca** contiene datos en claro. El fichero `operacion.json` (los datos sin
cifrar de cada operación) está explícitamente excluido en `.gitignore` como
red de seguridad adicional, aunque el flujo de sincronización tampoco debe
copiarlo nunca.

## Origen

El contenido real se construye y mantiene en el repositorio
[`operaciones-gestor`](https://github.com/xaviriera/operaciones-gestor)
(carpeta `torres-cotillas/visor/` para el visor y `data/tdc/` para los datos).

**No edites nada a mano en este repositorio.** Un workflow de GitHub Actions
en `operaciones-gestor` (`.github/workflows/publicar-visor.yml`) sincroniza
automáticamente los cambios cada vez que se hace push al visor de origen o al
`llavero.json`, sobrescribiendo el contenido de la carpeta `tdc/` de aquí.
Cualquier cambio manual se perderá en la siguiente sincronización.

## Estructura

- `CNAME` — dominio personalizado de GitHub Pages (`visor.tucambiodeuso.com`).
- `index.html` — página raíz sobria, sin listar operaciones.
- `tdc/` — visor de la operación Torres de Cotillas (`index.html`, imágenes y
  `llavero.json` cifrado).
