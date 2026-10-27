# Interfaz Visual

## Descripción de la sección

Esta sección define **cómo se ve** la interfaz. Su estructura y comportamiento funcional están en [[02 - UI y Menús]].

## HUD

El HUD sera minimo. Sera mas efocado en ver mas la escena que la interfaz. Mochi solo morira de un solo golpe, es por eso que varios elemnetos de un HUD típico no aplicaran.

Elementos:

| Elemento                 | Se muestra              | Descripción visual                                                                                                                                        |
| ------------------------ | ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Vida                     | **No aplica**     | Muerte de un solo golpe, no hay barra ni corazones                                                                                                         |
| Energía                 | **No aplica**     | No hay energía ni resistencia                                                                                                                             |
| Munición                | Si                      | Icono de mejilla con numeros.                                                                                                                              |
| Objeto seleccionado      | **Sí**          | Ícono del objeto en mejillas.                                                                                                                             |
| Objetivo                 | **No permanente** | La ruta se comunica con el entorno, luz y plataformas. Solo texto breve en cinemáticas                                                                   |
| Mapa                     | **No aplica**     | Niveles lineales, sin mapa                                                                                                                                 |
| Recursos                 | **Los de arriba** | Todo recurso vive en la mejilla                                                                                                                            |
| Indicadores contextuales | **Sí**           | Ícono de interacción al acercarse a un objeto, íconos de control del tutorial en cual aparecen una sola vez y **retícula discreta** al apuntar |


**Posición:** los avisos contextuales aparecen junto al objeto. Todo debe quedar dentro de la zona segura al 16:9 y no tapar el espacio central de la escena.

**Visibilidad:** el HUD se oculta en cinemáticas y en pausa.

## Jerarquía visual

1. **Mochi y el peligro cercano:** lo primero siempre es la escena, Mochi y lo que puede matarlo.
2. **Lo que se puede hacer ahora:** indicador de interacción o retícula de apuntado, que aparecen solo cuando importan.
3. **Las mejillas:** contador y objeto seleccionado, discreto y siempre en el mismo lugar.
4. **Ayudas del tutorial:** íconos de control temporales, solo la primera vez.

## Estados

**Normal**: HUD discreto, semitransparente cuando no hay cambios.

**Advertencia**: destello rojo breve en los bordes con ícono de alerta. Solo aparece en eventos clave.

**Daño o muerte**: Pausa de impacto de 0.2 s, animación cómica.

**Error**: cuando no hay con que disparar y se intenta ocupar, el contador parpadea.

**Éxito**: pantalla de victoria breve.

**Interacciones disponibles**: ícono con la tecla E, Q o SHIFT.

## Convenciones

**Tipografía:** 

Titulos y botones:

* Fuente redondeada, gruesa y amigable.

Textos y subtitulos:

* sans-serif muy legible.
* Sin textos largos en el tutorial

**Iconografía:** 

* Estilo redondeado, de línea gruesa y color plano, con contorno oscuro, coherente con el arte 3D.
* Los íconos de teclas reflejan el teclado y el mouse de una PC.
* Íconos propios: alertas, mejilla de contador para disparar.

**Tamaños mínimos:**

**Contraste:**

**Animaciones:**

## Pantallas

- Menú principal
- Pausa
- Configuración
- Inventario
- Mapa
- Victoria
- Derrota

> **Navegación:** [[00 - Índice]] · ← [[03 - Entornos]] · [[05 - Audio y Música]] →
