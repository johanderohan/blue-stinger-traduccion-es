# Blue Stinger — Traducción al español

[![Invítame a un café en Ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/johanderohan)

Ficha del proyecto, capturas y más traducciones al castellano en **[Parches en Castellano](https://parchesencastellano.com/traducciones/dreamcast/blue-stinger)**.

Traducción al **español de España** de *Blue Stinger* (Dreamcast, 1999), la aventura de acción
de Climax Graphics publicada por Activision en Norteamérica, que nunca salió en español.

La versión americana cuenta la historia con escenas habladas en inglés **sin subtítulos**.
Este parche traduce todos los textos del juego y además **añade subtítulos en castellano** a las
escenas habladas y a los vídeos, para que la historia se entienda de principio a fin.

La traducción se reparte como **parche**: no incluye el juego. Necesitas tu propia copia para
aplicarlo.

## Estado

Última versión: **[v1.0 — Primera versión](../../releases/tag/v1.0)**. Estado: **en revisión**.

| Parte | Estado |
|---|---|
| Mensajes, objetos, descripciones, puertas, tiendas, guardado | Traducidos (571 textos distintos, 1.417 apariciones) |
| Menús, terminales de ordenador, marcador y opciones | Traducidos (548 textos) |
| Subtítulos de las escenas habladas | **Añadidos**: 857 subtítulos en 191 escenas, sincronizados con la voz |
| Subtítulos de los vídeos | **Añadidos** en 9 vídeos (prólogo, escenas y finales) |
| Rótulos de interfaz en imagen | Traducidos (menú de título, guardar/cargar, armas del marcador…) |
| Caracteres españoles | **á é í ó ú ü ñ Á É Í Ó Ú Ü Ñ ¡ ¿ « »** |
| Partida completa de principio a fin | **No realizada** |

La traducción parte de la **versión americana en inglés** (texto del juego y transcripción
del doblaje), no del japonés. El inglés hablado se transcribió automáticamente y se revisó a mano
contra el contexto y una segunda transcripción. Traducción y revisión asistidas por IA, sin
revisión humana independiente.

### Cómo se ha comprobado

Todo en emulador (Flycast), no en una Dreamcast real:

- **Jugado desde partida nueva**: arranque con y sin VMU, título y opciones, vídeo de introducción
  completo con subtítulos, primeras zonas del puerto, primera conversación por radio con
  subtítulos, menús, inventario completo, guardar en la VMU, reiniciar y cargar.
- **Pruebas dirigidas** (saltando a salas o forzando mensajes): los 571 textos distintos del juego
  vistos en su ventana real en 72 salas; los 857 subtítulos de voz mostrados en pantalla; los
  9 vídeos reproducidos con el reproductor del juego; tiendas y pantalla de guardado.
- Una auditoría automática comprueba en cada imagen los límites de memoria conocidos (búfer de
  salas, búfer de la ventana de mensajes, espacio añadido) y la integridad del disco.
- El parche se ha aplicado sobre el original y el resultado se ha comparado byte a byte.

### Limitaciones conocidas

- No se ha jugado de principio a fin: la mayoría de escenas y salas se han comprobado de forma
  dirigida, no en el orden de la historia.
- No se ha probado en hardware real.
- Si abres el menú durante una escena hablada, el subtítulo se muestra en la parte superior.
- Se mantienen en inglés los logotipos y carteles del escenario, el texto grabado en los vídeos
  (se subtitula debajo) y algunos rótulos decorativos diminutos.
- Algunas pausas del doblaje son muy breves y su subtítulo pasa rápido.

## Cómo aplicar el parche

El parche modifica **solo la pista 3** de la imagen Redump del juego.

1. Descarga el parche `.xdelta` de la sección **[Releases](../../releases)**.
2. Consigue tu copia del juego en formato **Redump BIN/CUE** de la versión **USA**
   (`Blue Stinger (USA).cue` con tres pistas).
3. **Comprueba que tu pista 3 es la correcta**:

   | | |
   |---|---|
   | Archivo | `Blue Stinger (USA) (Track 3).bin` |
   | Tamaño | 1.185.760.800 bytes |
   | MD5 | `dd75046cc9f212a5d939cd823971527f` |

   ```bash
   md5sum "Blue Stinger (USA) (Track 3).bin"                    # Linux
   md5 "Blue Stinger (USA) (Track 3).bin"                       # macOS
   CertUtil -hashfile "Blue Stinger (USA) (Track 3).bin" MD5    # Windows
   ```

   Si no coincide, el parche fallará o dará un resultado corrupto.
4. Aplica el parche a la pista 3:
   - **Windows**: [Delta Patcher](https://github.com/marco-calautti/DeltaPatcher/releases)
   - **Linux / macOS**:
     `xdelta3 -d -s "Blue Stinger (USA) (Track 3).bin" Blue.Stinger.ES.v1.0.xdelta "Track 3 traducida.bin"`
5. Sustituye la pista 3 por la traducida **con el mismo nombre de archivo**
   (`Blue Stinger (USA) (Track 3).bin`). Las pistas 1 y 2 y el `.cue` no cambian.
6. Para **v1.0**, la pista 3 resultante tiene MD5 **`be798efe350923d599ad806cd537b0f5`**
   y el mismo tamaño que la original.
7. Carga el `.cue` en tu emulador (probado en Flycast).

Aplica cada versión sobre la **pista 3 original**, no sobre una ya traducida.

## Aviso

Este proyecto es una traducción hecha por afición, sin ánimo de lucro y sin relación alguna con
Climax Graphics, SEGA ni Activision. Aquí no se distribuye el juego ni ninguna parte de él: solo un
parche que modifica una copia que ya tengas.

Si eres el titular de los derechos y quieres que retire esto, abre una incidencia y lo hago.
