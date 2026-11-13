# Controles

## Descripción de la sección

Define la relación entre las acciones del jugador y las entradas físicas del dispositivo (exclusivo para PC: teclado y ratón).

## Mapa de controles (PC)

| Acción                    | Teclado                    | Ratón (Mouse) | Comportamiento / Detalle                                                                                           |
| :------------------------- | :------------------------- | :------------- | :----------------------------------------------------------------------------------------------------------------- |
| **Moverse**          | `W`, `A`, `S`, `D` | —             | Desplazamiento en el plano del escenario                                                                           |
| **Saltar**           | `ESPACIO` (pulsar)        | —             | Impulso vertical; mantener la tecla da un salto más alto y, al empezar a caer, activa el planeo |
| **Sprint**           | `SHIFT` (mantener)       | —             | Aumenta temporalmente la velocidad y gasta el combustible que comparte con el planeo                                               |
| **Planeo**           | `ESPACIO` (mantener en el aire) | —      | Ralentiza la caída y gasta el mismo combustible que el sprint; dura hasta 0.6 segundos por tramo en el aire             |
| **Recoger semillas** | Automático                | —             | Las semillas se recogen al tocarlas; no se guardan en un inventario                                                |
| **Pausa**            | `ESC`                    | Botón de pausa del HUD | Abre o cierra el menú de pausa |
| **Ver objetivo**     | `TAB`                    | Clic en la bandera del HUD | Vuelve a mostrar la tarjeta del objetivo actual |

## Principios de control

- **Respuesta instantánea:** El salto tiene cero retraso para asegurar aterrizajes precisos sobre superficies diminutas. Hay un pequeño margen para saltar justo después de salir de un borde y otro para pulsar un poco antes de aterrizar.
- **Salto y planeo con `ESPACIO`:** Pulsar la tecla en el suelo inicia el salto; si se mantiene, al empezar a caer Mochi planea.
- **Sin combinaciones complejas:** El plataformeo se basa en reflejos y timing natural, no en combinaciones laberínticas de teclas.
- **Combustible compartido:** `SHIFT` activa el sprint y mantener `ESPACIO` en el aire activa el planeo; los dos gastan la misma reserva, que solo se recarga en el suelo. Si se agota, no se puede esprintar ni planear hasta que vuelva al 30%. El planeo dura como máximo 0.6 segundos por tramo en el aire.
- **Acciones diferenciadas:** `SHIFT` queda reservado para sprintar; `CTRL` o `C` se usan para agacharse o deslizarse y no gastan combustible.

## Consulta de controles

La ventana **CONTROLES**, que se abre desde Ajustes, muestra la tecla de cada acción.

## Entrada y retroalimentación

- **Al saltar:** Audio cómico de patitas despegando con impulso elástico.
- **Al recoger semillas:** Destello y sonido breve; el contador del HUD aumenta.
- **Al esprintar:** La animación correspondiente y el indicador del HUD muestran el consumo de combustible.
- **Al quedarse sin combustible:** El sprint y el planeo se interrumpen; la barra del HUD se atenúa y el rayo parpadea hasta que la reserva vuelve al 30%.
- **Al impactar con un peligro:** Mochi reaparece en el último checkpoint y se abre la ventana **HAS MUERTO** con la causa, el contador de muertes y el botón "Revivir"; el juego continúa solo a los 3 s.

> **Navegación:** [[00 - Índice]] · ← [[03 - Sistemas]] · [[05 - Progresión]] →
