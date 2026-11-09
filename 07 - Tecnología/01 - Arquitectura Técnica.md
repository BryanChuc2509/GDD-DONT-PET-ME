# Arquitectura Técnica

## Descripción de la sección

Explica cómo está construido técnicamente el videojuego y cómo se comunican sus componentes.

## Arquitectura

```text
Teclado y ratón
      ↓
Control de Mochi y cámara
      ↓
Escenario, físicas e interacciones
      ↓
Enemigos, peligros y puzzles
      ↓
Interfaz y checkpoints
      ↓
Guardado local
```

## Componentes principales

| Componente | Responsabilidad | Dependencias |
|---|---|---|
| Jugador y cámara | Movimiento, salto, respuesta de cámara y estados de Mochi | Entrada, físicas del motor |
| Escenario | Niveles lineales, plataformas y peligros | Jugador, físicas |
| Enemigos y mecanismos | Patrullas y persecución, ventilador, memorama y elementos interactuables | Escenario, jugador |
| Interfaz | Menús, HUD de semillas, indicaciones y pausa | Estado del juego |
| Checkpoints y guardado | Reaparición y persistencia local del progreso y configuración | Estado del nivel, datos guardados |

## Comunicación

Los componentes se comunican mediante las funciones y eventos básicos del motor. Por ejemplo, una interacción actualiza el estado del mecanismo y la interfaz comunica el resultado. La arquitectura debe mantenerse directa y proporcional al tamaño del juego.

## Principios técnicos

- Bajo acoplamiento cuando sea razonable.
- Responsabilidades claras.
- Código mantenible.
- Datos separados de lógica cuando corresponda.
- Evitar dependencias innecesarias.
- Juego individual para PC, sin servidor, cuentas ni servicios en línea.
- Priorizar escenas y recursos 3D sencillos, reutilizables y adecuados para el alcance.


> **Navegación:** [[00 - Índice]] · ← [[04 - Guardado y Configuración]] · [[02 - Motor y Herramientas]] →
