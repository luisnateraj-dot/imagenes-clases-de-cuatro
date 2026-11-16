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

## Sonidos de las pistas del Metrónomo inteligente (16-nov-2026)

Carpeta **`vcsl/`** e índice **`instrumentos.json`** (aparte de `indice.json`, que carga entero `MotorRitmos`: así el Generador no los baja). Los usa el Metrónomo inteligente para sus cuatro pistas (`contexto/23`, §5.8.1 y §9).

- **Origen y licencia:** *Versilian Community Sample Library* (VCSL), <https://github.com/sgossner/VCSL>, **CC0 1.0** (dominio público, sin pedir crédito).
- **Instrumentos** (18 sonidos): claves (otras), woodblock, cencerro (abierto · apagado), cabasa (golpe · frotado), shaker (hacia abajo · hacia arriba · golpe seco), bombo (de batería · de orquesta), tambores de mano (tumba · conga · quinto · bongó), palmas y pandereta (golpe · sacudida).
- **Archivos:** `vcsl/<instrumento>_<sonido>_<f|m|s>.mp3`, MP3 mono 44,1 kHz, 128 kbps; *f* = fuerte, *m* = medio, *s* = suave, ya con su nivel. El *f* de cada sonido está igualado con la clave 2 *ff*; *m* y *s* usan la capa dinámica de VCSL si la hay (su diferencia natural, entre −4 y −9 dB y entre −9 y −15 dB) o, si no, otra toma a −6 y −12 dB.
- **`instrumentos.json`:** por instrumento, su nombre (es/en) y sus sonidos, cada uno con la letra de la casilla (es/en; vacía si el instrumento tiene un solo sonido), su nombre y, por nivel, `archivo`, `ataque_s`, `duracion_s` y `nivel_db`.
- Los arma `muestras/construir_sonidos_metronomo.py` del repositorio `cem-codigo`, con la copia local de VCSL.

## Una pista = un sonido (16-nov-2026, segunda tanda)

Carpeta **`pistas/`** e índice **`pistas.json`**, para el Metrónomo inteligente después de la revisión del 16-nov-2026 (`contexto/23`, §10): **cada pista es un solo sonido** (un gesto de un instrumento: el cencerro 1 abierto, el cencerro 1 apagado…) y las secciones de una casilla son **sus intensidades reales**.

- 33 sonidos en 9 grupos: claves (la 2 y la 4 de Iowa, que son las de arriba, sin copiar; y tres pares de VCSL), woodblock (3), cencerro (2 cencerros, abierto y apagado), cabasa (golpe, frotado), shaker (pequeño: hacia abajo, hacia arriba, golpe seco; grande: golpe, sacudida), bombo (de batería, de orquesta), tambores de mano (tumba, conga abierta y apagada, quinto, bongó grave y agudo), palmas (varias, una) y pandereta (2 panderetas, golpe y sacudida).
- `pistas/<sonido>_<n>.mp3`: n = 1 la intensidad más suave … la más fuerte (1, 2 o 3 capas, las que grabó VCSL; no se inventan con ganancia). La más fuerte, igualada con la clave 2 *ff*; las demás, con su diferencia natural (entre −3 y −18 dB).
- `pistas.json`: los grupos (es/en) y, por sonido, su grupo, su nombre (es/en) y sus niveles (`archivo`, `ataque_s`, `duracion_s`, `nivel_db`).
- Los arma `muestras/construir_sonidos_pistas.py` de `cem-codigo`. **`vcsl/` e `instrumentos.json` quedan** mientras esté instalada la versión anterior del Metrónomo; después se pueden borrar.
