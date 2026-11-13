# Datos y Persistencia

## Descripción de la sección

Define qué información necesita conservar el juego y cómo se estructura.

## Datos persistentes

- Nivel y checkpoint actual.
- Estado de los puzzles de progresión.
- Preferencias de configuración.

## Modelo de datos

El guardado local contiene una partida lineal con el nivel, el checkpoint, el estado de progresión y las opciones del jugador. No se requiere una base de datos, cuentas ni sincronización en línea.

## Formato

**Formato de guardado:** Archivo local sencillo; formato por confirmar durante la implementación.

**Ubicación:** Almacenamiento local de la aplicación en Windows.

**Versionado de datos:** Versión sencilla del esquema para identificar cambios incompatibles.

## Migraciones

Si cambia el formato, la versión nueva debe detectar los datos incompatibles y comunicar el problema sin indicar que el progreso se cargó correctamente. Las migraciones complejas no forman parte del alcance actual.

> **Navegación:** [[00 - Índice]] · ← [[03 - Requisitos Técnicos]] · [[05 - Seguridad y Riesgos Técnicos]] →
