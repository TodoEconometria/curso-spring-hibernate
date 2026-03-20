# Dia 14: Proyecto Personal - Completar y Profesionalizar

**Curso IFCD0014 -- Semana 3, Dia 14**

---

## Objetivos del dia

- Completar todos los endpoints REST para las 3 entidades
- Implementar validacion de datos con `@Valid` y anotaciones de Bean Validation
- Crear un `GlobalExceptionHandler` con `@ControllerAdvice`
- Documentar y probar la API con una coleccion Postman
- Subir la version completa a GitHub

## Conceptos clave

Bean Validation permite declarar restricciones directamente en la entidad: `@NotNull`, `@NotBlank`, `@Min`, `@Max`, `@Email`, `@Size`. Spring las aplica automaticamente cuando el controlador recibe un `@RequestBody` anotado con `@Valid`. Si falla la validacion, Spring devuelve un error 400.

El `GlobalExceptionHandler` con `@ControllerAdvice` centraliza el manejo de errores. En vez de try-catch en cada controlador, defines metodos con `@ExceptionHandler` que capturan excepciones especificas y devuelven respuestas HTTP apropiadas (404 para entidad no encontrada, 400 para datos invalidos, 409 para conflictos).

Una coleccion Postman organiza todos los requests de tu API: los endpoints de cada entidad con ejemplos de body, headers y respuestas esperadas. Es la forma profesional de documentar y probar una API, y la usaras en la demo del dia 20.

## Que vas a construir

La version completa de tu proyecto personal: todas las entidades con CRUD, validaciones, manejo de errores centralizado, datos de prueba en `data.sql` y coleccion Postman exportada.

## Arquitectura sugerida

```
src/main/java/com/tu/proyecto/
  modelo/          (3+ entidades con @Valid)
  repositorio/     (3 repositorios JPA)
  servicio/        (3 servicios con logica)
  controlador/     (3 controladores REST)
  excepcion/
    GlobalExceptionHandler.java
    RecursoNoEncontradoException.java
    DatosInvalidosException.java
src/main/resources/
  application.properties
  data.sql
```

## Ejercicios

1. Completar los controladores y servicios de las entidades restantes (las que faltan del dia 13)
2. Agregar validaciones `@NotBlank`, `@Min`, `@Email` (segun corresponda) en las entidades y `@Valid` en los controladores
3. Crear `GlobalExceptionHandler` que maneje: `RecursoNoEncontradoException` (404), `MethodArgumentNotValidException` (400), `DataIntegrityViolationException` (409)
4. Crear `data.sql` con datos de prueba para las 3 entidades
5. Crear una coleccion Postman con todos los endpoints, exportarla como JSON y guardarla en el repositorio

## Verificacion

- [ ] Las 3 entidades tienen CRUD completo funcionando
- [ ] Enviar datos invalidos devuelve 400 con mensajes claros
- [ ] Buscar un ID inexistente devuelve 404 con un JSON de error (no un stacktrace)
- [ ] La coleccion Postman permite probar toda la API con un click
- [ ] El proyecto esta subido a GitHub con commits descriptivos

## Profundiza con el libro

En *Arquitectura de Sistemas Enterprise* de @TodoEconometria, el capitulo "APIs REST robustas" cubre validacion avanzada (validaciones custom, grupos de validacion), estrategias de manejo de errores y como disenar respuestas de error consistentes siguiendo el estandar RFC 7807 (Problem Details).

---
Curso IFCD0014 | Prof. Juan Marcelo Gutierrez Miranda | @TodoEconometria
