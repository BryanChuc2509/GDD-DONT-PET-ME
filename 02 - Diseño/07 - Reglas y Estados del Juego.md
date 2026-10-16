# Reglas y Estados del Juego

## Descripción de la sección

Define las reglas globales y los estados que puede atravesar el videojuego.

## Estados principales

- Menú principal
- Cinemática Prólogo
- Jugando (Exploración / Parkour)
- Pausa
- Muerte / Fracaso (One-hit Kill)
- Cinemática de Transición / Giro cómico
- Victoria de Nivel
- Créditos

## Transiciones

| Estado origen | Evento | Estado destino | Condición |
|---|---|---|---|
| Menú principal | Seleccionar "Comenzar" | Cinemática Prólogo | Nueva partida |
| Jugando | Colisión con peligro mortal (agua, corriente, enemigo) | Muerte / Fracaso | Salud = 0 (One-Hit Kill) |
| Muerte / Fracaso | Finaliza animación cómica de muerte (1.5s) | Jugando | Reaparición en último Checkpoint |
| Jugando | Activar salida del nivel (ej. saltar por ventana) | Cinemática de Transición | Objetivo del nivel completado |
| Cinemática de Transición | Concluye cinemática (revelación del pasillo) | Jugando | Carga de Nivel 2 |
| Jugando | Presionar botón ESC / Start | Pausa | En cualquier momento jugable |

## Reglas globales

1. **Regla del Único Impacto (One-Hit Kill):** Cualquier fuente de peligro ambiental o contacto con fauna/enemigo aniquila a Mochi al instante. No existe barra de vida, armadura ni invulnerabilidad temporal.
2. **Gravedad y Masa Consistentes:** Si Mochi salta sobre un objeto inestable (una regla al borde de una mesa, una pila de ropa sucia mal doblada), este cede o colapsa según la física del motor.
3. **Persistencia de Checkpoints:** Al morir, los interruptores ya accionados se mantienen y Mochi reaparece en el punto de control seguro más cercano.

## Casos especiales

- **Comer durante un peligro:** La animación cosmética de comer (`R`) se interrumpe inmediatamente si el jugador realiza cualquier input de movimiento para evitar muertes accidentales por bloqueo de animación.
- **Caída al vacío sin peligro definido:** Si Mochi cae de una mesa a un suelo sin textura letal directa, la altura excesiva activa la animación cómica de aplastamiento y el reinicio inmediato por impacto de caída.



> **Navegación:** [[00 - Índice]] · ← [[06 - Economía y Recursos]] · [[01 - Premisa y Trama]] →
