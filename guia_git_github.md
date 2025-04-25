
🧭 Guía Definitiva para Crear y Subir Repositorios con Git y GitHub (Python + WSL)
✅ Objetivo
Ignorar archivos sensibles como .env

Trackear requirements.txt con las dependencias del proyecto

Crear el repo desde local y subirlo limpio a GitHub (público o privado)

Usar rama main desde el principio

Compatible con WSL y entorno Python

🔧 Paso a paso: Crear un proyecto local con Git y Python
1. Crear el directorio del proyecto
```bash
mkdir mi-proyecto
cd mi-proyecto
```
2. Crear y activar un entorno virtual
```bash
python3 -m venv venv
source venv/bin/activate
```
3. Instalar dependencias y generar requirements.txt
```bash
pip install requests beautifulsoup4
pip freeze > requirements.txt
```
4. Crear el archivo .gitignore
```bash
nano .gitignore
```
📄 Contenido recomendado:

```gitignore
# Entorno virtual
venv/

# Variables de entorno
.env

# Cachés y archivos compilados
__pycache__/
*.pyc
```

5. Inicializar el repositorio con rama main
```bash
git init -b main
```

6. Añadir y commitear los archivos
```bash
git add .
git commit -m "Primer commit limpio con .gitignore y requirements"
```

❗ ¿Ya habías subido archivos que ahora están en .gitignore?
```bash
git rm --cached -r .
git add .
git commit -m "Aplico .gitignore y limpio archivos ignorados"
```
Esto no borra archivos del disco, solo del seguimiento de Git.

7. Crear y subir el repositorio a GitHub
Si usás GitHub CLI (recomendado):
```bash
gh repo create mi-proyecto --private --source=. --remote=origin --push
```
✅ Esto crea el repo, lo vincula y sube tu código.

🧠 Tips útiles
Cambiar la rama por defecto a main globalmente (una vez):
```bash
git config --global init.defaultBranch main
```

Actualizar requirements.txt tras instalar nuevas dependencias:
```bash
pip freeze > requirements.txt
```

📦 Archivos clave que sí deben estar en tu repositorio
- requirements.txt
- Tu código fuente (.py, .ipynb, etc.)
- Archivos .md, documentación, scripts

🔒 Archivos que NO deben subirse (y deben estar en .gitignore)
- .env
- venv/
- .DS_Store, *.log, archivos temporales

📜 Comandos Git esenciales
```bash
git status              # Ver cambios
git add archivo.py      # Añadir archivo específico
git commit -m "mensaje"
git push                # Subir cambios
git pull                # Traer cambios del remoto
```

🧾 Historial y ramas
```bash
git log                 # Ver historial de commits
git branch              # Ver ramas locales
git switch main         # Cambiar a otra rama
```
