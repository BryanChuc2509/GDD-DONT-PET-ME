
# Audio y Música

## Descripción de la sección

Define la identidad sonora y cómo el audio comunica información al jugador.

La identidad sonora de Don't Pet Me es caricaturesca y tierna: Mochi, el hámster, se expresa con sonidos cortos y graciosos y el mundo responde con golpes, rebotes y chirridos exagerados. El audio cumple tres funciones:

1. **Dar personalidad a Mochi**: vocalizaciones no verbales que suenan solas mientras juega.
2. **Avisar del peligro antes de que llegue**: la escoba suena antes de caer, la aspiradora da una alerta al detectar al jugador, las plataformas tiemblan antes de desplomarse y los cables pelados zumban.
3. **Confirmar el progreso y las trampas**: monedas, checkpoints y aciertos tienen su sonido, y las trampas como la moneda trampay el checkpoint falso tienen uno propio para que el jugador sepa que lo engañaron.

## Música

**Temas principales:** el juego tiene 4 pistas en `Audio/Music/`, una por escena:

| Pista                    | Escena(s)      | Momento                           |
| ------------------------ | -------------- | --------------------------------- |
| `DontPetMe_Inicio`     | MainMenu       | Menú principal                   |
| `DontPetMe_Engranajes` | Level0_jaula   | Nivel 0: la jaula / tutorial      |
| `DontPetMe_Aventura`   | Level1_Greybox | Nivel 1: escritorio y estantería |
| `DontPetMe_Run`        | Level2_Pasillo | Nivel 2: el pasillo               |

En la **cinemática de introducción** (escena Intro) se apaga la música y suena el audio propio del video.

**Música dinámica:** No.

Cada escena tiene una sola pista en bucle que no cambia según lo que pase en el juego. Funciona así:

- Un `MusicManager` persistente con dos fuentes de audio que hacen crossfade de 1.5 s al cambiar de escena.
- Si la escena nueva usa la misma pista que la anterior, la música sigue sin cortarse (por ejemplo, del menú a "Nivel completado").
- La música es 2D y suena a un volumen base de **0.35**, multiplicado por el ajuste de Música del jugador.

## Efectos de sonido

Todos los efectos del nivel pasan por un catálogo central (`SfxCatalog`) y se cargan desde `Audio/SFX/Nivel/Resources/SfxNivel/`. Los de Mochi están en `Audio/SFX/Hamster/`. Muchos tienen variación de tono aleatoria para que no suenen repetitivos.

### Mochi (jugador)

| Evento             | Sonido                                                                | Propósito                                                                                         |
| ------------------ | --------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Correr             | `correr_puntitas_loop` (bucle)                                      | Pasitos que suben y bajan suavemente según la velocidad; se callan al detenerse o en el aire      |
| Saltar             | `salto_boing` o `salto_silbato` (al azar)                         | Confirmar el salto con un toque cómico                                                            |
| Aterrizar          | `aterrizaje_pomf`                                                   | Confirmar que tocó el piso (solo tras 0.15 s o más en el aire, para evitar sonidos en escalones) |
| Voces espontáneas | 7 voces: adorable, ay, curioso, enojado tierno, feliz, risita, triste | Darle personalidad: suena una al azar cada 4–9 s, sin repetir la anterior                         |
| Lanzar hilo        | `hilo_lanzar`                                                       | Confirmar el disparo del gancho                                                                    |
| Enganchar hilo     | `hilo_engancha`                                                     | Avisar que el gancho se agarró                                                                    |
| Columpiarse        | `hilo_columpio`                                                     | Dar sensación de impulso en el balanceo                                                           |
| Soltar hilo        | `hilo_soltar`                                                       | Confirmar que se soltó                                                                            |
| Recoger objeto     | `recoger_objeto`                                                    | Confirmar que lo está cargando                                                                    |
| Soltar objeto      | `soltar_objeto`                                                     | Confirmar que lo soltó                                                                            |
| Pisar a un enemigo | `rebote_objeto_2`                                                   | Recompensar el pisotón                                                                            |

### Progreso y trampas

| Evento             | Sonido                          | Propósito                                                                     |
| ------------------ | ------------------------------- | ------------------------------------------------------------------------------ |
| Moneda             | `moneda`                      | Recompensa por recoger (volumen bajo porque es muy frecuente)                  |
| Moneda trampa      | `moneda_trampa`               | Avisar que era una trampa y que el jugador sale disparado                      |
| Checkpoint         | `checkpoint`                  | Confirmar que se guardó el progreso                                           |
| Checkpoint falso   | `checkpoint_falso`            | Revelar el engaño                                                             |
| Nivel completado   | `checkpoint` (más fuerte)    | Celebrar que se llegó a la meta                                               |
| Pantalla de muerte | `muerte_ventana_2`            | Acompañar la ventana de derrota                                               |
| Aplastado          | `aplastado` / `aplastado_2` | Muerte por aplastamiento (trampas del Nivel 1 y paredes de la sala de memoria) |

