# Backlog del Proyecto

## Descripción de la sección

El backlog contiene el trabajo necesario para convertir el diseño en un videojuego funcional.

## Formato de tarea

### Tarea

#### T01 — Movimiento y salto de Mochi

**Descripción:** Implementar en Unity el desplazamiento, el salto y el doble salto de Mochi, con control en el aire, coyote time y buffer de salto.

**Responsable:** Bryan Chuc

**Prioridad:** Alta

**Dependencias:** Ninguna (es la primera tarea).

**Criterio de aceptación:** Mochi se mueve y salta con fluidez sobre un escenario de prueba, el doble salto alcanza plataformas más altas y el control se siente preciso y sin retraso.

**Estado:** Pendiente

#### T02 — Cámara en tercera persona

**Descripción:** Crear la cámara libre con seguimiento, control con mouse y stick, y manejo de colisiones con paredes y muebles.

**Responsable:** Dhayan Lee

**Prioridad:** Alta

**Dependencias:** T01.

**Criterio de aceptación:** La cámara sigue a Mochi sin atorarse en espacios reducidos y permite ver las plataformas para juzgar los saltos.

**Estado:** Pendiente

#### T03 — Sistema de canicas

**Descripción:** Programar la recolección de canicas, el inventario en la boca (contador), el disparo y la activación de interruptores.

**Responsable:** Bryan Chuc

**Prioridad:** Alta

**Dependencias:** T01.

**Criterio de aceptación:** Mochi recoge canicas, el contador se actualiza, el disparo impacta un objetivo y este abre una puerta o plataforma de forma consistente.

**Estado:** Pendiente

#### T04 — Checkpoints y guardado automático

**Descripción:** Implementar checkpoints, reaparición tras caída o captura y guardado en una sola ranura.

**Responsable:** Bryan Chuc (checkpoints) y Ahui (guardado)

**Prioridad:** Alta

**Dependencias:** T01, T03.

**Criterio de aceptación:** Al caer, el jugador reaparece en el último checkpoint; al cerrar y abrir el juego, “Continuar” carga el progreso.

**Estado:** Pendiente

#### T05 — IA de la aspiradora inteligente

**Descripción:** Programar el comportamiento de la aspiradora: patrullar, detectar a Mochi, perseguirlo y reaccionar a obstáculos.

**Responsable:** Dhayan Lee

**Prioridad:** Alta

**Dependencias:** T01, T02, T07.

**Criterio de aceptación:** La aspiradora detecta a Mochi, lo persigue a una velocidad justa y el jugador puede completar el tramo sin que se sienta injusto.

**Estado:** Pendiente

#### T06 — Bocetos y estilo visual

**Descripción:** Dibujar en papel los cuatro escenarios y a Mochi, y definir el estilo visual (low-poly o stylized) y la lista de assets.

**Responsable:** Gio Medina

**Prioridad:** Alta

**Dependencias:** Ninguna.

**Criterio de aceptación:** El equipo aprueba los bocetos, el estilo y la lista de assets.

**Estado:** Pendiente

#### T07 — Modelado 3D y animaciones

**Descripción:** Modelar, texturizar y animar a Mochi, la aspiradora y los escenarios en Blender, optimizados para equipos modestos.

**Responsable:** [Por asignar]

**Prioridad:** Alta

**Dependencias:** T06.

**Criterio de aceptación:** Los modelos se importan en Unity sin errores, mantienen 60 FPS y Mochi tiene animaciones de caminar, saltar, doble salto y reacciones.

**Estado:** Pendiente

#### T08 — Jaula con tutorial integrado

**Descripción:** Armar el nivel de la jaula en Unity con el tutorial de movimiento, doble salto y canicas, y el escape hacia la habitación.

**Responsable:** Gio Medina (diseño) y Ahui (armado en Unity)

**Prioridad:** Alta

**Dependencias:** T01, T03, T06.

**Criterio de aceptación:** Un jugador nuevo aprende los controles y escapa de la jaula sin leer textos largos.

**Estado:** Pendiente

#### T09 — Habitación (vertical slice)

**Descripción:** Armar el nivel de la habitación con plataformas, muebles, juguetes, libros, cables y obstáculos, con checkpoints.

**Responsable:** Ahui

**Prioridad:** Alta

**Dependencias:** T01, T04, T08.

**Criterio de aceptación:** Se completa de inicio a fin con arte, sonido y checkpoints definitivos.

**Estado:** Pendiente

#### T10 — Pasillo con persecución

**Descripción:** Armar el nivel del pasillo con desniveles y trampas, e integrar la persecución de la aspiradora.

**Responsable:** Ahui (nivel) y Dhayan Lee (persecución)

**Prioridad:** Alta

**Dependencias:** T05, T09.

**Criterio de aceptación:** El jugador puede completar la persecución y entiende por qué gana o pierde.

**Estado:** Pendiente

#### T11 — Sala y cierre del juego

**Descripción:** Armar la sala como último escenario y conectar la escena final del escape.

**Responsable:** Ahui

**Prioridad:** Media

**Dependencias:** T10, T16.

**Criterio de aceptación:** El jugador llega a la sala y se activa el final.

**Estado:** Pendiente

#### T12 — Menús, HUD y configuración

**Descripción:** Programar menú principal, pausa, HUD (contador de canicas, íconos de ayuda, retícula), pantalla de final y configuración esencial.

