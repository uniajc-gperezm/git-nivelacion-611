# TERMINAL - La guía fácil para bachilleres 🖥️

## ¿Qué es la Terminal?

La terminal (o línea de comandos) es como una **forma de hablar con tu computadora escribiendo órdenes**. En lugar de hacer clic en botones, escribes lo que quieres que haga.

Piensa en ella como un **teléfono donde le das instrucciones a la computadora**.

## ¿Para qué sirve?

- Navegar por carpetas
- Crear y borrar archivos
- Ejecutar programas
- Instalar librerías
- Ver información de archivos
- Trabajar con Git

## ¿Cómo abro la terminal?

### En Windows
1. Abre VS Code
2. Ve a **Terminal** → **New Terminal** (arriba del editor)
3. O presiona **Ctrl + Ñ**

### En Mac
1. Presiona **Command + Espacio**
2. Escribe "Terminal"
3. Presiona Enter

## Los comandos básicos (sin complicarte)

### 1. Ver dónde estoy
```
pwd
```
*Te muestra la ruta donde estás ahora*

### 2. Ver qué hay en esta carpeta
```
ls
```
*(En Windows: dir)*
*Te lista los archivos y carpetas*

### 3. Entrar en una carpeta
```
cd nombre-carpeta
```
*cd = "change directory" (cambiar carpeta)*

**Ejemplo:**
```
cd Documentos
```

### 4. Volver a la carpeta anterior
```
cd ..
```
*Los dos puntos significan "carpeta padre"*

### 5. Ir a la carpeta del usuario
```
cd ~
```
*La raya (~) significa tu carpeta de usuario*

### 6. Crear una carpeta
```
mkdir nombre-carpeta
```
*mkdir = "make directory"*

**Ejemplo:**
```
mkdir mi-proyecto
```

### 7. Crear un archivo
```
touch nombre-archivo.txt
```
*Crea un archivo vacío*

### 8. Ver el contenido de un archivo
```
cat nombre-archivo.txt
```
*Te muestra lo que hay dentro*

### 9. Copiar un archivo
```
cp archivo-original.txt copia-archivo.txt
```

### 10. Mover o renombrar un archivo
```
mv nombre-viejo.txt nombre-nuevo.txt
```

### 11. Borrar un archivo
```
rm nombre-archivo.txt
```
*¡Cuidado! Se borra para siempre*

### 12. Borrar una carpeta vacía
```
rmdir nombre-carpeta
```

### 13. Borrar una carpeta con contenido
```
rm -r nombre-carpeta
```
*-r significa "recursivo" (borra todo adentro)*
*¡CUIDADO! Se borra TODO para siempre*

### 14. Limpiar la pantalla
```
clear
```
*O en Windows: cls*

## Ejemplo de una sesión normal

```
$ pwd
/Users/julian/Documents

$ ls
proyecto1  proyecto2  README.md

$ cd proyecto1
$ pwd
/Users/julian/Documents/proyecto1

$ ls
index.html  style.css  script.js

$ cat index.html
<!DOCTYPE html>
<html>
...

$ cd ..
$ pwd
/Users/julian/Documents
```

## Características útiles

### El símbolo $
```
$ tu-comando
```
El $ es solo el símbolo de la terminal, **no lo escribes**, ya está ahí.

### Autocompletado
Escribe las primeras letras y presiona **Tab** para autocompletar.

**Ejemplo:**
```
cd Docu[TAB] → cd Documentos
```

### Histórico de comandos
Presiona **Flecha Arriba** para ver comandos anteriores.

### Ejecutar comandos anteriores
Puedes reutilizar comandos con las flechas del teclado.

## Combinaciones útiles

### Ejecutar dos comandos seguidos
```
comando1 && comando2
```
*El segundo solo se ejecuta si el primero funcionó*

**Ejemplo:**
```
cd mi-proyecto && ls
```

### Ver más información de un comando
```
comando --help
```
*Te muestra la ayuda del comando*

## Comandos especiales para programadores

### Instalar programas (Node.js, Python, etc)
```
npm install nombre-paquete
```

### Ejecutar un programa
```
node archivo.js
```

### Ejecutar Python
```
python archivo.py
```

## El orden de la terminal (cheat sheet)

```
pwd          → ¿Dónde estoy?
ls / dir     → ¿Qué hay aquí?
cd carpeta   → Entrar en carpeta
cd ..        → Salir de carpeta
mkdir        → Crear carpeta
touch        → Crear archivo
cat          → Ver contenido
cp           → Copiar
mv           → Mover/Renombrar
rm           → Borrar archivo
rm -r        → Borrar carpeta
clear / cls  → Limpiar pantalla
```

## Consejos prácticos

1. **Usa Tab para autocompletar** - Ahorra tiempo y evita errores
2. **Usa las flechas** - Para revisar comandos anteriores
3. **Ten cuidado con rm** - No hay papelera de reciclaje
4. **Usa ls antes de cd** - Para ver qué carpetas hay
5. **Si te pierdes, usa cd ~** - Vuelve a casa

## Mensajes comunes que verás

| Mensaje | Qué significa |
|---------|---------------|
| `No such file or directory` | El archivo/carpeta no existe |
| `Permission denied` | No tienes permiso |
| `command not found` | La orden no existe o no está instalada |
| `already exists` | El archivo/carpeta ya existe |

---

**¡Listo!** Con estos comandos básicos ya puedes hacer la mayoría de cosas en la terminal. 

**Recuerda:** Si algo sale mal, simplemente cierra la terminal y abre otra. ¡No te asustes!
