# UI y Menús

## Descripción de la sección

Define la estructura funcional de las interfaces y menús.

## Mapa de navegación

```text
Menú principal
├── Jugar (sin partida guardada) / Continuar (con partida guardada)
├── Nueva partida (solo con partida guardada; pide confirmación)
├── Ajustes
│   ├── Volumen general, música y efectos de sonido
│   ├── Ver controles
│   └── Restablecer ajustes
└── Salir del juego

Durante el juego
├── HUD
├── Ventana de muerte
└── Pausa (botón del HUD o Esc)
    ├── Continuar
    ├── Ajustes
    │   └── Ver controles
    └── Salir del juego
```

## Pantallas

### - Menú principal

**Propósito:** La vista principal al iniciar el juego. Permite comenzar el juego o continuarlo.

**Elementos:** Logo "Don't Pet Me" arriba a la izquierda y, debajo, la columna de botones. A la derecha, una escena 3D de la habitación (pared, ventana, cuadro, taza, libros y una pila) con Mochi animado de pie sobre la pila. Suena la música del menú. No muestra número de versión.

**Acciones disponibles:** Jugar o Continuar, Nueva partida, Ajustes y Salir del juego. Se navega con ratón y teclado; `Esc` cierra los ajustes o la confirmación.

**Estados:**

* **Sin partida guardada:** el botón principal dice "Jugar" y "Nueva partida" no aparece.
* **Con partida guardada:** el botón principal dice "Continuar" y aparece "Nueva partida". La partida guardada es el último nivel que se cargó (`GameProgress` lo guarda al entrar a cada nivel; no cuentan el menú ni la introducción).
* El botón bajo el ratón o seleccionado crece y suena.

**Transiciones:** "Jugar" lleva a la introducción y luego al tutorial de la jaula. "Continuar" carga el **inicio** del último nivel guardado, no el último checkpoint. "Nueva partida" abre la confirmación; si se acepta, borra la partida guardada y empieza desde la introducción. Al empezar a jugar, Mochi festeja y la pantalla se funde a negro. "Salir del juego" cierra el juego tras un fundido. "Ajustes" abre la ventana de ajustes.

#### - Introducción narrativa

**Propósito:** Contar la captura de Mochi en el picnic y su objetivo de volver al bosque, sin necesidad de jugar ese nivel.

**Elementos:** Video de la cinemática de inicio y el aviso "Presiona ESPACIO para saltar la historia" abajo a la derecha, que aparece con un fundido tras un momento.

**Acciones disponibles:** Ver la introducción o saltarla con `Espacio`. Durante el primer medio segundo no se puede saltar, para evitar saltos accidentales.

**Estados:** El aviso para saltar queda visible durante el video.

**Transiciones:** Al terminar o saltarla, entra directamente al tutorial de la jaula. Si el video no se puede reproducir, se pasa al tutorial.

#### HUD (interfaz en juego)

**Propósito:** Mostrar la información mínima necesaria sin tapar la escena.

**Elementos:** Contador de semillas (`recogidas/total` del nivel), contador de muertes, botón de objetivo con su tarjeta, barra de estamina, botón de pausa, avisos centrales y cuenta atrás del memorama. En cada nivel se suman los paneles de tutorial, los carteles de zona difícil y el marcador de entrega de la pila. El detalle visual está en [[04 - Interfaz Visual]]. No muestra vida, munición, mapa ni retícula de apuntado.

**Acciones disponibles:** Es informativo. Solo se puede pulsar el botón de pausa y la bandera del objetivo (o usar `Tab`) para volver a ver el objetivo actual.

**Estados:** El contador de semillas cambia al recoger una. La tarjeta del objetivo se anuncia cada vez que cambia y luego se reduce a la bandera. La barra de estamina avisa cuando se agota. Las indicaciones del tutorial aparecen en su zona y desaparecen al salir de ella.

**Transiciones:** Aparece al cargar cada nivel. Sigue visible detrás de las ventanas de pausa y de muerte, que oscurecen la escena. Al completar un nivel, la tarjeta muestra **¡OBJETIVO CUMPLIDO!** con el mensaje del nivel (por ejemplo, "¡Nivel 1 completado!") y, unos 6 s después, se carga el siguiente nivel.

#### - Menú de pausa

**Propósito:** Detener el juego para que el jugador pueda ajustar opciones o salir.

**Elementos:** Ventana **MENÚ** sobre la escena oscurecida, con botón de cerrar (X) y los botones Continuar (principal), Ajustes y Salir del juego.

**Acciones disponibles:** Reanudar (Continuar, la X o `Esc`), abrir los ajustes o salir del juego.

**Estados:** El juego queda detenido mientras el menú está abierto. No se abre si la ventana de muerte ya está en pantalla.

**Transiciones:** `Esc` o el botón de pausa del HUD abren y cierran la pausa. Dentro de Ajustes o Controles, `Esc` regresa un paso. "Salir del juego" cierra el juego directamente.

#### - Ajustes

**Propósito:** Permitir que cada jugador ajuste el sonido y consulte los controles.

**Elementos:** Ventana **AJUSTES** con botón de cerrar (X):

* **Volumen general, Música y Efectos de sonido:** deslizadores con su porcentaje.
* **Controles:** botón "Ver controles", que abre la ventana de controles.
* **Restablecer ajustes:** devuelve los tres volúmenes al 100%.

**Acciones disponibles:** Cambiar los volúmenes, ver los controles, restablecer y cerrar.

**Estados:** Los cambios de volumen se aplican al instante y se guardan al cerrar la ventana, así que se recuerdan entre sesiones.

**Transiciones:** Se abre desde el menú principal o desde la pausa y, al cerrarse, regresa a la pantalla de origen.

#### - Controles

**Propósito:** Consultar qué tecla hace cada acción.

**Elementos:** Ventana **CONTROLES** con dos columnas, acción y tecla:

| Acción | Tecla |
| --- | --- |
| Moverse | WASD / flechas |
| Cámara | Ratón |
| Saltar | Espacio |
| Planear | Mantén Espacio en el aire |
| Correr | Shift |
| Ver objetivo | Tab |
| Pausa | Esc |

**Acciones disponibles:** Solo consulta.

**Transiciones:** Al cerrarla (X o `Esc`) se vuelve a Ajustes.

#### - Ventana de muerte

**Propósito:** Decir por qué murió Mochi y volver a jugar rápido.

**Elementos:** Insignia de calavera con el contador de muertes, el título **HAS MUERTO**, la causa (por ejemplo, "¡Trampa de ratón! Ten cuidado con las trampas de ratón" o "¡Aplastado!"), el botón **Revivir** y el texto "Reviviendo en 3s".

**Acciones disponibles:** Pulsar "Revivir" o esperar la cuenta atrás.

**Estados:** El juego queda en pausa mientras la ventana está abierta; Mochi ya está colocado en el último checkpoint.

**Transiciones:** A los 3 s, o al pulsar "Revivir", la ventana se cierra y el juego continúa desde el último checkpoint.

## Confirmaciones

| Acción | Confirmación | Razón |
| --- | --- | --- |
| Nueva partida (si ya existe una partida guardada) | Ventana **¿NUEVA PARTIDA?** con el mensaje "Se borrará tu progreso guardado." y los botones "Sí, empezar" / "Cancelar". "Cancelar" queda seleccionado por defecto. | Borra la partida guardada |

>
> **Navegación:** [[00 - Índice]] · ← [[01 - UX y Flujo del Jugador]] · [[03 - Accesibilidad]] →
