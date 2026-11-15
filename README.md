# Gestor de enlaces Rentry

Aplicación estática para guardar y organizar páginas de Rentry. Está preparada para publicarse en **GitHub Pages**.

## Archivos

- `index.html`: aplicación completa. Es el archivo de entrada y debe permanecer en la raíz del repositorio.
- `favicon.svg`: icono SVG de la aplicación.

## Publicar en GitHub Pages

1. Crea un repositorio en GitHub.
2. Sube `index.html` y `favicon.svg` directamente a la raíz del repositorio.
3. Abre **Settings → Pages**.
4. En **Build and deployment**, selecciona **Deploy from a branch**.
5. Selecciona la rama `main` y la carpeta `/ (root)`. Guarda.
6. Abre la URL que GitHub Pages te proporcione.

Tailwind CSS se carga desde CDN, por lo que la primera carga requiere conexión a Internet.

## Almacenamiento

La aplicación guarda los registros automáticamente en `localStorage` del navegador. No necesita exportar/importar para el uso habitual, ni requiere un servidor.

**Importante:** GitHub Pages es alojamiento estático. No puede escribir un archivo `db.json` dentro del repositorio. Con esta versión, los datos pertenecen al navegador y perfil donde se guardaron; no se sincronizan entre dispositivos ni navegadores. Si se borran los datos del sitio en el navegador, se perderán.

Para sincronización real entre dispositivos se debe conectar una base de datos externa (por ejemplo, Supabase) y añadir autenticación. No se debe guardar una clave secreta de administrador de una base de datos en el JavaScript público.

## Funciones

- Crear, editar y eliminar registros.
- Acepta `rentry.co/slug`, `https://rentry.co/slug` o solo `slug`.
- Guarda código de edición opcional, oculto hasta pulsar **Ver código**.
- Copia enlace, enlace `/raw` y código de edición.
- Crea, renombra y elimina categorías.
- Conserva los enlaces al eliminar una categoría; pasan a **Sin categoría**.
- Busca por nombre, URL, categoría, etiqueta y notas.
- Filtra por categoría y ordena por fecha o nombre.
- Eliminar un registro solo lo quita del gestor. No modifica la página de Rentry.

## Privacidad

El código de edición se almacena localmente en el navegador en texto legible dentro de `localStorage`. No compartas el mismo perfil de navegador con otras personas si guardas códigos sensibles. Esta versión no transmite los datos a un servidor.
