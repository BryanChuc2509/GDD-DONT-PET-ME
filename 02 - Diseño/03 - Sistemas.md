# Sistemas del Juego

## Descripción de la sección

Los sistemas son conjuntos de reglas y componentes que trabajan juntos: movimiento, progresión, economía, checkpoints, puzzles y otros.

## Inventario de sistemas

| Sistema | Propósito | Dependencias | Estado |
| --- | --- | --- | --- |
| Físicas y Locomoción de Roedor | Controlar desplazamiento, saltos, escalada de tela y rebotes en plataformas de impulso. | Motor de físicas 3D | En proceso |
| Sprint y Planeo | Aplicar sprint y planeo de hasta 0.6 segundos por tramo en el aire, que gastan la misma reserva de combustible. | Controlador del personaje, HUD | Implementado |
| Semillas | Contar las semillas recogidas de cada nivel y usarlas como guía del recorrido. | HUD | Implementado |
| Checkpoints y Daño Absoluto | Reiniciar ante colisiones letales y conservar el progreso establecido. | Sistema de persistencia | Diseñado |
| Puzzles Físicos y Objetos de Objetivo | Permitir mover utilería e interactuar con objetos contextuales, como pilas y ranuras. | Motor de físicas, sistema de interacción | En proceso |

## Sistema de Sprint y Planeo

**Objetivo:**

Permitir al jugador esprintar y planear gastando una sola reserva de combustible, para que tenga que decidir cuándo usar cada acción.

**Entradas:**

Mantener `SHIFT` al desplazarse para esprintar y mantener `ESPACIO` en el aire para planear.

**Procesamiento / reglas:**

- Una sola reserva de 100 puntos, compartida por el sprint y el planeo.
- **Sprint:** gasta 22 puntos por segundo mientras se mantiene `SHIFT` y Mochi se mueve, también durante un salto.
- **Planeo:** gasta 45 puntos por segundo; Mochi cae despacio sin ascender. Dura como máximo 0.6 segundos por tramo en el aire y el límite se reinicia al tocar el suelo o al rebotar en una plataforma de impulso.
- **Recarga:** solo en el suelo, 0.6 segundos después del último gasto, a 40 puntos por segundo.
- **Agotamiento:** al llegar a 0 no se puede esprintar ni planear hasta que la reserva vuelva al 30%.
- Al reaparecer en un checkpoint, la reserva se llena por completo.
- Caminar, saltar y escalar no gastan combustible.

**Salidas:**

Velocidad de movimiento, estado y velocidad de caída del planeo, valor del combustible y estado de agotamiento para la barra del HUD.

**Estados posibles:**

- Desplazamiento normal
- Esprintando
- Planeando
- Esperando para recargar
- Recargando en el suelo
- Agotado (sin sprint ni planeo hasta llegar al 30%)

**Dependencias:**

Controlador del personaje, sistema de entrada y HUD.

**Interacciones:**

El sprint ayuda a tomar impulso y el planeo extiende el salto, pero ambos salen de la misma reserva: correr mucho antes de saltar deja menos para planear. Ninguna de las dos acciones protege a Mochi del daño.

**Datos que necesita:**

Entradas `SHIFT` y `ESPACIO`, tiempo transcurrido, combustible disponible, tiempo de planeo del tramo actual y estado de movimiento (suelo o aire).

**Datos que genera:**

Velocidad o estado de planeo actualizado, tiempo de planeo restante, valor del combustible y estado de agotamiento para el HUD.

**Riesgos:**

Que el jugador se quede sin combustible a mitad de un tramo largo por no saber que solo se recarga en el suelo. El tutorial lo explica en pantalla: "La estamina solo se recarga en el suelo: respira en cada repisa antes del siguiente salto".

**Criterios de aceptación:**

El jugador puede esprintar con `SHIFT` y planear hasta 0.6 segundos por tramo manteniendo `ESPACIO` en el aire. Ambas acciones gastan la misma reserva, que solo se recarga en el suelo y, al agotarse, bloquea las dos hasta volver al 30%.

## Sistema de Semillas

**Objetivo:**

Usar las semillas como guía visual del recorrido, sin emplearlas como munición.

**Procesamiento / reglas:**

- Al tocar una semilla, esta se recoge automáticamente y el contador del HUD suma una.
- Al cargar cada nivel se cuentan sus semillas para mostrar `recogidas/total`; el contador empieza en 0 en cada nivel.
- Al morir y reaparecer en un checkpoint, las semillas recogidas siguen contadas y no reaparecen.

**Salidas:**

Contador de semillas del HUD actualizado.

**Dependencias:**

HUD.

## Relaciones entre sistemas

El **Sistema de Físicas y Locomoción** interactúa con el **Sistema de Daño Absoluto**: si Mochi colisiona con una zona de peligro, el sistema de daño interrumpe inmediatamente el movimiento y activa la secuencia de muerte y recarga del checkpoint.

El **Sistema de Sprint y Combustible** modifica temporalmente la velocidad del personaje. El **Sistema de Semillas** actualiza el contador del HUD al recoger semillas.

Los **Puzzles Físicos y Objetos de Objetivo** utilizan interacción contextual con elementos del escenario; no dependen de semillas como proyectiles ni de un inventario general. Cuando un puzzle requiere un objeto —por ejemplo, una pila para activar un ventilador—, un aviso breve comunica el objetivo y un indicador señala el lugar de uso al recogerlo.

Describe qué sistemas dependen de otros y qué información intercambian.

> **Navegación:** [[00 - Índice]] · ← [[02 - Mecánicas]] · [[04 - Controles]] →
