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

Recolección de Semillas-Moneda

**Propósito:**

Guiar al jugador por las zonas y recompensar la exploración con una moneda para desbloquear aspectos cosméticos de Mochi.

**Activación:**

Las semillas se recogen automáticamente al tocarlas.

**Reglas:**

- La distribución de semillas orienta hacia el recorrido principal sin impedir que el jugador explore rutas secundarias.
- El saldo acumulado se conserva al morir y reaparecer en un checkpoint.
- Una skin básica se compra con semillas; otra skin se desbloquea al recolectar todas las semillas del juego. El precio de compra se ajustará durante el balance.

**Entrada:**

Contacto con una semilla.

**Estado inicial:**

Semillas disponibles en el escenario; saldo visible en el HUD.

**Estado final:**

Semilla retirada del escenario y su valor añadido al saldo.

**Recursos utilizados:**

Semillas recogidas y saldo de semillas.

**Recompensa:**

Compra de una skin básica o, al completar la colección, desbloqueo de una skin especial.

**Penalización:**

No recoger una semilla reduce el saldo final disponible, pero no bloquea la progresión del nivel.

**Interacciones con otras mecánicas:**

La guía visual de semillas complementa la iluminación, la geometría del nivel y los puntos de control.

**Casos límite:**

Las semillas ya recogidas no vuelven a aparecer al reaparecer en un checkpoint.

<!-- Copiar la plantilla anterior -->

### Mecánica 02

Salto e Inercia

**Propósito:**

Permitir el plataformeo vertical y salvar abismos gigantescos entre muebles.

**Activación:**

Pulsar `ESPACIO` en el suelo.

**Reglas:**

- Al caer desde arriba sobre un enemigo vulnerable, Mochi lo aplasta y lo mata; el rebote le permite continuar el recorrido.

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

Permitir que Mochi aumente temporalmente su velocidad al correr por el suelo mediante una reserva de combustible exclusiva del sprint.

**Activación:**

Mantener `SHIFT` mientras Mochi se desplaza por el suelo.

**Reglas:**

- El sprint solo se activa en el suelo y consume combustible mientras está activo.
- El combustible se regenera con el tiempo mientras el sprint no está activo, tanto en el suelo como en el aire. Caminar, saltar, planear y escalar no lo consumen.
- Si se agota el combustible mientras el sprint está activo, Mochi vuelve a su velocidad normal. No puede volver a esprintar hasta que la reserva se recupere.
- El combustible del sprint no afecta la disponibilidad, duración ni alcance del planeo.
- La capacidad y las tasas de consumo y recuperación se determinarán mediante pruebas de balance para ajustar el uso del sprint.

**Entrada:**

`SHIFT` (mantener mientras Mochi se desplaza por el suelo para esprintar).

**Estado inicial:**

Mochi se desplaza por el suelo y tiene combustible disponible.

**Estado final:**

Mochi vuelve a su velocidad normal al soltar `SHIFT` o agotar el combustible.

**Recursos utilizados:**

La reserva de combustible del sprint, mostrada mediante un indicador en el HUD.

**Recompensa:**

Mayor velocidad temporal en el suelo para recorrer tramos y tomar impulso antes de un salto.

**Penalización:**

Gastar todo el combustible impide esprintar hasta que la reserva se recupere.

**Interacciones con otras mecánicas:**

El sprint puede dar impulso antes de un salto. Su combustible es independiente del planeo y no protege contra peligros letales.

**Casos límite:**

Si el combustible se agota mientras `SHIFT` sigue presionado, el sprint se interrumpe y no se reactiva hasta que haya combustible disponible.

### Mecánica 04

Planeo

**Propósito:**

Reducir por un momento la velocidad de caída para extender un salto y ayudar a alcanzar plataformas lejanas o aterrizar con más control.

**Activación:**

Mantener `ESPACIO` cuando Mochi ya está en el aire.

**Reglas:**

- El planeo no consume combustible y está disponible independientemente de la reserva del sprint.
- Mientras planea, Mochi obtiene control horizontal limitado y desciende más despacio, pero no asciende ni queda suspendido.
- El planeo dura como máximo **1 segundo por tramo en el aire** y termina antes si se suelta `ESPACIO`. El doble salto no reinicia ese límite.

**Entrada:**

`ESPACIO` (mantener en el aire para planear; soltar para dejar de planear).

**Estado inicial:**

Mochi está en el aire.

**Estado final:**

El planeo termina al soltar `ESPACIO` o alcanzar 1 segundo en el tramo actual en el aire.

**Recursos utilizados:**

Ninguno.

**Recompensa:**

Más distancia y control durante un salto al ralentizar la caída.

**Penalización:**

Un mal cálculo del momento de activar el planeo puede dejar a Mochi corto de su destino cuando se agote el segundo disponible.

**Interacciones con otras mecánicas:**

El planeo complementa el salto y el doble salto. Es independiente del combustible del sprint y no protege contra peligros letales.

**Casos límite:**

Al alcanzar el límite de 1 segundo no se puede volver a planear durante ese mismo tramo en el aire, aunque quede combustible. El doble salto no reinicia el límite; este vuelve a estar disponible al tocar el suelo.

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

### Mecánica 06

Aplastar Enemigos desde Arriba

**Propósito:**

Dar una respuesta de movimiento defensiva cuando Mochi salta sobre enemigos vulnerables, sin introducir combate cuerpo a cuerpo.

**Activación:**

Caer sobre un enemigo desde arriba tras un salto.

**Reglas:**

- Solo los enemigos designados como vulnerables pueden ser eliminados al aplastarlos desde arriba.
- El contacto lateral o desde abajo sigue siendo peligroso y puede causar la muerte.
- Los jefes o enemigos resistentes requieren resolver su desafío específico; saltar sobre ellos no los derrota automáticamente.

**Entrada:**

Salto (`ESPACIO`) y contacto desde arriba.

**Estado inicial:**

Mochi está en el aire y un enemigo vulnerable está debajo.

**Estado final:**

El enemigo muere y Mochi rebota para continuar el recorrido.

**Recursos utilizados:**

Ninguno.

**Recompensa:**

Mata al enemigo vulnerable y despeja el paso de forma permanente.

**Penalización:**

Un contacto que no sea desde arriba puede provocar la muerte instantánea.

**Interacciones con otras mecánicas:**

Requiere leer el movimiento del enemigo y sincronizar el salto; no reemplaza el sigilo ni la evasión.

**Casos límite:**

La señal visual del enemigo debe comunicar si es vulnerable al salto antes de que el jugador se arriesgue.

## Mecánicas secundarias

No hay

Avisos contextuales:

   En desafíos complejos aparece un consejo breve, como indicar que se necesitan pilas para activar un ventilador. Al obtener una pila, un indicador señala el aparato o la ranura donde debe colocarse.

Lista las mecánicas que complementan la experiencia pero no constituyen el núcleo.

> **Navegación:** [[00 - Índice]] · ← [[01 - Jugabilidad]] · [[03 - Sistemas]] →
