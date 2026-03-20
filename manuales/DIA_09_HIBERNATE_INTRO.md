# Dia 9: Hibernate y JPA - Introduccion a la Persistencia

**Curso IFCD0014 -- Semana 2, Dia 9**

---

## Objetivos del dia

- Entender el problema de la impedancia objeto-relacional (por que necesitamos un ORM)
- Diferenciar JPA (especificacion) de Hibernate (implementacion)
- Configurar `persistence.xml` y conectar con H2 en memoria
- Mapear una clase Java como `@Entity` con `@Id`, `@GeneratedValue`, `@Column`
- Realizar operaciones CRUD con `EntityManager` y consultas con JPQL

## Conceptos clave

Las bases de datos relacionales guardan datos en tablas con filas y columnas. Java trabaja con objetos que tienen atributos y metodos. Esta diferencia se llama "impedancia objeto-relacional". Un ORM (Object-Relational Mapping) como Hibernate traduce automaticamente entre los dos mundos: un objeto Java se convierte en una fila, y viceversa.

JPA (Java Persistence API) es la especificacion estandar: define las anotaciones (`@Entity`, `@Id`, `@Column`) y las interfaces (`EntityManager`). Hibernate es la implementacion mas usada de JPA. Esto significa que tu codigo usa anotaciones de JPA, y Hibernate se encarga de generar el SQL real.

H2 es una base de datos en memoria ideal para desarrollo. No requiere instalacion: se incluye como dependencia Maven y se crea al iniciar la aplicacion. Los datos desaparecen al cerrar. En produccion se reemplaza por PostgreSQL o MySQL sin cambiar el codigo Java.

## Que vas a construir

Un proyecto Maven con Hibernate que persista entidades `Libro` en H2. El programa crea libros, los guarda en la base de datos, los consulta por ID y por titulo con JPQL, los actualiza y los elimina.

## Arquitectura sugerida

```mermaid
graph TB
    A[Codigo Java] -->|@Entity| B[JPA / Hibernate]
    B -->|SQL automatico| C[Base de Datos H2]
    D[persistence.xml] -->|configura| B
    E[EntityManager] -->|CRUD + JPQL| B
```

## Ejercicios

1. Crear un proyecto Maven con dependencias de Hibernate, JPA y H2 en el `pom.xml`
2. Configurar `persistence.xml` en `src/main/resources/META-INF/` con conexion a H2
3. Crear la entidad `Libro` con `@Entity`, `@Id`, `@GeneratedValue`, `@Column` y atributos: titulo, autor, precio, anioPublicacion
4. Implementar un CRUD completo con `EntityManager`: persist, find, merge, remove
5. Escribir consultas JPQL: buscar libros por autor, listar libros con precio mayor a X, contar libros por anio

## Verificacion

- [ ] Hibernate genera las tablas automaticamente al iniciar (ver SQL en la consola)
- [ ] Se pueden crear, leer, actualizar y eliminar libros sin escribir SQL manual
- [ ] Las consultas JPQL devuelven resultados correctos
- [ ] `persistence.xml` tiene la propiedad `hibernate.hbm2ddl.auto=create` para desarrollo
- [ ] Puedes explicar la diferencia entre `persist()` (nuevo) y `merge()` (actualizar)

## Profundiza con el libro

En *Arquitectura de Sistemas Enterprise* de @TodoEconometria, el capitulo "JPA e Hibernate: mapeando el mundo relacional" profundiza en las estrategias de generacion de ID, los estados del ciclo de vida de una entidad (transient, managed, detached, removed) y cuando usar JPQL vs Criteria API.

---
Curso IFCD0014 | Prof. Juan Marcelo Gutierrez Miranda | @TodoEconometria
