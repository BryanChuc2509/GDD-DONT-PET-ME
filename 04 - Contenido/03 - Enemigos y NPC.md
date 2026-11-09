# Enemigos y NPC

## Descripción de la sección

Documenta las entidades controladas por el juego y su comportamiento.

## Plantilla de enemigo

### Nombre

Araña de Rincón

**Rol de combate:**  Enemigo básico de patrulla y control de zona.

**Comportamiento:** Patrulla áreas oscuras o rincones del suelo y estantes en trayectos rectos predecibles. No persigue proactivamente al jugador a menos que este entre en su cono de visión directo.

**Resistencia:** Un disparo de semilla la aturde temporalmente; un salto desde arriba la mata.

**Daño:** Muerte instantánea por contacto (reinicio en el último punto de control).

**Defensas:** Ninguna.

**Velocidad:** Lenta

**Rango de detección:** Corto

**Ataques:** Contacto directo / Mordedura al tocar a Mochi.

**Debilidades:** Un disparo de semilla la aturde durante 4 segundos, permitiendo a Mochi pasar junto a ella. Si Mochi cae sobre ella desde arriba, la aplasta y la mata.

**Recompensa:** Al matarla con un salto desde arriba, despeja el paso de forma permanente hacia las semillas de girasol cercanas.

**Estados de IA:**

```text
Vigilar -> Detectar -> Atacar
|
v
Aturdido (por Semilla) -> Recuperar Patrulla
Muerta (por salto desde arriba)
```


### Nombre

Aspiradora Inteligente

**Rol de combate:** Enemigo persistente / Amenaza de persecución ambiental.

**Comportamiento:** Se desplaza por los pasillos y la cocina mapeando el terreno. Al detectar a Mochi, entra en modo de succión y persecución activa. Puede romper o remover pequeños obstáculos del entorno.

**Vida:** Inmune a ataques.

**Daño:** Muerte instantánea (succiona a Mochi si entra en su radio de absorción frontal).

**Defensas:** Carcasa blindada (los disparos de semillas rebotan sin hacerle efecto).

**Velocidad:** Rápida.

**Rango de detección:** Medio.

**Ataques:** Persecución frontal / Succión por flujo de aire en un cono frontal.

**Debilidades:** Poca maniobrabilidad en curvas cerradas. Se le puede hacer chocar contra cajas, zapatos o trampas si Mochi dispara semillas a interruptores o usa esquivas de último segundo.

**Recompensa:** Desbloquea el paso a la siguiente zona al quedar atascada temporalmente tras un choque.

**Estados de IA:**

**Plaintext**

```
Patrullar -> Detectar -> Perseguir -> Atacar (Succionar)
|
v
Perder objetivo / Choque -> Buscar / Desatascar
```


## Plantilla de NPC

Familiares de Mochi

**Función:** Aliados narrativos / Tutorial de memoria emocional.

**Ubicación:** Prólogo (Bosque).

**Interacción:** Aparecen en cinemáticas cortas para recordar la motivación de Mochi de regresar al hogar.

**Diálogos:** No definidos.

**Condiciones:** Se activan al inicio del juego.

**Recompensas / información:** Establecen la meta principal del juego.

> **Navegación:** [[00 - Índice]] · ← [[02 - Niveles]] · [[04 - Objetos y Coleccionables]] →