**Responsable:** Ahui

**Prioridad:** Media

**Dependencias:** T03, T04.

**Criterio de aceptación:** Se puede navegar con mouse, teclado y gamepad, y las opciones de volumen, resolución, sensibilidad de cámara y tamaño de texto se guardan.

**Estado:** Pendiente

#### T13 — Música y efectos de sonido

**Descripción:** Seleccionar música y efectos con licencia adecuada y definir una lista de sonidos por acción.

**Responsable:** Bruno LLovera (selección) y Dhayan Lee o Ahui (integración)

**Prioridad:** Media

**Dependencias:** T06.

**Criterio de aceptación:** Cada acción de la tabla de retroalimentación tiene su sonido y todas las licencias están registradas.

**Estado:** Pendiente

#### T14 — Obstáculos y dispositivos inteligentes

**Descripción:** Programar los obstáculos de la casa, como ventiladores y otros dispositivos que sirven de amenaza o ayuda.

**Responsable:** Dhayan Lee

**Prioridad:** Media

**Dependencias:** T01, T07.

**Criterio de aceptación:** Los dispositivos funcionan de forma predecible y se distinguen visualmente de los objetos seguros.

**Estado:** Pendiente

#### T15 — Pruebas funcionales y de rendimiento

**Descripción:** Probar controles, cámara, checkpoints, guardado y rendimiento en equipos modestos, y llevar un registro de errores.

**Responsable:** Dhayan Lee

**Prioridad:** Alta

**Dependencias:** T09 en adelante (pruebas ligeras desde el 2 de noviembre).

**Criterio de aceptación:** Sin errores críticos y 60 FPS estables en laptops de gama media o baja.

**Estado:** Pendiente

#### T16 — Introducción narrativa y escena final

**Descripción:** Escribir y producir la introducción de la captura (viñetas) y la escena final del escape.

**Responsable:** Bruno LLovera (guion) y Gio Medina (ilustraciones)

**Prioridad:** Media

**Dependencias:** T06.

**Criterio de aceptación:** Ambas piezas son breves, cómicas y se integran al flujo del juego.

**Estado:** Pendiente

#### T17 — Tráiler promocional

**Descripción:** Grabar material del vertical slice y editar el tráiler con escenarios, mecánicas y peligros.

**Responsable:** Bruno LLovera

**Prioridad:** Media

**Dependencias:** T09, T13.

**Criterio de aceptación:** El video está listo para publicarse antes del 11 de noviembre.

**Estado:** Pendiente

#### T18 — Publicación en itch.io y difusión

**Descripción:** Crear la página del juego (descripción, capturas, tráiler) y publicar en Instagram, YouTube y TikTok.

**Responsable:** Bruno LLovera (con apoyo de Bryan Chuc)

**Prioridad:** Baja

**Dependencias:** T15, T17.

**Criterio de aceptación:** El juego está publicado con modelo “paga lo que quieras”.

**Estado:** Pendiente

#### T19 — Preparación del stand y presentación

**Descripción:** Preparar ropa temática, stickers, decoración, build en USB y guion de la demostración.

**Responsable:** Bryan Chuc (con todo el equipo)

**Prioridad:** Baja

**Dependencias:** T15.

**Criterio de aceptación:** Todo está listo antes del 20 de noviembre.

**Estado:** Pendiente

### Backlog

**Preproducción (19 al 26 de octubre)**

* [ ] T01 — Movimiento y salto de Mochi (Bryan Chuc)
* [ ] T02 — Cámara en tercera persona (Dhayan Lee)
* [ ] T03 — Sistema de canicas (Bryan Chuc)
* [ ] T06 — Bocetos y estilo visual (Gio Medina)

**Producción (26 de octubre al 11 de noviembre)**

* [ ] T07 — Modelado 3D y animaciones ([Por asignar])
* [ ] T04 — Checkpoints y guardado automático (Bryan Chuc y Ahui)
* [ ] T08 — Jaula con tutorial integrado (Gio Medina y Ahui)
* [ ] T09 — Habitación, vertical slice (Ahui)
* [ ] T05 — IA de la aspiradora inteligente (Dhayan Lee)
* [ ] T10 — Pasillo con persecución (Ahui y Dhayan Lee)
* [ ] T14 — Obstáculos y dispositivos inteligentes (Dhayan Lee)
* [ ] T12 — Menús, HUD y configuración (Ahui)
* [ ] T13 — Música y efectos de sonido (Bruno LLovera)
* [ ] T16 — Introducción narrativa y escena final (Bruno LLovera y Gio Medina)
* [ ] T11 — Sala y cierre del juego (Ahui)
* [ ] T17 — Tráiler promocional (Bruno LLovera)

**Pruebas y entrega (2 al 20 de noviembre)**

* [ ] T15 — Pruebas funcionales y de rendimiento (Dhayan Lee)
* [ ] T18 — Publicación en itch.io y difusión (Bruno LLovera)
* [ ] T19 — Preparación del stand y presentación (Bryan Chuc)

## Priorización

Prioriza aquello que desbloquea otras tareas o valida primero las partes más riesgosas del proyecto.

> **Navegación:** [[00 - Índice]] · ← [[03 - Roadmap]] · [[05 - Gestión de Cambios]] →
