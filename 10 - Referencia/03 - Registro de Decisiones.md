 

# Registro de Decisiones

## Descripción de la sección

Esta sección conserva las decisiones importantes del proyecto y el razonamiento detrás de ellas.

Las solicitudes, su impacto y su seguimiento se consultan en [[05 - Gestión de Cambios#Registro|Gestión de Cambios]]. Cada entrada comparte su identificador con ese registro.

## D-01 · Bosque y tutorial en la jaula

**19 de octubre de 2026 · Aprobado.** El bosque se conserva en la introducción y la jaula pasa a ser la primera zona de la habitación. Así se reduce el trabajo de producir otro nivel y se integra el tutorial al inicio jugable. Responsable registrado: Bryan Chuc, con apoyo del equipo. *Actualizado por D-06: la jaula es ahora un nivel tutorial propio.*

## D-02 · Semillas y mecánicas

**3 de noviembre de 2026 · Documentado.** Las semillas marcan la ruta. Se retiran el inventario general, el disparo con semillas, el globo como acción y el hilo como acción del jugador: los hilos que cuelgan en la estantería de la araña se suben solos al tocarlos, sin pulsar ninguna tecla. Se incorpora sprint con `Shift`, combustible y enfriamiento antes de recargar. Se reutiliza la escalada del tutorial, señalada con textura de tela o hilos.

## D-03 · Recorrido y ayudas

**3 de noviembre de 2026 · Documentado.** La habitación se divide en jaula, escritorio, libros colgantes y estantería de la araña (con D-06, la jaula pasa a ser el nivel tutorial). Los checkpoints permiten retomar el recorrido. La jaula se presenta con un encuadre amplio y los barrotes que tapan a Mochi se vuelven transparentes. En desafíos difíciles se dan pistas breves. En el escritorio, al recoger una pila, un indicador señala dónde colocarla para activar el ventilador.

## D-04 · Planeo

**3 de noviembre de 2026 · Pendiente.** Las opciones son conservar, reducir o retirar el planeo. El comportamiento de hasta un segundo descrito en Diseño sirve de referencia para el prototipo mientras se decide. La duración del enfriamiento del sprint queda por balancear.

**12 de noviembre de 2026 · Resuelto.** Se conserva el planeo, reducido a 0.6 segundos por tramo en el aire. El sprint y el planeo gastan la misma reserva de combustible (la barra de estamina del HUD), que solo se recarga en el suelo y, si se agota, bloquea las dos acciones hasta volver al 30%. Así queda implementado en el juego.

## D-05 · Alcance narrativo

**4 de noviembre de 2026 · Documentado.** La historia de esta versión sigue la introducción de la captura, la fuga de la jaula, la habitación y la persecución del pasillo hasta la llegada a la sala. Cocina y jardín quedan fuera del recorrido.

## D-06 · Tutorial como nivel propio

**12 de noviembre de 2026 · Aprobado.** El recorrido jugable se organiza en tres niveles: el tutorial de la jaula (Nivel 0), la habitación de Reo (Nivel 1) y el pasillo (Nivel 2). La jaula deja de ser la primera zona de la habitación y pasa a ser un nivel propio, como ya está implementado en el juego. Reemplaza la parte de D-01 que integraba la jaula en la habitación y la zona de jaula de D-03.

> **Navegación:** [[00 - Índice]] · ← [[02 - Referencias e Inspiración]] · [[04 - Historial de Versiones]] →
