# Economía y Recursos

## Descripción de la sección

Documenta cualquier recurso cuantificable: moneda, energía, experiencia, materiales, tiempo o puntos.

## Recursos

| Recurso | Obtención | Uso | Límite | Pérdida |
| --- | --- | --- | --- | --- |
| Semillas | Dispersas por el recorrido y en zonas de exploración | Moneda para comprar una skin básica; su distribución también orienta al jugador | Sin límite de almacenamiento | No se pierden al morir; las semillas recogidas no reaparecen |
| Combustible compartido | Reserva propia de Mochi; se regenera al dejar de usar `SHIFT` | Esprintar en el suelo o planear en el aire (máximo 1 segundo por tramo en el aire) | Una sola barra limitada para ambas acciones; capacidad y tasas por balancear | Se consume con cualquiera de las dos acciones y se recupera al soltar `SHIFT` |
| Pilas u otros objetos de objetivo | Colocados en zonas de puzzle | Recoger e insertar en un dispositivo, como un ventilador | Solo el objeto requerido por el desafío; no hay inventario general | Se queda en el aparato al activarlo |
| Skins | Compra con semillas o recolección total | Personalización visual de Mochi | Según skins disponibles | No se pierden al morir |

## Fuentes y sumideros

**Fuentes:**

- Semillas distribuidas en el camino principal para orientar al jugador.
- Semillas adicionales en rincones o rutas opcionales para recompensar la exploración.
- Combustible regenerado automáticamente al no usar `SHIFT`, tanto en el suelo como en el aire.
- Objetos de objetivo ubicados cerca de los puzzles que los requieren.

**Sumideros:**

- Compra de una skin básica con semillas. El precio queda pendiente de balance.
- Gasto temporal de combustible al esprintar en el suelo o planear en el aire. El gasto en una acción reduce lo disponible para la otra; caminar, saltar y escalar no lo consumen.
- Colocación de objetos de objetivo en el mecanismo correspondiente.

## Reglas

- **Semillas como moneda:** No se guardan en las mejillas, no ocupan espacio de inventario y no se disparan ni se consumen para activar mecanismos.
- **Colección completa:** Recoger todas las semillas del juego desbloquea una skin especial.
- **Combustible compartido y regenerable:** El sprint y el planeo consumen la misma reserva. El planeo dura como máximo 1 segundo por tramo en el aire; el doble salto no reinicia ese límite. Si se gasta el combustible esprintando antes de saltar, no queda reserva para planear hasta que se recupere.
- **Objetos contextuales:** Las pilas y otros objetos de puzzle no forman parte de un inventario general. Se recogen y se colocan en su destino mediante interacción.
- **Sin pociones ni botiquines:** No existen recursos de curación. Cualquier daño provoca muerte instantánea (One-hit kill).

## Balance

- **¿Qué comportamiento queremos incentivar?:** Seguir la ruta marcada por las semillas, explorar desvíos y decidir si gastar el combustible en sprintar o reservarlo para planear durante un salto. Soltar `SHIFT` permite recuperar la reserva.
- **¿Qué comportamiento queremos evitar?:** Esprintar sin administrar el combustible y descubrir demasiado tarde que no queda carga para planear un salto necesario; ocultar semillas fuera de la lectura del escenario o hacer que la compra de una skin sea obligatoria para avanzar.
- **Valores por definir:** Precio de la skin comprable, total de semillas, capacidad y tasas de consumo y regeneración de la reserva compartida; se determinan mediante pruebas de juego, verificando que el jugador deba elegir entre sprint y planeo sin que una elección equivocada haga inevitable una caída.

> **Navegación:** [[00 - Índice]] · ← [[05 - Progresión]] · [[07 - Reglas y Estados del Juego]] →
