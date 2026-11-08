# afinador/

Imágenes del módulo **Afinador del cuatro** del CEM (contexto/19 del proyecto). Recortes de imágenes que ya están en este repositorio, para que el módulo cargue solo lo que usa.

| Archivo | Qué es | De dónde sale |
|---|---|---|
| `pala.webp` | La pala del cuatro vista de frente, con sus clavijas, la cejilla y los dos primeros espacios (540 × 940) | `partes/frontal_1400.webp`, recorte x 430–970, y 70–1010 (la cejilla queda en y = 667,8). Webp calidad 82 |
| `palosanto.webp` | Textura de la pala en el dibujo «Descubre tus clavijas» (280 × 592, veta vertical) | `partes/maderas/palosanto.webp`, recorte (400, 177)–(800, 1023), reducido. Webp calidad 80 |
| `ebano.webp` | Textura del diapasón en el mismo dibujo (208 × 172) | `partes/maderas/ebano.webp`, recorte (450, 476)–(750, 724), reducido. Webp calidad 80 |
| `armonico_mano.webp` | Cómo se hace el armónico del traste XII: la mano izquierda en el mástil, vista por el alumno (el pulgar detrás, el dedo medio sobre la barra del traste XII), sin fondo (1000 × 747) | Ilustración de Gemini a partir de una foto del profesor Luis Natera (8-nov-2026). El centro de la cuerda La es y = 0,54538 x + 7,637 y el punto quieto del armónico está en x = 476, sobre la barra del traste XII (el módulo dibuja ahí la vibración). La lupa del módulo amplía esta misma imagen (zona x 403–571, y 198–366). Webp calidad 84 |
| `armonico_detras.webp` | Lo que hay detrás de la yema del dedo medio: la piel del fondo y la cuerda La entera (113 × 113, opaca) | Hecha desde `armonico_mano.webp` con `pruebas/armonico_yema_capas.py` del proyecto (8-nov-2026). Va en x 444, y 198 de `armonico_mano.webp`. Webp sin pérdida |
| `armonico_yema.webp` | El dedo medio recortado, con su uña y su contorno (108 × 98, con transparencia) | El mismo programa. Va en x 450, y 190; al sonar el armónico, el módulo la sube 16 px en la lupa: la yema se separa de la cuerda para que el armónico se alargue (el profesor, 8-nov-2026). Webp sin pérdida |

Las coordenadas de las clavijas, los rodillos y las cuerdas que dibuja el módulo están medidas sobre `pala.webp`: si se cambia la foto, hay que medirlas de nuevo. Lo mismo con `armonico_mano.webp`: si cambia, hay que medir la cuerda y volver a hacer `armonico_detras.webp` y `armonico_yema.webp`.
