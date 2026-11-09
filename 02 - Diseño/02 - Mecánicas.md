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

- Al saltar sobre un enemigo vulnerable, Mochi lo aturde o aparta y puede rebotar para continuar el recorrido.

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

Se combina con el sprint para ganar impulso y con la escalada de superficies de tela.

**Casos límite:**

No alcanzar ciertas superficies.

### Mecánica 03

Sprint con Combustible

**Propósito:**

Dar al jugador dos usos alternativos de una sola reserva de combustible: aumentar la velocidad al correr por el suelo y planear brevemente en el aire para extender un salto y ralentizar la caída.

**Activación:**

Mantener `SHIFT` mientras Mochi se desplaza por el suelo para esprintar o mientras está en el aire para planear.

**Reglas:**

- Sprint y planeo consumen la misma reserva; el jugador debe decidir si gasta combustible en velocidad antes del salto o lo conserva para usarlo en el aire.
- En el aire, mantener `SHIFT` activa el planeo: Mochi obtiene control horizontal limitado y desciende más despacio, pero no asciende ni queda suspendido.
- El planeo dura como máximo **1 segundo por tramo en el aire** y termina antes si se suelta `SHIFT` o se agota el combustible. El doble salto no reinicia ese límite.
- El sprint consume combustible mientras está activo. El planeo consume combustible de esa misma reserva durante el tiempo que está activo.
- El combustible se regenera con el tiempo al dejar de usar `SHIFT`, tanto si Mochi está en el suelo como en el aire. No se consume al caminar, saltar o escalar.
- Si no queda combustible al despegar, no se puede activar el planeo en ese salto; el jugador deberá esperar a que la reserva se recupere antes de usarlo.
- La capacidad y las tasas de consumo y recuperación se determinarán mediante pruebas de balance para que el uso prolongado del sprint pueda dejar insuficiente combustible para planear.

**Entrada:**

`SHIFT` (mantener en el suelo para esprintar; mantener en el aire para planear; soltar para dejar de consumir y regenerar combustible).

**Estado inicial:**

Mochi tiene combustible disponible y se encuentra en el suelo o en el aire.

**Estado final:**

En el suelo, Mochi vuelve a su velocidad normal al soltar `SHIFT` o agotar el combustible. En el aire, el planeo termina al soltar `SHIFT`, agotar el combustible o alcanzar 1 segundo de planeo en el tramo actual en el aire.

**Recursos utilizados:**

Una sola reserva compartida de combustible, mostrada mediante un indicador en el HUD.

**Recompensa:**

Mayor velocidad temporal en el suelo o más distancia y control durante un salto.

**Penalización:**

Gastar todo el combustible en el sprint deja a Mochi sin planeo si lo necesita al saltar; agotar la reserva en el aire termina el planeo y puede dejarlo corto de su destino.

**Interacciones con otras mecánicas:**

El sprint puede dar impulso antes de un salto, pero ese gasto reduce lo disponible para planear. El planeo complementa el salto y el doble salto, pero no protege contra peligros letales.

**Casos límite:**

Si el combustible se agota mientras `SHIFT` sigue presionado, la acción activa se interrumpe. En el aire, alcanzar el límite de 1 segundo impide seguir planeando durante ese mismo tramo en el aire, aunque quede combustible; el doble salto no reinicia el límite y se podrá esprintar nuevamente al tocar el suelo.

### Mecánica 04

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

### Mecánica 05

Aplastar Enemigos desde Arriba

**Propósito:**

Dar una respuesta de movimiento defensiva cuando Mochi salta sobre enemigos vulnerables, sin introducir combate cuerpo a cuerpo.

**Activación:**

Caer sobre un enemigo desde arriba tras un salto.

**Reglas:**

- Solo los enemigos designados como vulnerables pueden ser eliminados.
- El contacto lateral o desde abajo sigue siendo peligroso y puede causar la muerte.
- Los jefes o enemigos resistentes requieren resolver su desafío específico; saltar sobre ellos no los derrota automáticamente.

**Entrada:**

Salto (`ESPACIO`) y contacto desde arriba.

**Estado inicial:**

Mochi está en el aire y un enemigo vulnerable está debajo.

**Estado final:**

El enemigo queda aturdido o desplazado brevemente y Mochi puede rebotar o continuar.

**Recursos utilizados:**

Ninguno.

**Recompensa:**

Una oportunidad breve para superar al enemigo y continuar el recorrido.

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
