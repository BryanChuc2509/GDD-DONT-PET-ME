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

### Mecánica 06

Cargar Pilas

**Propósito:**

Resolver el reto del hormiguero llevando las pilas hasta el ventilador.

**Activación:**

Tocar una pila: Mochi la levanta solo, sin pulsar ninguna tecla.

**Reglas:**

- Mochi carga una sola pila a la vez.
- Mientras la carga se mueve un 15% más lento, pero puede correr, saltar y planear.
- Si una hormiga aturde a Mochi, suelta la pila.
- Si Mochi muere, la pila que cargaba vuelve a su lugar original.
- Al tocar el compartimento del ventilador con una pila, esta se coloca sola. El ventilador necesita 3 pilas.

**Entrada:**

Contacto para recoger y colocar.

**Estado inicial:**

Mochi no carga nada y hay una pila libre en el escenario.

**Estado final:**

La pila queda colocada en el ventilador o vuelve a quedar libre en el escenario.

**Recursos utilizados:**

Las 3 pilas del Nivel 1.

**Recompensa:**

Con las 3 pilas colocadas, el ventilador se enciende, aspira a las hormigas durante 3 segundos y luego se cae; el objetivo cambia a "Llega a la salida".

**Penalización:**

Perder la pila por un aturdimiento obliga a volver por ella.

**Interacciones con otras mecánicas:**

Mientras Mochi carga una pila, un marcador en pantalla señala el ventilador y el objetivo del HUD cuenta las pilas colocadas (x/3). Las hormigas son la principal amenaza durante el transporte.

**Casos límite:**

Si Mochi suelta la pila por un aturdimiento y no hay suelo debajo, la pila vuelve a su lugar original.

### Mecánica 07

Aturdimiento y Lentitud

**Propósito:**

Que algunos enemigos y obstáculos estorben a Mochi sin matarlo, castigando el error con tiempo y posición.

**Activación:**

Recibir el efecto de una de las fuentes de la lista.

**Reglas:**

- **Aturdimiento:** Mochi no puede moverse, saltar ni correr durante un momento. Una hormiga lo aturde 1 segundo ("¡Aturdido!"). Una bola de telaraña rodante lo derriba lejos y lo aturde 0.8 segundos ("¡Derribado!").
- Después de un aturdimiento hay 0.75 segundos en los que no puede volver a ser aturdido.
- Si 4 hormigas lo tocan a la vez, Mochi muere ("¡Enjambre!").
- Al ser aturdido, Mochi suelta la pila que cargue y se suelta de la superficie que esté trepando.
- **Lentitud:** la telaraña que escupe la araña deja a Mochi al 35% de su velocidad durante 1.5 segundos ("¡Telaraña!"). El charco del gato lo deja al 45% mientras lo pisa y un momento después ("¡Charco del gato! Vas más lento").

**Entrada:**

Contacto con la fuente del efecto.

**Estado inicial:**

Mochi se mueve con normalidad.

**Estado final:**

Mochi recupera el control o su velocidad normal al terminar el efecto.

**Recursos utilizados:**

Ninguno.

**Recompensa:**

No aplica.

**Penalización:**

Mochi pierde tiempo y posición; puede caer de una plataforma o perder una pila.

**Interacciones con otras mecánicas:**

Estos efectos no matan por sí mismos, pero pueden dejar a Mochi al alcance de un peligro letal. Al reaparecer en un checkpoint se quitan todos los efectos.

**Casos límite:**

Un aturdimiento nuevo no se suma mientras dura otro ni durante los 0.75 segundos de protección.

### Mecánica 08

Plataformas de Impulso, Recorridos Guiados y Plataformas Móviles

**Propósito:**

Dar variedad al plataformeo con objetos del entorno que lanzan, transportan o se mueven.

**Activación:**

Pisar o tocar el objeto.

**Reglas:**

- **Plataformas de impulso:** al caer sobre el vaso o el globo del Nivel 1, Mochi sale lanzado hacia arriba; el vaso lanza más alto que el globo. El rebote reinicia el planeo.
- **Recorridos guiados:** en el pasillo, el tubo de cartón ("¡A rodar!") y el cable de la lámpara como tirolesa llevan a Mochi de un punto a otro sin control y lo sueltan con impulso al final. En la tirolesa, `ESPACIO` lo suelta a mitad del recorrido.
- **Hilos que cuelgan:** en la estantería de la araña, al tocar un hilo que cuelga de un estante, Mochi sube solo por él hasta el estante de arriba, sin pulsar ninguna tecla.
- **Plataformas móviles:** la noria del Nivel 1, cuyas cabinas giran y se mantienen horizontales; ascensores que suben y bajan; y libros colgantes que se balancean como péndulo. Mochi se mueve junto con la plataforma que pisa.
- **Plataformas que se caen:** la nota del tutorial, algunas repisas y libros tiemblan al pisarlos, se caen y reaparecen 3 segundos después.

**Entrada:**

Contacto con el objeto; `ESPACIO` para soltarse de la tirolesa.

**Estado inicial:**

