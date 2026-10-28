# Instrumentos melódicos del CEM

Notas sueltas de **clarinete en si♭** y **flauta** para las melodías y contravoces de los módulos del CEM (módulo de cifrados, `contexto/14_Modulo_Cifrados.md`).

## Origen y licencia

University of Iowa Electronic Music Studios, *Musical Instrument Samples* (grabaciones anteriores a 2012):
<https://theremin.music.uiowa.edu/MIS.html>. Según el sitio, las grabaciones «may be downloaded and used for any projects, without restrictions».

- Clarinete en si♭: Christine Bellomy (1998), *mf*. Rango D3–C7 (47 notas).
- Flauta, sin vibrato: Sonja Feig (2000), *mf*. Rango B3–C7 (38 notas).

## Contenido

- `clarinete/<nota>.mp3`, `flauta/<nota>.mp3`: una nota por archivo, MP3 mono 44,1 kHz, 128 kbps.
- Nombres por **altura real** (no escrita), con la misma convención que `audio/tonada/`: `C`, `Cs`, `D`, `Eb`, `E`, `F`, `Fs`, `G`, `Ab`, `A`, `Bb`, `B` + octava (C4 = Do central). Un archivo por sonido: Do♯ y Re♭ comparten `Cs`.
- `indice.json`: para cada nota, su `ataque_s` (punto que se alinea con el tiempo), su `bucle_s` (tramo estable para prolongarla con un fundido cruzado de 12 ms), su duración y su nivel.

## Procesado (28/10/2026)

Cada nota se recortó de las escalas originales, se **afinó** (corrección medida nota por nota), se **igualó en nivel** y se le **niveló el tramo estable** para que, al prolongarla, no se note el empalme. Los puntos del índice se midieron sobre el MP3 ya decodificado (incluyen el retardo del codificador).
