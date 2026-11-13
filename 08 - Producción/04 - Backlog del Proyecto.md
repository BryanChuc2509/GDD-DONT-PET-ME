# Backlog del Proyecto

## Descripción de la sección

El backlog contiene el trabajo necesario para convertir el diseño en un videojuego funcional.

## Formato de tarea

### Tarea

#### T01 — Movimiento y salto de Mochi

**Descripción:** Implementar en Unity el desplazamiento y el salto de Mochi según los controles definidos. El sprint y el planeo gastan la misma reserva de combustible, que solo se recarga en el suelo.

**Responsable:** Bryan Chuc

**Prioridad:** Alta

**Dependencias:** Ninguna (es la primera tarea).

**Criterio de aceptación:** Mochi se mueve y salta de forma fluida; el sprint y el planeo (hasta 0.6 segundos por tramo) gastan la misma reserva de combustible.

**Estado:** Pendiente

#### T02 — Cámara en tercera persona

**Descripción:** Implementar la cámara en tercera persona definida para el proyecto, con control de ratón según corresponda y manejo de colisiones con paredes y muebles.

**Responsable:** Dhayan Lee

**Prioridad:** Alta

**Dependencias:** T01.

**Criterio de aceptación:** La cámara sigue a Mochi sin atorarse en espacios reducidos y permite ver las plataformas para juzgar los saltos.

**Estado:** Pendiente

#### T03 — Interacción con pilas y ventilador

**Descripción:** Implementar la interacción contextual con las pilas y el ventilador del escritorio, sin asumir una mecánica de transporte que no esté definida.

**Responsable:** Bryan Chuc

**Prioridad:** Alta

**Dependencias:** T01.

**Criterio de aceptación:** Mochi completa la interacción definida y activa el ventilador para despejar el paso del encuentro de las hormigas. Las semillas solo guían el recorrido; no son munición.

**Estado:** Pendiente

#### T04 — Checkpoints y guardado automático

**Descripción:** Implementar checkpoints, reaparición tras caída o captura y guardado en una sola ranura.

**Responsable:** Bryan Chuc (checkpoints) y Ahui (guardado)

**Prioridad:** Alta

**Dependencias:** T01.

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

**Descripción:** Dibujar a Mochi y los tres niveles jugables (tutorial de la jaula, habitación y pasillo); definir el estilo visual y la lista de recursos.

**Responsable:** Gio Medina

**Prioridad:** Alta

**Dependencias:** Ninguna.

**Criterio de aceptación:** El equipo aprueba los bocetos, el estilo y la lista de assets.

**Estado:** Pendiente

#### T07 — Modelado 3D y animaciones

**Descripción:** Modelar y animar a Mochi, la aspiradora y los recursos necesarios para la habitación y el pasillo con complejidad adecuada para un juego 3D sencillo.

**Responsable:** Gio Medina (arte) y Bryan Chuc (integración en Unity)

**Prioridad:** Alta

**Dependencias:** T06.

**Criterio de aceptación:** Los recursos se importan en Unity sin errores y funcionan dentro de los objetivos de rendimiento propuestos; Mochi cuenta con las animaciones necesarias para movimiento y salto.

**Estado:** Pendiente

#### T08 — Jaula con tutorial integrado

**Descripción:** Armar la jaula como nivel tutorial (Nivel 0), previo a la habitación, y enseñar movimiento y salto. Las semillas no forman parte del tutorial como munición ni disparo.

**Responsable:** Gio Medina (diseño) y Ahui (armado en Unity)

**Prioridad:** Alta

**Dependencias:** T01, T06.

**Criterio de aceptación:** Un jugador nuevo aprende los controles y escapa de la jaula sin leer textos largos.

**Estado:** Pendiente

#### T09 — Habitación (vertical slice)

