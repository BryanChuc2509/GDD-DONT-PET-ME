# Mecánicas

## Descripción de la sección

Una mecánica es una regla o interacción mediante la cual el jugador puede actuar dentro del sistema del juego.

Documenta cada mecánica con suficiente detalle para que otro integrante pueda implementarla.

## Plantilla de mecánica

### Nombre de la mecánica

**Propósito:**
¿Qué aporta a la experiencia?

**Activación:**
¿Qué debe hacer el jugador?

**Reglas:**
¿Qué puede y qué no puede ocurrir?

**Entrada:**
¿Qué botón, gesto o acción la activa?

**Estado inicial:**

**Estado final:**

**Recursos utilizados:**

**Recompensa:**

**Penalización:**

**Interacciones con otras mecánicas:**

**Casos límite:**
¿Qué ocurre en situaciones poco comunes?

## Mecánicas principales

### Mecánica 01

Recolección de Semillas

**Propósito:**

Guiar al jugador por las zonas: las semillas marcan la ruta que debe seguir.

**Activación:**

Las semillas se recogen automáticamente al tocarlas.

**Reglas:**

- La distribución de semillas orienta hacia el recorrido principal sin impedir que el jugador explore rutas secundarias.
- El HUD muestra cuántas semillas se han recogido y el total del nivel. El contador empieza en 0 en cada nivel.
- Las semillas recogidas siguen contadas al morir y reaparecer en un checkpoint.
- Las semillas no se gastan ni se usan para activar mecanismos.

**Entrada:**

Contacto con una semilla.

**Estado inicial:**

Semillas disponibles en el escenario; el contador del HUD muestra las recogidas y el total del nivel.

**Estado final:**

Semilla retirada del escenario y contador del HUD aumentado en uno.

**Recursos utilizados:**

Semillas del nivel.

**Recompensa:**

Saber por dónde seguir y completar el contador del nivel.

**Penalización:**

No recoger una semilla no bloquea la progresión del nivel.

**Interacciones con otras mecánicas:**

La guía visual de semillas complementa la iluminación, la geometría del nivel y los puntos de control.

**Casos límite:**

Las semillas ya recogidas no vuelven a aparecer al reaparecer en un checkpoint. Algunas semillas son trampas: lanzan a Mochi por los aires o se alejan cuando se acerca.

<!-- Copiar la plantilla anterior -->

### Mecánica 02

Salto e Inercia

**Propósito:**

Permitir el plataformeo vertical y salvar abismos gigantescos entre muebles.

**Activación:**

Pulsar `ESPACIO` en el suelo.

**Reglas:**

- Soltar `ESPACIO` antes de tiempo corta el salto, así que la altura depende de cuánto se mantiene la tecla.
- Hay un pequeño margen para saltar justo después de salir de un borde y, si se pulsa `ESPACIO` un poco antes de aterrizar, el salto sale al tocar el suelo.
- Mochi solo puede saltar desde el suelo; mantener `ESPACIO` en el aire activa el planeo.

**Entrada:**

Barra espaciadora (`ESPACIO`).

**Estado inicial:**

Mochi en superficie firme.

**Estado final:**

Mochi en el aire o aterrizando tras la maniobra.

**Recursos utilizados:**

Ninguno (habilidad pasiva de movimiento).

**Recompensa:**

Acceso a plataformas superiores y conservación de fluidez de movimiento.

**Penalización:**

Un mal cálculo provoca caer a zonas letales (charcos, vacío, trampas).

**Interacciones con otras mecánicas:**

Se combina con el sprint para ganar impulso, con el planeo para ampliar el alcance de un salto y con la escalada de superficies de tela.

**Casos límite:**

No alcanzar ciertas superficies.

### Mecánica 03

Sprint con Combustible

**Propósito:**

Permitir que Mochi aumente temporalmente su velocidad gastando la reserva de combustible que comparte con el planeo.

**Activación:**

Mantener `SHIFT` mientras Mochi se desplaza.

**Reglas:**

- El sprint y el planeo comparten una sola reserva de combustible de 100 puntos, que el HUD muestra como la barra de estamina.
- El sprint gasta 22 puntos por segundo mientras se mantiene `SHIFT` y Mochi se mueve, también durante un salto. Con la reserva llena alcanza para unos 4.5 segundos.
- El combustible solo se recarga con Mochi en el suelo, 0.6 segundos después del último gasto, a 40 puntos por segundo. En el aire no se recarga.
- Si la reserva llega a 0, Mochi queda agotado: vuelve a su velocidad normal y no puede esprintar ni planear hasta que la reserva se recupere al 30%.
- Al reaparecer en un checkpoint, la reserva se llena por completo.
- Caminar, saltar y escalar no gastan combustible.

**Entrada:**

