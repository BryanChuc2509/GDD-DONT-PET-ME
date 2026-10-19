# Guardado y Configuración

## Descripción de la sección

Define cómo se conserva el progreso y qué opciones puede modificar el jugador.

## Guardado

**Tipo:** 

Automático.

**Cuándo se guarda:**

* Se tiene pensando que haya checkpoints en ciertas partes del mapa antes de pasar por una plataforma en la que se pueda perder rápido.
* De igual manera, habrá checkpoints al completar cada escenario (habitación).

**Qué datos se guardan:**

* El escenario
* El inventario que tenga
* El estado de los elementos como los puzzles o interruptores para no repetirlos si ya se han realizado.

**Cantidad de ranuras:**

Una sola ranura. Es suficiente tener únicamente una ranura para no complejizar el proyecto. 

**Qué ocurre si el guardado falla:**

* El juego continúa sin interrumpir al jugador y reintenta guardar en el siguiente checkpoint.
* Se muestra un mensaje breve y no intrusivo, por ejemplo: “No se pudo guardar el progreso.”

## Configuración

| Categoría    | Opciones                                                                                                     |
| ------------- | ------------------------------------------------------------------------------------------------------------ |
| Audio         | Volumen general, volumen de música, volumen de efectos de sonido.                                           |
| Video         | Resolución, modo pantalla completa o ventana y calidad gráfica (baja, media, alta)                         |
| Controles     | Sensibilidad de la cámara, invertir eje Y y visualización del mapa de controles de teclado/mouse           |
| Accesibilidad | Tamaño del texto, tamaño de los íconos del HUD y reducción de efectos de cámara                        |
| Jugabilidad   | Mostrar u ocultar los íconos de ayuda de controles y activar u ocultar la retícula al apuntar las canicas. |

## Restablecimiento

¿Qué opciones pueden volver a valores predeterminados?

> **Navegación:** [[00 - Índice]] · ← [[03 - Accesibilidad]] · [[01 - Arquitectura Técnica]] →
