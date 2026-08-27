# Portafolio Personal — Victor Andre Chiquito Toro

## Nombre del proyecto
Portafolio personal — Victor Andre Chiquito Toro

## Estudiante
Victor Andre Chiquito Toro

## Descripción breve
Portafolio personal interactivo desarrollado con HTML, CSS y JavaScript. Presenta mi
perfil como ethical hacker, mis habilidades técnicas, una sección de proyectos con
write-ups de vulnerabilidades reportadas y reconocidas por organizaciones como
Lenovo, Motorola, NASA y Harvard, y un formulario de contacto con validación.

## Actividad Integradora 2 — Funcionalidades con JavaScript
- **Modo claro / oscuro**: botón en el header que alterna el tema del sitio.
  La preferencia se guarda en `localStorage` y se aplica automáticamente en
  cada visita.
- **Banner de bienvenida**: si ya escribiste antes por el formulario de
  contacto, tu nombre queda guardado en `localStorage` y el sitio te saluda
  de nuevo al volver a abrirlo.
- **Contador de visitas simulado**: guardado y actualizado en `localStorage`,
  visible en el pie de página.
- **Validación del formulario de contacto**: verifica que nombre, correo y
  mensaje no estén vacíos y que el correo tenga un formato válido antes de
  mostrar un mensaje de confirmación (o de error).
- **Botón "Volver al inicio"**: aparece al hacer scroll hacia abajo y sube
  suavemente al tope de la página.
- **Modales de write-up**: se abren/cierran con JavaScript (`<dialog>` nativo).

## AppSec — Mitigaciones de OWASP Top 10 aplicadas
Como el sitio ya usa JavaScript del lado del cliente, se incorporaron buenas
prácticas de seguridad ofensiva aplicadas a mi propio código (dogfooding):

- **A03:2021 – Injection (XSS)**: todo el contenido dinámico se inserta con
  `textContent` (nunca `innerHTML`) al escribir datos que vienen del usuario
  (nombre del formulario, banner de bienvenida), evitando XSS basado en DOM.
  Se incluye además una función `escapeHTML()` como defensa en profundidad.
- **A05:2021 – Security Misconfiguration**: se agregó una cabecera
  `Content-Security-Policy` (meta tag) que restringe `script-src` a `'self'`
  — es decir, solo se ejecuta el JavaScript propio del sitio (`script.js`),
  bloqueando scripts inline o inyectados por terceros. También se restringen
  `img-src`, `font-src`, `style-src`, `object-src` y `frame-ancestors` a los
  orígenes estrictamente necesarios.
  > Nota: `style-src` incluye `'unsafe-inline'` porque algunos badges de
  > habilidades usan `style=""` inline para su color. Idealmente se
  > refactorizarían a clases CSS para poder quitar esa excepción.
- **Reverse tabnabbing**: todos los enlaces con `target="_blank"` usan
  `rel="noopener noreferrer"`.
- **Validación solo de UX, no de seguridad**: la validación del formulario en
  `script.js` está documentada como una mejora de experiencia de usuario, no
  como un control de seguridad — si este formulario tuviera un backend real,
  la validación debería repetirse siempre del lado del servidor.
- **Datos en `localStorage`**: solo se guardan datos no sensibles (nombre,
  preferencia de tema, contador de visitas), nunca contraseñas ni datos
  sensibles.

## Tecnologías utilizadas
- HTML5 (etiquetas semánticas: header, nav, main, section, footer, article)
- CSS3 (Flexbox, variables CSS con `:root`, pseudoclase `:hover`, modo claro/oscuro)
- JavaScript (Vanilla JS, `addEventListener`, manipulación del DOM, `localStorage`)
- Google Fonts (IBM Plex Mono, Inter)
- Git y GitHub

## Instrucciones para visualizar el proyecto
1. Clona este repositorio:
   ```
   git clone https://github.com/TatsuhiroSattou/victor-chiquito.git
   ```
2. Abre el archivo `index.html` en tu navegador (doble clic o "Open with Live Server"
   en VS Code).
3. No requiere instalación de dependencias adicionales.

## Captura de pantalla
<img width="1882" height="865" alt="Captura de pantalla 2026-08-27 163926" src="https://github.com/user-attachments/assets/e6d0184b-c5be-4d05-8a14-2fa5c172c2ee" />
<img width="1890" height="826" alt="Captura de pantalla 2026-08-27 164002" src="https://github.com/user-attachments/assets/53c76515-5c5f-49f8-9266-fad0fffbcb68" />


## Autor
- GitHub: [@TatsuhiroSattou](https://github.com/TatsuhiroSattou)
- Correo: Andreschiquito111@gmail.com

