# Dia 4: Arquitectura por Capas y Patrones

**Curso IFCD0014 -- Semana 1, Dia 4**

---

## Objetivos del dia

- Organizar el codigo en paquetes por responsabilidad (modelo, repositorio, servicio, excepcion)
- Implementar el patron Repository para separar el acceso a datos
- Crear una capa de servicio con logica de negocio
- Definir excepciones personalizadas para errores del dominio
- Aplicar inyeccion de dependencias manual (constructor injection)

## Conceptos clave

La arquitectura por capas separa responsabilidades: el **modelo** define los datos, el **repositorio** los almacena y recupera, el **servicio** contiene la logica de negocio, y la **excepcion** maneja errores del dominio. Cada capa solo conoce a la inmediata inferior.

El patron Repository abstrae el almacenamiento. Hoy usamos un `HashMap` en memoria, pero la interfaz sera la misma cuando migremos a Hibernate (dia 10) y a Spring Data JPA (dia 12). Esta es la potencia de programar contra interfaces.

La inyeccion de dependencias manual significa que el `PizzaService` recibe su `PizzaRepository` por constructor en vez de crearlo internamente. Esto permite cambiar la implementacion sin tocar el servicio. Es exactamente lo que Spring automatiza con `@Autowired`.

## Que vas a construir

Refactorizar la Pizzeria v1 en una Pizzeria v2 con paquetes organizados, repositorios con `HashMap`, servicios con validaciones, y excepciones como `PizzaNoEncontradaException`.

## Arquitectura sugerida

```
com.curso.pizzeria/
  modelo/
    Pizza.java, PizzaClasica.java, PizzaGourmet.java
    Pedido.java, Tamano.java (enum)
    Vendible.java, Preparable.java
  repositorio/
    PizzaRepository.java (interfaz)
    PizzaRepositoryImpl.java (HashMap)
  servicio/
    PizzaService.java
    PedidoService.java
  excepcion/
    PizzaNoEncontradaException.java
    PedidoVacioException.java
  App.java (main, instancia repositorios y servicios)
```

## Ejercicios

1. Crear los paquetes `modelo`, `repositorio`, `servicio` y `excepcion` y mover las clases existentes
2. Definir la interfaz `PizzaRepository` con metodos `guardar()`, `buscarPorId()`, `listarTodas()`, `eliminar()`
3. Implementar `PizzaRepositoryImpl` usando un `HashMap<Integer, Pizza>` como almacen
4. Crear `PizzaService` que reciba `PizzaRepository` por constructor y agregue validaciones (pizza no nula, precio positivo)
5. Implementar `PizzaNoEncontradaException` (extends `RuntimeException`) y lanzarla cuando se busca un ID inexistente

## Verificacion

- [ ] El proyecto compila con la estructura de paquetes correcta
- [ ] `PizzaService` no conoce `PizzaRepositoryImpl`, solo la interfaz
- [ ] Al buscar una pizza inexistente, se lanza `PizzaNoEncontradaException`
- [ ] Se puede cambiar `PizzaRepositoryImpl` por otra implementacion sin modificar el servicio
- [ ] El `main()` crea las dependencias y las inyecta por constructor

## Profundiza con el libro

En *Arquitectura de Sistemas Enterprise* de @TodoEconometria, el capitulo "Patrones Repository y Service" detalla como esta separacion por capas es el esqueleto de toda aplicacion Spring Boot, y como la DI manual que haces hoy es exactamente lo que el contenedor de Spring automatiza.

---
Curso IFCD0014 | Prof. Juan Marcelo Gutierrez Miranda | @TodoEconometria
