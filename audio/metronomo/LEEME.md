# Metrónomo del CEM

Cuatro golpes de **claves** para el metrónomo de los módulos del CEM: el compás de cuenta y el clic opcional mientras suena la pieza o el ritmo (generador de ritmos y módulo de cifrados, `contexto/13` y `contexto/14`).

## Origen y licencia

University of Iowa Electronic Music Studios, *Musical Instrument Samples*, colección *Hand Percussion* (Andrew Thierauf, 2013):
<https://theremin.music.uiowa.edu/MIShandpercussion.html>. Según el sitio, las grabaciones «may be downloaded and used for any projects, without restrictions».

## Contenido

| Archivo | Clave | Altura aprox. | Uso |
|---|---|---|---|
| `clave2_ff.mp3` | 2 | Sol♯6 (≈ 1,6 kHz) | tiempo 1 en el compás de cuenta |
| `clave2_mf.mp3` | 2 | Sol♯6 | tiempo 1 durante la pieza |
| `clave4_ff.mp3` | 4 | Re♯6 (≈ 1,2 kHz) | demás pulsos en el compás de cuenta |
| `clave4_mf.mp3` | 4 | Re♯6 | demás pulsos durante la pieza |

- Todos los archivos son MP3 mono a 44,1 kHz, 128 kbps, sin silencio inicial.
- Las dos *ff* están igualadas. Cada *mf* conserva su diferencia natural con su *ff* (clave 2: −6,8 dB; clave 4: −9,7 dB), así que en *mf* el tiempo 1 suena un poco más fuerte que los demás pulsos.
- `indice.json` da, para cada sonido:
  - `ataque_s`: el punto que se alinea con el pulso;
  - `duracion_s`: la duración;
  - `nivel_db`: el nivel relativo;
  - `pico_dbfs`: el pico.

  Incluye además las reglas de uso (`uso`).

## Sonidos de las pistas del Metrónomo inteligente

*(La primera tanda, `vcsl/` e `instrumentos.json` del 16-nov-2026, PR #64, se borró el mismo día, después de instalar la revisión «una pista = un sonido»: la reemplaza `pistas/`.)*

### Una pista = un sonido (16-nov-2026)

Carpeta **`pistas/`** e índice **`pistas.json`**, para el Metrónomo inteligente después de la revisión del 16-nov-2026 (`contexto/23`, §10): **cada pista es un solo sonido** (un gesto de un instrumento: el cencerro 1 abierto, el cencerro 1 apagado…) y las secciones de una casilla son **sus intensidades reales**.

- 33 sonidos en 9 grupos, todos de VCSL (*Versilian Community Sample Library*, <https://github.com/sgossner/VCSL>, **CC0 1.0**: dominio público, sin pedir crédito) salvo las claves 2 y 4: claves (la 2 y la 4 de Iowa, que son las de arriba, sin copiar; y tres pares de VCSL), woodblock (3), cencerro (2 cencerros, abierto y apagado), cabasa (golpe, frotado), shaker (pequeño: hacia abajo, hacia arriba, golpe seco; grande: golpe, sacudida), bombo (de batería, de orquesta), tambores de mano (tumba, conga abierta y apagada, quinto, bongó grave y agudo), palmas (varias, una) y pandereta (2 panderetas, golpe y sacudida).
- `pistas/<sonido>_<n>.mp3`: n = 1 la intensidad más suave … la más fuerte (1, 2 o 3 capas, las que grabó VCSL; no se inventan con ganancia). La más fuerte, igualada con la clave 2 *ff*; las demás, con su diferencia natural (entre −3 y −18 dB).
- `pistas.json`: los grupos (es/en) y, por sonido, su grupo, su nombre (es/en) y sus niveles (`archivo`, `ataque_s`, `duracion_s`, `nivel_db`).
- Los arma `muestras/construir_sonidos_pistas.py` de `cem-codigo`.

## El cuatro con las cuerdas apagadas (17-nov-2026)

- `cuatro/<golpe>_<n>.mp3` y **`cuatro.json`**: los golpes del cuatro con las cuerdas apagadas para la pista «Cuatro» del Metrónomo inteligente. Grabados por Luis Natera el 17-nov-2026 (`Golpes_apagados.wav`): 21 golpes o variantes, 5 tomas de cada uno (105). Abajo, arriba, golpe suave y fuerte, látigo arriba, abanico, abanico fino, abanico reentrante, chasquido abajo y arriba (suave, normal, fuerte), apagado abajo y arriba, redondo abajo y arriba, y arpegio con el pulgar (lento, medio, rápido).
- MP3 mono 44,1 kHz, 192 kbps, **sin normalizar** (conservan su diferencia natural de nivel); cada toma empieza 60 ms antes del golpe.
- En `cuatro.json`, cada toma lleva **`a`**, el punto que cae en el tiempo (en segundos desde el comienzo del archivo): el comienzo del golpe; en los abanicos, su último golpe (la yema del pulgar en el abanico, el pulgar en el fino, la uña del índice en el reentrante; Luis, 17-nov, 12:25); en el arpegio con el pulgar, la llegada a la última cuerda, Si (Luis, 17-nov, 12:19; antes, la tercera). Los apagados llevan **`db`: 24**, la ganancia que se suma al tocar (son unos 30 dB más suaves que los demás golpes).
- Los apagados se grabaron con un golpe de preparación delante; **el apagado es el segundo golpe de cada par** (Luis, 17-nov), y es el que se cortó.
- Los arma `muestras/construir_sonidos_cuatro.py` del repositorio de código (después de `cortar_golpes_apagados.py` y `arpegio_ultima_cuerda.py` y `abanicos_ultimo_golpe.py`).
