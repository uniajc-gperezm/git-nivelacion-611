 # Markdown básico para documentar código en GitHub

Markdown es un lenguaje sencillo para dar formato a texto usando caracteres especiales. GitHub interpreta los archivos con extensión `.md` y muestra el resultado como una página web.

## 1. Títulos

Se crean usando el símbolo `#`. La cantidad de símbolos indica el nivel del título:

```markdown
# Título principal
## Sección
### Subsección
```

Recomendación: usar un solo título principal (`#`) y organizar el resto con títulos secundarios.

## 2. Texto y saltos de línea

```markdown
Este es un párrafo de texto.

Este es otro párrafo separado por una línea vacía.
```

Para forzar un salto de línea dentro del mismo párrafo, se pueden dejar dos espacios al final de la línea o usar `<br>`:

```markdown
Primera línea  
Segunda línea
```

## 3. Énfasis

```markdown
**Texto en negrita**
*Texto en cursiva*
***Texto en negrita y cursiva***
~~Texto tachado~~
```

Resultado: **Texto en negrita**, *texto en cursiva*, ***texto importante*** y ~~texto eliminado~~.

## 4. Listas

### Lista sin orden

```markdown
- Elemento uno
- Elemento dos
	- Sub-elemento
```

Resultado:

- Elemento uno
- Elemento dos
	- Sub-elemento

### Lista numerada

```markdown
1. Instalar el programa
2. Crear el proyecto
3. Ejecutar las pruebas
```

### Lista de tareas

GitHub muestra casillas de verificación:

```markdown
- [x] Crear la estructura del proyecto
- [ ] Agregar las pruebas
- [ ] Actualizar la documentación
```

## 5. Código

Para mencionar un comando, nombre de archivo, variable o función dentro de una oración, usar una comilla invertida:

```markdown
Ejecute el comando `git status` desde la terminal.
```

Para bloques de varias líneas, usar tres comillas invertidas. Después de las comillas se puede indicar el lenguaje para activar el resaltado de sintaxis:

````markdown
```javascript
function saludar(nombre) {
	return `Hola, ${nombre}`;
}
```
````

Ejemplo mostrado por GitHub:

```javascript
function saludar(nombre) {
	return `Hola, ${nombre}`;
}
```

Algunos identificadores frecuentes son `javascript`, `python`, `java`, `html`, `css`, `json`, `sql`, `bash` y `markdown`.

## 6. Enlaces

```markdown
[Texto que verá el lector](https://github.com)
```

Ejemplo: [Visitar GitHub](https://github.com).

Para enlazar otro archivo del mismo repositorio, usar una ruta relativa:

```markdown
Consulta la [guía de Git](GIT.md).
```

También se puede enlazar una sección del mismo documento usando el texto del título convertido normalmente a minúsculas y separado por guiones:

```markdown
[Ir a la sección de código](#5-código)
```

## 7. Imágenes

```markdown
![Descripción de la imagen](ruta/de/la/imagen.png)
```

El texto entre corchetes es importante porque describe la imagen si no puede cargarse y mejora la accesibilidad.

## 8. Citas y notas

Una cita se escribe con `>`:

```markdown
> Una buena documentación explica qué hace el código y cómo ejecutarlo.
```

Resultado:

> Una buena documentación explica qué hace el código y cómo ejecutarlo.

Para mostrar una advertencia o una información destacada, GitHub permite usar estas formas:

```markdown
> [!NOTE]
> Esta función requiere una versión reciente de Node.js.

> [!WARNING]
> No guardes contraseñas ni tokens en el repositorio.
```

## 9. Tablas

Las tablas se construyen separando columnas con `|`:

```markdown
| Comando | Propósito |
| --- | --- |
| `git status` | Consultar el estado del repositorio |
| `git add` | Preparar cambios |
| `git commit` | Guardar cambios en el historial |
```

Resultado:

| Comando | Propósito |
| --- | --- |
| `git status` | Consultar el estado del repositorio |
| `git add` | Preparar cambios |
| `git commit` | Guardar cambios en el historial |

Se puede alinear el contenido usando dos puntos:

```markdown
| Izquierda | Centro | Derecha |
| :--- | :---: | ---: |
| Texto | Texto | Texto |
```

## 10. Separadores y caracteres especiales

Un separador horizontal se crea con tres guiones:

```markdown
---
```

Para mostrar literalmente un carácter que Markdown interpreta como formato, anteponer una barra invertida:

```markdown
\*Este texto no aparecerá en cursiva\*
```

## 11. Estructura recomendada para documentar un proyecto

Un archivo `README.md` puede seguir esta estructura:

````markdown
# Nombre del proyecto

Descripción breve del problema que resuelve el proyecto.

## Requisitos

- Python 3.12
- Git

## Instalación

```bash
git clone https://github.com/usuario/proyecto.git
cd proyecto
```

## Uso

```bash
python main.py
```

## Estructura del proyecto

```text
proyecto/
├── src/
├── tests/
└── README.md
```

## Funcionalidades

- [x] Crear usuarios
- [ ] Agregar autenticación

## Autor

Nombre del estudiante
````

## 12. Buenas prácticas para documentar código

- Explicar primero qué problema resuelve el proyecto.
- Indicar los requisitos antes de mostrar los comandos de instalación.
- Usar bloques de código con el lenguaje correcto.
- Mostrar ejemplos que se puedan copiar y ejecutar.
- Explicar los parámetros importantes de las funciones o comandos.
- Mantener actualizados los nombres de archivos, rutas y comandos.
- No publicar contraseñas, claves API, tokens ni información privada.
- Usar nombres descriptivos en los enlaces y en el texto alternativo de las imágenes.

## Ejemplo corto de documentación de una función

````markdown
### `calcular_total(precio, cantidad)`

Calcula el valor total de un producto.

```python
def calcular_total(precio, cantidad):
		return precio * cantidad
```

**Parámetros:**

- `precio`: valor unitario del producto.
- `cantidad`: número de unidades.

**Retorna:** el valor total de la compra.

**Ejemplo:**

```python
total = calcular_total(15000, 2)
print(total)  # 30000
```
````

La vista previa de GitHub permite comprobar cómo se verá el archivo antes de compartirlo. También es recomendable revisar los enlaces, ejecutar los ejemplos y confirmar que las rutas relativas funcionen desde el repositorio.
