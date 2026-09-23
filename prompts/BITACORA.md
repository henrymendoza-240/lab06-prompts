# Bitacora de prompts

Laboratorio 06: Fundamentos de Ingenieria de Prompts.

Herramienta de IA usada: ChatGPT (o Gemini / Claude / Copilot)

## Ejercicio 2: Tokens y ventana de contexto

### 1. Tabla de conteo de tokens
| Texto | Caracteres | Tokens |
|-------|------------|--------|
| Los estudiantes programan en Java. | 34 | 7 |
| The students program in Java. | 29 | 6 |
| desafortunadamente | 18 | 4 |

### 2. Explicacion de la ventana de contexto
En el mismo chat la IA recordaba que la aplicacion se llamaba TiendaTec y usaba Java Swing porque esa informacion estaba almacenada dentro de su ventana de contexto activa. Al abrir un chat nuevo, la ventana de contexto inicio totalmente vacia, por lo que la IA no tenia forma de acceder a los datos anteriores.

## Ejercicio 3: Temperatura

### 1. Resultados del simulador en Java
| Temperatura | % de BiblioTec | Nombres en los 5 intentos |
|-------------|----------------|---------------------------|
| 0 | 100.0% | BiblioTec, BiblioTec, BiblioTec, BiblioTec, BiblioTec |
| 0.5 | 65.3% | BiblioTec, LibroYa, BiblioTec, BiblioTec, BiblioTec |
| 1 | 44.5% | PrestaLibro, LibroYa, LibroYa, LibroYa, BiblioTec |
| 1.8 | 32.2% | LibroYa, PrestaLibro, LectoGo, BiblioTec, PrestaLibro |

### 2. Interpretacion
Al aumentar la temperatura, los porcentajes de probabilidad se distribuyen entre todas las opciones, haciendo que los nombres generados en los 5 intentos sean mas variados y creativos. El simulador nunca inventa un nombre nuevo fuera de la lista porque la temperatura solo altera el riesgo al elegir entre las opciones conocidas, no le agrega conocimientos adicionales.

## Ejercicio 4: Prompt vago vs estructurado

| Criterio | Prompt vago | Prompt estructurado |
|----------|-------------|---------------------|
| Menciona el objetivo del sistema | No | Si |
| Menciona a los usuarios principales | No | Si |
| Tiene exactamente 3 funcionalidades | No | Si |
| Esta en 3 parrafos | No | Si |
| Lo usaria en un informe real | No | Si |

## Ejercicio 5: Anatomia de un prompt

### 1. Tabla de componentes
| Componente | Texto de mi prompt |
|------------|--------------------|
| Rol | Actua como desarrollador Java. |
| Instruccion | Crea un programa en Java para gestionar los productos de una tienda usando una clase Producto con los atributos codigo, nombre, precio y stock. |
| Contexto | La tienda requiere un modelo basico en memoria para administrar su inventario. |
| Formato | Explica primero la estructura de la clase y luego presenta el codigo Java. |
| Ejemplo | Usa este estilo para los metodos: getPrecio(), setPrecio(double precio). |

### 2. Evolucion nivel a nivel
- **Nivel 1:** Genero un codigo generico simple sin atributos definidos.
- **Nivel 2 (Rol):** Adopto un estilo mas profesional de programacion.
- **Nivel 3 (Contexto):** Enfoco el programa al dominio de una tienda comercial.
- **Nivel 4 (Instruccion):** Agrego exactamente los cuatro atributos solicitados a la clase.
- **Nivel 5 (Formato + Ejemplo):** Organizo la respuesta separando la explicacion del codigo y aplico la convencion exacta de nombres solicitada.

## Ejercicio 6: Del prompt basico al profesional

### 1. Evaluacion de la respuesta profesional
| Criterio | Cumple (Si / No) |
|----------|------------------|
| ¿Esta escrito en Java y usa Swing? | Si |
| ¿Pide correo y contraseña? | Si |
| ¿Explica el funcionamiento antes o despues del codigo? | Si |
| ¿El codigo esta organizado en clases? | Si |
| ¿Valida los datos que ingresa el usuario? | No |

### 2. Prompt profesional mejorado (con restricciones e iteracion)
```text
Actua como desarrollador Java. Crea un ejemplo de login para una aplicacion de escritorio utilizando Swing. El usuario debe ingresar correo y contrasena. Explica brevemente el funcionamiento y presenta el codigo organizado por clases.

Mejora el codigo anterior con estas restricciones: no uses librerias externas, valida que el correo contenga @ y que la contrasena tenga al menos 8 caracteres, y muestra los mensajes con JOptionPane.