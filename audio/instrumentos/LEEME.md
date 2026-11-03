# Instrumentos melódicos del CEM

Notas sueltas de **clarinete en si♭** y **flauta** en tres dinámicas (*pp*, *mf*, *ff*), para las melodías y contravoces de los módulos del CEM (módulo de cifrados, `contexto/14_Modulo_Cifrados.md`).

## Origen y licencia

University of Iowa Electronic Music Studios, *Musical Instrument Samples* (grabaciones anteriores a 2012):
<https://theremin.music.uiowa.edu/MIS.html>. Según el sitio, las grabaciones «may be downloaded and used for any projects, without restrictions».

| Instrumento | Intérprete | *pp* | *mf* | *ff* |
|---|---|---|---|---|
| Clarinete en si♭ | Christine Bellomy (1998) | D3–B6 (46) | D3–C7 (47) | D3–B6 (46) |
| Flauta, sin vibrato | Sonja Feig (2000) | B3–B♭6 (35) | B3–C7 (38) | B3–C♯7 (39) |

Si una dinámica no tiene una nota, se usa la dinámica más cercana.

## Contenido

- `clarinete/<pp|mf|ff>/<nota>.mp3` y `flauta/<pp|mf|ff>/<nota>.mp3`: una nota por archivo, en MP3 mono a 44,1 kHz.
- Las notas se nombran por su **altura real**, no por la escrita, con la convención de `audio/tonada/`: `C`, `Cs`, `D`, `Eb`, `E`, `F`, `Fs`, `G`, `Ab`, `A`, `Bb`, `B` más la octava (C4 = Do central). Hay un archivo por sonido: Do♯ y Re♭ comparten `Cs`.
- `indice.json` da, para cada nota y dinámica:
  - `ataque_s`: el punto que se alinea con el tiempo;
  - `bucle_s`: el tramo estable con que se prolonga la nota, mediante un fundido cruzado de 12 ms en fase;
  - la duración, el nivel y la corrección de afinación aplicada.

  Incluye además las reglas de reproducción (`reproduccion`).

## Procesado (28/10/2026)

- Cada nota se recortó de las escalas originales **según su altura detectada**. Después se **afinó**, midiendo la corrección nota por nota (mediana 2,7 cents, máximo 8), y se **niveló su tramo estable** para que no se note el empalme al prolongarla.
- **Escalón fijo entre dinámicas:** *pp* está 12 dB por debajo de *mf* y *ff* 6 dB por encima. El timbre de cada dinámica es el de su grabación.
- Los puntos del índice se midieron sobre el MP3 ya decodificado, así que incluyen el retardo del codificador.
- Este juego reemplaza al del PR #1, que solo tenía *mf* y cuya afinación quedó mal corregida.

## Reproducción

- **Escala de dinámicas** (respecto a *mf*): *pp* −14 dB · *p* −9 · *mp* −4 · *mf* 0 · *f* +5 · *ff* +9.
- **La grabación se elige en el ataque de cada nota,** según la dinámica de ese instante, y se mantiene toda la nota. Dentro de una nota, los reguladores solo cambian el volumen. Cambiar de grabación en mitad de una nota sostenida se oye como un remiendo.

## Contrabajo (3/11/2026)

Bajo de los ritmos del Generador (pasaje y joropo corrío; `contexto/15_Bajo_llanero.md` en el proyecto del CEM).

- **Origen:** University of Iowa, *Musical Instrument Samples*, contrabajo en **pizzicato, *mf*** (Alison Mann, 2001), las escalas de cada cuerda. Uso sin restricciones, como las demás.
- `contrabajo/<nota>.mp3`: una nota por archivo, **de Mi1 a Re3** (23 notas), en primera posición:
  - cuerda Mi: Mi1–La♭1;
  - cuerda La: La1–Do♯2;
  - cuerda Re: Re2–Fa♯2;
  - cuerda Sol: Sol2–Re3.
- **Formato:** MP3 mono a 192 kbps, 2,5 s con fundido final. Los nombres siguen la convención de arriba (A1, Bb1, Cs2…; altura real).
- **Procesado:**
  - cada nota se recortó desde su pellizco: el ataque se busca en los 400 ms siguientes al umbral, para no tomar un roce previo como comienzo (el «ta-raaa» del Mi2, 3/11/2026);
  - se afinó por remuestreo (`cents_corregidos`, el desvío que tenía);
  - se niveló: RMS de 10 a 210 ms tras el comienzo = −20 dB (`nivel_rms_db`).
- **`contrabajo/indice.json`:** claves = número MIDI (Do4 = 60), con `nota`, `archivo`, `cuerda` y `cents_corregidos`, más `rango` y `nivel_rms_db`. El motor mide el ataque al cargar.
- **Script:** `pruebas/contrabajo_notas.py` (en el proyecto del CEM).
- **`contrabajo/reglas.json`:** los parámetros del bajo (`parametros`), que usa la pieza `MotorBajo` del CEM: nivel, duraciones, nota de paso, V7 en la quinta, partío y cruzao alternados con la base (`variacion_si` / `variacion_no`) y cierre. Cada ritmo dice su `bajo` en `ritmos/ritmos.json`.
