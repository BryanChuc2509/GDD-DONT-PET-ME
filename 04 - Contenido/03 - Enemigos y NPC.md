# Enemigos y NPC

## Descripción de la sección

Documenta los personajes no controlados por el jugador, las amenazas y sus interacciones con Mochi. Las decisiones tomadas para el diseño actual prevalecen sobre variantes antiguas de la entrega 3.

## Reglas comunes

- El contacto con un enemigo es mortal para Mochi.
- Mochi no puede derrotar enemigos: los esquiva o usa el entorno para avanzar.
- Las semillas solo guían el recorrido: no son munición y no aturden ni atacan enemigos.
- El minijefe de las hormigas se supera con el reto de las pilas y el ventilador.

## Enemigos

### Araña de Rincón

**Rol:** Enemigo de la habitación (Nivel 1).

**Comportamiento:** Detecta a Mochi cuando se acerca y lo persigue por el suelo, sin alejarse demasiado de su zona ni seguirlo a plataformas mucho más altas o más bajas. Cada pocos segundos le escupe una telaraña apuntando hacia donde se mueve.

**Daño:** Tocarla causa muerte instantánea ("¡Araña!"). La telaraña no mata: si alcanza a Mochi, lo deja al 35% de su velocidad durante 1.5 segundos ("¡Telaraña!").

**Vulnerabilidad:** No se puede derrotar; Mochi debe evitarla.

**Interacciones:** No recibe daño ni se aturde con semillas.

### Aspiradora Inteligente

**Rol:** Amenaza de persecución del pasillo.

**Origen:** Los padres de Leo la programaron para cazar al ratón que ronda la casa.

**Comportamiento:** Despierta cuando Mochi entra en su zona, lo confunde con el ratón y lo persigue por cualquier terreno: sube escalones y rampas, baja desniveles y empuja los objetos ligeros. Si Mochi se aleja mucho, acelera para alcanzarlo. Cuando lo tiene cerca, avisa parpadeando y embiste; si Mochi está más alto, salta para alcanzarlo. Si se queda atascada o muy atrás, "toma un atajo" y reaparece detrás de él.

**Daño:** Si alcanza a Mochi, este muere ("¡Aspirado! La aspiradora es todo terreno y embiste: no hay sitio seguro").

**Vulnerabilidad:** No se puede derrotar ni con semillas; el jugador debe escapar y aprovechar el entorno para avanzar.

**Estado de diseño:** Amenaza principal del pasillo. Persigue a la misma velocidad a la que camina Mochi, así que el jugador no puede detenerse.

### Ciempiés (Walker)

**Rol:** Enemigo de patrulla.

**Apariencia:** Ciempiés.

**Comportamiento:** Camina en línea recta y da media vuelta al llegar a una pared o al borde de la plataforma. No persigue a Mochi.

**Daño:** El contacto con Mochi es mortal según la regla general de enemigos.

**Vulnerabilidad:** No se puede derrotar; Mochi debe esquivarlo.

**Ubicación:** 2 en el tutorial de la jaula y 6 en el Nivel 1, sobre repisas, mesas y estantes. No aparece en el pasillo.

### Minijefe de las hormigas

**Rol:** Minijefe del escritorio de la habitación.

**Comportamiento:** Un hormiguero de entre 6 y 9 hormigas (nacen más con el tiempo) protege a la hormiga reina. Las hormigas se mueven como los fantasmas de Pac-Man: alternan ratos en los que se dispersan por las esquinas con ratos en los que persiguen a Mochi, y cada una tiene su propia forma de perseguirlo. Si Mochi está en una plataforma alta, algunas trepan o le caen desde arriba ("¡Hormiga desde arriba!"). Una hormiga lo aturde 1 segundo ("¡Aturdido!") y le hace soltar la pila; 4 a la vez lo matan ("¡Enjambre!"). La reina no se mueve, pero tocarla es mortal ("¡La reina!"). También hay hormigas que patrullan y matan al tocarlas ("¡Hormiga!").

**Cómo se supera:** Mochi recoge las 3 pilas y las lleva al compartimento del ventilador. Al colocar la tercera, el ventilador aspira a todas las hormigas durante 3 segundos y después se cae; el objetivo cambia a "Llega a la salida".

**Vulnerabilidad:** No se puede derrotar directamente. La resolución definida es activar el ventilador.


### Araña lanzadora

**Rol:** Amenaza de la estantería del Nivel 1.

**Comportamiento:** Está fija en lo alto de la estantería y lanza una bola de telaraña cada pocos segundos. Unas las echa a rodar por los estantes, como los barriles de Donkey Kong: ruedan cuesta abajo y, al llegar al final de un estante, caen al siguiente. Otras se las lanza directamente a Mochi.

**Daño:** Las bolas de telaraña no matan: derriban a Mochi y lo aturden 0.8 segundos ("¡Derribado!"), lo que puede hacerlo caer de la estantería.

**Cómo se supera:** Mochi esquiva las bolas y sube la estantería por los hilos que cuelgan de los estantes, que se suben con solo tocarlos.

**Vulnerabilidad:** No se puede derrotar.

## Retos que no son enemigos

### Sala de memoria

**Tipo:** Puzzle de memoria al final de la habitación.

**Función:** Una secuencia de baldosas del suelo se ilumina, todas del mismo color y cada una con su propia nota musical. Mochi la memoriza y la repite cayendo con un salto sobre las baldosas en el mismo orden. Son 16 baldosas (4×4) y 5 rondas, con secuencias de 3 a 5 baldosas.

**Fallo:** Si Mochi se equivoca o se acaba el tiempo, las paredes de la sala lo aplastan y el reto empieza otra vez desde la ronda 1.

**Personaje asociado:** Ninguno; la sala funciona sola cuando Mochi entra.

### Trampas de Leo

**Tipo:** Peligros del escenario.

**Ejemplos:** Semillas trampa, checkpoints falsos, objetos que huyen, bloques ocultos, libro con resorte, libros que se caen encima, grapadora y pisapapeles que caen, pinchos que salen del suelo, ventilador que sopla, barra giratoria y plataformas falsas. El detalle está en [[02 - Mecánicas]] (Mecánica 10).

**Regla:** Pueden sorprender al jugador, pero deben dar señales legibles y respetar los criterios de aviso de peligro del GDD.

### Peligros del pasillo

**Tipo:** Peligros del escenario, no personajes.

**Ejemplos:** Ratoneras colocadas por los padres de Leo (algunas ocultas), escobas que caen avisando con su sombra, cables electrificados, piezas de Lego, una rejilla y tablas falsas por donde se cae, tachuelas y el charco del gato, que frena a Mochi.

**Función:** Añaden obstáculos al recorrido mientras Mochi escapa de la aspiradora.

## NPC

### Copo y Trufa

**Función:** Hermanos menores de Mochi y motor emocional de la aventura.

**Ubicación:** Introducción narrativa en el bosque; no participan en el recorrido jugable actual.

**Interacción:** Se presentan junto a Mochi antes de su captura. Su vínculo explica por qué Mochi quiere regresar al bosque.

### Leo y su familia

**Función:** Personajes humanos de la historia, principalmente fuera de cámara.

**Interacción:** Leo captura a Mochi y sus bromas originan trampas en la habitación. Sus padres buscan al ratón que recorre la casa, lo que explica la programación de la aspiradora y las ratoneras.

> **Navegación:** [[00 - Índice]] · ← [[02 - Niveles]] · [[04 - Objetos y Coleccionables]] →
