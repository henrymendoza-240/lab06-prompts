# Tarea: Mi prompt profesional

## Funcionalidad elegida
Modulo de registro de clientes para una tienda de comercio electronico.

## Version 1: Prompt basico
```text
Hazme un codigo para registrar clientes.
```
## Version 2
```text
Actua como desarrollador Java. Crea una clase para registrar clientes en un sistema de ventas. Debe incluir campos como nombre, correo y telefono.
```
## Version 3: prompt final
 ```text
Actua como desarrollador Java Senior. Diseña un modulo de registro de clientes para una plataforma de e-commerce.

Instrucciones: Crea una clase Cliente con los atributos id, nombre, correo y telefono. Incluye un metodo para validar los datos de entrada antes de registrar.

Restricciones: No uses librerias externas, no permitas correos sin '@', ni nombres vacios.

Ejemplo de salida de validacion: "Error: El correo debe contener un arroba (@)".

Formato: Presenta primero una breve explicacion de la arquitectura en 2 parrafos y luego el codigo Java dentro de un bloque estructurado.
```
## Componentes del prompt final
| Componente | Texto de mi prompt |
|------------|--------------------|
| Rol | Actua como desarrollador Java Senior. |
| Instruccion | Crea una clase Cliente con los atributos id, nombre, correo y telefono e incluye un metodo para validar los datos de entrada. |
| Contexto | Diseña un modulo de registro de clientes para una plataforma de e-commerce. |
| Formato | Presenta primero una breve explicacion de la arquitectura en 2 parrafos y luego el codigo Java dentro de un bloque estructurado. |
| Ejemplo | Ejemplo de salida de validacion: "Error: El correo debe contener un arroba (@)". |
## Evaluacion del resultado
 | Criterio | Cumple (Si / No) |
|----------|------------------|
| ¿El codigo esta escrito en Java puro sin librerias externas? | Si |
| ¿Incluye las validaciones de correo y nombre? | Si |
| ¿Presenta la explicacion de arquitectura en 2 parrafos? | Si |
| ¿Proporciona mensajes de error claros segun el ejemplo? | Si |
## Errores que evite
1. **Ser demasiado general**: En la V1 no indique lenguaje ni atributos, lo que genero un codigo inutil en Python. Lo evite especificando Java, los campos exactos y el dominio del proyecto en la V3.

2. **No indicar el formato:** En la V1 y V2 la IA entrego la respuesta dispersa. Lo evite exigiendo 2 parrafos explicativos de arquitectura seguidos por el bloque de codigo.