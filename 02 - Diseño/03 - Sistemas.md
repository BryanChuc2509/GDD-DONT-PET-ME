# Sistemas del Juego

## Descripción de la sección

Los sistemas son conjuntos de reglas y componentes que trabajan juntos: movimiento, progresión, economía, checkpoints, puzzles y otros.

## Inventario de sistemas

| Sistema | Propósito | Dependencias | Estado |
| --- | --- | --- | --- |
| Físicas y Locomoción de Roedor | Controlar desplazamiento, saltos, escalada de tela y rebotes sobre enemigos vulnerables. | Motor de físicas 3D | En proceso |
| Sprint y Planeo | Aplicar sprint con combustible propio en el suelo y planeo de hasta 1 segundo en el aire, independiente de ese combustible. | Controlador del personaje, HUD | Diseñado |
| Semillas y Cosméticos | Registrar semillas recogidas como moneda y desbloquear skins. | Persistencia, HUD, menú de cosméticos | Diseñado |
| Checkpoints y Daño Absoluto | Reiniciar ante colisiones letales y conservar el progreso establecido. | Sistema de persistencia | Diseñado |
| Puzzles Físicos y Objetos de Objetivo | Permitir mover utilería e interactuar con objetos contextuales, como pilas y ranuras. | Motor de físicas, sistema de interacción | En proceso |

## Sistema de Sprint y Planeo

**Objetivo:**

Permitir al jugador esprintar en el suelo usando una reserva de combustible propia y planear durante un máximo de 1 segundo por tramo en el aire, sin consumir esa reserva.

**Entradas:**

Mantener `SHIFT` en el suelo para esprintar y mantener `ESPACIO` en el aire para planear.

**Procesamiento / reglas:**

- En el suelo, mantener `SHIFT` aumenta temporalmente la velocidad de desplazamiento mientras quede combustible.
- En el aire, mantener `ESPACIO` activa un planeo con control horizontal limitado y descenso más lento; Mochi no asciende ni queda suspendido. El planeo no consume combustible.
- El planeo dura como máximo 1 segundo por tramo en el aire; el doble salto no reinicia ese límite.
- El sprint consume combustible mientras está activo y se detiene al agotarse la reserva. El planeo sigue disponible sin importar cuánto combustible quede.
- El combustible del sprint se regenera mientras no se está esprintando, tanto en el suelo como en el aire. Caminar, saltar, planear y escalar no lo consumen.
- La capacidad y las tasas de consumo y regeneración del sprint se determinarán mediante pruebas de balance.

**Salidas:**

Velocidad de movimiento en el suelo, estado y control de planeo en el aire, valor de combustible del sprint e indicador correspondiente en el HUD.

**Estados posibles:**

- Desplazamiento normal
- Esprintando
- Planeando
- Recuperando combustible del sprint
- Sin combustible para el sprint

**Dependencias:**

Controlador del personaje, sistema de entrada y HUD.

**Interacciones:**

El sprint facilita atravesar tramos y tomar impulso para saltar; el planeo puede extender un salto y ralentizar la caída. El combustible solo afecta al sprint y no limita el planeo. Ninguna acción protege a Mochi del daño.

**Datos que necesita:**

Entradas `SHIFT` y `ESPACIO`, tiempo transcurrido, combustible disponible para el sprint, tiempo de planeo del tramo actual y estado de movimiento (suelo o aire).

**Datos que genera:**

Velocidad o estado de planeo actualizado, tiempo de planeo restante y valor del combustible del sprint para el HUD y el guardado.

**Riesgos:**

Que el balance del sprint resulte poco claro o que una duración fija del planeo no dé suficiente control para aterrizar con justicia.

**Criterios de aceptación:**

El jugador puede esprintar en el suelo con `SHIFT`, consumiendo una reserva propia que se regenera cuando no esprinta, y planear hasta 1 segundo por tramo en el aire manteniendo `ESPACIO`, sin consumir ni depender de esa reserva.

## Sistema de Semillas y Cosméticos

**Objetivo:**

Usar las semillas como moneda coleccionable y como guía visual del recorrido, sin emplearlas como munición.

**Procesamiento / reglas:**

- Al tocar una semilla, esta se recoge automáticamente y aumenta el saldo mostrado en el HUD.
- El saldo se conserva al morir y reaparecer en un checkpoint; las semillas recogidas no reaparecen.
- Una skin básica se compra con semillas; otra skin se desbloquea al recolectar todas las semillas del juego.
- El precio de la skin comprable se ajustará durante el balance.

**Salidas:**

Saldo actualizado, progreso de colección y desbloqueos cosméticos.

**Dependencias:**

Persistencia del progreso, HUD y menú de cosméticos.

## Relaciones entre sistemas

El **Sistema de Físicas y Locomoción** interactúa con el **Sistema de Daño Absoluto**: si Mochi colisiona con una zona de peligro, el sistema de daño interrumpe inmediatamente el movimiento y activa la secuencia de muerte y recarga del checkpoint.

El **Sistema de Sprint y Combustible** modifica temporalmente la velocidad del personaje. El **Sistema de Semillas y Cosméticos** actualiza el saldo al recoger semillas y registra los desbloqueos.

Los **Puzzles Físicos y Objetos de Objetivo** utilizan interacción contextual con elementos del escenario; no dependen de semillas como proyectiles ni de un inventario general. Cuando un puzzle requiere un objeto —por ejemplo, una pila para activar un ventilador—, un aviso breve comunica el objetivo y un indicador señala el lugar de uso al recogerlo.

Describe qué sistemas dependen de otros y qué información intercambian.

> **Navegación:** [[00 - Índice]] · ← [[02 - Mecánicas]] · [[04 - Controles]] →
