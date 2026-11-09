 ()

# UX y Flujo del Jugador

## Descripción de la sección

UX (experiencia de usuario) describe qué tan comprensible, cómoda y coherente resulta la interacción con el videojuego.

## Flujo principal

```text
Inicio → Menú principal → Nueva partida → Cómic de captura → Jaula (tutorial)
       → Habitación (escritorio y hormigas → libros colgantes
         → estantería con pelotas → memorama)
       → Pasillo (persecución) → Salida del pasillo
                                 ↑             ↓
                                 └── Pausa ────┘
```

La jaula es la primera zona de la habitación, no un nivel aparte. El jugador puede pausar durante el gameplay. Si Mochi muere por un peligro, reaparece en el último checkpoint.

## Primeros minutos

El juego comienza con una breve introducción tipo cómic que muestra la captura de Mochi durante el picnic familiar y establece su deseo de volver con Copo y Trufa. Después, Mochi despierta en la jaula y el tutorial introduce las acciones básicas de forma gradual, sin interrumpir innecesariamente el juego.

1. **Movimiento:** El jugador aprende a desplazarse y explorar el espacio de la jaula.
2. **Salto:** El entorno presenta desniveles sencillos para practicar el salto antes de afrontar plataformas más exigentes.
3. **Escape:** Mochi sale de la jaula y comienza el recorrido por la habitación. La forma exacta de abrir la jaula se define en el diseño del nivel.
4. **Lectura del entorno:** Señales visuales ayudan a identificar rutas, peligros, refugios y objetos con los que se puede interactuar.
5. **Desafíos principales:** El jugador consigue pilas y activa el ventilador para superar el encuentro de las hormigas; después se refugia en huecos de la estantería para evitar las pelotas y repite en orden la secuencia del memorama.
6. **Persecución:** En el pasillo, la aspiradora persigue a Mochi y el jugador combina movimiento y lectura de los obstáculos para alcanzar la salida.

## Retroalimentación

Para cada acción importante define:

**Entrada → Respuesta visual → Respuesta sonora → Resultado**


| Acción | Entrada | Respuesta visual | Respuesta sonora | Resultado |
| --- | --- | --- | --- | --- |
| Movimiento y salto | Teclas de movimiento y salto | Animación de Mochi y respuesta visible al despegar y aterrizar | Efectos breves asociados al movimiento | El jugador comprende el control y la distancia del salto |
| Recoger semillas | Tocar una semilla | La semilla desaparece y el saldo del HUD se actualiza | Sonido breve de recolección | Aumenta la moneda; no se añade munición ni un objeto de uso |
| Interactuar con el ventilador | Acercarse y usar la interacción contextual | Se indica el objeto interactuable y el cambio de estado del mecanismo | Sonido de activación | El ventilador se activa y despeja el paso del encuentro de hormigas |
| Memorizar las baldosas | Observar la muestra | Los cuadros se iluminan en una secuencia de colores | Señal breve por cada cuadro, si se implementa | El jugador observa el orden antes de repetirlo saltando |
| Refugiarse de una pelota | Entrar en un hueco de la estantería | La pelota pasa sin alcanzar a Mochi | Sonido de impacto de la pelota en el entorno | El jugador puede continuar ascendiendo |
| Inicio de persecución | La aspiradora detecta a Mochi | La aspiradora se orienta hacia él y comienza a seguirlo | El motor se vuelve audible o cambia de intensidad | El jugador reconoce que debe escapar |
| Muerte y reaparición | Tocar un peligro letal o caer | Se muestra brevemente la consecuencia y la transición al checkpoint | Efecto breve de impacto o fallo | Mochi reaparece en el último checkpoint |
| Activar un checkpoint | Alcanzar el punto de control definido en el nivel | Una señal visual confirma su activación | Señal sonora breve | La reaparición queda actualizada |

## Fricción intencional

¿Qué dificultad forma parte del diseño y qué dificultad es simplemente mala experiencia de usuario?

**Dificultad que forma parte del diseño:**

* Calcular los saltos entre plataformas y el momento para avanzar.
* Observar y repetir correctamente la secuencia del memorama.
* Leer el ritmo de las pelotas de tenis y usar los huecos como refugio.
* Escapar de la aspiradora mientras se evitan las trampas del pasillo.
* Aprender de los peligros inesperados sin tener que repetir tramos largos.

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
  El entorno y las indicaciones breves del tutorial explican el objetivo inmediato; la forma de las plataformas ayuda a leer la ruta.
- Dónde ir?
  Las plataformas y señales visuales distinguen la ruta principal de los desvíos y refugios.
- Qué puede interactuar?
  Un indicador contextual aparece al acercarse a un objeto interactuable.
- ¿Qué ocurrió?
  Las acciones importantes tienen una respuesta visual y sonora clara, para que el jugador entienda el efecto de sus decisiones.
- Por qué ganó o perdió?
  Los peligros letales y la reaparición en el checkpoint dejan claro por qué falló el intento. No hace falta interrumpir el flujo con una pantalla de derrota extensa.

> **Navegación:** [[00 - Índice]] · ← [[05 - Audio y Música]] · [[02 - UI y Menús]] →
