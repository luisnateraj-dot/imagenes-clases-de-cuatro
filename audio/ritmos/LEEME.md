# Generador de ritmos del CEM — golpes del prototipo

Golpes sueltos de cuatro grabados por Luis Natera (28-oct-2026) para el **motor de ritmos** del CEM: generador de ritmos, módulo de cifrados y, más adelante, Acordes básicos y Progresiones armónicas (`contexto/13_Modulo_Generador_Ritmos.md`).

## Contenido

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

Grabación completa de los 36 acordes de `contexto/08b_Digitaciones_tonada.md`. Re y La7 son las digitaciones D = 0·0·0·3 y A7 = 0·2·1·2.
