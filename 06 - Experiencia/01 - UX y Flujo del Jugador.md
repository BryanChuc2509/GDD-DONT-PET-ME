 ()

# UX y Flujo del Jugador

## Descripción de la sección

UX (experiencia de usuario) describe qué tan comprensible, cómoda y coherente resulta la interacción con el videojuego.

## Flujo principal

```text
Inicio → Menú principal → Nueva partida →  Captura (cinemática) → Jaula (Tutorial) → Habitación → Pasillo (persecución) → Sala → Final
                                ↑                                   ↓
                                └──────────────────────────────── Pausa ←───────────────────────────────────────────────────────────┘
```

El jugador puede pausar el videojuego en cualquier parte del gameplay. Si ej jugador cae o se muere regresa al último checkpoint sin tener que iniciar por el principio o el menú inicial.

## Primeros minutos

El juego comienza con una pequeña cinematica de como (10-15 segundos) el hamster es atrapado en el bosque. Seguidamente la pantalla se pone negra y comienza dentro de la jaula del cuarto donde se enseñan los controles de forma gradual. Los controles se presentan mediante Pantalla

1. **Moverse y mirar:** Mochi aparece en la jaula con espacio suficiente para caminar y explorar. El jugador aprende a desplazarse con WASD.
2. **Saltar:** Dentro de la Jaula Existen desniveles, troncos, entre otros elementos relacionados a un hámster que pueden usarse para saltar. Se usa la barra espaciadora para saltar
3. **Doble salto:** Hay zonas de la jaula que no se alcanza con un solo salto. Se muestra la indicación de presionar salto de nuevo en el aire. 
4. **Canicas:** Mochi encuentra canicas o semillas dentro de la jaula, las guarda en la boca y aprende a dispararlas contra un objetivo simple, en este caso para poder abrir el seguro de la jaula mal cerrada.
5. **Escape:** Al usar lo aprendido para abrir la jaula, Mochi sale hacia la habitación, lo que cierra el tutorial y da paso al primer momento cómico y narrativo del juego.

## Retroalimentación

Para cada acción importante define:

**Entrada → Respuesta visual → Respuesta sonora → Resultado**


| Acción                         | Entrada                       | Respuesta visual                                                                | Respuesta sonora                                                  | Resultado                                        |
| ------------------------------- | ----------------------------- | ------------------------------------------------------------------------------- | ----------------------------------------------------------------- | ------------------------------------------------ |
| Saltar                          | Espacio                       | Una pequeña nube de polvo al saltar                                            | Sonido corto y ligero de                                          | Mochi sube y puede controlar su trayectoria      |
| Doble salto                     | Doble Espacio                 | Giro rápido de Mochi                                                           | Sonido similar al primer salto pero con cierto efecto de esfuerzo | Impulso extra para alcanzar plataformas altas    |
| Recoger canica                  | Tecla E                       | Las mejillas de Mochi se hinchan y el contador del HUD aumenta                  | Sonido de “pop” suave                                           | Se suma una canica al inventario                 |
| Disparar canica                 | Clic izquierdo                | Mochi escupe la canica y el contador baja                                      | Sonido de escupitajo y rebote                                     | La canica activa un mecanismo o empuja un objeto |
| Interruptor activado            | Canica impacta el objetivo    | El objeto se ilumina y se mueve o habilita alguna plataforma                    | Sonido de clic                                                    | Se abre un nuevo camino                          |
| Ser detectado por la aspiradora | Entrar en su rango de visión | La aspiradora gira hacia Mochi y se enciende una luz roja                       | Motor que acelera y alarma corta                                  | Comienza la persecución                         |
| Caída                          | Caer al vacío                | Mochi rebota queda apachurrado con el suelo (No gráfico, a modo de burla/meme) | Sonido gracioso tipo payaso                                       | Regresa al último checkpoint                    |
| Checkpoint                      | Acercase a un bebedero.       | Pequeño animación de 2 segundos bebiendo agua                                 | Campanita suave                                                   | Checkpoint guardado                              |

## Fricción intencional

¿Qué dificultad forma parte del diseño y qué dificultad es simplemente mala experiencia de usuario?

**Dificultad que forma parte del diseño:**

* Precisión en los saltos y dobles saltos para llegar a plataformas lejanas.
* Resolver pequeños acertijos con canicas y objetos del entorno.
* Leer el comportamiento de la aspiradora para esquivarlo.
* Mantener el ritmo durante las persecuciones.
* Algunos trolleos de vez en cuando en cuanto al entorno

**Dificultad que sería mala experiencia de usuario (y se evita):**

* Cámara que se atora con los barrotes de la jaula, muebles o paredes en espacios reducidos.
* Plataformas difíciles de distinguir del fondo o saltos ciegos.
* Controles imprecisos o con retraso al saltar.
* Checkpoints lejanos que obliguen a repetir tramos largos.
* Peligros que no se entienden o no se pueden anticipar.
* Textos largos o instrucciones que interrumpan el ritmo, especialmente en el tutorial inicial.

## Descubrimiento

¿Cómo sabe el jugador:

- Qué hacer?
  El entorno describe lo que se debe hacer. Se busca utilizar una guía implicita a través de las plataformas para que el jugador sepa hacia donde tiene que ir.
- Dónde ir?
  Se busca que las plataformas sean evidentes para indicar el Camino. De igual manera se busca Agregar cierta iluminación para guiar al usuario.
- Qué puede interactuar?
  El jugador podrá ver que es un objeto interactuable cuando se acerque y salga un icono o a través de un pequeño brillo/destello distintivo
- Qué ocurrió?
  Cada acción tiene respuesta visual y sonora inmediata, por lo que el jugador entiende el efecto de sus decisiones al instante
- Por qué ganó o perdió?
  Las derrotas son visibles y claras, se muestra una vista de "Has perdido" con un pequeño mensaje de feedback como "Mochi descubrió que roer los cables no traen nada bueno"

  **Navegación:**[[00 - Índice]] · ← [[05 - Audio y Música]] · [[02 - UI y Menús]] →
