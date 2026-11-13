# Jugabilidad

## Descripción de la sección

La jugabilidad explica **qué hace el jugador, qué recibe a cambio y cómo evoluciona la experiencia**.

## Bucle principal de juego

Describe el ciclo que se repite durante la experiencia.

**Ejemplo conceptual:**

`Explorar → Encontrar desafío → Resolver → Obtener recompensa → Mejorar → Explorar`

**Bucle del proyecto:**

`Mochi debe evaluar cada habitación humana como un circuito colosal de plataformas. Sigue semillas que sirven como monedas y guía visual, escala superficies de tela reconocibles, salta sobre los enemigos para apartarlos del camino y administra el combustible del sprint para superar tramos exigentes. El planeo funciona de forma independiente, hasta 1 segundo por tramo en el aire.`

El recorrido jugable se divide en tres niveles consecutivos: **Tutorial (Nivel 0) — la jaula, Nivel 1 — el cuarto de Leo y Nivel 2 — el pasillo**. En el tutorial, Mochi aprende las acciones básicas y escapa de la jaula. En el cuarto, el recorrido se divide en zonas consecutivas: **1) escritorio, 2) libros colgantes y 3) pasillo de pelotas que caen**, donde Mochi debe avanzar y encontrar un hueco seguro. Las zonas enseñan y combinan las mecánicas antes de conducir al pasillo.

## Acciones principales del jugador

| Acción                                                     | Propósito                                                                                                                         | Resultado                                                                                                                                                                   |
| ----------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Desplazamiento y parkour** (`WASD` + `Espacio`) | Saltar abismos, encadenar saltos y escalar superficies de tela.                                                                    | Mochi gana altura y conserva la inercia para recorrer plataformas.                                                                                                          |
| **Sprint** (`Shift`)                       | Aumentar temporalmente la velocidad al desplazarse por el suelo. | Consume combustible propio; al agotarse, Mochi vuelve a su velocidad normal. |
| **Planeo** (`Espacio` mantenido en el aire) | Avanzar un poco más y ralentizar la caída durante un salto. | No consume ni depende de combustible; dura como máximo 1 segundo por tramo en el aire. |
| **Escalar tela**                                      | Trepar por superficies cuya textura tejida comunica que son escalables.                                                            | Mochi asciende mientras conserve contacto con la superficie.                                                                                                                |
| **Aplastar enemigos** (saltar sobre ellos)            | Aprovechar la altura para aplastar enemigos, no jefes.                                                                            | Abre una oportunidad para continuar sin convertir el juego en uno de combate.                                                                                               |
| **Recoger semillas** (contacto)                       | Obtener monedas y seguir la ruta sugerida por su distribución.                                                                    | Aumenta el saldo; las semillas no son munición ni se guardan en un inventario.                                                                                             |
| **Empuje de físicas** (moverse contra el objeto)     | Mover objetos del escenario, como libros y cajas.                                                                                  | Habilita rampas, plataformas o caminos alternos.                                                                                                                            |

## Experiencia segundo a segundo

¿Qué hace el jugador durante los primeros minutos?

La jaula abre con un plano amplio y poco acercado que permite reconocer sus barrotes y el escenario. Al comenzar el control de Mochi, el barrote lateral más cercano a la cámara se vuelve transparente para mantener visible al personaje y el espacio de juego. El tutorial introduce movimiento y salto; después enseña el sprint en el suelo con `Shift` y el planeo en el aire manteniendo `Espacio`, dejando claro que solo el sprint consume combustible y que el planeo está disponible independientemente de la reserva. También enseña la escalada por una superficie de tela y el salto sobre enemigos.

## Experiencia minuto a minuto

¿Qué actividades se repiten durante una sesión?

El jugador alterna entre secciones de plataformas de precisión, puzzles físicos (empujar libros o colocar pilas en aparatos), exploración de semillas-moneda y momentos de tensión cómica al esquivar amenazas. En los saltos, decide cuándo gastar combustible en correr antes del despegue; el planeo se puede usar de forma independiente para controlar la caída. Los avisos breves aparecen solo en zonas donde una pista es necesaria; por ejemplo, indican que se necesitan pilas para activar un ventilador. Al obtener el objeto, un indicador visual señala el ventilador o la ranura donde colocarlo.

## Experiencia a largo plazo

¿Qué hace que el jugador quiera continuar?

El deseo de ver qué nueva habitación o trampa absurda de la cotidianidad humana tocará superar, sumado al humor satírico de las falsas esperanzas de escape que sufren Mochi y su orgullo de hámster.

## Condición de victoria

¿Qué debe lograr el jugador para avanzar o terminar?

Sobrevivir al recorrido lineal del mapa y alcanzar el punto físico de transición al final del nivel.

## Condición de derrota

¿Qué situaciones provocan fracaso?

Muerte instantánea (One-hit kill). Al no existir un sistema de curación, cualquier error fatal reinicia la partida en el último punto de control. Esto incluye caer al vacío, tocar agua o líquidos electrificados, y ser alcanzado por enemigos (arañas, el gato o el robot aspirador).

## Ritmo

Describe cómo alternan:

- **Exploración** Seguir semillas-moneda como guía visual y analizar el entorno.
- **Acción** Secuencias de huida pura donde no hay tiempo para pensar, como escapar del radio de succión del robot aspirador o saltar sobre notas adhesivas que se caen a los dos segundos.
- **Descanso** Zonas seguras dentro de madrigueras improvisadas o la jaula inicial
- **Desafío** Zonas de plataformeo vertical, enemigos que se pueden aplastar desde arriba y puzzles contextuales de objetos.
- **Recompensa** Monedas para comprar una skin básica y una skin especial por recolectar todas las semillas.
- Historia Revelación humorística de que la supuesta libertad no era más que otro escenario.

## Principios de interacción

¿Qué reglas debe seguir el juego para que las acciones del jugador sean claras, consistentes y predecibles?

**Letalidad Coherente:** El peligro no es una barra que baja lentamente. Si un elemento es letal para un roedor de 100 gramos en la vida real, en el juego provoca la muerte inmediata.

**Lectura del recorrido y de las interacciones:** Las semillas forman una guía visual sin sustituir la exploración. Las superficies escalables se distinguen con una textura claramente tejida; los objetos de objetivo, como pilas y ranuras, muestran una señal contextual y un indicador de destino cuando corresponde.

**Físicas Exageradas y Satíricas:** Aunque la gravedad y los saltos son predecibles para el parkour, las interacciones con el entorno están al servicio del humor absurdo. Mochi puede tener una fuerza desproporcionada para empujar ciertos obstáculos clave, y el escenario puede reaccionar de forma cómicamente injusta (objetos que caen "de la nada" o trampas que se activan solas) para alimentar la comedia trágica de su escape.

> **Navegación:** [[00 - Índice]] · ← [[04 - Pilares de Diseño]] · [[02 - Mecánicas]] →
