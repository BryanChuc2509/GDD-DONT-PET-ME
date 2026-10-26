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

Almacenamiento y Disparo de mejillas (con Fijado de Cámara)

**Propósito:** 

Proveer un sistema de inventario y ataque a distancia integrado a la anatomía de un hámster, prescindiendo de armas convencionales y adaptado a una cámara de seguimiento cinemático.

**Activación:**

Presionar `E` para recoger objetos del entorno; mantener `CLIC DERECHO` para activar el modo de apuntado con fijado de cámara (lock-on/enfoque focalizado hacia dianas o con parábola de disparo) y presionar `CLIC IZQUIERDO` para escupir el proyectil seleccionado.

**Reglas:**

- Mochi solo puede almacenar un número limitado de objetos en sus mejillas según su capacidad.
- **Cámara y Fijado (Lock-on):** Dado que la cámara es fija y de seguimiento dinámico automático (el jugador no la controla libremente con el ratón), al mantener `CLIC DERECHO` la cámara realiza un zoom sutil y un encuadre de fijado (*lock-on*) centrándose en el interruptor, mecanismo o enemigo más cercano en su cono visual, o proyectando la trayectoria predictiva frente a Mochi.
- Las semillas actúan como proyectiles de impacto balístico para activar botones remotos o aturdir enemigos.
- Mientras mantiene el fijado (`CLIC DERECHO`), la velocidad de desplazamiento de Mochi se reduce para permitir ajustes finos de posición.
- No se puede disparar en mitad de ciertas animaciones (como escalando, rodando o colgado del globo).

**Entrada:**

`E` (Recoger) / `CLIC DERECHO (Mantener)` para apuntar y fijar + `CLIC IZQUIERDO` para disparar.

**Estado inicial:**

Mejillas vacías o con munición almacenada; modo de navegación estándar de cámara.

**Estado final:**

Proyectil expulsado hacia el objetivo fijado; reducción de la munición/objeto en las mejillas y retorno al encuadre dinámico normal de la cámara.

**Recursos utilizados:**

Semillas / Objetos arrojadizos del inventario bucal.

**Recompensa:**

Activación precisa de mecanismos a distancia o neutralización momentánea de amenazas sin perder visibilidad en un entorno con cámara de seguimiento.

**Penalización:**

Gasto de munición limitado; si el jugador se queda sin semillas en salas con interruptores elevados, deberá buscar suministros en el entorno.

**Interacciones con otras mecánicas:**

Si Mochi rueda, salta o se desliza con `SHIFT`, el apuntado con fijado se interrumpe inmediatamente.

**Casos límite:**

Si no hay objetivos en rango frontal, el fijado mantendrá la orientación del vector hacia donde mira Mochi con una parábola libre guiada por el cursor. Si el jugador intenta comer mientras apunta, la acción de fijado se cancela.

<!-- Copiar la plantilla anterior -->

### Mecánica 02

Salto, Doble Salto e Inercia

**Propósito:**

Permitir el plataformeo vertical y salvar abismos gigantescos entre muebles.

**Activación:**

Pulsar `ESPACIO` en el suelo; volver a pulsar `ESPACIO` en el aire. Mantener `ESPACIO` agachado para Salto Cargado.

**Reglas:**

- El segundo salto reinicia la trayectoria vertical pero mantiene la velocidad horizontal.
- Al caer desde grandes alturas, si se presiona la tecla de agacharse/deslizarse (`SHIFT`) justo antes de impactar, Mochi ejecuta una rodada que conserva la velocidad en lugar de frenarse.

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

Teniendo el hilo seleccionado en el inventario de las mejillas, apuntar a un anclaje compatible manteniendo `CLIC DERECHO` (fijado de cámara en el anclaje) y presionar `CLIC IZQUIERDO` para lanzar el hilo.

**Reglas:**

* El hilo no se pega en cualquier lado; solo funciona en anclajes metálicos o salientes rígidos definidos por el diseño de nivel (como pinzas de papel o tachuelas).
* El jugador debe usar las teclas de movimiento para ganar impulso (momentum) antes de soltarse.

**Entrada:**

`CLIC DERECHO (Fijar anclaje) + CLIC IZQUIERDO (Lanzar)` con Hilo seleccionado.

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

**Deslizamiento y Agacharse (`SHIFT`):**
   Al correr y presionar `SHIFT`, Mochi realiza un deslizamiento fluido que conserva la inercia para pasar por debajo de rendijas de puertas, muebles bajos o cables colgantes. Si se pulsa estando quieto, Mochi se agacha reduciendo su perfil y ocultándose de amenazas. También permite ejecutar una rodada amortiguadora al tocar tierra tras un salto.
**Escalada de Superficies Porosas:**
   Mochi se adhiere a telas, ropa desparramada y persianas para ascender verticalmente mientras mantenga contacto.

Lista las mecánicas que complementan la experiencia pero no constituyen el núcleo.

> **Navegación:** [[00 - Índice]] · ← [[01 - Jugabilidad]] · [[03 - Sistemas]] →
