# Generador de ritmos del CEM — tomas de los golpes

Golpes sueltos de cuatro grabados por Luis Natera (28-oct-2026) para el **motor de ritmos** del CEM: generador de ritmos, módulo de cifrados y, más adelante, Acordes básicos y Progresiones armónicas (`contexto/13_Modulo_Generador_Ritmos.md`).

## Fichas «Sobre este ritmo» (30-oct-2026)

- **`fichas.json`:** los textos de la ficha de cada familia de ritmos (de dónde viene, dónde se toca, estilos, variantes, piezas con enlaces para escuchar, fuentes), en español e inglés. El Generador la muestra con el botón «Sobre este ritmo» en los ritmos que aparecen en su lista `ritmos`. Las partituras de golpes no están aquí: el Generador las dibuja con los datos de `ritmos.json`. El formato está explicado en la clave `_formato`. Un cambio en este archivo se ve al recargar el Generador, sin tocar GAS. Fichas (30-oct-2026): merengue venezolano (los cuatro merengues), tonada, vals criollo, el orquídea y joropo llanero (joropo corrío, joropo por derecho y pasaje). Las piezas pueden ir en grupos con subtítulo, cada estilo puede llevar su nivel y un párrafo puede enlazar a otro módulo del CEM.

## Desde el 1-nov-2026: segunda grabación en casa

- **`casa01/<clave>_<n>.mp3`:** E, B, Dm, Gm y B7 (claves `mi`, `si`, `rem`, `solm`, `si7`), grabados por Luis el 1-nov-2026 con el mismo equipo; los mismos golpes que `casa31/`, látigo arriba incluido; 5 tomas elegidas por golpe (en E, 4 de abajo y 4 de arriba). Con los de `casa31/` completan **Re menor** (Dm, Gm, A7) y **Si mayor** (B, E, F♯7), y **Mi mayor** para I–V7–I (E, B7).
- **`casa01/do_…`, `casa01/re7_…`** (1-nov-2026, 02:36): C y D7, de la tercera grabación en casa; con el G de `casa31/` completan **Sol mayor** (G, C, D7).
- **Carga por tonalidad:** el Generador (desde el 1-nov) baja al abrir solo los acordes de la tonalidad elegida, más los chasquidos y el metrónomo; al cambiar de tonalidad, baja los que falten.

## Desde el 31-oct-2026: grabación en casa del 31-oct

- **`casa31/<clave>_<n>.mp3`:** las tomas que usa ahora el motor, grabadas por Luis el 31-oct-2026 con el mismo equipo y en la misma sala (Re, La7, Sol, Si m, Mi m y Fa♯7, digitaciones de `08b`). Sustituyen a las de `informal/`:
  - los mismos golpes que la grabación informal, y además los **chasquidos reales en tres niveles** (suave, normal, fuerte);
  - **`<acorde>_latigo_arriba`** (l↑, látigo arriba: la uña del pulgar pega del golpeador antes de la Si), de la grabación de las 20:52, con 3 a 5 tomas por acorde, cortadas desde 90 ms antes del acorde para que quepa ese golpe previo.
- **`ritmos.json`:** los 18 ritmos recalibrados con la grabación de Luis del 31-oct y corregidos de oído por él (látigo arriba en la 4.ª corchea de los merengues básicos, +4 dB; onda nueva con ✕↓ en la 7.ª semicorchea; bolero, bambuco, gaita de furro y joropo corrío ajustados). **Resto tras el chasquido por ritmo:** el común baja a −16 dB y τ 100 ms, y la danza zuliana y la gaita de furro van sin resto (`"resto": {"db": null}`); necesita el `MotorRitmos` del 31-oct (noche).
- Las carpetas `informal/`, `golpes/` y `cierres/` quedan sin usar.

## Desde el 30-oct-2026: grabación informal

- **`informal/<clave>_<n>.mp3`:** las tomas que usa el motor, de la grabación informal de Luis (29-oct-2026): Re, La7, Sol, Si m, Mi m y Fa♯7 (digitaciones de `08b`), con 5 tomas de cada golpe:
  - `<acorde>_abajo_normal` (↓) y `<acorde>_bloque_suave` (⇓), largas (3,5 s): sirven también de cierre;
  - `<acorde>_arriba` (↑), `<acorde>_semichasquido_abajo` y `<acorde>_semichasquido_arriba` (s✕↓, s✕↑), de 1,3 s;
  - `chasquido_abajo` y `chasquido_arriba` (normales) y `chasquido_<dirección>_suave` / `_fuerte`: con el pico de la normal en `indice.json`, así que suenan con su diferencia real de nivel (abajo: suave −2,8 dB, fuerte +2,0 dB; arriba: −2,2 y +2,9 dB);
  - en `indice.json`, «reserva»: bloque fuerte y abanico de cada acorde, grabados pero sin usar todavía (el motor no los carga).
- **`ritmos.json`:** los 17 ritmos recalibrados con estas tomas; 13 con el groove medido en grabaciones reales de Luis del 29 y 30-oct-2026.
- Las carpetas `golpes/` y `cierres/` (prototipo del 28-oct-2026) quedan sin usar.

## Contenido (prototipo, 28-oct-2026)

- **`golpes/<clave>_<n>.mp3`:** varias tomas por golpe, que el motor alterna al azar sin repetir la anterior. Cada toma dura 1,3 s después del ataque y termina con un fundido.
  - Re y La7: `re_abajo_normal`, `re_abajo_fuerte` (bloque), `re_arriba`, `la7_abajo_normal`, `la7_abajo_fuerte`, `la7_arriba`.
  - Chasquidos, que no dependen del acorde: `chasquido_abajo`, `chasquido_arriba`.
- **`cierres/<clave>_<n>.mp3`:** golpes de Re largos (3,5 s), que se dejan sonar al final: `re_abajo_normal` y `re_abajo_fuerte`.
- **`indice.json`:** las tomas, su punto de ataque y su nivel. En la clave `_formato` se explica cómo se calcula el ataque al cargar, para no depender del retardo del codificador MP3.
- **`ritmos.json`:** los datos de los 8 ritmos:
  - patrón y figuras;
  - swing medido de la grabación real y desvío del azar;
  - nivel de cada golpe;
  - cierre;
  - reglas de los fundidos y del chasquido (regla u3);
  - tempos mínimo, grabado y máximo;
  - clics del metrónomo (pulso y subdivisión);
  - sonoridad de cada ritmo.

Todo en MP3 mono a 44,1 kHz, 128 kbps.

## Pendiente

Sesión de estudio (4-nov-2026): grabación completa de los 36 acordes de `contexto/08b_Digitaciones_tonada.md`. Re y La7 son las digitaciones D = 0·0·0·3 y A7 = 0·2·1·2.
