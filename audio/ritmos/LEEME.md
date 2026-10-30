# Generador de ritmos del CEM — tomas de los golpes

Golpes sueltos de cuatro grabados por Luis Natera (28-oct-2026) para el **motor de ritmos** del CEM: generador de ritmos, módulo de cifrados y, más adelante, Acordes básicos y Progresiones armónicas (`contexto/13_Modulo_Generador_Ritmos.md`).

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
