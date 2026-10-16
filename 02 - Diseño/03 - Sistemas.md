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

### Nombre

**Objetivo:**

Proveer al jugador de una forma orgánica y temática de transportar herramientas y munición dentro de la boca del roedor.

**Entradas:**

Pulsar `E` (recoger), `Q` (rueda/selector de inventario), `SHIFT + Click` (expulsar/disparar).

**Procesamiento / reglas:**

* Comprueba si el objeto en suelo es interactuable y si hay espacio en las mejillas.
* Modifica visualmente el modelo 3D de Mochi inflando sus mejillas al guardar elementos.

* Asigna comportamiento contextual a cada ítem (semilla = proyectil; hilo = gancho; clip = llave; pila = energía; globo = elevación).

**Salidas:**

Proyectiles disparados, objetos utilizados en el escenario, cambios cosméticos en el rostro de Mochi.

**Estados posibles:**

- Vacío

- Capacidad Parcial

- Capacidad Llena

-Apuntando proyectil

**Dependencias:**

Controlador del personaje, motor de proyectiles y colisiones.

**Interacciones:**

Al escupir una semilla a un interruptor, dispara el evento del puzzle ambiental.

**Datos que necesita:**

Tipo de ítem interactuado, posición del jugador, vector de cámara (apuntado).

**Datos que genera:**

Instancia de proyectil / Uso de herramienta consumible.

**Riesgos:**

Que el jugador se quede sin munición en un lugar cerrado

**Criterios de aceptación:**

El jugador puede seleccionar y disparar un objeto con precisión y suavidad en menos de 1 segundo.

## Relaciones entre sistemas

El **Sistema de Físicas y Locomoción** interactúa con el **Sistema de Daño Absoluto**: si el cálculo de velocidad o colisión intersecta con una zona de peligro (ej. charco electrificado), el sistema de daño interrumpe inmediatamente el movimiento y activa la secuencia de muerte y recarga de checkpoint.

El **Inventario de Mejillas** alimenta a los **Puzzles de Microentorno**, ya que los proyectiles activan switches que modifican la física del escenario (apagar la corriente, soltar rampas).

Describe qué sistemas dependen de otros y qué información intercambian.

> **Navegación:** [[00 - Índice]] · ← [[02 - Mecánicas]] · [[04 - Controles]] →
