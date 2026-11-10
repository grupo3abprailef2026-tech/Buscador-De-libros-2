📚 Biblioteca del colegio

Catálogo de libros con búsqueda instantánea, filtros por categoría y ficha de detalle. Es un proyecto de código abierto: cualquiera puede agregar libros enviando un cambio al archivo books.json.

No necesita instalar nada ni usar un servidor propio: son solo archivos estáticos.

Ver el sitio

Opción 1: GitHub Pages (recomendada, gratis)

Sube estos archivos a tu repositorio.
Ve a Settings > Pages.
En "Branch" elige main y la carpeta / (root), y guarda.
En un minuto tendrás tu sitio en https://TU-USUARIO.github.io/TU-REPOSITORIO/.

Opción 2: en tu computador Abrir index.html con doble clic no carga el catálogo, porque el navegador bloquea la lectura de books.json. Ejecuta esto en la carpeta del proyecto:

bash
python3 -m http.server 8000

y abre http://localhost:8000.

Cómo agregar un libro
Abre books.json en GitHub y presiona el lápiz ✏️ (Edit).
Copia un bloque existente y agrégalo antes del último ]. Separa los bloques con una coma.
Presiona Commit changes y elige Create a new branch / Propose changes.
Abre el Pull Request. Un mantenedor lo revisará y lo aprobará.

Ejemplo:

json
{
  "title": "Título del libro",
  "author": "Nombre del autor",
  "category": "Novela",
  "isbn": "9780000000000",
  "year": 2020,
  "available": true,
  "description": "Una o dos frases sobre de qué trata.",
  "location": "Estante A1"
}
Campo	Obligatorio	Qué es
title	Sí	Título del libro
author	Sí	Autor o autores
category	Sí	Se crean automáticamente los filtros con las categorías que uses
available	Sí	true si está en la biblioteca, false si está prestado
isbn	No	Se puede buscar por este dato
year	No	Año de publicación
description	No	Resumen breve (también se usa en la búsqueda)
location	No	Dónde encontrarlo físicamente
color	No	Color de la portada, por ejemplo "#2a5bd7". Si no lo pones, se genera uno automático

Reglas del JSON: usa comillas dobles ", no dejes coma después del último elemento y escribe true/false sin comillas. Puedes validar tu archivo en jsonlint.com.

Personalizar

Al inicio del <script> en index.html hay un bloque CONFIG con el nombre del colegio, el mensaje de préstamo y el enlace a tu repositorio. Cámbialos y listo.

Marcar un libro como prestado

Cambia "available": true por "available": false en books.json y guarda el cambio.

Licencia

MIT. Puedes usarlo, modificarlo y compartirlo libremente. Agrega un archivo LICENSE desde GitHub (Add file > Create new file, escribe LICENSE y elige la plantilla MIT).
