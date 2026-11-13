# Niveles

## Descripción de la sección

Documenta el objetivo, el orden de las zonas y los desafíos de cada nivel jugable. El contenido sigue la progresión indicada para el tutorial de la jaula, la habitación y el pasillo.

## Tutorial (Nivel 0) — La jaula

**Objetivo principal:** Aprender las acciones básicas, escapar de la jaula y alcanzar la meta del tutorial para pasar al Nivel 1.

**Objetivos secundarios:** Recoger las semillas, que marcan la ruta, y explorar rutas opcionales.

**Mecánicas introducidas:** Movimiento, salto, sprint, planeo y escalada en superficies designadas.

**Desarrollo:** Mochi despierta en la jaula después de la captura. Las indicaciones del tutorial presentan cada acción de forma gradual mientras busca la forma de salir. Después de escapar, el tutorial incluye un laberinto de tubos con un botón que abre la salida y un primer tramo del escritorio; termina al alcanzar la meta, la tecla Enter del teclado.

**Enemigos y obstáculos:** Bichos que hay que esquivar, café caliente, plataformas que se caen y monedas trampa.

**Puntos de control:** Repartidos entre la jaula, las repisas y el escritorio.

**Condición de entrada:** Termina la introducción narrativa y Mochi despierta en la jaula.

**Condición de salida:** Mochi alcanza la meta del tutorial y pasa al Nivel 1.

**Orden del recorrido:**

```text
Jaula → escape → laberinto de tubos y escritorio → meta del tutorial → Nivel 1
```

## Nivel 1 — La habitación de Leo

**Objetivo principal:** Recorrer la habitación y superar sus desafíos hasta abrir el paso al pasillo.

**Objetivos secundarios:** Recoger las semillas, que marcan la ruta, y explorar rutas opcionales.

**Mecánicas utilizadas:** Movimiento, salto, sprint y planeo con combustible compartido, escalada en superficies designadas, interacción contextual con objetos y puzzle de memoria resuelto saltando sobre baldosas.

### Zona 1: Escritorio

Mochi avanza por los muebles y objetos cotidianos a escala colosal. Puede empujar objetos para abrirse camino y encontrar las pilas requeridas en el desafío siguiente.

### Zona 2: Minijefe de las hormigas

El minijefe de las hormigas bloquea el avance. Mochi debe encontrar y colocar las pilas en el ventilador para activarlo y superar el encuentro. La solución es usar el ventilador.

Un hormiguero de 6 a 9 hormigas, que se mueven como los fantasmas de Pac-Man, protege a la hormiga reina. Hay 3 pilas repartidas por la zona; al colocar la tercera en el ventilador, este aspira a todas las hormigas durante 3 segundos y se cae, dejando el camino libre. Una hormiga aturde a Mochi y le hace soltar la pila; 4 a la vez lo matan.

### Zona 3: Libros colgantes

Mochi cruza los libros y las superficies escalables del recorrido para alcanzar la siguiente sección de la habitación.

### Zona 4: Estantería de la araña

La araña lanzadora echa a rodar bolas de telaraña por los estantes, como los barriles de Donkey Kong, y lanza otras directamente a Mochi. Las bolas derriban y aturden a Mochi, así que debe esquivarlas mientras sube la estantería por los hilos que cuelgan de los estantes.

### Zona 5: Sala de memoria

Al entrar, una pared se levanta detrás de Mochi y lo encierra en una sala con 16 baldosas en el suelo (4×4). El reto tiene 5 rondas y en cada una:

1. Una cuenta atrás de 3 segundos anuncia la ronda ("Ronda x/5: observa").
2. Las baldosas de la secuencia se iluminan una por una, todas del mismo color, y cada baldosa suena con su propia nota musical.
3. Mochi repite la secuencia cayendo con un salto sobre cada baldosa, en el mismo orden ("¡Tu turno! Salta sobre las baldosas en orden"). Caminar sobre una baldosa no cuenta.

**Dificultad:**

- La secuencia tiene 3 baldosas en la primera ronda, 4 en la segunda y 5 de la tercera a la quinta. Con 5 baldosas, la secuencia forma un camino de baldosas vecinas y no repite ninguna.
- Cada baldosa de la muestra se ilumina 0.9 segundos en la primera ronda y 0.7 en la última.
- Para cada baldosa hay un tiempo límite, con cuenta atrás en pantalla: 5 segundos en la primera ronda y 3 en la última. El tiempo vuelve a empezar después de cada acierto.

