# La terminal: navegación y superpoderes básicos

La terminal es una aplicación que permite comunicarse con el sistema operativo escribiendo comandos. En lugar de buscar opciones con el mouse, se escribe una instrucción y el sistema muestra un resultado o ejecuta una acción.

Esta guía usa comandos de **Bash**, disponibles en Linux, macOS y Git Bash para Windows. Algunos comandos equivalentes de PowerShell aparecen en la sección de Windows.

## 1. Cómo funciona la terminal

Una línea de terminal suele tener esta forma:

```text
usuario@equipo:~/proyecto$ comando opcion argumento
```

- `usuario`: cuenta que está utilizando la terminal.
- `~/proyecto`: carpeta actual.
- `$`: indica que la terminal está lista para recibir un comando.
- `comando`: programa que se desea ejecutar.
- `opcion`: modifica el comportamiento del comando.
- `argumento`: archivo, carpeta o valor sobre el que trabaja el comando.

Ejemplo:

```bash
ls -la documentos
```

Aquí `ls` es el comando, `-la` son opciones y `documentos` es el argumento.

La terminal distingue entre mayúsculas y minúsculas: `Proyecto`, `proyecto` y `PROYECTO` pueden ser nombres diferentes.

## 2. Ayuda y comandos básicos

Antes de memorizar un comando, se puede consultar su ayuda:

```bash
comando --help
man comando
```

Por ejemplo:

```bash
git --help
ls --help
```

Comandos de información rápida:

```bash
pwd                 # Mostrar la carpeta actual
whoami              # Mostrar el usuario actual
date                # Mostrar fecha y hora
clear               # Limpiar la pantalla
history             # Mostrar comandos anteriores
```

También se puede usar la tecla `Flecha arriba` para recuperar comandos anteriores y `Tab` para autocompletar nombres de archivos o comandos.

## 3. Moverse por carpetas

### Mostrar la carpeta actual

```bash
pwd
```

`pwd` significa *print working directory*.

### Listar archivos y carpetas

```bash
ls                  # Lista básica
ls -l               # Lista detallada
ls -la              # Incluye archivos ocultos
ls -lah             # Incluye tamaños fáciles de leer
```

### Cambiar de carpeta

```bash
cd nombre-carpeta    # Entrar en una carpeta
cd ..                # Subir un nivel
cd ~                 # Ir a la carpeta personal
cd -                 # Volver a la carpeta anterior
cd /                 # Ir a la raíz del sistema
```

Una ruta puede ser **relativa** a la carpeta actual:

```bash
cd src/componentes
```

O **absoluta**, comenzando desde la raíz:

```bash
cd /home/estudiante/proyecto
```

Los espacios en nombres de archivos deben protegerse con comillas o con `\\`:

```bash
cd "Mi Proyecto"
cd Mi\\ Proyecto
```

## 4. Crear, copiar, mover y eliminar

Crear carpetas y archivos vacíos:

```bash
mkdir proyecto
mkdir -p proyecto/src/componentes
touch README.md
```

Copiar archivos o carpetas:

```bash
cp origen.txt copia.txt
cp -r carpeta-original carpeta-copia
```

Mover o cambiar el nombre:

```bash
mv archivo.txt documentos/
mv viejo-nombre.txt nuevo-nombre.txt
```

Eliminar archivos o carpetas:

```bash
rm archivo-temporal.txt
rm -r carpeta
```

`rm` elimina directamente y normalmente no envía los archivos a una papelera. Antes de usar `rm -r`, confirmar la ruta con `pwd` y `ls`. No ejecutar comandos destructivos que no se entiendan, especialmente:

```bash
rm -rf /
rm -rf *
```

## 5. Leer y editar archivos desde la terminal

```bash
cat README.md       # Mostrar el archivo completo
less README.md      # Leer página por página
head -n 10 archivo  # Mostrar las primeras 10 líneas
tail -n 10 archivo  # Mostrar las últimas 10 líneas
tail -f registro.log # Seguir un archivo que está creciendo
```

En `less` se puede usar `Espacio` para avanzar, `b` para retroceder y `q` para salir.

Para editar un archivo se puede usar el editor configurado en el equipo:

```bash
code README.md
```

En Git Bash, el comando `code` funciona cuando Visual Studio Code fue agregado al `PATH`.

## 6. Rutas, comodines y archivos ocultos

Los comodines permiten seleccionar varios nombres:

```bash
ls *.js       # Archivos que terminan en .js
ls src/*.py   # Archivos Python directamente dentro de src
ls archivo?.txt # Un solo carácter variable
```

Algunos archivos de configuración comienzan con punto y son ocultos:

```bash
ls -la
```

` .gitignore` y ` .env` son ejemplos comunes. No publiques archivos `.env` si contienen secretos.

## 7. Buscar archivos y texto

### Buscar archivos con `find`

```bash
find . -name "*.py"
find . -type f -name "README.md"
find . -type d -name "tests"
```

El punto (`.`) significa “desde la carpeta actual”.

### Buscar texto con `grep`

```bash
grep "TODO" archivo.js
grep -R "nombreFuncion" src/
grep -Rni "error" .
```

- `-R`: busca dentro de subcarpetas.
- `-n`: muestra el número de línea.
- `-i`: ignora mayúsculas y minúsculas.

En proyectos grandes, `rg` (*ripgrep*) suele ser más rápido:

