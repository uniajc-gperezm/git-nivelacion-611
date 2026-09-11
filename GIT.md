# Git desde la terminal

Esta guia resume el flujo basico para trabajar con Git desde la terminal.

## 1. Conceptos esenciales

- **Repositorio:** carpeta controlada por Git.
- **Working tree:** archivos que estamos editando.
- **Staging area:** cambios seleccionados para el proximo commit.
- **Commit:** registro de una version del proyecto.
- **Repositorio remoto:** copia del proyecto alojada en GitHub u otro servidor.

El flujo habitual es:

```text
editar archivos -> git status -> git add -> git commit -> git push
```

## 2. Configuracion inicial

Se realiza una sola vez por equipo:

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu-correo@ejemplo.com"
git config --global init.defaultBranch main
```

Para comprobar la configuracion:

```bash
git config --global --list
git --version
```

## 3. Crear u obtener un repositorio

### Crear un repositorio local

Desde la carpeta del proyecto:

```bash
git init
```

### Clonar un repositorio existente

```bash
git clone https://github.com/usuario/proyecto.git
cd proyecto
```

## 4. Revisar el estado del proyecto

Antes y despues de trabajar, consulta el estado:

```bash
git status
```

Este comando muestra archivos nuevos, modificados, preparados para commit y la rama actual.

Para consultar los cambios que aun no se han preparado:

```bash
git diff
```

## 5. Preparar cambios

Agregar un archivo especifico:

```bash
git add nombre-del-archivo.txt
```

Agregar todos los cambios de la carpeta actual:

```bash
git add .
```

Quitar un archivo del staging sin perder sus cambios:

```bash
git restore --staged nombre-del-archivo.txt
```

## 6. Crear un commit

Un commit debe representar un cambio concreto y tener un mensaje claro:

```bash
git commit -m "Agrega validacion del formulario"
```

Consultar el historial resumido:

```bash
git log --oneline
```

Consultar el commit mas reciente con sus cambios:

```bash
git show
```

## 7. Trabajar con ramas

Ver las ramas locales:

```bash
git branch
```

Crear y cambiarse a una rama nueva:

```bash
git switch -c nombre-de-la-rama
```

Cambiarse a una rama existente:

```bash
git switch main
```

Unir una rama en la rama actual:

```bash
git merge nombre-de-la-rama
```

Una convencion sencilla es usar ramas descriptivas, por ejemplo:

```text
feature/login
fix/error-formulario
docs/guia-git
```

## 8. Conectar con GitHub y sincronizar

Agregar el repositorio remoto con el nombre habitual `origin`:

```bash
git remote add origin https://github.com/usuario/proyecto.git
```

Ver los remotos configurados:

```bash
git remote -v
```

Enviar la rama actual por primera vez:

```bash
git push -u origin main
```

En los siguientes envios basta con:

```bash
git push
```

Descargar e integrar los cambios del remoto:

```bash
git pull
```

Descargar cambios sin integrarlos automaticamente:

```bash
git fetch origin
```

Antes de empezar a trabajar en equipo, es recomendable actualizar la rama:

```bash
git switch main
git pull origin main
```

## 9. Ignorar archivos

Crea un archivo llamado `.gitignore` en la raiz del proyecto para no subir archivos generados, credenciales o configuraciones locales.

Ejemplo:

```gitignore
node_modules/
.env
*.log
__pycache__/
```

Nunca se deben subir contrasenas, tokens ni claves privadas al repositorio.

## 10. Deshacer cambios de forma segura

Descartar cambios no guardados de un archivo. Esta accion elimina los cambios locales del archivo:

```bash
git restore nombre-del-archivo.txt
```

Modificar el mensaje del ultimo commit si todavia no se ha enviado:

```bash
git commit --amend -m "Nuevo mensaje del commit"
```

Crear un nuevo commit que deshace otro commit, opcion recomendada cuando el commit ya fue publicado:

```bash
git revert ID_DEL_COMMIT
```

Evita usar `git reset --hard` si no tienes claro que cambios se perderan.

## 11. Flujo completo de ejemplo

```bash
# 1. Obtener la version mas reciente
git pull origin main

# 2. Crear una rama para el cambio
git switch -c feature/saludo

# 3. Editar archivos y revisar los cambios
git status
git diff

# 4. Preparar y guardar el cambio
git add .
git commit -m "Agrega saludo inicial"

# 5. Publicar la rama
git push -u origin feature/saludo
```

> En el ejemplo anterior, los comandos deben escribirse sin los comentarios. La rama correcta es `feature/saludo`.

## 12. Recomendaciones

- Ejecuta `git status` con frecuencia.
- Haz commits pequenos, relacionados y faciles de explicar.
- Escribe mensajes en modo imperativo: `Agrega`, `Corrige`, `Actualiza`.
- Actualiza tu rama antes de comenzar una tarea.
- Revisa los archivos preparados con `git diff --staged` antes del commit.
- No uses `git add .` sin revisar si existen archivos sensibles o innecesarios.
