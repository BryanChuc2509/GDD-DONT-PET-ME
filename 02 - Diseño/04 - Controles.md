# Controles

## Descripción de la sección

Define la relación entre las acciones del jugador y las entradas físicas del dispositivo (exclusivo para PC: teclado y ratón).

## Mapa de controles (PC)

| Acción                    | Teclado                    | Ratón (Mouse) | Comportamiento / Detalle                                                                                           |
| :------------------------- | :------------------------- | :------------- | :----------------------------------------------------------------------------------------------------------------- |
| **Moverse**          | `W`, `A`, `S`, `D` | —             | Desplazamiento en el plano del escenario                                                                           |
| **Saltar**           | `ESPACIO` (pulsar)        | —             | Impulso vertical / segundo impulso aéreo; la pulsación inicial no activa el planeo                                |
| **Sprint**           | `SHIFT` (mantener)       | —             | Aumenta temporalmente la velocidad en el suelo y consume combustible                                               |
| **Planeo**           | `ESPACIO` (mantener en el aire) | —      | Ralentiza la caída sin consumir combustible; dura hasta 1 segundo por tramo en el aire             |
| **Recoger semillas** | Automático                | —             | Las semillas se recogen al tocarlas; no se guardan en un inventario                                                |
| **Pausa**            | `ESC`                    | —             | Abre o cierra el menú de pausa                                                                                    |

## Principios de control

- **Respuesta instantánea:** El salto y el doble salto tienen cero retraso para asegurar aterrizajes precisos sobre superficies diminutas.
- **Salto y planeo con `ESPACIO`:** Pulsar la tecla inicia el salto o el segundo impulso aéreo; mantenerla cuando Mochi ya está en el aire activa el planeo.
- **Sin combinaciones complejas:** El plataformeo se basa en reflejos y timing natural, no en combinaciones laberínticas de teclas.
- **Combustible del sprint:** `SHIFT` activa el sprint en el suelo y consume su propia reserva. El planeo con `ESPACIO` no consume combustible y está disponible independientemente de esa reserva; dura como máximo 1 segundo por tramo (el doble salto no reinicia el límite).
- **Acciones diferenciadas:** `SHIFT` queda reservado para sprintar; `CTRL` o `C` se usan para agacharse o deslizarse y no gastan combustible.

## Reasignación

El jugador podrá reasignar libremente las teclas en el menú de opciones para mayor accesibilidad y comodidad en PC.

## Entrada y retroalimentación

- **Al saltar:** Audio cómico de patitas despegando con impulso elástico.
- **Al recoger semillas:** Destello y sonido breve; el contador del HUD aumenta.
- **Al esprintar:** La animación correspondiente y el indicador del HUD muestran el consumo de combustible.
- **Al quedarse sin combustible:** El sprint se interrumpe; el indicador comunica que la reserva debe regenerarse antes de volver a esprintar. El planeo sigue disponible.
- **Al impactar con un peligro:** Pausa de impacto súbita de 0.2 s, sonido de sorpresa de caricatura y pantalla a negro hacia el checkpoint.

> **Navegación:** [[00 - Índice]] · ← [[03 - Sistemas]] · [[05 - Progresión]] →
