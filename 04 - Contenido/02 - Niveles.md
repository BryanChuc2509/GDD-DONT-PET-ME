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

El minijefe de las hormigas bloquea el avance. Mochi debe encontrar y colocar las pilas en el ventilador para activarlo y superar el encuentro. La solución definida es usar el ventilador; no se asumen ataques ni una forma de derrotarlo mediante saltos.

La apariencia y los ataques del minijefe, la cantidad y ubicación de las pilas y el efecto exacto del ventilador quedan por definir.

### Zona 3: Libros colgantes

Mochi cruza los libros y las superficies escalables del recorrido para alcanzar la siguiente sección de la habitación.

### Zona 4: Estantería y pelotas de tenis

Un personaje lanza pelotas de tenis mientras Mochi asciende por la estantería. Debe encontrar y alcanzar a tiempo los huecos de la estantería y meterse en ellos para evitar los impactos, y luego continuar subiendo. La solución no consiste en saltar por encima de las pelotas.

La identidad y el diseño del personaje están por definir. Donkey Kong es solo una referencia para la idea de lanzar objetos; aquí se usan pelotas de tenis, no barriles.

### Zona 5: Memorama de baldosas

Un personaje todavía sin identificar presenta una secuencia: ciertos cuadros del suelo se iluminan en distintos colores y en un orden determinado. Mochi debe memorizar qué cuadros se iluminan y en qué orden; después, salta sobre esos mismos cuadros en la secuencia correcta para activar el mecanismo y abrir el paso al pasillo.

La cantidad de cuadros, la longitud y velocidad de la secuencia, los intentos permitidos y la identidad del personaje quedan por definir.

**Enemigos y obstáculos del nivel:**

- Araña de rincón, amenaza de contacto.
- Walker, oruga de peluche blanca que patrulla rutas fijas y aparece de forma dispersa por el mapa. Sus ubicaciones están por definir.
- Minijefe de las hormigas en el escritorio.
- Personaje aún sin identificar que lanza pelotas de tenis en la estantería.
- Libros, plataformas y otros mecanismos trampa.

**Coleccionables y objetos clave:** Semillas que guían el recorrido; pilas para activar el ventilador.

**Puntos de control:** Ubicaciones por definir en la habitación.

**Condición de entrada:** Mochi completa el tutorial de la jaula (Nivel 0).

**Condición de salida:** Mochi resuelve el memorama y abre el acceso al pasillo.

**Orden del recorrido:**

```text
Escritorio → Minijefe de las hormigas
→ Libros colgantes → Estantería con pelotas de tenis
→ Memorama de baldosas → Pasillo
```

## Nivel 2 — El pasillo

**Objetivo principal:** Cruzar el pasillo, escapar de la aspiradora y sus trampas, y llegar a la salida del nivel.

**Mecánicas introducidas:** Leer una persecución activa y encontrar refugio o rutas seguras entre los peligros.

**Mecánicas utilizadas:** Movimiento, salto, sprint y planeo. El sprint y el planeo gastan el mismo combustible.

**Enemigos y obstáculos:**

- Aspiradora inteligente, programada por los padres de Leo para perseguir al ratón que ronda la casa; confunde a Mochi con su objetivo.
- Ratoneras colocadas para atrapar al ratón.
- Escobas que caen y pelotas que ruedan por el pasillo.
- Walker puede aparecer patrullando en puntos dispersos del mapa.

**Coleccionables:** Semillas que guían el recorrido. La fotografía familiar bajo el mueble recibidor queda como coleccionable opcional propuesto, pendiente de confirmación.

**Puntos de control:** Ubicaciones por definir entre los tramos de mayor riesgo.

**Condición de entrada:** Mochi completa la habitación y abre el paso al pasillo.

**Condición de salida:** Mochi supera la persecución y alcanza la salida del pasillo. La sala y el regreso al bosque no son niveles adicionales de este recorrido.

**Orden del recorrido:**

```text
Entrada al pasillo → persecución de la aspiradora
→ ratoneras y obstáculos móviles → salida del nivel
```

## Criterios de calidad

- El recorrido tiene tres niveles: el tutorial de la jaula (Nivel 0), la habitación (Nivel 1) y el pasillo (Nivel 2).
- El orden de zonas en la habitación se mantiene: escritorio, minijefe de las hormigas, libros colgantes, estantería con pelotas de tenis y memorama.
- El jugador se refugia en huecos de la estantería para evitar las pelotas; no se le indica saltar por encima.
- El memorama enseña una secuencia de cuadros iluminados y se resuelve saltando los mismos cuadros en el mismo orden.
- Las semillas guían el recorrido; no son munición.
- Walker es una oruga de peluche blanca con patrullas fijas dispersas por el mapa.

> **Navegación:** [[00 - Índice]] · ← [[01 - Estructura del Contenido]] · [[03 - Enemigos y NPC]] →
