# J.A.R.V.I.S. Helmet HUD

Interfaz holográfica estilo Iron Man que corre en el navegador y usa tu cámara web. Detecta tu rostro en tiempo real con **MediaPipe Face Mesh** y proyecta sobre él un HUD futurista en azul cian.

Todo vive en un solo archivo HTML, sin instalación ni dependencias locales.

## Características

- Malla facial de 468 puntos más seguimiento de iris.
- Recuadro de escaneo que muestra `SCANNING...` y luego `USER IDENTIFIED: TONY STARK`.
- Retícula de apuntado giratoria que sigue tu nariz.
- Caja de datos flotante (yaw, roll, BPM, estado de los ojos) que acompaña tu rostro.
- Marco del casco, brújula, telemetría simulada, barras de carga, reactor arc y radar.
- Efectos analógicos: líneas de escaneo, parpadeo y glitch aleatorio.
- Diseño responsivo a pantalla completa.

## Demo rápida

1. Abre `index.html` en Chrome o Edge.
2. Acepta el permiso de cámara.
3. Mueve la cabeza: los hologramas te siguen.

> Si el navegador bloquea la cámara al abrir el archivo con `file://`, sírvelo en local:
>
> ```bash
> python -m http.server 8000
> # luego abre http://localhost:8000
> ```

## Tecnologías

| Uso | Herramienta |
| --- | --- |
| Detección facial | [MediaPipe Face Mesh](https://www.npmjs.com/package/@mediapipe/face_mesh) (CDN jsDelivr) |
| Tipografías | Orbitron y Share Tech Mono (Google Fonts) |
| Dibujo del HUD | Canvas 2D, CSS y SVG |

## Requisitos

- Navegador moderno con soporte de `getUserMedia` (Chrome, Edge, Firefox, Safari).
- Webcam.
- Conexión a internet (los modelos y fuentes se cargan desde CDN).

## Personalización

- **Color del HUD:** cambia `--c` en `:root` y la constante `CYAN` en el script (formato `r,g,b`).
- **Nombre identificado:** edita el texto `USER IDENTIFIED: TONY STARK` en la función `drawFace`.
- **Duración del escaneo:** ajusta el valor `3000` (ms) en `drawFace`.

## Privacidad

El video se procesa únicamente en tu navegador. No se graba ni se envía a ningún servidor.

## Publicar en GitHub Pages

Como Pages sirve el sitio por HTTPS, la cámara funciona sin configuración extra.

1. Sube el repositorio con el archivo llamado `index.html`.
2. Ve a **Settings → Pages**.
3. En **Branch** elige `main` y la carpeta `/ (root)`.
4. Guarda y abre la URL que GitHub te indica.

## Licencia

MIT. Úsalo, modifícalo y compártelo libremente.

## Créditos

Proyecto fan-made inspirado en la interfaz de Iron Man. Iron Man, J.A.R.V.I.S. y Tony Stark son marcas de Marvel; este proyecto no está afiliado a Marvel ni a Disney.
