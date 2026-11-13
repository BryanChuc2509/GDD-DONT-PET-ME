# Interfaz Visual

## Descripción de la sección

Documenta la información que el juego muestra al jugador y las reglas visuales de la interfaz.

## HUD

El HUD es un solo prefab (`HUD.prefab`) que el `LevelManager` crea al cargar cada nivel. Está diseñado a 1920×1080, escala con la pantalla y se reparte en las esquinas para dejar libre el centro, donde está Mochi.

| Elemento | Posición | Qué muestra | Comportamiento |
| --- | --- | --- | --- |
| Contador de semillas | Arriba a la izquierda | Icono de semilla y cápsula con `recogidas/total` del nivel actual | El icono da un pequeño salto al recoger una semilla. El total se cuenta al cargar el nivel y el contador empieza en 0 en cada nivel. |
| Contador de muertes | Arriba a la izquierda, junto a las semillas | Calavera y `×N` | Suma 1 cada vez que Mochi muere y reaparece. Se reinicia al pasar a otro nivel. |
| Objetivo | Debajo de los contadores | Botón con una bandera | Cuando cambia el objetivo, una tarjeta sale de la bandera con el título **NUEVO OBJETIVO** y el texto, se queda 3 s y vuelve a encogerse en la bandera. Con `Tab` o al pulsar la bandera se muestra otra vez como **OBJETIVO ACTUAL**. Al completar el nivel muestra **¡OBJETIVO CUMPLIDO!** con el mensaje del nivel. Los avances pequeños, como "Lleva las pilas al ventilador (2/3)", cambian el texto sin volver a anunciarlo. |
| Barra de estamina | Abajo a la izquierda | Icono de rayo y barra verde | El relleno se encoge de derecha a izquierda al gastar. Si se agota, el relleno se atenúa y el rayo parpadea hasta que se recupera. |
| Botón de pausa | Arriba a la derecha | Botón redondo de pausa | Abre el menú de pausa, igual que `Esc`. |
| Avisos | Centro, en la parte alta de la pantalla | Textos cortos con contorno: "Checkpoint", "¡Chof!", "¡Ventilador encendido!", "¡Tu turno!"… | Aparecen unos 2.5 s y se desvanecen solos. |
| Cuenta atrás | Centro, encima de los avisos | Segundos restantes con un decimal | Solo durante el turno del jugador en el memorama. |

**Indicadores contextuales** (se colocan en cada nivel, fuera del prefab del HUD):

- **Panel de tutorial:** instrucciones en la parte inferior, como un subtítulo, mientras Mochi está en la zona y 1.5 s después de salir. Puede fijar un nuevo objetivo. Solo se ve un panel a la vez.
- **Cartel de zona difícil:** aviso llamativo en el tercio inferior, encima del panel de tutorial, durante 4 s al entrar en la zona (por ejemplo, al llegar al hormiguero de la reina o a la sala de memoria).
- **Marcador de entrega:** mientras Mochi carga una pila, un marcador rebota sobre el ventilador con el texto "Lleva la pila al ventilador". Si el destino no se ve, una flecha en el borde de la pantalla apunta hacia él.
- **Título de apertura:** en el tutorial, el plano inicial muestra "La prisión de Mochi" y "Pulsa cualquier tecla para saltar".

El HUD no muestra vida, munición, inventario ni mapa: Mochi muere de un solo golpe y no lleva objetos aparte de la pila que carga.

## Jerarquía visual

1. **Mochi y la escena:** el HUD ocupa las esquinas y deja libre el centro.
2. **Avisos y cuenta atrás:** lo que está pasando ahora (checkpoint, trampa, turno del memorama), en el centro.
3. **Objetivo:** se anuncia grande al cambiar y después se reduce a la bandera.
4. **Estamina:** abajo a la izquierda, para consultarla durante saltos y sprints.
5. **Contadores de semillas y muertes:** información de consulta en la esquina superior izquierda.

## Estados

- **Normal:** contadores, bandera del objetivo, barra de estamina y botón de pausa visibles.
- **Recompensa:** el icono del contador de semillas salta al recoger una.
- **Advertencia:** estamina agotada (relleno atenuado y rayo parpadeando) y cuenta atrás del memorama.
- **Éxito:** aviso "Checkpoint" con sonido y festejo de Mochi; tarjeta **¡OBJETIVO CUMPLIDO!** al terminar el nivel.
- **Muerte:** ventana **HAS MUERTO** sobre la escena (ver [[02 - UI y Menús]]).
- **Pausa:** ventana **MENÚ** sobre la escena, con el juego detenido.

## Convenciones

**Tipografía:** Fredoka Bold (TextMeshPro) en toda la interfaz. Los avisos del centro llevan contorno para leerse sobre cualquier fondo.

**Iconografía:** Ilustrada, con contorno marrón: semilla, calavera, bandera, rayo, pausa, play, engrane (ajustes), salida, volumen, nota musical, ondas de sonido, controles y reinicio.

**Colores:** Marrón #582D14 para textos principales, marrón suave #805638 para textos secundarios, crema #FFF8E8 para los avisos y papel #F4E2CC en las ventanas. El botón principal es amarillo y los secundarios son crema con borde marrón. Detrás de las ventanas, la escena se oscurece con un velo marrón al 60%.

**Ventanas:** Marco de madera con una cinta de título ("MENÚ", "AJUSTES", "CONTROLES"), botón redondo de cerrar con una X y hojas decorativas en las esquinas.

**Tamaños mínimos:** Resolución de referencia 1920×1080. Textos de ventanas de 30 a 58 px, avisos de 54 px, cuenta atrás de 72 px e iconos del HUD de 93 a 117 px.

**Contraste:** Texto marrón oscuro sobre papel claro en ventanas y botones; avisos crema con contorno sobre la escena.

**Animaciones:** Las ventanas aparecen con un pequeño rebote (0.3 s) y se cierran al instante. La tarjeta del objetivo sale de la bandera y vuelve a ella. Los contadores saltan al cambiar. Los botones crecen al pasar el ratón o seleccionarlos y suenan al pasar y al pulsar.

**Navegación:** Ratón y teclado. Al abrir una ventana queda seleccionado su botón principal.

## Pantallas

- Menú principal
- Introducción (video con aviso para saltar)
- HUD de juego
- Pausa
- Ajustes
- Controles
- Ventana de muerte
- Confirmación de nueva partida

El detalle de cada pantalla está en [[02 - UI y Menús]]. El final de cada nivel se anuncia en la tarjeta del objetivo.


> **Navegación:** [[00 - Índice]] · ← [[03 - Entornos]] · [[05 - Audio y Música]] →
