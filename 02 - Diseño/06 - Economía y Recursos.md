# Economía y Recursos

## Descripción de la sección

Documenta cualquier recurso cuantificable: moneda, energía, experiencia, materiales, tiempo o puntos.

## Recursos

| Recurso | Obtención | Uso | Límite | Pérdida |
| --- | --- | --- | --- | --- |
| Semillas | Dispersas por el recorrido y en zonas de exploración | Moneda para comprar una skin básica; su distribución también orienta al jugador | Sin límite de almacenamiento | No se pierden al morir; las semillas recogidas no reaparecen |
| Combustible del sprint | Reserva propia de Mochi; se regenera cuando no está esprintando | Esprintar en el suelo con `SHIFT` | Barra limitada para el sprint; capacidad y tasas por balancear | Se consume únicamente al esprintar |
| Pilas u otros objetos de objetivo | Colocados en zonas de puzzle | Recoger e insertar en un dispositivo, como un ventilador | Solo el objeto requerido por el desafío; no hay inventario general | Se queda en el aparato al activarlo |
| Skins | Compra con semillas o recolección total | Personalización visual de Mochi | Según skins disponibles | No se pierden al morir |

## Fuentes y sumideros

**Fuentes:**

- Semillas distribuidas en el camino principal para orientar al jugador.
- Semillas adicionales en rincones o rutas opcionales para recompensar la exploración.
- Combustible del sprint regenerado automáticamente mientras Mochi no esprinta, tanto en el suelo como en el aire.
- Objetos de objetivo ubicados cerca de los puzzles que los requieren.

**Sumideros:**

- Compra de una skin básica con semillas. El precio queda pendiente de balance.
- Gasto temporal de combustible al esprintar en el suelo. Caminar, saltar, planear y escalar no lo consumen.
- Colocación de objetos de objetivo en el mecanismo correspondiente.

## Reglas

- **Semillas como moneda:** No se guardan en las mejillas, no ocupan espacio de inventario y no se disparan ni se consumen para activar mecanismos.
- **Colección completa:** Recoger todas las semillas del juego desbloquea una skin especial.
- **Combustible del sprint:** Solo el sprint con `SHIFT` consume la reserva y esta se regenera mientras Mochi no esprinta. El planeo al mantener `ESPACIO` no consume ni depende del combustible y dura como máximo 1 segundo por tramo en el aire; el doble salto no reinicia ese límite.
- **Objetos contextuales:** Las pilas y otros objetos de puzzle no forman parte de un inventario general. Se recogen y se colocan en su destino mediante interacción.
- **Sin pociones ni botiquines:** No existen recursos de curación. Cualquier daño provoca muerte instantánea (One-hit kill).

## Balance

- **¿Qué comportamiento queremos incentivar?:** Seguir la ruta marcada por las semillas, explorar desvíos y administrar el combustible para usar el sprint cuando convenga. El planeo permanece disponible de forma independiente, hasta 1 segundo por tramo en el aire.
- **¿Qué comportamiento queremos evitar?:** Esprintar sin administrar el combustible y ocultar semillas fuera de la lectura del escenario o hacer que la compra de una skin sea obligatoria para avanzar.
- **Valores por definir:** Precio de la skin comprable, total de semillas, capacidad y tasas de consumo y regeneración del combustible del sprint; se determinan mediante pruebas de juego.

> **Navegación:** [[00 - Índice]] · ← [[05 - Progresión]] · [[07 - Reglas y Estados del Juego]] →
