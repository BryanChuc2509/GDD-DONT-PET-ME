# Motor y Herramientas

## Descripción de la sección

Documenta las herramientas utilizadas para crear el videojuego y por qué fueron seleccionadas.

## Motor

**Motor:** Unity.

**Versión:** Unity 6 (6000.6.4f1).

**Renderizado:** Universal Render Pipeline (URP 17.6.0), con un estilo 3D sencillo y estilizado y post-procesado ligero, como el desenfoque del fondo.

**Física:** Física integrada de Unity para movimiento, colisiones y objetos interactuables. El comportamiento se ajusta a las necesidades de plataformas, sin buscar simulación física compleja.

**Sistema de entrada:** Input System 1.20.0, con teclado y ratón. Las acciones están en `InputSystem_Actions.inputactions`.

## Lenguajes

| Lenguaje | Uso                                     |
| -------- | --------------------------------------- |
| C#       | Lógica de juego y componentes de Unity |

## Herramientas

| Herramienta                                            | Propósito                                  | Versión   |
| ------------------------------------------------------ | ------------------------------------------- | ---------- |
| Blender                                                | Modelado y preparación de recursos 3D      | Confirmado |
| Visual Studio Code u otro editor elegido por el equipo | Edición de scripts y archivos del proyecto | Confirmado |
| Git y Git LFS                                          | Control de versiones del proyecto           | Confirmado |

## Dependencias

No se requiere un servidor ni un servicio en línea. Estos son los paquetes de Unity que usa el proyecto:

| Paquete | Versión | Uso |
| --- | --- | --- |
| Universal RP | 17.6.0 | Renderizado y post-procesado |
| Input System | 1.20.0 | Controles de teclado y ratón |
| AI Navigation | 2.0.14 | NavMesh para que las hormigas y la araña de rincón encuentren el camino |
| Unity UI (incluye TextMeshPro) | 2.6.0 | HUD, menús y textos |
| Video (módulo de Unity) | — | Video de introducción |

El proyecto usa Git con Git LFS para los archivos binarios (modelos, texturas, audio y video).

## Convenciones del proyecto

- Mantener una estructura de carpetas y nombres consistentes.
- Usar control de versiones para el proyecto y sus cambios.
- Preferir recursos 3D ligeros y formatos compatibles con Unity.
- Mantener los scripts y componentes simples y reutilizables, sin añadir sistemas innecesarios.

> **Navegación:** [[00 - Índice]] · ← [[01 - Arquitectura Técnica]] · [[03 - Requisitos Técnicos]] →
