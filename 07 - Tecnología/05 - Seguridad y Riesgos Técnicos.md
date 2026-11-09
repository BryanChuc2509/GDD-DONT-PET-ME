# Seguridad y Riesgos Técnicos

## Descripción de la sección

Documenta riesgos técnicos y medidas para reducir fallos, pérdida de datos o abuso de sistemas.

## Riesgos

| Riesgo | Probabilidad | Impacto | Mitigación |
|---|---|---|---|
| Rendimiento menor al esperado en algunos PC | Media | Medio | Usar recursos y efectos 3D sencillos y validar una build en equipos de prestaciones modestas. |
| Colisión o cámara imprecisa en espacios estrechos | Media | Alto | Probar la jaula, los muebles y las rutas de plataformas con el jugador y la cámara reales. |
| Fallo al guardar el progreso local | Baja | Alto | Mostrar un aviso claro y evitar comunicar éxito si el guardado falla. |

## Datos sensibles

El juego no requiere cuentas, datos personales ni estadísticas en línea. El progreso y la configuración se guardan localmente.

## Multijugador

No aplica: el juego es individual y no contempla conexión en red en el alcance actual.

## Recuperación

La pérdida de conexión no afecta al juego. Si el guardado local falla o no se puede leer, se debe mostrar un aviso claro y no presentar el progreso como cargado correctamente. El procedimiento de recuperación se definirá al implementar el guardado.


> **Navegación:** [[00 - Índice]] · ← [[04 - Datos y Persistencia]] · [[01 - Alcance]] →
