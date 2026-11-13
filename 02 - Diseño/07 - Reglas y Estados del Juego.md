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
| Jugando en el suelo | Mantener `SHIFT` | Sprint activo | Hay combustible disponible |
| Jugando en el aire | Mantener `ESPACIO` | Planeo activo | No se ha agotado el máximo de 1 segundo en ese tramo en el aire |
| Sprint activo | Soltar `SHIFT` o agotar combustible | Jugando | Se detiene el sprint; la reserva se regenera mientras no se esprinta |
| Planeo activo | Soltar `ESPACIO` o alcanzar 1 segundo de planeo | Jugando | Se detiene el planeo; no depende del combustible |
| Jugando | Colisión con peligro mortal (agua, corriente, enemigo) | Muerte / Fracaso | One-Hit Kill; excepción: caer desde arriba sobre un enemigo vulnerable lo mata |
| Muerte / Fracaso | Se pulsa "Revivir" o pasan 3 s en la ventana de muerte | Jugando | Mochi ya reapareció en el último checkpoint |
| Jugando | Llegar a la meta del nivel | Victoria de Nivel | Se muestra **¡OBJETIVO CUMPLIDO!** y, unos 6 s después, se carga el siguiente nivel |
| Jugando | Presionar `ESC` o el botón de pausa del HUD | Pausa | En cualquier momento jugable, salvo con la ventana de muerte abierta |

## Reglas globales

1. **Regla del Único Impacto (One-Hit Kill):** Cualquier fuente de peligro ambiental o contacto con fauna/enemigo aniquila a Mochi al instante, excepto cuando cae desde arriba sobre un enemigo designado como vulnerable, al que mata. No existe barra de vida, armadura ni invulnerabilidad temporal.
2. **Gravedad y Masa Consistentes:** Si Mochi salta sobre un objeto inestable (una regla al borde de una mesa, una pila de ropa sucia mal doblada), este cede o colapsa según la física del motor.
3. **Persistencia de Checkpoints:** Al morir, los interruptores activados y los objetivos de puzzle completados se mantienen cuando el diseño los marque como persistentes. Mochi reaparece en el punto de control seguro más cercano.
4. **Semillas como moneda:** Las semillas se recogen al tocarlas, orientan el recorrido y aumentan el saldo; no son munición, no se usan en ataques ni se almacenan en un inventario.
5. **Colección y desbloqueos:** Una skin básica puede comprarse con semillas y la skin especial se desbloquea al recolectarlas todas. Las skins no alteran las capacidades de Mochi.
6. **Combustible exclusivo del sprint:** Mantener `SHIFT` mientras se desplaza por el suelo activa el sprint y consume su reserva, que se regenera mientras Mochi no esprinta. Mantener `ESPACIO` en el aire activa el planeo, que no consume ni depende de ese combustible y dura como máximo 1 segundo por tramo en el aire (el doble salto no reinicia el límite). El sprint y el planeo no evitan daño ni alteran las reglas de letalidad.
7. **Interacción contextual:** Los objetos de objetivo, como las pilas, se recogen y colocan en su aparato mediante interacción; no existe un inventario general de herramientas.
8. **Avisos y objetivos legibles:** En desafíos complejos aparece un consejo breve, por ejemplo, indicar que se necesitan pilas para activar un ventilador. Al obtener el objeto, un indicador visual señala su destino. Los consejos para un jefe de hormigas u otro reto deben explicar la acción necesaria sin resolver el desafío por completo.
9. **Lectura de superficies escalables:** Las superficies válidas para trepar se identifican con una textura claramente tejida; la decoración que no sea escalable no debe usar el mismo tratamiento.

## Presentación de la jaula

La jaula inicia con un encuadre amplio y poco acercado para que se entienda el espacio y que Mochi está encerrado. Cuando el jugador recibe el control o empieza a moverse, el lado de la jaula más cercano a la cámara se vuelve transparente para mantener visible al personaje y el área jugable.

## Casos especiales

- **Uso de objetos durante un peligro:** Las interacciones contextuales se interrumpen inmediatamente si el jugador recibe un impacto letal o inicia una acción de movimiento que no sea compatible.
- **Combustible agotado:** El sprint se detiene al vaciarse la reserva, aunque `SHIFT` continúe presionado. Solo se reactiva cuando vuelve a haber combustible.
- **Planeo agotado:** El planeo se interrumpe cuando se suelta `ESPACIO` o se alcanza 1 segundo de planeo en el tramo actual en el aire. El doble salto no reinicia el límite; este se reinicia al volver a tocar el suelo. El planeo no depende del combustible del sprint.
- **Caída al vacío sin peligro definido:** Si Mochi cae desde una altura excesiva a un suelo no letal, se activa la animación cómica de aplastamiento y el reinicio inmediato por impacto de caída.
- **Semillas y reaparición:** Las semillas ya recogidas permanecen en el saldo y no reaparecen tras morir.

> **Navegación:** [[00 - Índice]] · ← [[06 - Economía y Recursos]] · [[01 - Premisa y Trama]] →
