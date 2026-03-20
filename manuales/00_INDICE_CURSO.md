# Indice del Curso IFCD0014 -- Spring e Hibernate

**100 horas | 20 dias | 5 semanas**

## Guias del Alumno

Cada archivo es la guia de referencia para un dia de clase. Siganlos en orden. Para los tutoriales paso a paso, consulta el libro *Arquitectura de Sistemas Enterprise* de @TodoEconometria.

---

### Semana 1: Fundamentos de Java y OOP (Dias 1-5, 25h)

| Dia | Archivo | Contenido |
|-----|---------|-----------|
| 1 | `DIA_01_FUNDAMENTOS_JAVA.md` | JDK 21, primer programa, variables, tipos, control de flujo, arrays |
| 2 | `DIA_02_POO_BASICA.md` | Clases, objetos, constructores, getters/setters, static, enums |
| 3 | `DIA_03_PIZZERIA_OOP.md` | Interfaces (Vendible, Preparable), clase abstracta Pizza, herencia, polimorfismo, Pedido |
| 4 | `DIA_04_ARQUITECTURA_CAPAS.md` | Paquetes por capa, patron Repository, Service, excepciones custom, DI manual |
| 5 | `DIA_05_MAVEN_INTRO.md` | Maven basico, pom.xml, Streams API, Optional, puente a Spring |

### Semana 2: Maven Avanzado e Hibernate (Dias 6-10, 25h)

| Dia | Archivo | Contenido |
|-----|---------|-----------|
| 6 | `DIA_06_MAVEN_STREAMS.md` | Ciclo de vida Maven, plugins, Streams pipelines, GPS Arquitectonico |
| 7 | `DIA_07_MAVEN_PIZZERIA.md` | Pizzeria como proyecto Maven, dependencia Gson, exportar pedidos a JSON |
| 8 | `DIA_08_MAVEN_AVANZADO.md` | Scopes de dependencias, perfiles dev/prod, JUnit 5, multi-modulo |
| 9 | `DIA_09_HIBERNATE_INTRO.md` | ORM, JPA vs Hibernate, persistence.xml, @Entity, EntityManager, CRUD, JPQL |
| 10 | `DIA_10_PIZZERIA_HIBERNATE.md` | Pizza/Cliente/Pedido como @Entity, @ManyToOne, @ManyToMany, @JoinTable, H2 |

### Semana 3: Spring Boot (Dias 11-14, 20h)

| Dia | Archivo | Contenido |
|-----|---------|-----------|
| 11 | `DIA_11_SPRING_BOOT_INTRO.md` | IoC/DI, Spring Initializr, Lombok, JpaRepository, @RestController, Swagger |
| 12 | `DIA_12_PIZZERIA_SPRING.md` | Pizzeria como API REST, 3 entidades con relaciones, Controller/Service/Repository, data.sql |
| 13 | `DIA_13_PROYECTO_PERSONAL.md` | Elegir blueprint, disenar entidades, crear proyecto Spring Boot, primer CRUD |
| 14 | `DIA_14_PROYECTO_COMPLETO.md` | Completar endpoints, @Valid, GlobalExceptionHandler, coleccion Postman, GitHub |

### Semana 4: Docker y CI/CD (Dias 15-18, 20h)

| Dia | Archivo | Contenido |
|-----|---------|-----------|
| 15 | `DIA_15_DOCKER_INTRO.md` | Contenedores vs VMs, Docker Desktop, Dockerfile multi-stage, docker build/run |
| 16 | `DIA_16_DOCKER_COMPOSE.md` | Docker Compose, H2 a PostgreSQL, app + BD + Adminer, volumenes y redes |
| 17 | `DIA_17_CICD_GITHUB_ACTIONS.md` | CI/CD conceptos, GitHub Actions, workflows, build/test/package en cada push |
| 18 | `DIA_18_DEPLOY_PRODUCCION.md` | Dockerizar proyecto, Compose + PostgreSQL + CI/CD, deploy a Railway |

### Semana 5: Presentaciones (Dias 19-20, 10h)

| Dia | Archivo | Contenido |
|-----|---------|-----------|
| 19 | `DIA_19_PREPARAR_DEMO.md` | Checklist tecnico, README profesional, estructura de presentacion, plan B |
| 20 | `DIA_20_DEMO_DAY.md` | Presentaciones, evaluacion entre pares, cierre del curso, proximos pasos |

---

## Evolucion del Proyecto Pizzeria

```
v1 (Dia 3)  --> Java puro: interfaces, herencia, polimorfismo
v2 (Dia 4)  --> Paquetes por capas, Repository pattern, DI manual
v3 (Dia 5)  --> Maven, Streams API, Optional
v4 (Dia 7)  --> Maven + Gson (exportar pedidos a JSON)
v5 (Dia 10) --> Hibernate + H2 (persistencia con @Entity)
v6 (Dia 12) --> Spring Boot + REST API + Swagger
```

## Patron Arquitectonico

```
HTTP Request --> Controller --> Service --> Repository --> Database
(Postman)      (@RestController) (@Service) (JpaRepository) (PostgreSQL)
```

## Libro de referencia

*Arquitectura de Sistemas Enterprise* de @TodoEconometria contiene los tutoriales completos paso a paso, ejercicios adicionales y capitulos avanzados sobre seguridad, microservicios y testing.

---
Curso IFCD0014 | Prof. Juan Marcelo Gutierrez Miranda | @TodoEconometria
