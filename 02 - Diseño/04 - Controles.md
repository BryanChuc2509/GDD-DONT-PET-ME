# Controles

## Descripción de la sección

Define la relación entre las acciones del jugador y las entradas físicas del dispositivo (exclusivo para PC: teclado y ratón).

## Mapa de controles (PC)

| Acción                    | Teclado                    | Ratón (Mouse) | Comportamiento / Detalle                                                                                           |
| :------------------------- | :------------------------- | :------------- | :----------------------------------------------------------------------------------------------------------------- |
| **Moverse**          | `W`, `A`, `S`, `D` | —             | Desplazamiento en el plano del escenario                                                                           |
| **Saltar**           | `ESPACIO`                | —             | Impulso vertical / segundo impulso aéreo                                                                          |
| **Sprint / Planeo**  | `SHIFT` (mantener)       | —             | En el suelo esprinta; en el aire planea hasta 1 segundo por tramo en el aire. Ambos usos consumen la misma reserva |
| **Recoger semillas** | Automático                | —             | Las semillas se recogen al tocarlas; no se guardan en un inventario                                                |
| **Pausa**            | `ESC`                    | —             | Abre o cierra el menú de pausa                                                                                    |

## Principios de control

- **Respuesta instantánea:** El salto y el doble salto tienen cero retraso para asegurar aterrizajes precisos sobre superficies diminutas.
- **Sin combinaciones complejas:** El plataformeo se basa en reflejos y timing natural, no en combinaciones laberínticas de teclas.
- **Uso compartido de `SHIFT`:** En el suelo, mantener la tecla activa el sprint; en el aire, activa el planeo por un máximo de 1 segundo por tramo en el aire (el doble salto no reinicia el límite). Las dos acciones consumen el mismo combustible; soltar la tecla detiene el gasto y permite regenerarlo.
- **Acciones diferenciadas:** `SHIFT` queda reservado para sprintar; `CTRL` o `C` se usan para agacharse o deslizarse y no gastan combustible.

## Reasignación

El jugador podrá reasignar libremente las teclas en el menú de opciones para mayor accesibilidad y comodidad en PC.

## Entrada y retroalimentación

- **Al saltar:** Audio cómico de patitas despegando con impulso elástico.
- **Al recoger semillas:** Destello y sonido breve; el contador del HUD aumenta.
- **Al esprintar o planear:** La animación correspondiente y un único indicador del HUD muestran que se consume la reserva compartida.
- **Al quedarse sin combustible:** El sprint o el planeo se interrumpen; el indicador comunica que la reserva debe regenerarse antes de volver a usar cualquiera de las dos acciones.
- **Al impactar con un peligro:** Pausa de impacto súbita de 0.2 s, sonido de sorpresa de caricatura y pantalla a negro hacia el checkpoint.

> **Navegación:** [[00 - Índice]] · ← [[03 - Sistemas]] · [[05 - Progresión]] →
