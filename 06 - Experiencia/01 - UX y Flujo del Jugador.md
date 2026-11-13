 ()

# UX y Flujo del Jugador

## Descripción de la sección

UX (experiencia de usuario) describe qué tan comprensible, cómoda y coherente resulta la interacción con el videojuego.

## Flujo principal

```text
Inicio → Menú principal → Nueva partida → Cómic de captura → Tutorial: jaula (Nivel 0)
       → Habitación, Nivel 1 (escritorio y hormigas → libros colgantes
         → estantería con pelotas → memorama)
       → Pasillo (persecución) → Salida del pasillo
                                 ↑             ↓
                                 └── Pausa ────┘
```

El juego tiene tres niveles: el tutorial de la jaula (Nivel 0), la habitación (Nivel 1) y el pasillo (Nivel 2). El jugador puede pausar durante el gameplay. Si Mochi muere por un peligro, reaparece en el último checkpoint.

## Primeros minutos

El juego comienza con una breve introducción tipo cómic que muestra la captura de Mochi durante el picnic familiar y establece su deseo de volver con Copo y Trufa. Después, Mochi despierta en la jaula y el tutorial introduce las acciones básicas de forma gradual, sin interrumpir innecesariamente el juego.

1. **Movimiento:** El jugador aprende a desplazarse y explorar el espacio de la jaula.
2. **Salto:** El entorno presenta desniveles sencillos para practicar el salto antes de afrontar plataformas más exigentes.
3. **Escape:** Mochi sale de la jaula y completa el tutorial; después comienza el recorrido por la habitación (Nivel 1). La forma exacta de abrir la jaula se define en el diseño del nivel.
4. **Lectura del entorno:** Señales visuales ayudan a identificar rutas, peligros, refugios y objetos con los que se puede interactuar.
5. **Desafíos principales:** El jugador consigue pilas y activa el ventilador para superar el encuentro de las hormigas; después se refugia en huecos de la estantería para evitar las pelotas y repite en orden la secuencia del memorama.
6. **Persecución:** En el pasillo, la aspiradora persigue a Mochi y el jugador combina movimiento y lectura de los obstáculos para alcanzar la salida.

## Retroalimentación

Para cada acción importante define:

**Entrada → Respuesta visual → Respuesta sonora → Resultado**

| Acción | Entrada | Respuesta visual | Respuesta sonora | Resultado |
| --- | --- | --- | --- | --- |
| Movimiento y salto | Teclas de movimiento y salto | Animación de Mochi y respuesta visible al despegar y aterrizar | Efectos breves asociados al movimiento | El jugador comprende el control y la distancia del salto |
| Recoger semillas | Tocar una semilla | La semilla desaparece, el contador de semillas del HUD suma una y su icono da un salto | Sonido breve de recolección | El contador avanza; no se añade munición ni un objeto de uso |
| Interactuar con el ventilador | Llevar la pila hasta el compartimento del ventilador | Mientras Mochi carga una pila, un marcador señala el ventilador; el objetivo del HUD cuenta las pilas colocadas (x/3) y un aviso confirma que se enciende | Sonido de activación | El ventilador se activa y despeja el paso del encuentro de hormigas |
| Memorizar las baldosas | Observar la muestra | Los cuadros se iluminan en una secuencia de colores | Señal breve por cada cuadro, si se implementa | El jugador observa el orden antes de repetirlo saltando |
| Refugiarse de una pelota | Entrar en un hueco de la estantería | La pelota pasa sin alcanzar a Mochi | Sonido de impacto de la pelota en el entorno | El jugador puede continuar ascendiendo |
| Inicio de persecución | La aspiradora detecta a Mochi | La aspiradora se orienta hacia él y comienza a seguirlo | El motor se vuelve audible o cambia de intensidad | El jugador reconoce que debe escapar |
| Muerte y reaparición | Tocar un peligro letal o caer | Mochi reaparece en el último checkpoint y se abre la ventana **HAS MUERTO** con la causa y el contador de muertes; se cierra sola a los 3 s o con "Revivir" | Efecto del peligro y sonido de la ventana de muerte | Mochi reaparece en el último checkpoint |
| Activar un checkpoint | Alcanzar el punto de control definido en el nivel | El aviso "Checkpoint" aparece en el centro y Mochi festeja | Señal sonora breve | La reaparición queda actualizada |

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
  La tarjeta de objetivo del HUD anuncia cada objetivo nuevo y se puede volver a ver con `Tab`. El entorno y las indicaciones breves del tutorial lo explican; la forma de las plataformas ayuda a leer la ruta.
- Dónde ir?
  Las plataformas y señales visuales distinguen la ruta principal de los desvíos y refugios.
- Qué puede interactuar?
  Las pilas se recogen al tocarlas y, mientras Mochi carga una, un marcador en pantalla señala dónde llevarla. Los carteles de zona avisan de los retos importantes.
- ¿Qué ocurrió?
  Las acciones importantes tienen una respuesta visual y sonora clara, para que el jugador entienda el efecto de sus decisiones.
- Por qué ganó o perdió?
  La ventana de muerte dice la causa de cada muerte y cuántas lleva el jugador, y se cierra sola a los 3 s para no cortar el ritmo. Al completar un nivel, la tarjeta del objetivo muestra **¡OBJETIVO CUMPLIDO!**.

> **Navegación:** [[00 - Índice]] · ← [[05 - Audio y Música]] · [[02 - UI y Menús]] →