```bash
rg "TODO|FIXME" src/
rg --files -g "*.js"
```

## 8. El superpoder principal: combinar comandos

La terminal permite conectar la salida de un comando con la entrada de otro usando una tubería (`|`):

```bash
ls -la | less
```

Ejemplos prácticos:

```bash
find . -type f | wc -l
git log --oneline | head -n 10
grep -Rni "TODO" src/ | less
history | tail -n 20
```

La idea general es:

```text
comando-que-produce-datos | comando-que-filtra-o-transforma
```

Otros comandos útiles para transformar resultados:

```bash
sort archivo.txt       # Ordenar líneas
uniq archivo.txt       # Eliminar repeticiones consecutivas
wc -l archivo.txt      # Contar líneas
cut -d, -f1 datos.csv  # Extraer una columna separada por comas
```

Ejemplo: contar las extensiones de archivos JavaScript encontrados:

```bash
find . -type f -name "*.js" | wc -l
```

## 9. Guardar y reutilizar resultados

La redirección `>` guarda la salida en un archivo y reemplaza su contenido:

```bash
ls -la > listado.txt
```

La redirección `>>` agrega información al final:

```bash
date >> actividad.log
```

Para mostrar la salida en pantalla y guardarla al mismo tiempo:

```bash
git status | tee estado.txt
```

La entrada estándar puede venir de un archivo usando `<`:

```bash
sort < nombres.txt
```

Hay que tener cuidado con `>` porque sobrescribe el archivo sin pedir confirmación en muchos entornos.

## 10. Variables y comandos encadenados

Una variable guarda un valor temporal:

```bash
NOMBRE="Ana"
echo "Hola, $NOMBRE"
```

Una variable útil es `$PATH`, que contiene las carpetas donde la terminal busca comandos:

```bash
echo "$PATH"
```

Los comandos pueden ejecutarse en secuencia:

```bash
mkdir practica && cd practica
```

`&&` ejecuta el segundo comando solo si el primero funciona. Esto es más seguro que continuar automáticamente después de un error.

También se puede ejecutar una instrucción y luego otra aunque la primera falle usando `;`:

```bash
echo "Inicio"; echo "Fin"
```

Para ejecutar una tarea en segundo plano se agrega `&`:

```bash
code . &
```

## 11. Procesos y programas

Consultar procesos activos:

```bash
ps
ps aux
```

Detener un comando que está ejecutándose:

```text
Ctrl + C
```

Pausar temporalmente un proceso:

```text
Ctrl + Z
```

Ver trabajos pausados o en segundo plano:

```bash
jobs
```

No es recomendable terminar procesos del sistema sin identificar primero su propósito.

## 12. Comandos útiles para proyectos

Desde la carpeta de un proyecto:

```bash
code .                 # Abrir la carpeta en Visual Studio Code
git status              # Consultar el estado de Git
git log --oneline       # Ver el historial resumido
npm install             # Instalar dependencias de un proyecto Node.js
npm test                # Ejecutar pruebas, si están configuradas
python main.py          # Ejecutar un programa Python
```

Antes de ejecutar un comando del proyecto, revisar su `README.md`, `package.json`, `requirements.txt` o archivo equivalente.

## 13. Equivalencias comunes en Windows PowerShell

Si no se usa Git Bash sino PowerShell, estos comandos son equivalentes o similares:

| Acción | Bash / Git Bash | PowerShell |
| --- | --- | --- |
| Carpeta actual | `pwd` | `Get-Location` |
| Listar archivos | `ls` | `Get-ChildItem` |
| Cambiar carpeta | `cd carpeta` | `Set-Location carpeta` |
| Copiar | `cp origen destino` | `Copy-Item origen destino` |
| Mover | `mv origen destino` | `Move-Item origen destino` |
| Eliminar | `rm archivo` | `Remove-Item archivo` |
| Buscar texto | `grep texto archivo` | `Select-String texto archivo` |
| Limpiar pantalla | `clear` | `Clear-Host` |

PowerShell también acepta alias como `ls`, `cd`, `cp`, `mv` y `rm`, pero sus opciones no siempre son iguales a las de Bash.

## 14. Flujo de práctica recomendado

```bash
mkdir practica-terminal
cd practica-terminal
mkdir src docs
touch src/app.js docs/notas.md
printf "console.log('Hola');\n" > src/app.js
find . -type f | sort
grep -Rni "console" .
cat src/app.js
```

Este ejercicio crea un proyecto pequeño, escribe código, busca archivos, encuentra texto y muestra el resultado sin abrir un explorador de archivos.

## 15. Reglas de seguridad

- Confirmar siempre la carpeta actual con `pwd` antes de mover o eliminar archivos.
- Inspeccionar una ruta con `ls` antes de usar `rm`, `mv` o `cp`.
- Evitar ejecutar comandos copiados de Internet sin entenderlos.
- No pegar contraseñas, tokens ni claves privadas en la terminal o en archivos del repositorio.
- No usar `sudo` o permisos de administrador salvo que sea necesario y se conozca el efecto.
- Recordar que `>` puede sobrescribir archivos y `rm` puede eliminarlos permanentemente.
- Usar `Ctrl + C` para detener un comando que parece quedarse ejecutándose.

La terminal se vuelve poderosa cuando se combinan comandos pequeños y verificables. La mejor práctica es avanzar paso a paso, revisar la salida y automatizar únicamente después de entender cada instrucción.
