# GIT - La guía fácil para bachilleres 😎

## ¿Qué es Git?

Git es como un **control de cambios** para tu código. Imagina que tienes un documento importante en Word, y quieres guardar todas las versiones que escribiste. Git hace exactamente eso, pero para código.

Es como tener un **historial de cambios** donde puedes:
- Ver qué cambié
- Cuándo lo cambié
- Por qué lo cambié
- Volver atrás si cometí un error

## ¿Para qué sirve?

1. **Historial de cambios**: Puedes ver todos los cambios que has hecho
2. **Trabajo en equipo**: Varios programadores pueden trabajar en el mismo proyecto sin pisarse
3. **Recuperación**: Si algo se daña, puedes volver a una versión anterior
4. **Respaldo**: Tus cambios quedan guardados

## Los comandos básicos que necesitas (sin complicarte)

### 1. Preparar Git por primera vez
```
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```
*Esto es como registrarse, solo lo haces una vez*

### 2. Crear un proyecto nuevo
```
git init
```
*Le dices a Git que vigile esta carpeta*

### 3. Ver qué has cambiado
```
git status
```
*Te muestra qué archivos has modificado*

### 4. Guardar un cambio (paso 1 - Preparar)
```
git add .
```
*"Git, prepárate para guardar estos cambios"*
*El punto (.) significa "todos los archivos"*

### 5. Guardar un cambio (paso 2 - Confirmar)
```
git commit -m "Tu mensaje aquí"
```
*Ahora sí guardas. El -m es el mensaje que describes qué hiciste*

**Ejemplo real:**
```
git commit -m "Agregué el formulario de login"
```

### 6. Ver tu historial de cambios
```
git log
```
*Te muestra todos los cambios que guardaste*

## El flujo normal de trabajo (resumen)

```
1. Modificas tus archivos
         ↓
2. Escribes: git add .
         ↓
3. Escribes: git commit -m "Describe qué hiciste"
         ↓
4. ¡Listo! Tu cambio está guardado
```

## Trabajar con GitHub (la nube)

### Subir tu código a GitHub
```
git push
```
*Sube tus cambios a la internet*

### Bajar cambios de GitHub
```
git pull
```
*Descarga los cambios que hicieron otros*

## Cosas útiles para recordar

- **add** = preparar cambios
- **commit** = guardar cambios  
- **push** = subir a internet
- **pull** = bajar de internet
- **status** = ver el estado actual
- **log** = ver el historial

## Un ejemplo paso a paso (la vida real)

```
1. Abres VS Code y trabajas en tu código
2. Terminas de programar una nueva función
3. Abres la terminal y escribes: git status
4. Git te dice: "Cambiaste el archivo app.js"
5. Escribes: git add .
6. Escribes: git commit -m "Agregué la función de login"
7. Escribes: git push
8. ¡Listo! Tu código está en GitHub
```

## ¿Cometiste un error?

```
git checkout nombre-archivo
```
*Vuelve el archivo a cómo estaba*

```
git reset HEAD~1
```
*Deshace el último commit (sin borrar los cambios)*

---

**Recuerda:** Git es tu amigo. Úsalo para guardar cambios importantes frecuentemente, así nunca perderás tu trabajo.