### Entorno y trampas troll

| Evento                              | Sonido                                | Propósito                                                           |
| ----------------------------------- | ------------------------------------- | -------------------------------------------------------------------- |
| Ventilador (cerca)                  | `viento_ventilador_loop` (bucle 3D) | Señalar dónde está la corriente de aire                           |
| Lanzado por viento / resorte        | `viento_lanzado`                    | Confirmar el impulso                                                 |
| Trampolín / resorte                | `rebote_objeto`                     | Remarcar el rebote                                                   |
| Bloque oculto                       | `bonk`                              | Golpe cómico al chocar con un bloque invisible                      |
| Objeto que huye                     | `hilo_columpio` (whoosh)            | Remarcar que la plataforma se escapó                                |
| Plataforma o trampa a punto de caer | `objeto_tiembla`                    | **Avisar** del peligro antes de la caída                      |
| Caída de objeto                    | `objeto_cae` + `golpe_suelo`      | Impacto de trampas que caen o se vuelcan y del ventilador que se cae |
| Péndulo                            | `balanceo_crujido_1` / `_2`       | Crujido al balancearse                                               |
| Noria                               | `noria_loop` (bucle 3D)             | Ubicar la noria en el espacio                                        |
| Interruptor                         | `ui_clic` (fuerte)                  | Confirmar que se activó                                             |
| Charco de café electrificado       | `agua_electrica_loop` (bucle 3D)    | Avisar del peligro eléctrico (Nivel 0)                              |

### Enemigos

| Evento                    | Sonido                                 | Propósito                                                                       |
| ------------------------- | -------------------------------------- | -------------------------------------------------------------------------------- |
| Araña camina             | `arana_pasos_loop` (bucle 3D)        | Su volumen sube con la velocidad de la araña: indica qué tan rápido se acerca |
| Araña ataca              | `arana_chillido`                     | Avisar del ataque                                                                |
| Araña lanza telaraña    | `telarana_lanzar`                    | Avisar que viene un proyectil                                                    |
| Bola de telaraña rodando | `telarana_rodando_loop` (bucle 3D)   | Ubicar la bola que rueda                                                         |
| Golpe de telaraña        | `telarana_pegajoso`                  | Confirmar que pegó                                                              |
| Hormigas marchan          | `hormigas_marcha_loop` (bucle 3D)    | Ubicar a la colonia y a las patrullas                                            |
| Hormiga grita             | `hormiga_chillido`                   | Avisar que detectaron o tocaron a Mochi                                          |
| Aturdido                  | `aturdido`                           | Indicar que el enjambre lo aturdió                                              |
| Aspiradora: motor         | `aspiradora_motor_loop` (bucle 3D)   | Ubicar a la aspiradora robot en el pasillo                                       |
| Aspiradora: alerta        | `aspiradora_alerta`                  | **Avisar** que detectó al jugador                                         |
| Aspiradora: succión      | `aspiradora_succion_loop` (bucle 3D) | Remarcar la zona de succión                                                     |
| Aspiradora atrapa         | `aspiradora_atrapa`                  | Muerte o captura                                                                 |

### Pasillo (Nivel 2)

| Evento                    | Sonido                                                                | Propósito                              |
| ------------------------- | --------------------------------------------------------------------- | --------------------------------------- |
| Escoba a punto de caer    | `escoba_aviso` (3D, en el punto de impacto)                         | **Avisar** dónde va a caer       |
| Escoba golpea             | `escoba_golpe`                                                      | Impacto                                 |
| Ratonera                  | `trampa_raton_ay`                                                   | Castigo cómico al pisarla              |
| Cable pelado (cerca)      | `cable_zumbido_loop` (bucle 3D, 12 cables)                          | **Avisar** del peligro eléctrico |
| Calambre                  | `cable_calambre`                                                    | Daño por electricidad                  |
| Entrar / salir del túnel | `tunel_entrar` / `tunel_salir`                                    | Marcar la transición                   |
| Rodar en el túnel        | `tunel_rodar_loop` (2D)                                             | Lo que oye Mochi dentro del túnel      |
| Tirolesa                  | `tirolesa_engancha` → `tirolesa_deslizar` → `tirolesa_soltar` | Acompañar el recorrido completo        |

### Sala de memoria (tipo Simón, Nivel 1)

| Evento                       | Sonido                                     | Propósito                                                                                 |
| ---------------------------- | ------------------------------------------ | ------------------------------------------------------------------------------------------ |
| La sala muestra la secuencia | `simon_pc_1` … `simon_pc_6`           | **Cada baldosa tiene su propia nota**, así la secuencia se puede memorizar de oído |
| El jugador pisa una baldosa  | `simon_jugador_1` … `simon_jugador_6` | Misma nota que la baldosa, con otro timbre                                                 |
| Cuenta regresiva             | `simon_tick_cuenta`                      | Marcar el tiempo                                                                           |
| Acierto                      | `simon_correcto`                         | Confirmar que la ronda salió bien                                                         |
| Error                        | `simon_error`                            | Avisar del fallo                                                                           |
| Las paredes aprietan         | `simon_paredes_aprietan`                 | Aumentar la tensión del castigo                                                           |

