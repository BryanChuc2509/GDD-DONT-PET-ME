# Guardado y Configuración

## Descripción de la sección

Define cómo se conserva el progreso y qué opciones puede modificar el jugador.

## Guardado

**Tipo:** Automático.

**Cuándo se guarda:**

* Al activar los checkpoints definidos en la habitación y el pasillo.
* Al completar un puzzle importante o actualizar el punto de reaparición, si el diseño técnico lo requiere.

**Qué datos se guardan:**

* Nivel y checkpoint actuales.
* Estado de los puzzles necesarios para la progresión.
* Preferencias de configuración.

**Cantidad de ranuras:**

Una sola ranura local, suficiente para el recorrido lineal y el alcance actual.

**Qué ocurre si el guardado falla:**

* Se muestra un aviso breve si no se puede guardar.
* El fallo no debe presentarse como un guardado exitoso; se conserva el último guardado válido cuando sea posible.

## Configuración

| Categoría | Opciones |
| --- | --- |
| Audio | Volumen general, música y efectos de sonido, con deslizadores en porcentaje. Se guardan al cerrar la ventana de ajustes. |
| Controles | Ventana de consulta con la tecla de cada acción. |

## Restablecimiento

El botón "Restablecer ajustes" devuelve el volumen general, la música y los efectos al 100%.

> **Navegación:** [[00 - Índice]] · ← [[03 - Accesibilidad]] · [[01 - Arquitectura Técnica]] →