**Descripción:** Preparar las zonas de la habitación (Nivel 1) en este orden: escritorio con el minijefe de las hormigas, libros colgantes y tramo de pelotas de tenis con huecos de refugio. El memorama se integra como reto de cierre de la última zona. Incluir checkpoints y los objetos definidos para el recorrido; el puzzle se implementa en T11.

**Responsable:** Ahui

**Prioridad:** Alta

**Dependencias:** T01, T04, T08.

**Criterio de aceptación:** La habitación presenta todas las zonas en el orden establecido y permite recorrerlas; el minijefe se supera con pilas y ventilador, y las pelotas se evitan usando los huecos. El memorama queda integrado y funcional con T11.

**Estado:** Pendiente

#### T10 — Pasillo con persecución

**Descripción:** Armar el pasillo como Nivel 2 (último nivel), con la persecución de la aspiradora, ratoneras, escobas que caen y pelotas rodantes.

**Responsable:** Ahui (nivel) y Dhayan Lee (persecución)

**Prioridad:** Alta

**Dependencias:** T05, T09.

**Criterio de aceptación:** El jugador puede completar la persecución y entiende por qué gana o pierde.

**Estado:** Pendiente

#### T11 — Memorama de baldosas

**Descripción:** Implementar el puzzle de memoria al final de la habitación: mostrar una secuencia de cuadros que se iluminan en distintos colores y permitir que Mochi la repita saltando sobre los cuadros en el mismo orden.

**Responsable:** Ahui (diseño e integración) y Bryan Chuc (programación)

**Prioridad:** Alta

**Dependencias:** T01, T09.

**Criterio de aceptación:** La secuencia se presenta de forma legible, se valida el orden de los saltos y una respuesta incorrecta permite reintentar sin bloquear el progreso.

**Estado:** Pendiente

#### T12 — Menús, HUD y configuración

**Descripción:** Programar menú principal, pausa, HUD con contador de semillas, indicaciones contextuales, checkpoints y configuración esencial. No incluir contador de munición ni retícula para disparar.

**Responsable:** Ahui

**Prioridad:** Media

**Dependencias:** T03, T04.

**Criterio de aceptación:** Se puede navegar con teclado y ratón; las opciones de configuración implementadas y el contador de semillas se muestran de forma coherente con el diseño.

**Estado:** Pendiente

#### T13 — Música y efectos de sonido

**Descripción:** Seleccionar música y efectos con licencia adecuada y definir una lista de sonidos por acción.

**Responsable:** Bruno LLovera (selección) y Dhayan Lee o Ahui (integración)

**Prioridad:** Media

**Dependencias:** T06.

**Criterio de aceptación:** Las acciones principales tienen la retroalimentación sonora prevista y las licencias de los recursos de audio están registradas.

**Estado:** Pendiente

#### T14 — Obstáculos y dispositivos inteligentes

**Descripción:** Integrar los mecanismos y peligros definidos para los niveles, incluido el ventilador del escritorio, las pelotas de tenis de la estantería y las trampas del pasillo. No añadir dispositivos ni encuentros fuera del alcance acordado.

**Responsable:** Dhayan Lee

**Prioridad:** Media

**Dependencias:** T01, T07.

**Criterio de aceptación:** Los mecanismos y peligros cumplen su función, se distinguen de los elementos seguros y pueden anticiparse mediante señales legibles.

**Estado:** Pendiente

#### T15 — Pruebas funcionales y de rendimiento

**Descripción:** Probar controles, cámara, checkpoints, guardado y rendimiento en equipos modestos, y llevar un registro de errores.

**Responsable:** Dhayan Lee

**Prioridad:** Alta

**Dependencias:** T09, T10, T11 y T12. Las pruebas funcionales pueden iniciar al integrarse cada sistema.

**Criterio de aceptación:** Sin errores bloqueantes y con resultados medidos frente a los objetivos técnicos propuestos: 30 FPS mínimos estables y 60 FPS objetivo.

**Estado:** Pendiente

#### T16 — Introducción narrativa

