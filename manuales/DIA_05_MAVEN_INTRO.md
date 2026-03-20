# Dia 5: Maven Basico y Puente a Spring

**Curso IFCD0014 -- Semana 1, Dia 5**

---

## Objetivos del dia

- Entender Maven como herramienta de build: compilar, testear y empaquetar con un comando
- Crear un proyecto Maven desde cero con la estructura estandar
- Leer y modificar el archivo `pom.xml` (groupId, artifactId, dependencies)
- Conocer Streams API y Optional como herramientas del Java moderno
- Identificar los conceptos del curso que se vienen: Hibernate, Spring, Docker

## Conceptos clave

Maven aplica el principio "convention over configuration": si colocas el codigo en `src/main/java` y los tests en `src/test/java`, Maven sabe que hacer sin configuracion adicional. El archivo `pom.xml` declara las dependencias y Maven las descarga automaticamente desde Maven Central.

La Streams API (Java 8+) permite procesar colecciones de forma declarativa: `lista.stream().filter(...).map(...).collect(...)`. En vez de escribir bucles `for`, describes QUE quieres obtener. `Optional<T>` elimina los `NullPointerException` al representar explicitamente la ausencia de valor.

Estos dos conceptos (Maven para gestionar dependencias, Streams para procesar datos) son el puente entre el Java basico de esta semana y el ecosistema profesional (Hibernate, Spring) de las semanas siguientes.

## Que vas a construir

Un proyecto Maven funcional con la Pizzeria v2 migrada a la estructura Maven estandar, aplicando Streams para filtrar pizzas por categoria, calcular estadisticas de pedidos y buscar con Optional.

## Arquitectura sugerida

```
pizzeria-maven/
  pom.xml
  src/
    main/java/com/curso/pizzeria/
      modelo/
      repositorio/
      servicio/
      excepcion/
      App.java
    test/java/com/curso/pizzeria/
      servicio/
        PizzaServiceTest.java
```

## Ejercicios

1. Crear un proyecto Maven (manualmente o con `mvn archetype:generate`) con groupId `com.curso` y artifactId `pizzeria`
2. Migrar la Pizzeria v2 a la estructura `src/main/java` de Maven y verificar que compila con `mvn compile`
3. Usar Streams para implementar `buscarPorTamano(Tamano t)` que filtre y devuelva una lista
4. Implementar `buscarPorId()` que devuelva `Optional<Pizza>` en vez de `null`
5. Calcular con Streams el precio promedio de todas las pizzas y el pedido mas caro (`mapToDouble`, `average`, `max`)

## Verificacion

- [ ] `mvn compile` compila sin errores
- [ ] `mvn package` genera un JAR en la carpeta `target/`
- [ ] Los metodos de busqueda usan Streams en vez de bucles for
- [ ] `buscarPorId()` devuelve `Optional<Pizza>` y se usa con `ifPresent()` o `orElseThrow()`
- [ ] Puedes explicar que hace cada seccion del `pom.xml`

## Profundiza con el libro

El capitulo "Maven y el ecosistema de build" en *Arquitectura de Sistemas Enterprise* de @TodoEconometria conecta la gestion de dependencias de Maven con Spring Boot Starters, y explica por que entender `pom.xml` es esencial antes de trabajar con Spring Initializr.

---
Curso IFCD0014 | Prof. Juan Marcelo Gutierrez Miranda | @TodoEconometria
