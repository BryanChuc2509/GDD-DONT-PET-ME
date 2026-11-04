# Sistemas del Juego

## Descripción de la sección

Los sistemas son conjuntos de reglas y componentes que trabajan juntos: movimiento, progresión, economía, checkpoints, puzzles y otros.

## Inventario de sistemas

| Sistema | Propósito | Dependencias | Estado |
| --- | --- | --- | --- |
| Físicas y Locomoción de Roedor | Controlar desplazamiento, saltos, escalada de tela y rebotes sobre enemigos vulnerables. | Motor de físicas 3D | En proceso |
| Sprint, Planeo y Combustible | Aplicar sprint en el suelo o planeo breve en el aire con una sola reserva compartida; regenerarla al soltar `SHIFT`. | Controlador del personaje, HUD | Diseñado |
| Semillas y Cosméticos | Registrar semillas recogidas como moneda y desbloquear skins. | Persistencia, HUD, menú de cosméticos | Diseñado |
| Checkpoints y Daño Absoluto | Reiniciar ante colisiones letales y conservar el progreso establecido. | Sistema de persistencia | Diseñado |
| Puzzles Físicos y Objetos de Objetivo | Permitir mover utilería e interactuar con objetos contextuales, como pilas y ranuras. | Motor de físicas, sistema de interacción | En proceso |

## Sistema de Sprint, Planeo y Combustible

**Objetivo:**

Permitir al jugador administrar una sola reserva de combustible para esprintar en el suelo o planear brevemente durante un salto.

**Entradas:**

Mantener o soltar `SHIFT`.

**Procesamiento / reglas:**

- En el suelo, mantener `SHIFT` aumenta temporalmente la velocidad de desplazamiento mientras quede combustible.
- En el aire, mantener `SHIFT` activa un planeo con control horizontal limitado y descenso más lento; Mochi no asciende ni queda suspendido.
- Sprint y planeo consumen el mismo combustible. El planeo dura como máximo 1 segundo por tramo en el aire; el doble salto no reinicia ese límite.
- El combustible se regenera al soltar `SHIFT`, tanto en el suelo como en el aire; caminar, saltar y escalar no lo consumen.
- Al agotarse el combustible, la acción activa termina. Si no queda combustible al despegar, no se puede planear en ese salto.
- La capacidad y las tasas de consumo y regeneración se determinarán mediante pruebas de balance para que el sprint prolongado pueda dejar insuficiente combustible para planear.

**Salidas:**

Velocidad de movimiento en el suelo, estado y control de planeo en el aire, valor actualizado de combustible e indicador correspondiente en el HUD.

**Estados posibles:**

- Desplazamiento normal
- Esprintando
- Planeando
- Recuperando combustible
- Sin combustible

**Dependencias:**

Controlador del personaje, sistema de entrada y HUD.

**Interacciones:**

El sprint facilita atravesar tramos y tomar impulso para saltar; el planeo puede extender un salto y ralentizar la caída. Gastar combustible en una acción reduce lo disponible para la otra. Ninguna protege a Mochi del daño.

**Datos que necesita:**

Entrada `SHIFT`, tiempo transcurrido, combustible disponible, tiempo de planeo del salto actual y estado de movimiento (suelo o aire).

**Datos que genera:**

Velocidad o estado de planeo actualizado, tiempo de planeo restante y valor de combustible para el HUD y el guardado.

**Riesgos:**

Que el balance permita esprintar y planear sin tomar decisiones, o que agotar el combustible provoque una caída inevitable sin una oportunidad justa de recuperarlo.

**Criterios de aceptación:**

El jugador puede esprintar en el suelo y planear hasta 1 segundo por tramo en el aire con `SHIFT`; ambas acciones reducen la misma barra de combustible, que se regenera al soltar la tecla. Si gasta la reserva en el sprint, el planeo no se activa hasta recuperar combustible.

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
