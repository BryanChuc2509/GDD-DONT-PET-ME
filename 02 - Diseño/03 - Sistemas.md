# Sistemas del Juego

## Descripción de la sección

Los sistemas son conjuntos de reglas y componentes que trabajan juntos: combate, inventario, IA, diálogo, progresión, economía, misiones, etc.

## Inventario de sistemas

| Sistema                          | Propósito                                                                                                | Dependencias                                                 | Estado     |
| -------------------------------- | --------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ | ---------- |
| Físicas y Locomoción de Roedor | Controlar la aceleración, saltos, rebotes, escalada y conservación de inercia de Mochi.                 | Motor de físicas 3D                                         | En proceso |
| Inventario de Mejillas           | Gestionar la capacidad, almacenamiento y expulsión de objetos recogidos.                                 | Sistema de interfaz (`Q`), Sistema de interacción (`E`) | En proceso |
| Daño Absoluto                   | Controlar el reinicio instantáneo ante colisiones letales (agua, electricidad, enemigos).                | Sistema de Checkpoints                                       | Diseñado  |
| Puzzles Físicos de Microentorno | Permitir el desplazamiento de utilería (libros, zapatillas multicontacto, latas) mediante masa de Mochi. | Motor de físicas de cuerpos rígidos                        | En proceso |

## Plantilla de sistema

### Sistema de Inventario de Mejillas y Disparo

**Objetivo:**

Proveer al jugador de una forma orgánica y temática de transportar herramientas y munición dentro de la boca del roedor, complementada con un sistema de apuntado con fijado (*lock-on*) asistido adaptado a la cámara de seguimiento automático.

**Entradas:**

Pulsar `E` (recoger), `Q` (rueda/selector de inventario), `CLIC DERECHO (mantener)` (apuntar y fijar objetivo con cámara), `CLIC IZQUIERDO` (expulsar/disparar objeto activo).

**Procesamiento / reglas:**

* Comprueba si el objeto en suelo es interactuable y si hay espacio disponible en las mejillas.
* Modifica visualmente el modelo 3D de Mochi inflando sus mejillas al almacenar elementos.
* **Sistema de Fijado y Cámara (Lock-on):** Debido a que la cámara no es controlada libremente por el ratón (es una cámara fija de seguimiento dinámico ligada al movimiento de Mochi), al mantener `CLIC DERECHO` el sistema proyecta un cono de detección frontal:
  - Si detecta un elemento interactuable (interruptores, dianas, trampas o enemigos), la cámara realiza un suave encuadre de fijado (*lock-on focus*) centrando la atención en el objetivo y trazando la parábola balística directa.
  - Si no hay dianas en el rango frontal, la cámara se acerca levemente y proyecta una parábola balística libre guiada por el puntero respecto a la orientación de Mochi.
* Al presionar `CLIC IZQUIERDO`, el sistema instancia el proyectil balístico y aplica el impulso cinemático correspondiente hacia el vector fijado.
* Asigna comportamiento contextual a cada ítem (semilla = proyectil; hilo = gancho; clip = llave; pila = energía; globo = elevación).

**Salidas:**

Proyectiles disparados, activación de dianas o mecanismos, objetos utilizados en el escenario, cambios visuales en el rostro de Mochi y transición dinámica en el encuadre de la cámara.

**Estados posibles:**

- Vacío
- Capacidad Parcial
- Capacidad Llena
- Apuntando con fijado de cámara (*Lock-on* activo)

**Dependencias:**

Controlador del personaje, sistema de cámara de seguimiento / cinemática, motor de físicas de proyectiles y colisiones.

**Interacciones:**

Al escupir una semilla a un interruptor fijado, dispara el evento del puzzle ambiental o aturde momentáneamente a un enemigo. Al activar una acción de movilidad con `SHIFT` (deslizarse), el estado de apuntado se cancela automáticamente.

**Datos que necesita:**

Tipo de ítem interactuado, posición del jugador, orientación de Mochi, vector y objetivo fijado por la cámara (*lock-on target*).

**Datos que genera:**

Instancia de proyectil con vector balístico / Uso de herramienta consumible.

**Riesgos:**

Que el jugador se quede sin munición en un lugar cerrado

**Criterios de aceptación:**

El jugador puede seleccionar y disparar un objeto con precisión y suavidad en menos de 1 segundo.

## Relaciones entre sistemas

El **Sistema de Físicas y Locomoción** interactúa con el **Sistema de Daño Absoluto**: si el cálculo de velocidad o colisión intersecta con una zona de peligro (ej. charco electrificado), el sistema de daño interrumpe inmediatamente el movimiento y activa la secuencia de muerte y recarga de checkpoint.

El **Inventario de Mejillas** alimenta a los **Puzzles de Microentorno**, ya que los proyectiles activan switches que modifican la física del escenario (apagar la corriente, soltar rampas).

Describe qué sistemas dependen de otros y qué información intercambian.

> **Navegación:** [[00 - Índice]] · ← [[02 - Mecánicas]] · [[04 - Controles]] →
