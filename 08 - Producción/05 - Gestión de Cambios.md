# Gestión de Cambios

## Descripción de la sección

El diseño de un videojuego cambia. Esta sección evita que las modificaciones importantes se pierdan o aparezcan sin evaluar sus consecuencias.

### Solicitud de cambio

**Fecha:** 19 de octubre de 2026.

**Cambio propuesto:** Eliminar el nivel jugable del bosque. La captura de Mochi en el picnic pasa a contarse con una introducción narrativa breve (imágenes fijas o viñetas), y el juego inicia directamente en la jaula, donde se integra el tutorial de controles (movimiento, salto, doble salto y canicas).

**Motivo:** Limitaciones de tiempo. Se cuenta con unas 3.5 semanas de desarrollo (del 19 de octubre al 13 de noviembre, con el evento el 20 de noviembre), y el bosque implicaba modelar, diseñar y programar un escenario completo adicional.

**Beneficio esperado:**

* Reduce el trabajo de modelado 3D, diseño de niveles y pruebas de un escenario completo.
* Libera tiempo para pulir el vertical slice (jaula y habitación) y la persecución del pasillo.
* Disminuye el riesgo de no llegar a un build estable para la fecha de entrega.
* Mantiene la enseñanza de las mecánicas principales mediante un tutorial integrado en el espacio de la jaula.

**Costo estimado:**

* Se pierde el nivel de exploración al aire libre y el contraste visual entre naturaleza y casa.
* Se pierde la secuencia jugable de la captura, que ahora será una escena no interactiva.
* Se requiere trabajo nuevo, pero pequeño: guion e ilustraciones de la introducción y rediseño del tutorial dentro de la jaula
* Se pasa de cinco a cuatro escenarios jugables.

**Impacto en otros sistemas:**

| Sección               | Impacto                                                                                   |
| ---------------------- | ----------------------------------------------------------------------------------------- |
| Visión del Juego      | Ajustar la progresión (de cinco a cuatro escenarios) y las características principales. |
| UX y Flujo del Jugador | El flujo inicia en la jaula y los primeros minutos se rediseñaron.                       |
| UI y Menús            | Se añadió la pantalla de introducción narrativa.                                       |
| Alcance                | El bosque queda en “No incluido” y el vertical slice es jaula y habitación.            |

**Decisión:** Aprobado. El nivel del bosque se elimina del alcance jugable y se sustituye por la introducción narrativa y el tutorial en la jaula. No se reincorporará en esta versión; solo podría considerarse después del evento como contenido futuro  en dado caso de que el equipo planee seguir expandiendo y actualizando el jeugo.

**Responsable:** Bryan Chuc (líder de proyecto), con apoyo de todo los integrantes del equipo 

### Registro

| Fecha       | Cambio                                                                                                           | Motivo                                                                      | Impacto                                                                                                                                             | Estado     |
| ----------- | ---------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| 19 oct 2026 | Eliminar el nivel jugable del bosque y sustituirlo por una introducción narrativa. El tutorial pasa a la jaula. | Falta de tiempo (unas 3.5 semanas de desarrollo antes del 13 de noviembre). | Se pasa de cinco a cuatro escenarios jugables. Se reducen modelado, diseño y pruebas. Se actualizan Visión, Pilares 2 y 5, Plataforma y tráiler. | Aprobado   |
| 19 oct 2026 | Actualizar documentos afectados (Visión, Pilares, Público y Plataforma).                                       | Mantener coherencia con el cambio.                                          | Solo edición de texto, sin costo de desarrollo.                                                                                                    | Completado |

> **Navegación:** [[00 - Índice]] · ← [[04 - Backlog del Proyecto]] · [[01 - Criterios de Calidad]] →
