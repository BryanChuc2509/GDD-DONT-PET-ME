# Reglas y Estados del Juego

## Descripción de la sección

Define las reglas globales y los estados que puede atravesar el videojuego.

## Estados principales

- Menú principal
- Cinemática de introducción
- Jugando (Exploración / Parkour)
- Sprint activo
- Planeo activo
- Pausa
- Muerte / Fracaso (One-hit Kill)
- Victoria de Nivel

## Transiciones

| Estado origen | Evento | Estado destino | Condición |
|---|---|---|---|
| Menú principal | Seleccionar "Jugar" o "Nueva partida" | Cinemática de introducción | Empieza una partida desde el inicio |
| Jugando | Mantener `SHIFT` al desplazarse | Sprint activo | Mochi no está agotado |
| Jugando en el aire | Mantener `ESPACIO` mientras cae | Planeo activo | Mochi no está agotado y no ha usado los 0.6 segundos de planeo de ese tramo en el aire |
| Sprint activo | Soltar `SHIFT` o agotar el combustible | Jugando | Se detiene el sprint; la reserva se recarga en el suelo poco después de dejar de gastar |
| Planeo activo | Soltar `ESPACIO`, alcanzar 0.6 segundos de planeo, agotar el combustible o aterrizar | Jugando | Se detiene el planeo |
| Jugando | Colisión con peligro mortal (agua, corriente, enemigo) | Muerte / Fracaso | One-Hit Kill |
| Muerte / Fracaso | Se pulsa "Revivir" o pasan 3 s en la ventana de muerte | Jugando | Mochi ya reapareció en el último checkpoint |
| Jugando | Llegar a la meta del nivel | Victoria de Nivel | Se muestra **¡OBJETIVO CUMPLIDO!** y, unos 6 s después, se carga el siguiente nivel |
| Jugando | Presionar `ESC` o el botón de pausa del HUD | Pausa | En cualquier momento jugable, salvo con la ventana de muerte abierta |

## Reglas globales

1. **Regla del Único Impacto (One-Hit Kill):** Cualquier fuente de peligro ambiental o contacto con fauna/enemigo aniquila a Mochi al instante. No existe barra de vida, armadura ni invulnerabilidad temporal.
2. **Gravedad y Masa Consistentes:** Si Mochi salta sobre un objeto inestable (una regla al borde de una mesa, una pila de ropa sucia mal doblada), este cede o colapsa según la física del motor.
3. **Persistencia de Checkpoints:** Al morir, los interruptores activados y los objetivos de puzzle completados se mantienen cuando el diseño los marque como persistentes. Mochi reaparece en el punto de control seguro más cercano.
4. **Semillas como guía:** Las semillas se recogen al tocarlas y orientan el recorrido; el HUD cuenta las recogidas y el total del nivel. No son munición, no se usan en ataques ni se almacenan en un inventario.
5. **Combustible compartido:** Mantener `SHIFT` al desplazarse activa el sprint y mantener `ESPACIO` en el aire activa el planeo; los dos gastan la misma reserva. La reserva solo se recarga en el suelo, poco después de dejar de gastar, y se llena al reaparecer en un checkpoint. Si se agota, no se puede esprintar ni planear hasta que vuelva al 30%. El planeo dura como máximo 0.6 segundos por tramo en el aire. El sprint y el planeo no evitan daño ni alteran las reglas de letalidad.
6. **Interacción contextual:** Los objetos de objetivo, como las pilas, se recogen y colocan en su aparato mediante interacción; no existe un inventario general de herramientas.
7. **Avisos y objetivos legibles:** En desafíos complejos aparece un consejo breve, por ejemplo, indicar que se necesitan pilas para activar un ventilador. Al obtener el objeto, un indicador visual señala su destino. Los consejos para un jefe de hormigas u otro reto deben explicar la acción necesaria sin resolver el desafío por completo.
8. **Lectura de superficies escalables:** Las superficies válidas para trepar se identifican con una textura claramente tejida; la decoración que no sea escalable no debe usar el mismo tratamiento.

## Presentación de la jaula

La jaula inicia con un encuadre amplio y poco acercado para que se entienda el espacio y que Mochi está encerrado. Cuando el jugador recibe el control o empieza a moverse, el lado de la jaula más cercano a la cámara se vuelve transparente para mantener visible al personaje y el área jugable.

## Casos especiales

- **Uso de objetos durante un peligro:** Las interacciones contextuales se interrumpen inmediatamente si el jugador recibe un impacto letal o inicia una acción de movimiento que no sea compatible.
- **Combustible agotado:** El sprint y el planeo se detienen al vaciarse la reserva, aunque `SHIFT` o `ESPACIO` sigan presionados. Solo se reactivan cuando la reserva vuelve al 30%, recargándose en el suelo.
- **Planeo agotado:** El planeo se interrumpe al soltar `ESPACIO`, al alcanzar 0.6 segundos de planeo en el tramo actual o al acabarse el combustible. El límite de tiempo se reinicia al tocar el suelo o al rebotar en una plataforma de impulso.
- **Caída al vacío sin peligro definido:** Si Mochi cae desde una altura excesiva a un suelo no letal, se activa la animación cómica de aplastamiento y el reinicio inmediato por impacto de caída.
- **Semillas y reaparición:** Las semillas ya recogidas siguen contadas en el HUD y no reaparecen tras morir.

> **Navegación:** [[00 - Índice]] · ← [[06 - Economía y Recursos]] · [[01 - Premisa y Trama]] →