`SHIFT` (mantener mientras Mochi se desplaza).

**Estado inicial:**

Mochi se desplaza y no está agotado.

**Estado final:**

Mochi vuelve a su velocidad normal al soltar `SHIFT` o agotar el combustible.

**Recursos utilizados:**

La reserva de combustible compartida con el planeo, mostrada en la barra con un rayo de la esquina inferior izquierda del HUD.

**Recompensa:**

Mayor velocidad temporal para recorrer tramos y tomar impulso antes de un salto.

**Penalización:**

Gastar todo el combustible impide esprintar y planear hasta que la reserva vuelva al 30%.

**Interacciones con otras mecánicas:**

El sprint da impulso antes de un salto. Como comparte el combustible con el planeo, correr mucho antes de saltar deja menos reserva para planear. No protege contra peligros letales.

**Casos límite:**

Si el combustible se agota mientras `SHIFT` sigue presionado, el sprint se interrumpe; la barra del HUD se atenúa y el rayo parpadea hasta que la reserva vuelve al 30%.

### Mecánica 04

Planeo

**Propósito:**

Reducir por un momento la velocidad de caída para extender un salto y ayudar a alcanzar plataformas lejanas o aterrizar con más control.

**Activación:**

Mantener `ESPACIO` en el aire. El planeo empieza cuando Mochi ya va cayendo, no durante la subida del salto.

**Reglas:**

- El planeo gasta el mismo combustible que el sprint: 45 puntos por segundo, unos 27 puntos por un planeo completo.
- Mientras planea, Mochi cae despacio y conserva el control en el aire, pero no asciende ni queda suspendido.
- Dura como máximo **0.6 segundos por tramo en el aire** y termina antes si se suelta `ESPACIO` o se acaba el combustible. El límite se reinicia al tocar el suelo o al rebotar en una plataforma de impulso.
- Con el combustible agotado no se puede planear.

**Entrada:**

`ESPACIO` (mantener en el aire para planear; soltar para dejar de planear).

**Estado inicial:**

Mochi está en el aire, cayendo, y no está agotado.

**Estado final:**

El planeo termina al soltar `ESPACIO`, alcanzar 0.6 segundos en el tramo actual, agotar el combustible o aterrizar.

**Recursos utilizados:**

La reserva de combustible compartida con el sprint.

**Recompensa:**

Más distancia y control durante un salto al ralentizar la caída.

**Penalización:**

Un mal cálculo del momento de planear puede dejar a Mochi corto de su destino. Planear sin medida vacía la reserva y deja a Mochi sin sprint ni planeo hasta recargar en el suelo.

**Interacciones con otras mecánicas:**

El planeo complementa el salto y comparte el combustible con el sprint. Como la reserva solo se recarga en el suelo, encadenar varios saltos planeando la vacía. No protege contra peligros letales.

**Casos límite:**

Al alcanzar el límite de 0.6 segundos no se puede volver a planear en ese mismo tramo en el aire, aunque quede combustible; vuelve a estar disponible al tocar el suelo o al rebotar. Si el combustible se acaba a mitad del planeo, este se corta y Mochi cae con normalidad.

### Mecánica 05

Escalada de Superficies de Tela

**Propósito:**

Permitir el ascenso por ropa y otras superficies escalables.

**Activación:**

Saltar o caminar hacia una superficie marcada visualmente con una textura tejida y mantener la dirección de ascenso.

**Reglas:**

- Solo se puede escalar en superficies designadas y reconocibles por su apariencia de tela o hilos.
- Mochi pierde el agarre al alejarse de la superficie o alcanzar un borde no escalable.

**Entrada:**

Movimiento hacia la superficie y dirección de ascenso.

**Estado inicial:**

Mochi está junto a una superficie de tela escalable.

**Estado final:**

Mochi alcanza una plataforma superior o suelta la superficie.

**Recursos utilizados:**

Ninguno.

**Recompensa:**

Acceso a plataformas altas y rutas de exploración.

**Penalización:**

Perder el agarre puede provocar una caída hacia una zona peligrosa.

**Interacciones con otras mecánicas:**

El sprint puede ayudar a aproximarse; el combustible no se consume durante la escalada.

**Casos límite:**

Las superficies decorativas que no se puedan escalar deben diferenciarse visualmente de la tela marcada como escalable.

## Mecánicas secundarias

No hay

Avisos contextuales:

   En desafíos complejos aparece un consejo breve, como indicar que se necesitan pilas para activar un ventilador. Al obtener una pila, un indicador señala el aparato o la ranura donde debe colocarse.

Lista las mecánicas que complementan la experiencia pero no constituyen el núcleo.

> **Navegación:** [[00 - Índice]] · ← [[01 - Jugabilidad]] · [[03 - Sistemas]] →
