# Dia 12: Pizzeria Spring Boot - API REST Completa

**Curso IFCD0014 -- Semana 3, Dia 12**

---

## Objetivos del dia

- Migrar la Pizzeria de Hibernate puro a Spring Boot + Spring Data JPA
- Modelar 3 entidades con relaciones JPA en el contexto de Spring
- Implementar la arquitectura Controller > Service > Repository completa
- Poblar datos iniciales con `data.sql`
- Probar todos los endpoints con Postman o Swagger UI

## Conceptos clave

La migracion de Hibernate puro a Spring Data JPA es sorprendentemente simple: reemplazas `EntityManager` por `JpaRepository`, eliminas `persistence.xml` (Spring usa `application.properties`), y Spring gestiona las transacciones automaticamente. El codigo de negocio en el servicio casi no cambia.

Spring Data JPA genera implementaciones automaticas a partir de nombres de metodos. `findByNombre(String nombre)` genera el SQL `SELECT * FROM pizza WHERE nombre = ?` sin que escribas una sola linea de implementacion. Para consultas complejas, se usa `@Query` con JPQL.

El archivo `data.sql` en `src/main/resources` se ejecuta automaticamente al iniciar la aplicacion, insertando datos de prueba. Esto permite tener un entorno listo para probar sin configuracion manual.

## Que vas a construir

Pizzeria v6: una API REST completa con Spring Boot. Tres entidades (Pizza, Cliente, Pedido) con relaciones, tres controladores con endpoints CRUD, servicios con logica de negocio y datos precargados.

## Arquitectura sugerida

```
com.curso.pizzeria/
  modelo/
    Pizza.java (@Entity, @Data)
    Cliente.java (@Entity, @Data)
    Pedido.java (@Entity, @ManyToOne, @ManyToMany)
  repositorio/
    PizzaRepository.java (extends JpaRepository)
    ClienteRepository.java
    PedidoRepository.java
  servicio/
    PizzaService.java (@Service)
    ClienteService.java
    PedidoService.java
  controlador/
    PizzaController.java (@RestController)
    ClienteController.java
    PedidoController.java
  PizzeriaApplication.java (@SpringBootApplication)
```

## Ejercicios

1. Crear un proyecto Spring Boot con Initializr y configurar `application.properties` para H2 y Swagger
2. Definir las 3 entidades con sus relaciones (`@ManyToOne` en Pedido>Cliente, `@ManyToMany` en Pedido>Pizza)
3. Crear los 3 repositorios con metodos de busqueda personalizados (`findByNombreContaining`, `findByClienteId`)
4. Implementar los servicios con logica de negocio (validar que un pedido tiene al menos una pizza)
5. Crear `data.sql` con INSERT de 5 pizzas, 3 clientes y 2 pedidos de prueba

## Verificacion

- [ ] La aplicacion inicia con `mvn spring-boot:run` y los datos de `data.sql` se cargan
- [ ] GET /api/pizzas devuelve las 5 pizzas precargadas
- [ ] POST /api/pedidos crea un pedido asociado a un cliente con varias pizzas
- [ ] GET /api/pedidos/{id} devuelve el pedido con los datos del cliente y las pizzas
- [ ] DELETE /api/pizzas/{id} falla si la pizza esta en un pedido (integridad referencial)

## Profundiza con el libro

En *Arquitectura de Sistemas Enterprise* de @TodoEconometria, el capitulo "Spring Data JPA: del boilerplate a la productividad" compara el codigo de Hibernate puro (dia 10) con Spring Data JPA (hoy) linea por linea, mostrando la reduccion de codigo y las convenciones que lo hacen posible.

---
Curso IFCD0014 | Prof. Juan Marcelo Gutierrez Miranda | @TodoEconometria
