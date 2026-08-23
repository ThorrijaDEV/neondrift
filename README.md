# ✦ NEONDRIFT

Endless runner arcade en **un solo HTML**: canvas, chiptune generado con WebAudio y cero assets. Corre, salta (doble salto), esquiva bloques y pinchos mientras el mundo acelera — con la estética hyperpop de la casa.

```
[ESPACIO] saltar ×2   [P] pausa   [R] reinicio   tap en móvil
```

## Por qué

Quería demostrar que un juego "de verdad" — física propia, colisiones, partículas, música procedural, récord persistente — cabe en un único fichero sin build step ni dependencias: ábrelo y juega.

## Qué lleva dentro

- **Física manual**: gravedad, doble salto con recarga al aterrizar, integración delta-time.
- **Colisiones AABB** contra obstáculos generados proceduralmente con separación mínima garantizada según velocidad.
- **Chiptune WebAudio**: arpegio en loop + bleeps de salto/punto/muerte generados con osciladores — cero ficheros de audio.
- **Juice**: partículas al morir, estela neón, rejilla en perspectiva, suelo desplazándose.
- **Récord** en localStorage.
- **9 auto-tests** embebidos (`window.__selftest()`) que corren headless: gravedad, salto/doble/recarga, AABB, separación de spawns, apoyo de obstáculos y puntuación.

## Jugar

```bash
# online
xdg-open https://thorrijadev.github.io/neondrift/
# offline
curl -LO https://raw.githubusercontent.com/ThorrijaDEV/neondrift/main/index.html
xdg-open index.html
```

## CI headless

```bash
chromium --headless --dump-dom 'file://.../index.html' | grep ST::
# ST::grav:PASS jump:PASS nojumps:PASS land:PASS aabb-hit:PASS aabb-miss:PASS spawn-gap:PASS obst-ground:PASS score:PASS
```

## Licencia

[MIT](LICENSE)
