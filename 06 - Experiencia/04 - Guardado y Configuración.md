# Guardado y Configuración

## Descripción de la sección

Define cómo se conserva el progreso y qué opciones puede modificar el jugador.

## Guardado

**Tipo:** Automático.

**Cuándo se guarda:** Cada vez que se carga un nivel (el tutorial, la habitación o el pasillo). El menú principal y la introducción no cuentan.

**Qué datos se guardan:**

* El último nivel al que se entró.
* El volumen general, el de la música y el de los efectos, al cerrar la ventana de ajustes.

No se guardan el checkpoint, las semillas recogidas, el contador de muertes ni el estado de los puzzles: al continuar, el nivel empieza desde el principio.

**Cantidad de ranuras:** Una sola partida.

**Continuar y Nueva partida:** Si hay una partida guardada, el menú principal muestra "Continuar", que carga el inicio de ese nivel, y "Nueva partida", que pide confirmación y borra la partida guardada.

**Si el guardado no se puede usar:** No se muestra ningún aviso. Si el nivel guardado no se puede cargar, el menú lo ignora y muestra "Jugar".

## Configuración

| Categoría | Opciones |
| --- | --- |
| Audio | Volumen general, música y efectos de sonido, con deslizadores en porcentaje. Se guardan al cerrar la ventana de ajustes. |
| Controles | Ventana de consulta con la tecla de cada acción. |

## Restablecimiento

El botón "Restablecer ajustes" devuelve el volumen general, la música y los efectos al 100%.

> **Navegación:** [[00 - Índice]] · ← [[03 - Accesibilidad]] · [[01 - Arquitectura Técnica]] →
