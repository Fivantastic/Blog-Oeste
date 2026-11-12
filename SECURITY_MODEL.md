# Modelo de amenazas – Fivantastic/Blog-Oeste

_Lo marcado como "inferido" es lectura del código; lo marcado como "propietario" lo ha confirmado Iván._

## Resumen del sistema
Sitio web estático de práctica ("Blog para el curso de Platzi"). El repositorio contiene solo:
- `postblog.html`: página de un artículo ("Oeste Vaquero") con un enlace externo a `https://www.oestevaquero.com/`.
- `CSS/estilos.css`: hoja de estilos.
- `README.md`, `historia.txt`: texto libre.

No hay backend, JavaScript, formularios, dependencias, CI ni infraestructura como código. Nota: `postblog.html` enlaza `css/estilos.css` en minúsculas mientras la carpeta es `CSS/` (fallo funcional en hosts sensibles a mayúsculas, no de seguridad).

## Componentes
- **Web estática**: `postblog.html`, `CSS/estilos.css` — lo que ve el visitante.
- **Contenido del repositorio**: `README.md`, `historia.txt`, historial de git — visible públicamente en GitHub.

## Fronteras de confianza y puntos de entrada
- Visitante anónimo ↔ página estática. El propietario no sabe cómo ni si se publica (propietario); no hay repositorio de infraestructura entre los accesibles.
- Cualquiera en Internet ↔ repositorio público en GitHub (lectura) y su historial.
- Página ↔ sitio externo `oestevaquero.com` mediante enlace (sin `target="_blank"`).

## Activos
- **Datos personales que aparezcan en el repositorio o su historial** — activo principal (propietario). Ej.: `historia.txt` incluye la edad del autor; el historial de git expone nombre y correo del autor.
- Integridad del contenido publicado (inferido).
- Credenciales de la cuenta de GitHub: no deberían aparecer en el repo ni en su historial (inferido; un commit menciona "probar la llave").

## Atacantes relevantes
- Cualquiera que lea el repositorio público y su historial (inferido).
- Visitante anónimo de la página (inferido).

## Controles existentes
- Sin código ejecutable en servidor ni cliente: superficie de ataque mínima.

## Fuera de alcance / riesgo aceptado
- **Enlaces a sitios externos (`oestevaquero.com`)**: riesgo aceptado (propietario). Hallazgos sobre el destino o el comportamiento de esos enlaces no se priorizan.

## Preguntas abiertas
- Hosting y despliegue desconocidos; si se publica, ¿con qué cabeceras/configuración?
