# Automatization

# File Organizer Automation

Un proyecto de automatización con Python que organiza automáticamente los archivos de tu carpeta de descargas en subcarpetas según su tipo (Imágenes, Documentos, Videos, Audio, Archivos, Otros). Incluye una landing page (HTML + TailwindCSS) para presentar el proyecto y un botón de descarga que entrega el script `assets/file_organizer.py`.


Preview: ![Demo Screenshot](assets/demo.png)

---

## Características

* Organización automática por extensión (imágenes, documentos, videos, audio, archivos comprimidos…)
* Compatible con Windows, macOS y Linux
* Configurable vía argumentos de línea de comandos
* Ejecución manual o programada con cron (Linux/macOS) o Task Scheduler (Windows)
* Landing lista para publicar en GitHub Pages

---

## Estructura del proyecto

```text
.
├── index.html
├── css/
│   └── style.css
├── js/
│   ├── main.js
│   └── aos-init.js
├── assets/
│   ├── file_organizer.py
│   └── demo.png
└── README.md
```

---

## Empezar

### 1) Clonar el repositorio

```bash
git clone https://github.com/TU-USUARIO/REPO-NAME.git
cd REPO-NAME
```

### 2) Requisitos

* Python 3.6+

Verifica tu versión:

```bash
python --version
```

En algunos entornos, el comando puede ser `python3`.

---

## Uso del script

### Ejecutar en la carpeta de descargas por defecto

```bash
python assets/file_organizer.py
```

### Ejecutar con carpeta personalizada

```bash
python assets/file_organizer.py --source "C:\MiCarpeta"
# macOS/Linux
python3 assets/file_organizer.py --source "/Users/tuusuario/Downloads"
```

El script moverá los archivos a subcarpetas dentro de la carpeta indicada. Para extensiones no reconocidas, usará `Other/`.

---

## Programar ejecución automática

### Linux/macOS – cron (cada hora)

```bash
crontab -e
# Añade esta línea y guarda
0 * * * * /usr/bin/python3 /ruta/al/proyecto/assets/file_organizer.py
```

### Windows – Task Scheduler (cada hora)

1. Abre Programador de tareas → Crear tarea básica.
2. Desencadenador: Diariamente → Repetir cada 1 hora.
3. Acción: Iniciar un programa.
4. Programa/script: `python`
5. Agregar argumentos: `C:\ruta\al\proyecto\assets\file_organizer.py`

Alternativa por consola (PowerShell / CMD):

```bat
schtasks /Create /SC HOURLY /TN "FileOrganizer" /TR "python C:\ruta\al\proyecto\assets\file_organizer.py" /F
```

---

## Publicar la landing en GitHub Pages

1. Sube el repo a GitHub.
2. En Settings → Pages:

   * Source: Deploy from a branch
   * Branch: main (o master) y /root
3. Guarda. GitHub generará la URL: `https://TU-USUARIO.github.io/REPO-NAME/`

El botón Download Script en `index.html` apunta a `assets/file_organizer.py`. Asegúrate de que ese archivo exista en esa ruta.

---

## Tecnologías usadas

* Python – Script de automatización
* TailwindCSS – Estilos responsivos
* Feather Icons – Íconos SVG
* AOS.js – Animaciones on-scroll
* GitHub Pages – Hosting estático

---

## Contribuir

Las contribuciones son bienvenidas. Haz un fork, crea tu rama y abre un pull request.

```bash
git checkout -b feature/mi-mejora
# ...
git commit -m "feat: descripción corta"
git push origin feature/mi-mejora
```

---

## Licencia

Distribuido bajo la MIT License. Consulta `LICENSE` para más información.

---

