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

Almacenamiento y Disparo de mejillas

**Propósito:** 

Proveer un sistema de inventario y ataque a distancia integrado a la anatomía de un hámster, prescindiendo de armas convencionales.

**Activación:**

Presionar `E` para recoger objetos; mantener `SHIFT` para apuntar con una parábola visual y hacer `CLICK IZQUIERDO` para escupir.

**Reglas:**

- Mochi solo puede almacenar un número limitado de objetos en sus mejillas.
- Las semillas funcionan como proyectiles de impacto para golpear botones o aturdir enemigos.
- No se puede disparar en mitad de ciertas animaciones (como escalar).

**Entrada:**

`E` (Recoger) / `SHIFT + Click` (Apuntar y disparar).

**Estado inicial:**

Mejillas vacías

**Estado final:**

Objeto proyectado contra el objetivo; reducción del inventario bucal.

**Recursos utilizados:**

Semillas / Objetos interactivos del escenario.

**Recompensa:**

Activación de mecanismos lejanos o aturdimiento de amenazas.

**Penalización:**

Quedarse sin semillas en zonas que requieren pulsar interruptores remotos.

**Interacciones con otras mecánicas:**

Si Mochi rueda o salta, la parábola de disparo se desestabiliza.

**Casos límite:**

Si el jugador intenta comer mientras apunta, la acción de apuntar se cancela.

<!-- Copiar la plantilla anterior -->

### Mecánica 02

Salto, Doble Salto e Inercia

**Propósito:**

Permitir el plataformeo vertical y salvar abismos gigantescos entre muebles.

**Activación:**

Pulsar `ESPACIO` en el suelo; volver a pulsar `ESPACIO` en el aire. Mantener `ESPACIO` agachado para Salto Cargado.

**Reglas:**

- El segundo salto reinicia la trayectoria vertical pero mantiene la velocidad horizontal.
- Al caer desde grandes alturas, si se presiona la tecla de agacharse/deslizarse justo antes de impactar, Mochi ejecuta una rodada que conserva la velocidad en lugar de frenarse.

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

Se combina con el Wall Jump rebotando en superficies verticales o con el deslizamiento bajo zócalos.

**Casos límite:**

El doble salto no se reactiva hasta que las patas toquen nuevamente una superficie válida.

### Mecánica 03

Balanceo con Hilo

**Propósito:**

Permitir a Mochi cruzar vacíos gigantescos entre muebles balanceándose al estilo liana o gancho de agarre.

**Activación:**

Teniendo el hilo seleccionado en el inventario de las mejillas, apuntar a un anclaje compatible y presionar el botón de disparo/acción.

**Reglas:**

* El hilo no se pega en cualquier lado; solo funciona en anclajes metálicos o salientes rígidos definidos por el diseño de nivel (como pinzas de papel o tachuelas).
* El jugador debe usar las teclas de movimiento para ganar impulso (momentum) antes de soltarse.

**Entrada:**

`SHIFT + Click` (con Hilo seleccionado).

**Estado inicial:**

Mochi saltando hacia el vacío y lanzando el hilo.

**Estado final:**

Mochi llegando a salvo en una plataforma lejana tras cortar o soltar el balanceo.

**Recursos utilizados:**

Hilo (almacenado en las mejillas).

**Recompensa:**

Superación de grandes abismos y mantenimiento de la fluidez del parkour.

**Penalización:**

Soltarse en el ángulo equivocado o en el momento incorrecto provoca caer en picada hacia el vacío o zonas letales.

**Interacciones con otras mecánicas:**

No hay

**Casos límite:**

Disparar el hilo hacia una superficie que no tiene un punto de anclaje válido cancelará la animación inmediatamente sin gastar el objeto.

### Mecánica 04

Ascenso con Globo

**Propósito:**

Otorgar movilidad vertical pura para alcanzar repisas de extrema altura donde no existen plataformas para saltar o escalar.

**Activación:**

Seleccionar el globo en el inventario y activarlo. Mochi lo infla rápidamente y comienza a flotar.

**Reglas:**

* El ascenso es a una velocidad vertical constante y anula la gravedad temporalmente.
* El control horizontal (moverse a los lados) es extremadamente lento y limitado mientras se flota.
* El globo se revienta inmediatamente si toca una superficie afilada (lápices con punta, chinchetas, bordes de metal).

**Entrada:**

Botón de usar objeto del inventario (ej. mantener pulsado `Click`).

**Estado inicial:**

Mochi en el suelo, sacando el globo de su boca e inflándolo.

**Estado final:**

Mochi aterrizando en una zona elevada (o cayendo si el globo explota).

**Recursos utilizados:**

Globo

**Recompensa:**

Acceso rápido a zonas altas, atajos o áreas secretas fuera del alcance del doble salto.

**Penalización:**

Si el jugador calcula mal y choca contra un objeto punzante a gran altura, el globo explota y la caída resultante puede ser letal.

**Interacciones con otras mecánicas:**

No se pueden disparar semillas ni usar el deslizamiento mientras Mochi está colgado del globo.

**Casos límite:**

Si Mochi llega al techo de una habitación (una superficie plana sin salientes), se quedará flotando atascado contra el techo hasta que el globo termine su tiempo límite de uso y se desinfle solo.

## Mecánicas secundarias

**Deslizamiento y Agacharse:**
   Permite reducir el perfil del hámster para pasar por debajo de rendijas de puertas, muebles o cables colgantes.
**Escalada de Superficies Porosas:**
   Mochi se adhiere a telas, ropa desparramada y persianas para ascender verticalmente mientras mantenga contacto.

Lista las mecánicas que complementan la experiencia pero no constituyen el núcleo.

> **Navegación:** [[00 - Índice]] · ← [[01 - Jugabilidad]] · [[03 - Sistemas]] →
