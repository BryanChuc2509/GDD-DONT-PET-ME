# Datos y Persistencia

## Descripción de la sección

Define qué información necesita conservar el juego y cómo se estructura.

## Datos persistentes

- El último nivel al que se entró.
- El volumen general, el de la música y el de los efectos.

## Modelo de datos

El guardado usa `PlayerPrefs` de Unity, con estas claves:

| Clave | Contenido | Cuándo se escribe |
| --- | --- | --- |
| `DPM_SavedScene` | Nombre de la escena del último nivel | Al cargar cada nivel; se borra al empezar una nueva partida |
| `DPM_MasterVolume` | Volumen general (0 a 1) | Al cambiarlo en Ajustes |
| `DPM_MusicVolume` | Volumen de la música (0 a 1) | Al cambiarlo en Ajustes |
| `DPM_SfxVolume` | Volumen de los efectos (0 a 1) | Al cambiarlo en Ajustes |

No se requiere una base de datos, cuentas ni sincronización en línea.

## Formato

**Formato de guardado:** `PlayerPrefs` de Unity (pares de clave y valor).

**Ubicación:** En Windows, el registro del usuario (`HKEY_CURRENT_USER\Software\DefaultCompany\DontPetMe`).

**Versionado de datos:** No hay versión de esquema.

## Migraciones

No hay migraciones. Si el nivel guardado ya no existe en el juego, se ignora y el menú muestra "Jugar".

> **Navegación:** [[00 - Índice]] · ← [[03 - Requisitos Técnicos]] · [[05 - Seguridad y Riesgos Técnicos]] →
