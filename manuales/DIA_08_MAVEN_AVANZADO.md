# Dia 8: Maven Avanzado y Testing con JUnit 5

**Curso IFCD0014 -- Semana 2, Dia 8**

---

## Objetivos del dia

- Entender los scopes de dependencias Maven (compile, test, provided, runtime)
- Configurar perfiles Maven para entornos dev y prod
- Escribir tests unitarios con JUnit 5 (@Test, @BeforeEach, assertions)
- Testear la capa de servicio de la Pizzeria
- Conocer la estructura de un proyecto multi-modulo (conceptual)

## Conceptos clave

Los scopes de Maven controlan cuando una dependencia esta disponible. `compile` (por defecto) la incluye siempre. `test` solo durante los tests (JUnit). `provided` la proporciona el servidor (Servlet API). `runtime` solo en ejecucion (driver JDBC). Elegir el scope correcto mantiene el JAR final limpio.

Los perfiles Maven permiten configuraciones diferentes segun el entorno. Un perfil `dev` puede usar H2 en memoria, mientras que `prod` usa PostgreSQL. Se activan con `mvn package -Pdev` o `mvn package -Pprod`. Spring Boot tiene un mecanismo similar con `application-dev.properties`.

JUnit 5 es el framework de testing estandar en Java. Un test unitario verifica que un metodo individual funciona correctamente, aislado del resto del sistema. `@Test` marca un metodo como test. `@BeforeEach` prepara el estado antes de cada test. Las assertions (`assertEquals`, `assertThrows`, `assertTrue`) verifican los resultados.

## Que vas a construir

Una suite de tests para `PizzaService` y `PedidoService` que verifique la logica de negocio: crear pizzas validas, rechazar datos invalidos, calcular totales y manejar excepciones.

## Arquitectura sugerida

```
src/
  main/java/com/curso/pizzeria/
    servicio/PizzaService.java
    servicio/PedidoService.java
  test/java/com/curso/pizzeria/
    servicio/PizzaServiceTest.java
    servicio/PedidoServiceTest.java
```

## Ejercicios

1. Agregar JUnit 5 al `pom.xml` con scope `test` y crear la primera clase de test
2. Escribir un test que verifique que `PizzaService.crear()` devuelve una pizza con los datos correctos
3. Escribir un test que verifique que crear una pizza con precio negativo lanza `IllegalArgumentException`
4. Testear que `PedidoService.calcularTotal()` devuelve la suma correcta de los items
5. Configurar un perfil `dev` en el `pom.xml` que active un flag de debug y verificar con `mvn compile -Pdev`

## Verificacion

- [ ] `mvn test` ejecuta todos los tests y muestra resultados verdes
- [ ] Al menos 5 tests unitarios cubren la logica de `PizzaService` y `PedidoService`
- [ ] Un test verifica el comportamiento con datos invalidos (assertThrows)
- [ ] `mvn dependency:tree` muestra JUnit con scope `test`
- [ ] El perfil `dev` se activa correctamente con `-Pdev`

## Profundiza con el libro

El capitulo "Testing en la arquitectura enterprise" de *Arquitectura de Sistemas Enterprise* de @TodoEconometria explica la piramide de tests (unitarios > integracion > E2E) y como JUnit 5 se integra con Spring Boot Test para probar controladores y repositorios.

---
Curso IFCD0014 | Prof. Juan Marcelo Gutierrez Miranda | @TodoEconometria
