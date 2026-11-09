# UI y Menús

## Descripción de la sección

Define la estructura funcional de las interfaces y menús.

## Mapa de navegación

```text
Menú principal
├── Nueva partida
├── Continuar
├── Configuración
│   ├── Audio
│   ├── Video
│   ├── Controles
│   └── Accesibilidad básica
└── Salir

Durante el juego
└── Pausa
    ├── Continuar
    ├── Configuración
    ├── Reiniciar desde checkpoint
    └── Volver al menú principal
```

## Pantallas

### - Menú principal

**Propósito:** La vista principal al iniciar el Juego. Permite que el usuario pueda comenzar el juego o continuarlo.

**Elementos:** Mochi como imagen, fondo con un detalle de la habitación, botones grandes (Nueva partida, Continuar, Configuración, Salir) y número de versión.

**Acciones disponibles:** Iniciar una nueva partida, continuar desde el último checkpoint, abrir la configuración o salir del juego. Se navega con teclado y ratón.

**Estados:** “Continuar” aparece deshabilitado si no existe un progreso guardado. El botón seleccionado se resalta con un cambio de tamaño o brillo.

**Transiciones:** “Nueva partida” lleva a la introducción narrativa y luego a la jaula. “Continuar” carga directamente el último checkpoint. “Configuración” abre la pantalla de opciones.

#### - Introducción narrativa

**Propósito:** Contar la captura de Mochi en el picnic y su objetivo de volver al bosque, sin necesidad de jugar ese nivel.

**Elementos:** Viñetas con poco texto y una indicación para avanzar u omitir la introducción.

**Acciones disponibles:** Avanzar las viñetas u omitir la introducción.

**Estados:** La indicación para avanzar u omitir debe ser visible y fácil de entender.

**Transiciones:** Al terminar, entra directamente a la jaula (tutorial).

#### HUD (interfaz en juego)

**Propósito:** Mostrar la información mínima necesaria sin tapar la escena.

**Elementos:** Saldo de semillas, indicador contextual al acercarse a un objeto interactuable, indicaciones breves del tutorial y señal de activación del checkpoint. No muestra munición ni retícula de apuntado.

**Acciones disponibles:** Es informativo. Solo muestra la información, el jugador no interactúa con él.

**Estados:** El saldo cambia al recoger semillas. Las indicaciones del tutorial aparecen en el momento oportuno y desaparecen una vez que dejan de ser necesarias.

**Transiciones:** Se oculta durante las cinemáticas y en la pantalla de pausa.

#### - Menú de pausa

**Propósito:** Detener el juego para que el jugador pueda ajustar opciones, reiniciar o salir.

**Elementos:** Fondo semitransparente sobre la escena congelada y botones de Continuar, Configuración, Reiniciar desde checkpoint y Volver al menú principal.

**Acciones disponibles:** Reanudar, abrir la configuración, reiniciar desde el último checkpoint o salir al menú.

**Estados:** El juego queda detenido mientras el menú está abierto. Si no hay un checkpoint previo, se reinicia desde el inicio del nivel.

**Transiciones:** `ESC` abre y cierra la pausa. “Volver al menú principal” pide confirmación.

#### - Configuración

**Propósito:** Permitir que cada jugador ajuste el juego a su equipo y a sus preferencias.

**Elementos:** Pestañas de Audio, Video, Controles y Accesibilidad.

* **Audio:** deslizadores de volumen general, música y efectos de sonido.
* **Video:** resolución y modo pantalla completa o ventana.
* **Controles:** Consultar y, si se conserva en el alcance, reasignar los controles de teclado y ratón.
* **Accesibilidad:** Tamaño del texto y opciones básicas confirmadas para la versión final.

**Acciones disponibles:** Cambiar valores, restablecer a valores por defecto, aplicar y volver.

**Estados:** Los cambios de audio se aplican al instante, mientras que los de video pueden pedir confirmación. Se recuerdan las preferencias entre sesiones.

**Transiciones:** Se puede abrir desde el menú principal o desde la pausa, y siempre regresa a la pantalla de origen.

#### Pantalla de final

**Propósito:** Cerrar el recorrido jugable actual con la salida de Mochi del pasillo.

**Elementos:** Cierre breve y botones para volver al menú o salir. La continuación narrativa fuera de la casa no se presenta como un nivel jugable de esta versión.

**Acciones disponibles:** Volver al menú principal o salir.

**Estados:** La transición de cierre no debe ocultar el estado final del recorrido.

**Transiciones:** Regresa al menú principal.

## Confirmaciones

Documenta acciones destructivas o irreversibles y cómo se confirman.

| Acción                                           | Confirmación                                                                                                                 | Razón                          |
| ------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ------------------------------- |
| Nueva partida (si ya existe un progreso guardado) | Mensaje: “Ya tienes una partida guardada. Si empiezas una nueva, perderás tu progreso. ¿Continuar?” con opciones Sí / No | Sobrescribe el guardado         |
| Volver al menú principal desde la pausa          | Mensaje: “¿Volver al menú? Se perderá el progreso desde el último checkpoint.” con opciones Sí / No                    | Evita salir por accidente       |
| Salir del juego                                   | Mensaje breve de confirmación con opciones Sí / No                                                                          | Evita cerrar el juego por error |
| Restablecer configuración                        | Mensaje: “¿Restablecer todos los valores por defecto?”                                                                     | Cambia varios ajustes a la vez  |

>
> **Navegación:** [[00 - Índice]] · ← [[01 - UX y Flujo del Jugador]] · [[03 - Accesibilidad]] →
