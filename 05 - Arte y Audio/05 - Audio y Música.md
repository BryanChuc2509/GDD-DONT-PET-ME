
# Audio y Música

## Descripción de la sección

Define la identidad sonora y cómo el audio comunica información al jugador.

En Don't Pet Me el hamster está en peligro todo el tiempo, así que casi siempre el aviso llega primero por el oído y después por la vista.

## Música

**Estilo:** Orquesta y sonidos acústicos con humor. Cada tipo de nivel tiene su tema, los tranquilos van con swing y acordes de jazz, los de peligro son épicos con coros, y las persecuciones son rápidas, con reloj de fondo.

**Instrumentación:**

- Orquesta: violines, cellos, contrabajo, cornos, trompetas, trombones, arpa, timbales.
- Juguetería: xilófono, glockenspiel, celesta, caja musical, kalimba, ukelele, piano de juguete.
- Mecanismo de reloj: tic-tac, engranajes, alarma de cronómetro.
- Cocina: cuchara en taza, ollas, sartén, garrafón, cafetera, microondas.
- Batería suave o híbrida según el nivel.

Todo se produjo en LMMS con samples propios (AudioFileProcessor). Cada tema tiene su proyecto `.mmp`, su `.mid` y su carpeta de sonidos.

**Temas principales:**

| Tema             | Uso                          | Tempo / Tono                | Notas                            |
| ---------------- | ---------------------------- | --------------------------- | -------------------------------- |
| Creditos Finales | Creditos del final del juego | 107 BPM, Fa menor           | Groove relajado, silbido y voces |
| Aventura         | Nivel Tutorial              | 150 BPM con swing, Fa mayor | El tema "alegre" principal       |
| Engranajes       | Nivele 1                     | 150 BPM, Mi → Fa → La♭   | Sube de tono dos veces, 3 min    |
| Run              | Nivel 2                      | 176 → 188 BPM, Do menor    | Tic-tacs que no paran            |
| Inicio           | Menú principal              | 116 BPM, Fa → Sol          | Coro de niños "la la la"        |

**Música dinámica:** Sí

- **Por capas:** LMMS exporta cada pista por separado. Así podemos tener la base sonando y meter o quitar capas según lo que pase: en exploración solo cuerdas y percusión ligera, cuando aparece una trampa entran los tic-tacs como en peligro, metales y coro.
- **Por secciones:** los temas ya vienen divididos en partes. El juego salta de una a otra al terminar el compás, nunca a la mitad.
- **Tempo:** el tempo sube con la canción. Si el jugador muere, la canción no vuelve al principio sino retoma desde la última sección antes del checkpoint.
- **Loops:** casi todos los temas tienen un OGG que se repite sin corte.

## Efectos de sonido

| Evento                      | Sonido                                                     | Propósito                                                      |
| --------------------------- | ---------------------------------------------------------- | --------------------------------------------------------------- |
| Salto                       | Pluck corto y agudo (pizzicato)                            | Confirmar que se registró el salto sin tapar la música        |
| Aterrizaje                  | Golpe suave de madera (`bloque_madera`)                  | Que el jugador sienta el piso y mida la caída                  |
| Trampa por activarse        | Tic-tac que se acelera (`tic` / `tac`)                 | Avisar con tiempo, aunque la trampa esté fuera de cámara      |
| Peligro inminente           | Alarma de cronómetro (`alarma`)                         | Último aviso antes del golpe, sube la tensión                 |
| Persecución empieza        | Alarma + latido de corazón (`latido`)                   | Marcar el cambio de ritmo antes de que entre la música         |
| Mecanismo o palanca         | Engranaje que gira (`engranaje`)                         | Avisar que algo del escenario cambió, aunque no se vea         |
| Puzzle resuelto             | "Ding" de microondas (`microondas_ding`)                 | Premio claro, es el mismo sonido de "idea" del tutorial         |
| Recoger objeto              | Nota de glockenspiel, sube con cada objeto seguido         | Recompensa rápida que anima a seguir recogiendo                |
| Checkpoint                  | Arpa en glissando + "ooh" corto del coro                   | Alivio: "aquí estás a salvo"                                  |
| Muerte del hamster          | "BOOM" de olla (`olla_boom`) + caja musical que se apaga | Que se entienda que perdió, pero con humor y sin que sea cruel |
| Reaparecer                  | Silbato que sube (`silbato_sube`)                        | Rápido y gracioso, para que morir no frustre                   |
| Abrir la jaula (tutorial)   | Rallador raspando (`rallador`) + golpe de tapa de olla   | Primer logro del juego, se tiene que sentir grande              |
| Escapar de una persecución | Golpes de stop + "¡ta-da!"                                | Cerrar la tensión con un remate claro                          |
| Navegar en menús           | Bloque de madera suave                                     | Respuesta inmediata sin cansar                                  |
| Confirmar en menús         | Nota de xilófono                                          | Distinto al de navegar para no confundirlos                     |
| Pantalla de título         | Coro cantando "Pet... Me"                                  | Presentar la marca sonora del juego                             |

## Audio espacial

Sí, pero solo para lo que pasa en el escenario. Trampas, mecanismos, enemigos y objetos suenan desde su posición: paneo izquierda-derecha y volumen según la distancia. Así el tic-tac de una trampa se oye más fuerte al acercarse y el jugador sabe de qué lado viene el peligro. La música, los sonidos de interfaz y los del propio hamster (salto, aterrizaje, muerte) no son posicionales para que siempre se oigan igual.

## Voz

**Narración:** No hay narrador. El tutorial se explica con el escenario y los sonidos.

**Diálogos hablados:** No hay diálogos. El hamster se expresa con chillidos cortos. La única "voz" con palabras es el coro que canta "Pet Me" en la pantalla de título, en el jefe final y en los créditos.

**Idiomas:** No hay voz que traducir. "Pet Me" se queda en inglés en todas las versiones porque es el nombre del juego.

## Mezcla

Define prioridades, volumen relativo y comportamiento de la música ante eventos importantes.

**Prioridad (de mayor a menor):**

1. Avisos de peligro: tic-tac de trampas, alarma.
2. Sonidos del hamster: salto, aterrizaje, muerte.
3. Recompensas: puzzle resuelto, objetos, checkpoint.
4. Música.
5. Ambiente y sonidos de fondo.

Si suenan muchos sonidos a la vez, los de menor prioridad bajan o se cortan primero.

**Volumen relativo:**

- La música va unos 6 dB por debajo de los efectos.
- Todos los temas se normalizan al mismo volumen percibido al importarlos, porque salieron de LMMS con niveles distintos.
- El grave fuerte de Galope Celestial (versión Bass) y del jefe final no debe tapar los avisos de peligro.
- Hay sliders separados de Música, Efectos e Interfaz en opciones.

**Comportamiento ante eventos:**

- **Alarma o peligro inminente:** la música baja unos 6 dB mientras suena el aviso y vuelve en medio segundo.
- **Muerte:** la música se apaga en menos de un segundo (con un filtro que la hace sonar "lejos"), suena el efecto de muerte y al reaparecer retoma desde la sección del checkpoint.
- **Pausa:** la música sigue, más baja y filtrada, para que no se sienta un corte.
- **Puzzle resuelto o checkpoint:** la música no se interrumpe; el sonido entra encima, sin pausas.
- **Jefe final:** sin bajar la música salvo en los avisos de ataque, porque la canción es parte de la pelea.

> **Navegación:** [[00 - Índice]] · ← [[04 - Interfaz Visual]] · [[01 - UX y Flujo del Jugador]] →