Mochi llega al objeto.

**Estado final:**

Mochi sale lanzado, llega al final del recorrido o se baja de la plataforma.

**Recursos utilizados:**

Ninguno.

**Recompensa:**

Alcanzar zonas altas o lejanas.

**Penalización:**

Calcular mal el momento deja a Mochi en el vacío.

**Interacciones con otras mecánicas:**

Después de un impulso se puede planear para alargar el salto.

**Casos límite:**

Las plataformas que se caen vuelven a su sitio aunque Mochi no muera.

### Mecánica 09

Interruptores

**Propósito:**

Abrir el camino cambiando algo del escenario.

**Activación:**

Tocar el interruptor; el botón se hunde.

**Reglas:**

- Cada interruptor se activa una sola vez y queda activado aunque Mochi muera.
- Puede encender o apagar objetos, cortar la corriente, cambiar el objetivo o terminar el nivel.
- **Tutorial:** el botón dentro del laberinto de tubos abre la salida ("¡Salida abierta!") y la tecla Enter es la meta del nivel ("¡Escapaste de la jaula!").
- **Nivel 1:** el interruptor de la regleta corta la corriente de los cables electrificados ("Corriente cortada"), otro activa un puente ("¡Puente activado!") y otro apaga el ventilador que sopla a Mochi ("¡Ventilador apagado!"). La meta del nivel también es un interruptor.
- **Nivel 2:** la meta en la sala de estar es un interruptor que termina el nivel.

**Entrada:**

Contacto.

**Estado inicial:**

Interruptor sin pulsar.

**Estado final:**

Interruptor pulsado y su efecto aplicado.

**Recursos utilizados:**

Ninguno.

**Recompensa:**

Se abre la ruta o se completa el nivel.

**Penalización:**

Ninguna.

**Interacciones con otras mecánicas:**

Mientras tienen corriente, los cables electrificados matan al tocarlos ("¡Calambre!").

**Casos límite:**

Un interruptor activado no se puede desactivar.

### Mecánica 10

Trampas de Leo

**Propósito:**

Sorprender al jugador con el humor absurdo de las bromas de Leo.

**Activación:**

Tocar la trampa o acercarse a ella.

**Reglas:**

- **Semillas trampa:** parecen semillas; al tocarlas lanzan a Mochi por los aires y le quitan el control un momento ("¡Moneda trampa!"). Están en los tres niveles.
- **Checkpoints falsos:** parecen checkpoints y lanzan a Mochi ("¡Checkpoint falso!"). Están en el Nivel 1 y en el pasillo.
- **Objetos que huyen:** en el Nivel 1, una semilla, un libro y la meta se apartan cuando Mochi se acerca. La semilla y el libro regresan después de unos segundos; la meta se queda en su nuevo sitio.
- **Bloques ocultos:** son invisibles hasta que Mochi los golpea saltando desde abajo; entonces aparecen y le cortan el salto ("¡Bloque oculto!").
- **Libro con resorte:** al pisarlo se abre de golpe y lanza a Mochi ("¡Boing! Ese libro tenía resorte").
- **Libros que se caen encima:** tiemblan y caen sobre Mochi; matan mientras caen y luego quedan tumbados como escalón ("¡Plaf!").
- **Objetos que caen desde arriba:** la grapadora y el pisapapeles caen cuando Mochi pasa debajo, matan al caer y vuelven a subir.
- **Pinchos que salen del suelo** cuando Mochi se acerca ("¡Pinchos!"), en el Nivel 1 y en el pasillo.
- **Ventilador que sopla y barra giratoria:** lanzan a Mochi lejos ("¡Fiuuuuu!", "¡Zas!").
- **Plataformas falsas:** un libro, un tablón, una tabla y un zócalo se caen al pisarlos sin temblar antes.

**Entrada:**

Contacto con la trampa o acercarse a ella.

**Estado inicial:**

La trampa parece un objeto inofensivo.

**Estado final:**

Mochi sale lanzado, pierde el salto, cae o muere, según la trampa.

**Recursos utilizados:**

Ninguno.

**Recompensa:**

No aplica.

**Penalización:**

Mochi puede caer al vacío o morir.

**Interacciones con otras mecánicas:**

Cada trampa avisa con un mensaje en el centro del HUD. Las que lanzan a Mochi le quitan el control entre 0.9 y 1.5 segundos.

**Casos límite:**

Los libros que cayeron se vuelven a poner de pie si Mochi muere.

## Mecánicas secundarias

### Ver objetivo

Con `TAB`, o al pulsar la bandera del HUD, vuelve a aparecer la tarjeta con el objetivo actual. Cada objetivo nuevo se anuncia solo y después la tarjeta se reduce a la bandera.

### Avisos contextuales

En desafíos complejos aparece un consejo breve, como indicar que se necesitan pilas para activar un ventilador. Al obtener una pila, un indicador señala el aparato o la ranura donde debe colocarse.

> **Navegación:** [[00 - Índice]] · ← [[01 - Jugabilidad]] · [[03 - Sistemas]] →