**Descripción:** Escribir e ilustrar una introducción breve tipo cómic que muestre la captura de Mochi durante el picnic y establezca su motivación para volver con Copo y Trufa. El bosque no es un nivel jugable.

**Responsable:** Bruno LLovera (guion) y Gio Medina (ilustraciones)

**Prioridad:** Media

**Dependencias:** T06.

**Criterio de aceptación:** La introducción es breve, comprensible y se integra antes de que Mochi despierte en la jaula.

**Estado:** Pendiente

#### T17 — Tráiler promocional

**Descripción:** Grabar material del vertical slice y editar el tráiler con escenarios, mecánicas y peligros.

**Responsable:** Bruno LLovera

**Prioridad:** Media

**Dependencias:** T09, T13.

**Criterio de aceptación:** El video representa los niveles y mecánicas acordados y está listo antes de la fecha de entrega que confirme el equipo.

**Estado:** Pendiente

#### T18 — Publicación en itch.io y difusión

**Descripción:** Crear la página del juego (descripción, capturas, tráiler) y publicar en Instagram, YouTube y TikTok.

**Responsable:** Bruno LLovera (con apoyo de Bryan Chuc)

**Prioridad:** Baja

**Dependencias:** T15, T17.

**Criterio de aceptación:** La página y la publicación están listas si el equipo mantiene itch.io y el modelo de distribución dentro de sus entregables.

**Estado:** Pendiente

#### T19 — Preparación del stand y presentación

**Descripción:** Preparar ropa temática, stickers, decoración, build en USB y guion de la demostración.

**Responsable:** Bryan Chuc (con todo el equipo)

**Prioridad:** Baja

**Dependencias:** T15.

**Criterio de aceptación:** El material de presentación y la copia de respaldo están listos para la fecha del evento confirmada por el equipo.

**Estado:** Pendiente

### Backlog

Las casillas y los estados "Pendiente" se conservaron del plan anterior y deben actualizarse con el equipo; no representan una verificación del avance actual.

**Preproducción (orden de trabajo; fechas por confirmar)**

* [X] T01 — Movimiento y salto de Mochi (Bryan Chuc)
* [X] T02 — Cámara en tercera persona (Dhayan Lee)
* [X] T03 — Interacción con pilas y ventilador (Bryan Chuc y Ahui)
* [X] T06 — Bocetos y estilo visual (Gio Medina)

**Producción**

* [X] T07 — Modelado 3D y animaciones (Gio Medina y Bryan Chuc)
* [X] T04 — Checkpoints y guardado automático (Bryan Chuc y Ahui)
* [X] T08 — Jaula con tutorial integrado (Gio Medina y Ahui)
* [X] T09 — Habitación, vertical slice (Ahui)
* [X] T05 — IA de la aspiradora inteligente (Dhayan Lee)
* [X] T10 — Pasillo con persecución (Ahui y Dhayan Lee)
* [ ] T14 — Obstáculos y dispositivos inteligentes (Dhayan Lee)
* [ ] T12 — Menús, HUD y configuración (Ahui)
* [ ] T13 — Música y efectos de sonido (Bruno LLovera)
* [ ] T16 — Introducción narrativa tipo cómic (Bruno LLovera y Gio Medina)
* [ ] T11 — Memorama de baldosas (Ahui y Bryan Chuc)
* [ ] T17 — Tráiler promocional (Bruno LLovera)

**Pruebas, estabilización y entrega (fechas por confirmar)**

* [ ] T15 — Pruebas funcionales y de rendimiento (Dhayan Lee)
* [ ] T18 — Publicación en itch.io y difusión (Bruno LLovera)
* [ ] T19 — Preparación del stand y presentación (Bryan Chuc)

## Priorización

Prioriza aquello que desbloquea otras tareas o valida primero las partes más riesgosas del proyecto.

> **Navegación:** [[00 - Índice]] · ← [[03 - Roadmap]] · [[05 - Gestión de Cambios]] →
