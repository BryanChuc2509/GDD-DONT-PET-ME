# Progresión

## Descripción de la sección

Explica cómo cambia la experiencia desde el inicio hasta el final. La progresión puede afectar al personaje, al mundo, a las habilidades, al contenido o al conocimiento del jugador.

## Progresión general

Describe las etapas principales del juego:

1. **Introducción narrativa:** La captura de Mochi en el bosque se presenta en una breve secuencia; el juego no incluye un nivel jugable en el bosque.
2. **Zona 1 — La jaula:** El jugador aprende el movimiento y el salto en un encuadre amplio que presenta el espacio; al tomar control, el lado de la jaula más cercano a la cámara se vuelve transparente.
3. **Zona 2 — El escritorio:** Se introducen el sprint y el combustible compartido, la recolección de semillas-moneda y la interacción contextual con objetos y mecanismos.
4. **Zona 3 — Libros colgantes:** El jugador aprende a reconocer y escalar superficies con textura tejida y combina la escalada con saltos, sprint y planeo.
5. **Zona 4 — Pelotas que caen:** Tramo de avance bajo presión, con pelotas que ruedan o caen por un pasillo; el jugador lee sus patrones y decide si gastar combustible en correr o reservarlo para planear hasta un segundo y alcanzar un hueco seguro.
6. **Continuación del recorrido:** Las zonas posteriores combinan las habilidades aprendidas con nuevos peligros y checkpoints.

## Progresión del jugador

El jugador aprende a calcular saltos y a administrar una única reserva para el sprint en el suelo y el planeo en el aire. Si consume todo el combustible corriendo antes de saltar, no podrá planear y quizá no alcance la plataforma; por eso debe decidir cuándo correr y cuándo guardar combustible. Soltar `SHIFT` permite recuperar la reserva. También reconoce las superficies de tela escalables, aprende a saltar sobre enemigos vulnerables y usa la distribución de semillas como orientación y recompensa de exploración. Las semillas ya no son munición.

## Progresión del personaje

¿Qué mejora el personaje?

- **Vida:** **Inmutable**. No hay mejoras de salud; Mochi siempre muere de un solo golpe (One-hit kill).
- **Daño:** No hay combate con armas. Saltar sobre enemigos vulnerables los aturde o aparta brevemente; no se derrotan como sistema de combate.
- **Habilidades:** Desplazamiento, salto, doble salto, sprint en el suelo, planeo en el aire, agacharse y escalar las superficies designadas están disponibles durante el recorrido y se enseñan de forma gradual.
- **Combustible:** Una reserva temporal compartida por el sprint y el planeo; este último dura como máximo 1 segundo por tramo en el aire y el doble salto no reinicia ese límite. Se regenera al dejar de usar `SHIFT`. La capacidad y las tasas se ajustan mediante pruebas.
- **Colección:** Las semillas se recogen como moneda y no ocupan espacio de inventario ni se consumen al usarlas.
- **Cosméticos:** Una skin básica se compra con semillas; otra skin se desbloquea al recolectar todas las semillas del juego.
- **Objetos contextuales:** Algunos puzzles requieren recoger y colocar un objeto concreto, como una pila. Estos objetos se gestionan solo durante su desafío y no forman parte de un inventario general.

## Desbloqueos

| Desbloqueo | Requisito | Efecto |
|---|---|---|
| Skin básica | Reunir y gastar la cantidad requerida de semillas | Cambia la apariencia de Mochi sin afectar sus capacidades |
| Skin de colección completa | Recoger todas las semillas del juego | Desbloquea un aspecto especial de Mochi |
| Ventilador u otro dispositivo | Recoger el objeto de objetivo indicado y colocarlo en su ranura | Activa el mecanismo y abre o facilita el recorrido |

El precio de la skin comprable y el total de semillas se definirán durante el balance.

## Checkpoints

Se coloca un checkpoint en pausas seguras entre desafíos, en particular al salir de la jaula y al terminar zonas de escritorio, libros colgantes y pelotas. Al morir, Mochi reaparece en el último checkpoint; las semillas ya recogidas y los puzzles que el juego marque como persistentes se conservan.

## Curva de dificultad

La jaula es segura y presenta controles básicos. El escritorio introduce obstáculos y enseña el sprint; los libros colgantes enseñan a escalar y usar el planeo; el pasillo de pelotas combina velocidad, planeo, observación y elección de refugios. Las zonas posteriores aumentan la presión y combinan habilidades ya aprendidas.

## Curva de aprendizaje

Antes de un tramo que exija velocidad o planeo, el jugador practica ambos usos de `SHIFT` y observa que comparten combustible. El diseño muestra una oportunidad para usar el sprint y otra para reservar la carga y planear; así el jugador entiende que gastarla toda antes de un salto puede impedirle llegar. Antes de escalar rutas importantes, el tutorial muestra de forma clara la textura tejida de las superficies válidas. Las pistas contextuales se reservan para desafíos difíciles y se acompañan de un indicador de destino cuando el jugador obtiene el objeto necesario.


> **Navegación:** [[00 - Índice]] · ← [[04 - Controles]] · [[06 - Economía y Recursos]] →
