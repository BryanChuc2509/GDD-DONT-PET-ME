# Gestión de Cambios

## Descripción de la sección

El diseño de un videojuego cambia. Esta sección evita que las modificaciones importantes se pierdan o aparezcan sin evaluar sus consecuencias.

Para cada cambio, esta nota registra la solicitud, su impacto y su estado. En el [[03 - Registro de Decisiones]] se documentan la resolución y sus motivos con el mismo identificador.

### Solicitud de cambio

**Fecha:** 19 de octubre de 2026.

**Cambio propuesto:** Eliminar el nivel jugable del bosque. La captura de Mochi durante el picnic se cuenta mediante una introducción narrativa breve. El juego inicia cuando Mochi despierta en la jaula, que es la zona inicial de la habitación, y aprende allí las acciones básicas.

**Motivo:** Limitaciones de tiempo. Se cuenta con unas 3.5 semanas de desarrollo (del 19 de octubre al 13 de noviembre, con el evento el 20 de noviembre), y el bosque implicaba modelar, diseñar y programar un escenario completo adicional.

**Beneficio esperado:**

* Reduce el trabajo de modelado 3D, diseño de niveles y pruebas de un escenario completo.
* Libera tiempo para pulir el vertical slice (jaula y habitación) y la persecución del pasillo.
* Disminuye el riesgo de no llegar a un build estable para la fecha de entrega.
* Mantiene la enseñanza de las acciones principales mediante un tutorial integrado en la jaula, sin convertirla en un nivel independiente.

**Costo estimado:**

* Se pierde el nivel de exploración al aire libre y el contraste visual entre naturaleza y casa.
* Se pierde la secuencia jugable de la captura, que ahora será una escena no interactiva.
* Se requiere trabajo acotado: guion e ilustraciones de la introducción y diseño del tutorial dentro de la jaula.
* El recorrido jugable se organiza en dos niveles: la habitación, que comienza en la jaula, y el pasillo.

**Impacto en otros sistemas:**

| Sección               | Impacto                                                                                   |
| ---------------------- | ----------------------------------------------------------------------------------------- |
| Visión del Juego | La captura y la motivación de Mochi se presentan en la introducción narrativa. |
| UX y Flujo del Jugador | El flujo comienza con la introducción y continúa en la jaula, primera zona de la habitación. |
| UI y Menús | Se incorpora una introducción narrativa breve en video. |
| Alcance | El bosque no es jugable; el recorrido jugable comprende la habitación y el pasillo. |

**Decisión:** Aprobado. El bosque se mantiene como parte de la historia, pero no es un nivel jugable de esta versión. La introducción presenta la captura y el tutorial inicia en la jaula, dentro de la habitación.

**Actualización (12 de noviembre de 2026):** Con [[03 - Registro de Decisiones#D-06 · Tutorial como nivel propio\|D-06]], la jaula deja de ser la zona inicial de la habitación y pasa a ser un nivel tutorial propio. El recorrido jugable queda en tres niveles: tutorial, habitación y pasillo.

**Responsable:** Bryan Chuc (líder de proyecto), con apoyo de todo el equipo.

### Registro

| Fecha       | Cambio                                                                                                           | Motivo                                                                      | Impacto                                                                                                                                             | Estado     |
| ----------- | ---------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| 19 oct 2026 | [[03 - Registro de Decisiones#D-01 · Bosque y tutorial en la jaula\|D-01]] · Eliminar el nivel jugable del bosque y sustituir la captura por una introducción narrativa. El tutorial inicia en la jaula, dentro de la habitación. | Reducir el trabajo de producción y pruebas del escenario exterior. | Se establece un recorrido jugable de dos niveles: habitación y pasillo. | Aprobado |
| 19 oct 2026 | Actualizar los documentos afectados por el cambio de alcance. | Mantener coherencia entre narrativa, flujo y producción. | El bosque permanece en la historia, pero no se produce como nivel jugable. | Completado |
| 3 nov 2026 | [[03 - Registro de Decisiones#D-02 · Semillas y mecánicas\|D-02]] · Semillas para orientar el recorrido. Retirar el inventario general y definir sprint y escalada. | Simplificar acciones y orientar la exploración. | Diseño, controles, economía y tutorial. | Documentado en el GDD |
| 3 nov 2026 | [[03 - Registro de Decisiones#D-03 · Recorrido y ayudas\|D-03]] · Organizar la habitación en cuatro zonas e incluir checkpoints, encuadre inicial de la jaula y pistas contextuales. | Hacer legibles la ruta y los retos. | Niveles y UX. | Documentado en el GDD |
| 3 nov 2026 | [[03 - Registro de Decisiones#D-04 · Planeo\|D-04]] · Evaluar si se conserva, se reduce o se elimina el planeo. | Validar cuánto control aéreo necesita el recorrido. | Movimiento, tutorial y diseño de saltos. Se conserva con 0.6 segundos por tramo y gasta el mismo combustible que el sprint. | Resuelto (12 nov 2026) |
| 4 nov 2026 | [[03 - Registro de Decisiones#D-05 · Alcance narrativo\|D-05]] · Limitar el recorrido narrado al alcance actual. | Alinear la historia con la versión jugable. | Historia y referencias a entornos. | Documentado en el GDD |
| 12 nov 2026 | [[03 - Registro de Decisiones#D-06 · Tutorial como nivel propio\|D-06]] · Separar la jaula como nivel tutorial (Nivel 0). | Reflejar el juego implementado, donde la jaula es un nivel propio. | Recorrido de tres niveles: tutorial, habitación y pasillo. Afecta estructura, niveles, UX, alcance y producción. | Aprobado |

Consulta el [[03 - Registro de Decisiones]] para ver qué se resolvió y qué sigue abierto.

> **Navegación:** [[00 - Índice]] · ← [[04 - Backlog del Proyecto]] · [[01 - Criterios de Calidad]] →
