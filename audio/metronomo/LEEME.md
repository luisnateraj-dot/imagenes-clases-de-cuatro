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
