# Alma Ríos — Portfolio de demostración

Landing page de una sola página para una artista visual ficticia. Es un proyecto educativo de HTML y CSS: el nombre, la biografía, las obras, los hitos, los eventos y el contacto son datos de demostración que deben sustituirse antes de publicar.

## Objetivos

- Presentar identidad, biografía, trayectoria y próximas presentaciones.
- Practicar HTML semántico, CSS responsive, accesibilidad y SEO técnico.
- Mantener una estructura pequeña y fácil de personalizar.

## Tecnologías

- HTML5 y CSS3.
- Datos estructurados Schema.org en JSON-LD.
- Git para control de versiones.

No se usan JavaScript, frameworks, fuentes remotas ni dependencias externas. Los SVG de `assets/images/` son ilustraciones vectoriales originales de demostración.

## Estructura

```text
.
├── index.html
├── styles.css
├── README.md
├── server.py
├── .vscode/
│   └── settings.json
└── assets/
    └── images/
        ├── quietud-agua.svg
        ├── retrato-estudio.svg
        └── umbral-dorado.svg
```

## Ejecución

Abre `index.html` directamente en el navegador. Para usar el servidor de la plantilla oficial, instala Flask y ejecuta:

```bash
pip3 install flask
python3 server.py
```

Después visita `http://localhost:3000`.

## Accesibilidad

- El documento declara español, usa landmarks semánticos y mantiene un único H1.
- Incluye un enlace para saltar al contenido, navegación por anclas y foco visible.
- Las imágenes informativas tienen textos alternativos; se evita depender solo del color.
- El diseño responde a móvil y escritorio, y reduce movimiento cuando el sistema lo solicita.

## SEO

- Título y descripción de página, viewport y jerarquía de encabezados.
- JSON-LD describe el sitio, el personaje, dos obras y dos eventos ficticios.
- Los datos estructurados coinciden con el contenido visible; no se incluyen dominios ni perfiles sociales de producción.

## Personalización

1. Sustituye nombre, textos, correo, obras, hitos y eventos de demostración en `index.html`.
2. Cambia las ilustraciones SVG de `assets/images/` por imágenes del artista y actualiza sus textos `alt`.
3. Actualiza el JSON-LD para que describa únicamente información visible y confirmada.
4. Revisa las fechas, el contraste y el diseño en los tamaños de pantalla que te interesen.

## Publicación en GitHub

1. Crea un repositorio nuevo en tu cuenta y añade este proyecto.
2. Añade el remoto de tu repositorio nuevo. Si ya existe un remoto llamado `origin`, actualiza su URL en vez de añadirlo de nuevo:

   ```bash
   git remote add origin <URL-de-tu-repositorio>
   # Si origin ya existe: git remote set-url origin <URL-de-tu-repositorio>
   ```

3. Guarda los cambios con un mensaje descriptivo y súbelos:

   ```bash
   git add index.html styles.css README.md assets/images
   git commit -m "feat: create accessible artist portfolio"
   git push -u origin main
   ```

La plantilla oficial incluye `server.py` y preferencias de editor en `.vscode/settings.json`; se conservan para mantener la vista previa local y el formato del entorno.
