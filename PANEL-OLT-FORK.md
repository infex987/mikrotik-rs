# Rama `panel-olt/mit-0.7`

Fork de [ferrohd/mikrotik-rs](https://github.com/ferrohd/mikrotik-rs) mantenido por el equipo de
panel-olt (mf-Dashboard) para su propio uso.

- **Base:** el tag `v0.7.0` (commit `c64acc6`), la última versión publicada bajo **MIT OR
  Apache-2.0**. Ese es el código publicado en crates.io como `mikrotik-rs` 0.7.0,
  `mikrotik-tokio` 0.1.0 y `mikrotik-proto` 0.1.0. Las licencias originales (`LICENSE-MIT`,
  `LICENSE-APACHE`) se conservan, y los cambios de esta rama se publican bajo las mismas.
- **Upstream pasó a AGPL-3.0-only desde 0.8.0.** Esta rama **no contiene código de 0.8.0 ni
  posterior**; sus mejoras se escriben aquí de forma independiente.
- **Cambios propios:**
  - `mikrotik-tokio`: canal de respuestas **sin límite** por comando. El original, de capacidad
    16, cancelaba el comando en cuanto llegaban más de 15 filas de golpe, así que las listas
    largas (`/ip/address`, `/log`…) salían cortadas en la fila 16.
  - Soltar el receptor sigue cancelando el comando en el router.
  - Test nuevo: `long_list_in_one_burst_is_not_truncated` (100 filas en una ráfaga). Falla con el
    código original.

Las versiones de los crates **no cambian**, porque el panel las usa mediante `[patch.crates-io]`
fijado a un commit de esta rama.
