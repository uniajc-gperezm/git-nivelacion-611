# MARKDOWN - La guía fácil para bachilleres 📝

## ¿Qué es Markdown?

Markdown es una **forma simple de escribir texto con formato** sin usar un programa complicado como Word.

Es como si escribieras un mensaje de WhatsApp pero **le pides que se vea bonito y organizado**.

Con Markdown puedes hacer:
- **Texto en negrita**
- *Texto en cursiva*
- Listas
- Títulos
- Código
- Y mucho más

**Lo mejor:** Es súper simple y funciona en casi todo (GitHub, Discord, Slack, etc).

## ¿Por qué lo usamos en programación?

Los programadores usan Markdown porque:
1. Es fácil de leer (incluso sin ver el formato)
2. Se ve bien en GitHub
3. Es rápido de escribir
4. Funciona en documentación

## La sintaxis básica (sin complicarte)

### 1. Títulos

```
# Título grande (h1)
## Título mediano (h2)
### Título pequeño (h3)
#### Título más pequeño (h4)
```

**Cómo se ve:**
# Título grande (h1)
## Título mediano (h2)
### Título pequeño (h3)

*Usa # para los títulos. Más # = más pequeño*

---

### 2. Texto en negrita

```
Este es **texto en negrita**
O también así: __texto en negrita__
```

**Resultado:** Este es **texto en negrita**

---

### 3. Texto en cursiva

```
Este es *texto en cursiva*
O también así: _texto en cursiva_
```

**Resultado:** Este es *texto en cursiva*

---

### 4. Negrita Y cursiva

```
Este es ***texto en negrita y cursiva***
O también así: ___texto en negrita y cursiva___
```

**Resultado:** Este es ***texto en negrita y cursiva***

---

### 5. Listas sin orden

```
- Elemento 1
- Elemento 2
- Elemento 3
```

**Resultado:**
- Elemento 1
- Elemento 2
- Elemento 3

*También puedes usar * o + en lugar de -*

---

### 6. Listas ordenadas

```
1. Primer paso
2. Segundo paso
3. Tercer paso
```

**Resultado:**
1. Primer paso
2. Segundo paso
3. Tercer paso

---

### 7. Código en una línea

```
Usa `código` así para código dentro del texto
```

**Resultado:** Usa `código` así para código dentro del texto

---

### 8. Bloque de código

````
```
function hola() {
  console.log("¡Hola mundo!");
}
```
````

**Resultado:**
```
function hola() {
  console.log("¡Hola mundo!");
}
```

*También puedes especificar el lenguaje:*

````
```javascript
function hola() {
  console.log("¡Hola mundo!");
}
```
````

---

### 9. Separador (una línea)

```
---
```

O también:
```
***
```

**Resultado:**

---

### 10. Enlaces

```
[Texto del enlace](https://www.google.com)
```

**Resultado:** [Texto del enlace](https://www.google.com)

---

### 11. Imágenes

```
![Descripción](ruta-de-la-imagen.jpg)
```

**Ejemplo:**
```
![Logo de GitHub](https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png)
```

---

### 12. Citas (blockquote)

```
> Esto es una cita importante
```

**Resultado:**
> Esto es una cita importante

---

### 13. Tablas

```
| Nombre | Edad | Ciudad |
|--------|------|--------|
| Juan   | 18   | Madrid |
| María  | 20   | Barcelona |
```

**Resultado:**

| Nombre | Edad | Ciudad |
|--------|------|--------|
| Juan   | 18   | Madrid |
| María  | 20   | Barcelona |

---

### 14. Lista de tareas (checkboxes)

```
- [x] Tarea completada
- [ ] Tarea sin completar
- [x] Otra tarea hecha
```

**Resultado:**
- [x] Tarea completada
- [ ] Tarea sin completar
- [x] Otra tarea hecha

---

### 15. Texto tachado

```
~~Esto está tachado~~
```

**Resultado:** ~~Esto está tachado~~

---

## Ejemplo completo (un README real)

```markdown
# Mi Proyecto Increíble 🚀

Este es un proyecto para aprender programación.

## ¿Qué hace?

Calcula el promedio de tus notas y te dice si aprobaste o no.

## Requisitos

- Python 3.8 o superior
- Un corazón valiente 💪

## Instalación

```
git clone https://github.com/mi-usuario/mi-proyecto
cd mi-proyecto
pip install -r requirements.txt
```

## Cómo usar

```
python main.py
```

Luego sigue las instrucciones.

## Mis mejores notas

| Materia | Nota |
|---------|------|
| Matemáticas | 9.5 |
| Programación | 10 |
| Inglés | 8.0 |

## Autor

Yo mismo 😎

## Licencia

MIT
```

---

## Resumen rápido (cheat sheet)

```
#              Título
##             Subtítulo
###            Sección

**texto**      Negrita
*texto*        Cursiva
***texto***    Negrita y cursiva
~~texto~~      Tachado

`código`       Código en línea
```código```   Bloque de código

[enlace](url)  Enlace

---                Separador

> cita           Cita

-Elemento        Lista

1. Elemento      Lista ordenada

| col | col |    Tabla

[x]              Checkbox
```

---

## Consejos para escribir buen Markdown

1. **Usa espacios en blanco** - Separa las secciones para que sea más fácil leer
2. **Sé consistente** - Si usas # usa siempre #, no mezcles con otras cosas
3. **Estructura tu documento** - Como si fuera un ensayo, con introducción, cuerpo y conclusión
4. **Usa listas** - Cuando tengas múltiples cosas, las listas quedan mejor que párrafos largos
5. **Destaca lo importante** - Usa negrita para lo que realmente importa

## Lugares donde se usa Markdown

- **GitHub**: En los README.md
- **Discord**: En los mensajes
- **Reddit**: Para los posts
- **Slack**: En los canales
- **Documentación**: Casi toda la documentación en internet
- **Blogs**: Muchos blogs usan Markdown
- **Obsidian**: Aplicación de notas (muy usada por estudiantes)

---

## Práctica: Escribe tu primer Markdown

Intenta crear un archivo llamado `PRACTICA.md` y escribe:
- Un título con tu nombre
- Una sección "Sobre mí" con 3 características tuyas en negrita
- Una sección "Mis materias favoritas" con una lista
- Una tabla con tus notas
- Una cita que te inspire

---

**¡Listo!** Ahora ya sabes Markdown. Es así de simple. Úsalo para documentar tu código y verás que la gente lo entiende mucho mejor. 📚
