# Economía y Recursos

## Descripción de la sección

Documenta cualquier recurso cuantificable: moneda, energía, experiencia, materiales, tiempo o puntos.

## Recursos

| Recurso | Obtención | Uso | Límite | Pérdida |
| --- | --- | --- | --- | --- |
| Semillas | Dispersas por el recorrido y en zonas de exploración | Marcar la ruta que debe seguir el jugador; el HUD cuenta las recogidas y el total del nivel | Las que haya en cada nivel | No se pierden al morir; las semillas recogidas no reaparecen; el contador empieza en 0 en cada nivel |
| Combustible (estamina) | Reserva propia de Mochi; se recarga solo en el suelo, poco después de dejar de gastar | Esprintar con `SHIFT` y planear manteniendo `ESPACIO` en el aire | 100 puntos | Se gasta al esprintar (22 por segundo) y al planear (45 por segundo); se llena al reaparecer en un checkpoint |
| Pilas u otros objetos de objetivo | Colocados en zonas de puzzle | Recoger e insertar en un dispositivo, como un ventilador | Solo el objeto requerido por el desafío; no hay inventario general | Se queda en el aparato al activarlo |

## Fuentes y sumideros

**Fuentes:**

- Semillas distribuidas en el camino principal para orientar al jugador.
- Semillas adicionales en rincones o rutas opcionales para recompensar la exploración.
- Combustible recargado automáticamente cuando Mochi está en el suelo y deja de gastarlo (40 por segundo, tras 0.6 segundos).
- Objetos de objetivo ubicados cerca de los puzzles que los requieren.

**Sumideros:**

- Gasto de combustible al esprintar y al planear. Caminar, saltar y escalar no lo consumen.
- Colocación de objetos de objetivo en el mecanismo correspondiente.

## Reglas

- **Semillas como guía:** Marcan la ruta del recorrido. No se guardan en las mejillas, no ocupan espacio de inventario, no se gastan y no se disparan ni se consumen para activar mecanismos.
- **Combustible compartido:** El sprint con `SHIFT` y el planeo al mantener `ESPACIO` gastan la misma reserva, que solo se recarga en el suelo. Si se agota, no se puede esprintar ni planear hasta que vuelva al 30%. El planeo dura como máximo 0.6 segundos por tramo en el aire.
- **Objetos contextuales:** Las pilas y otros objetos de puzzle no forman parte de un inventario general. Se recogen y se colocan en su destino mediante interacción.
- **Sin pociones ni botiquines:** No existen recursos de curación. Cualquier daño provoca muerte instantánea (One-hit kill).

## Balance

- **¿Qué comportamiento queremos incentivar?:** Seguir la ruta marcada por las semillas, explorar desvíos y repartir el combustible entre el sprint y el planeo, descansando en el suelo para recargarlo.
- **¿Qué comportamiento queremos evitar?:** Esprintar o planear sin administrar el combustible y ocultar semillas fuera de la lectura del escenario.
- **Valores actuales del combustible:** capacidad de 100 puntos, sprint de 22 por segundo, planeo de 45 por segundo (máximo 0.6 segundos por tramo), recarga de 40 por segundo tras 0.6 segundos en el suelo y recuperación al 30% después de agotarse.

> **Navegación:** [[00 - Índice]] · ← [[05 - Progresión]] · [[07 - Reglas y Estados del Juego]] →
