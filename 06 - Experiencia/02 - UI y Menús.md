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

**Acciones disponibles:** Iniciar una nueva partida, continuar desde el último checkpoint, abrir la configuración o salir del juego. Se puede navegar con mouse, teclado o gamepad.

**Estados:** “Continuar” aparece deshabilitado si no existe un progreso guardado. El botón seleccionado se resalta con un cambio de tamaño o brillo.

**Transiciones:** “Nueva partida” lleva a la introducción narrativa y luego a la jaula. “Continuar” carga directamente el último checkpoint. “Configuración” abre la pantalla de opciones.

#### - Introducción narrativa

**Propósito:** Contar la captura de Mochi en el picnic y su objetivo de volver al bosque, sin necesidad de jugar ese nivel.

**Elementos:** Imágenes fijas o viñetas con poco texto, música de fondo y un botón para avanzar (presionar X para omitir).

**Acciones disponibles:**  Omitir la introducción.

**Estados:** Se debe dejar presionado la tecla "X" por 3 segundos para omitir.

**Transiciones:** Al terminar, entra directamente a la jaula (tutorial).

#### HUD (interfaz en juego)

**Propósito:** Mostrar la información mínima necesaria sin tapar la escena .

**Elementos:** Contador de canicas o semillas en la boca (ícono de mejilla con número), indicador de interacción que aparece al acercarse a un objeto, íconos breves de controles durante el tutorial, ícono de checkpoint y reticula discreta para apuntar al disparar canicas.

**Acciones disponibles:** Es informativo. Solo muestra la información, el jugador no interactúa con él.

**Estados:** El contador parpadea al recoger o gastar una canica. Los íconos del tutorial aparecen una sola vez y desaparecen. La retícula solo se muestra al apuntar. 

**Transiciones:** Se oculta durante las cinemáticas y en la pantalla de pausa.

#### - Menú de pausa

**Propósito:** Detener el juego para que el jugador pueda ajustar opciones, reiniciar o salir.

**Elementos:** Fondo semitransparente sobre la escena congelada y botones de Continuar, Configuración, Reiniciar desde checkpoint y Volver al menú principal.

**Acciones disponibles:** Reanudar, abrir la configuración, reiniciar desde el último checkpoint o salir al menú.

**Estados:** El juego queda detenido mientras el menú está abierto. Si no hay un checkpoint previo, se reinicia desde el inicio del nivel.

**Transiciones:** Esc o el botón Start abren y cierran la pausa. “Volver al menú principal” pide confirmación.


#### - Configuración

**Propósito:** Permitir que cada jugador ajuste el juego a su equipo y a sus preferencias.

**Elementos:** Pestañas de Audio, Video y Controles

* **Audio:** deslizadores de volumen general, música y efectos de sonido.
* **Video:** resolución, modo pantalla completa o ventana, calidad gráfica y activar o desactivar VSync.
* **Controles:** Cambiar algunos controles a preferencia

**Acciones disponibles:** Cambiar valores, restablecer a valores por defecto, aplicar y volver.

**Estados:** Los cambios de audio se aplican al instante, mientras que los de video pueden pedir confirmación. Se recuerdan las preferencias entre sesiones.

**Transiciones:** Se puede abrir desde el menú principal o desde la pausa, y siempre regresa a la pantalla de origen.

#### Pantalla de final

**Propósito:** Cerrar la aventura con la escapada de Mochi y dar una sensación de recompensa.

**Elementos:** Escena final, mensaje breve de agradecimiento, créditos del equipo y botones para volver al menú o salir.

**Acciones disponibles:** Ver los créditos, volver al menú principal o salir.

**Estados:** Los créditos se pueden omitir.

**Transiciones:** Regresa al menú principal.

## Confirmaciones

Documenta acciones destructivas o irreversibles y cómo se confirman.

| Acción                                           | Confirmación                                                                                                                 | Razón                          |
| ------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ------------------------------- |
| Nueva partida (si ya existe un progreso guardado) | Mensaje: “Ya tienes una partida guardada. Si empiezas una nueva, perderás tu progreso. ¿Continuar?” con opciones Sí / No | Sobrescribe el guardado         |
| Volver al menú principal desde la pausa          | Mensaje: “¿Volver al menú? Se perderá el progreso desde el último checkpoint.” con opciones Sí / No                    | Evita salir por accidente       |
| Salir del juego                                   | Mensaje breve de confirmación con opciones Sí / No                                                                          | Evita cerrar el juego por error |
| Restablecer configuración                        | Mensaje: “¿Restablecer todos los valores por defecto?”                                                                     | Cambia varios ajustes a la vez  |

> **Navegación:** [[00 - Índice]] · ← [[01 - UX y Flujo del Jugador]] · [[03 - Accesibilidad]] →
