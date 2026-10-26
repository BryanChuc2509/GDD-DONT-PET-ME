# Dirección de Arte

## Descripción de la sección

Define la identidad visual del videojuego y las reglas que deben seguir los recursos gráficos.

## Identidad visual

**Estilo: Un cartoon 3D estilizado, de pocos polígonos y con texturas pintadas a mano. Buscamos formas simples y colores limpios en vez de realismo, porque así los peligros se leen de un vistazo, Blender se vuelve manejable para un equipo chico y el juego corre a 60 FPS en laptops de gama media. Con esto queda resuelta la duda del Roadmap entre “low-poly o stylized”  *(propuesto)* .**

**Referencias: Remy de *Ratatouille* por su carisma, los cortos de Chuck Jones por la elasticidad y las miradas a cámara, y Sid de *Toy Story* para la silueta de Leo: un niño travieso, no un villano. *Super Mario 64* nos sirve para pensar la lectura de las plataformas. Sugiero sumar  *Tom y Jerry* , que ya cuenta la casa desde el punto de vista de un roedor.**

**Sensación buscada: El jugador debe sentirse pequeño, ágil y astuto, y reírse, pero sin bajar la guardia: en cualquier momento algo puede aplastar a Mochi. Por eso el arte primero hace gracia y luego avisa del peligro, nunca al revés.**

**Nivel de realismo: El estilo es caricaturesco, pero la escala va en serio. Un libro es un monolito, una taza es una torre y un cable es un puente. Ahí está el corazón del Pilar 1.**

**Formas predominantes:**

| Forma                 | Dónde aparece                               | Qué transmite                            |
| --------------------- | -------------------------------------------- | ----------------------------------------- |
| Redondeada y blanda   | Mochi, Copo, Trufas, Semilla.                | Algo seguro.                              |
| Rectangular y rígida | Muebles, libros, laptop y puertas.           | El mundo humano.                          |
| Puntiaguda            | Chinchetas, lápices, utensilios, ratoneras. | Peligro                                   |
| Circular y plana      | Aspiradora inteligente.                      | Una máquina simpatica que te puede matar |

**Iluminación: Cálida y suave en el bosque, que es el hogar. Dentro de la casa se vuelve más artificial y contrastada. Además de ambientar, la luz hace de guía: ilumina el camino que el jugador debería seguir. El detalle de cada zona está en [[03 - Entornos]].**

**Materiales: La base es mate y pintada a mano, con pocos materiales distintos para cuidar el rendimiento. Madera, tela, papel y plástico llevan color plano con algo de ruido pintado. El metal (clips, pinzas, tachuelas, la llave) sí brilla, y eso también es una pista de juego: lo metálico suele ser un anclaje del hilo. Los líquidos son saturados y reflejantes, con chispas cuando son peligrosos, y las pantallas son emisivas para que el “falso bosque” del monitor atraiga la mirada. Los shaders los definirá la sección [[02 - Motor y Herramientas]], que todavía está vacía.**

## Paleta de color

Los códigos hex son un punto de partida  *(propuesto)* ; habrá que ajustarlos con la luz real de Unity.

**Colores principales:**

| Color            | Hex     | Uso                                                      |
| ---------------- | ------- | -------------------------------------------------------- |
| Canela Mochi     | #C98B4E | Pelaje. Debe ser lo primero que se vea en cada escena.   |
| Crema            | #F7ECD9 | Vientre y mejillas de Mochi, pelaje de Copo.             |
| Verde Bosque     | #5E9E5A | Prólogo, final, menú y la falsa luz verde del monitor. |
| Amarillo Semilla | #F2C94C | Semillas y recompensas.                                  |

**Colores secundarios:**

| Color          | Hex     | Uso                         |
| -------------- | ------- | --------------------------- |
| Madera cálida | #B07A4A | Jaula, escritorio y muebles |
| Azul monitor   | #5AA9E6 | Escritorio y pantallas      |
| Gris pasillo   | #9AA3AD | Pasillo y baldosas          |
| Naranja cocina | #E8803A | Cocina y estufa             |

**Colores para información jugable:**

| Significado          | Color              | Cómo se usa                             |
| -------------------- | ------------------ | ---------------------------------------- |
| Se puede interactuar | Dorado #FFD23F    | Destello e ícono al acercarse           |
| Anclaje del hilo     | Plateado  #C9D1D9 | Pinzas, tachuelas y salientes rígidos   |
| Peligro eléctrico   | Cian #28E0E8      | Con chispas, en charcos y cables pelados |
| Checkpoint           | Azul agua #4DB6E8 | El bebedero                              |

## Reglas visuales

1. **Todo gigante, pero legible.** La escala exagerada no puede esconder el camino. Si una plataforma sirve, debe distinguirse del fondo; no queremos saltos a ciegas.
2. **Un mismo lenguaje en todos los niveles.** Las pinzas de papel siempre piden hilo y los interruptores rojos siempre piden semilla. Nunca cambian de significado.
3. **El peligro avisa antes de matar.** Como la muerte es instantánea, cada amenaza debe anunciarse con forma, color, movimiento o sonido. Ninguna muerte puede llegar sin señal.
4. **Mochi destaca.** Cálido y saturado contra fondos más neutros o fríos, con luz de contorno si hace falta.
5. **El humor vive en los detalles.** Post-its irónicos, Windows XP haciéndose pasar por bosque, marcas de quemaduras, el desorden de Leo. Todo texto del entorno se localiza.
6. **Cómico, nunca gráfico.** Las muertes son exageradas y de caricatura, sin sangre.
7. **Cuidar los 60 FPS.** Cada decisión de arte tiene que respetar ese presupuesto (30 como mínimo).

## Referencias

Añade enlaces o imágenes dentro de la carpeta del proyecto.

> **Navegación:** [[00 - Índice]] · ← [[05 - Misiones y Desafíos]] · [[02 - Personajes y Animación]] →