### Interfaz

| Evento                          | Sonido                    | Propósito                                            |
| ------------------------------- | ------------------------- | ----------------------------------------------------- |
| Pasar el ratón sobre un botón | `ui_hover`              | Retroalimentación de la selección                   |
| Clic en un botón               | `ui_clic`               | Confirmar la acción                                  |
| Mover el slider de Efectos      | `moneda` (vista previa) | Que el jugador escuche el volumen que está eligiendo |

## Audio espacial

¿Se utilizará audio posicional? Sí, de forma mixta.

- **2D (sin posición):** la música, la interfaz, todo lo que hace Mochi, los pasos, saltos, voces, hilo, recoger o soltar y lo que le pasa a él, las monedas, checkpoints y golpes recibidos. La cámara siempre sigue al hámster, así que estos sonidos no necesitan posición.
- **3D (posicional):** los peligros y objetos del mundo: arañas, telarañas, trampas que caen o se vuelcan, péndulos, trampolines, bloques ocultos, la escoba y todos los bucles ambientales como el ventilador, noria, charco eléctrico, cables, hormigas y aspiradora.
- **Atenuación lineal:** se oyen a volumen completo hasta 12 m, que es la distancia aproximada de la cámara al hámster y se apagan del todo a los 35 m. El efecto Doppler está desactivado.
- Los sonidos sueltos usan un grupo de 10 fuentes 2D y 12 fuentes 3D que se reutilizan y persisten entre escenas.

## Voz

**Narración:** no hay narración dentro del juego. La cinemática de introducción usa el audio de su propio video, al que se le aplica el volumen General del jugador.

**Diálogos hablados:** no hay. Mochi solo hace vocalizaciones no verbales con 7 emociones, adorable, ay, curioso, enojado tierno, feliz, risita y triste. Suenan al azar cada 4–9 segundos, con al menos 0.4 s entre voces para que no se encimen y con variación de tono.

**Idiomas:** el audio no depende de ningún idioma, porque no hay palabras habladas. Los textos de la interfaz están en español y el proyecto no usa ningún sistema de localización.

## Mezcla

**Controles del jugador.** en el menú de pausa y en Ajustes, se guardan con PlayerPrefs y empiezan al 100 %:

- **General:** controla el volumen de todo el juego y también el de la cinemática.
- **Música:** multiplica el volumen base de la música (0.35).
- **Efectos:** multiplica el volumen de todos los efectos, incluidas las voces de Mochi. Al moverlo suena una moneda como vista previa.
- Hay un botón para restablecer los tres volúmenes al máximo.

**Niveles de volumen del catálogo de efectos:**

| Nivel            | Valor | Ejemplos                                                                            |
| ---------------- | ----- | ----------------------------------------------------------------------------------- |
| Bucle silencioso | 0.1   | Pasos de araña, marcha de hormigas, crujido del péndulo                           |
| Suave            | 0.2   | Moneda, hover de la interfaz, aviso de la escoba, zumbido del cable                 |
| Medio            | 0.4   | Checkpoint, clic de la interfaz, temblor, motor de la aspiradora                    |
| Normal           | 0.6   | La mayoría de efectos y los bucles del ventilador y la noria                       |
| Fuerte           | 0.9   | Nivel completado, aplastado, calambre, error del Simón, paredes, aspiradora atrapa |

**Prioridades:** los sonidos que comunican un peligro grave o el resultado de una acción (muerte, error, nivel completado) son los más fuertes. Los que suenan muy seguido (monedas, hover) y los bucles de ambiente son los más bajos, para que no tapen las señales importantes. Los sonidos de Mochi están ajustados muy bajos en cada nivel (saltos y pasos entre 0.007 y 0.05, voces entre 0.08 y 0.12) para que no cansen.

**Comportamiento ante eventos:**

- **Pausa:** los bucles ambientales se pausan y los pasos de Mochi se callan. La música sigue sonando.
- **Cambio de escena:** crossfade de música de 1.5 s.
- **Cinemática:** la música se detiene para dejar sonar el video.
- **Muerte y nivel completado:** tienen su propio efecto, pero la música no cambia ni se baja.
- Los efectos del nivel solo suenan en escenas que los tienen activados (los niveles, el menú y la pantalla final de la demo).
- No se usa un Audio Mixer de Unity. Los volúmenes se calculan por código, aunque los scripts ya tienen espacio para asignar grupos "Music" y "SFX" si se agrega uno más adelante.

> **Navegación:** [[00 - Índice]] · ← [[04 - Interfaz Visual]] · [[01 - UX y Flujo del Jugador]] →