**Fallo:** Si Mochi cae en una baldosa equivocada o se acaba el tiempo, todas las baldosas se marcan en el color de peligro y las paredes se cierran y lo aplastan ("¡Aplastado!"). Mochi reaparece en el checkpoint de la sala y el reto vuelve a empezar desde la ronda 1.

**Éxito:** Al superar las 5 rondas, las baldosas se marcan como correctas ("¡Memoria superada!"), la pared de salida se hunde y el objetivo cambia a "Llega a la meta". La meta del nivel se aparta cuando Mochi se acerca (es una de las trampas de Leo).

**Enemigos y obstáculos del nivel:**

- Araña de rincón, amenaza de contacto.
- Ciempiés (Walker), que camina de un lado a otro sobre repisas y estantes.
- Minijefe de las hormigas en el escritorio.
- Araña lanzadora de bolas de telaraña en la estantería.
- Libros, plataformas y otros mecanismos trampa.

**Coleccionables y objetos clave:** Semillas que guían el recorrido; pilas para activar el ventilador.

**Puntos de control:** 16 checkpoints repartidos por la habitación, además de un checkpoint falso.

**Condición de entrada:** Mochi completa el tutorial de la jaula (Nivel 0).

**Condición de salida:** Mochi supera la sala de memoria y alcanza la meta del nivel, que da paso al pasillo.

**Orden del recorrido:**

```text
Escritorio → Minijefe de las hormigas
→ Libros colgantes → Estantería de la araña
→ Sala de memoria → Meta → Pasillo
```

## Nivel 2 — El pasillo

**Objetivo principal:** Llegar a la sala de estar antes que la aspiradora, cruzando las trampas del pasillo.

**Mecánicas introducidas:** Huir de una persecución activa, recorridos guiados (tubo de cartón y tirolesa) y trepar por objetos del pasillo (abrigo, cortina, bolsa y barrera).

**Mecánicas utilizadas:** Movimiento, salto, sprint y planeo (gastan el mismo combustible) y escalada.

**Enemigos y obstáculos:**

- Aspiradora inteligente, programada por los padres de Leo para cazar al ratón que ronda la casa; confunde a Mochi con su objetivo. Despierta cuando Mochi entra en su zona y lo persigue por cualquier terreno: sube escalones, avisa parpadeando antes de embestir y salta si Mochi está más alto. Si se atasca o se queda muy atrás, "toma un atajo" y reaparece detrás de él. Si lo alcanza, Mochi muere ("¡Aspirado!").
- 42 ratoneras, algunas ocultas: al pisarlas, Mochi sale volando y luego muere ("¡Trampa de ratón!").
- Escobas que caen; antes de caer, su sombra crece en el suelo ("¡Escobazo!").
- Cables electrificados en el suelo ("¡Calambre! Salta los cables del suelo").
- Piezas de Lego ("¡Pisaste un Lego!").
- Una rejilla y tablas falsas por donde Mochi cae ("¡Te caíste por la rejilla!", "No te fíes de las tablas...").
- Tachuelas que salen del suelo ("¡Pinchos!").
- Charco del gato, que frena a Mochi.
- Checkpoints falsos y semillas trampa.

**Coleccionables:** 16 semillas que guían el recorrido.

**Puntos de control:** 4 checkpoints entre los tramos de mayor riesgo, además de 2 checkpoints falsos.

**Condición de entrada:** Mochi completa la habitación (Nivel 1).

**Condición de salida:** Mochi llega a la sala de estar antes que la aspiradora. Es el final del recorrido jugable.

**Orden del recorrido:**

```text
Inicio → Alfombra → Tubo de cartón, zapatero y tirolesa
→ Bloques y rejilla → Tablas falsas → Pasillo de trampas
→ Puerta (clímax de la persecución) → Sala de estar
```

## Criterios de calidad

- El recorrido tiene tres niveles: el tutorial de la jaula (Nivel 0), la habitación (Nivel 1) y el pasillo (Nivel 2).
- El orden de zonas en la habitación se mantiene: escritorio, minijefe de las hormigas, libros colgantes, estantería de la araña y memorama.
- En la estantería, el jugador esquiva las bolas de telaraña y sube por los hilos que cuelgan de los estantes.
- La sala de memoria muestra secuencias de baldosas iluminadas y se resuelve cayendo con un salto sobre las mismas baldosas, en el mismo orden.
- Las semillas guían el recorrido; no son munición.
- El ciempiés (Walker) camina de un lado a otro y da media vuelta en paredes y bordes; aparece en el tutorial y en el Nivel 1.

> **Navegación:** [[00 - Índice]] · ← [[01 - Estructura del Contenido]] · [[03 - Enemigos y NPC]] →
