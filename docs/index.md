# Spring Boot + Hibernate — De Cero a Produccion

<div align="center">

<img src="assets/todoeconometria_logo.png" alt="TodoEconometria" width="350">

*"Sin experiencia no hay conocimiento"*

</div>

---

## Que es este curso

Un curso profesional de **100 horas** que te lleva desde los fundamentos de Java hasta desplegar una aplicacion real en produccion. No es un tutorial suelto: es un camino completo de 20 sesiones donde cada dia construye sobre lo anterior.

Empiezas escribiendo tu primer `HelloWorld.java`. Al final del curso tienes una API REST funcionando en la nube con PostgreSQL, Docker y deploy automatico.

El hilo conductor es un proyecto de **Pizzeria** que evoluciona contigo: arranca en Java puro, le agregas Maven, despues Hibernate para guardar datos, Spring Boot para convertirla en API REST, y al final la metes en Docker y la despliegas en Railway.

---

## Para quien es

- **Si vienes de otro lenguaje** y quieres aprender el ecosistema Java/Spring profesional.
- **Si estas empezando** y quieres un camino estructurado, no videos sueltos.
- **Si quieres portfolio real**: al terminar tienes un proyecto desplegado en produccion con Swagger, Docker y CI/CD.

No necesitas experiencia previa en Java. Los primeros 5 dias cubren los fundamentos desde cero.

---

## Como participar

Este curso fue disenado para impartirse con profesor, pero todo el material esta abierto para que lo hagas por tu cuenta.

**Paso 1.** Haz fork del repositorio (boton Fork arriba a la derecha en GitHub).

**Paso 2.** Clona tu fork y configura el upstream:

```bash
git clone https://github.com/TU_USUARIO/curso-spring-hibernate.git
cd curso-spring-hibernate
git remote add upstream https://github.com/TodoEconometria/curso-spring-hibernate.git
```

**Paso 3.** Abre `manuales/DIA_01_FUNDAMENTOS_JAVA.md` y empieza. Sigue los dias en orden.

**Paso 4.** En los dias 13-14 eliges uno de los 16 blueprints y construyes tu propio proyecto.

**Paso 5.** Cuando termines, entrega tu trabajo final en:

```
entregas/trabajo_final/comunidad/TU_USUARIO/
```

Copia la plantilla con `cp -r trabajo_final/plantilla/ entregas/trabajo_final/comunidad/TU_USUARIO/` y documenta tus prompts en `PROMPTS.md`.

**Paso 6.** Sincroniza tu fork si hay material nuevo:

```bash
git fetch upstream
git merge upstream/main
```

---

## Recorrido del curso

| Semana | Dias | Que aprendes |
|:------:|:----:|-------------|
| 1 | 1-5 | Java desde cero: fundamentos, POO, interfaces, herencia, arquitectura por capas, Maven |
| 2 | 6-10 | Maven avanzado, Streams, Hibernate, JPA, relaciones entre entidades |
| 3 | 11-14 | Spring Boot, REST APIs, Swagger, Lombok, proyecto personal con blueprint |
| 4 | 15-18 | Docker, Docker Compose, PostgreSQL, GitHub Actions, deploy en Railway |
| 5 | 19-20 | Preparar presentacion y Demo Day |

### La Pizzeria: el hilo conductor

```
Dia 3  → Java puro: interfaces, herencia, polimorfismo
Dia 4  → Arquitectura: paquetes, Repository, Service, excepciones
Dia 7  → Maven + Gson: exportar pedidos a JSON
Dia 10 → Hibernate + H2: Pizza, Cliente, Pedido como @Entity
Dia 12 → Spring Boot: API REST completa con Swagger
Dia 16 → Docker Compose: PostgreSQL + Adminer + app
Dia 18 → Deploy en Railway con CI/CD automatico
```

---

## Que hay en el repositorio

<div class="grid cards" markdown>

-   :material-book-open-variant:{ .lg .middle } **Manuales**

    ---

    20 guias dia a dia, desde Java hasta Docker.

    [:octicons-arrow-right-24: Ver manuales](https://github.com/TodoEconometria/curso-spring-hibernate/tree/main/manuales)

-   :material-puzzle:{ .lg .middle } **Blueprints**

    ---

    16 proyectos individuales para elegir tu dominio.

    [:octicons-arrow-right-24: Ver blueprints](blueprints.md)

-   :material-trophy:{ .lg .middle } **Evaluacion**

    ---

    Rubrica, ranking y sistema de entregas.

    [:octicons-arrow-right-24: Ver evaluacion](evaluacion.md)

-   :material-git:{ .lg .middle } **Git y GitHub**

    ---

    Como hacer fork, clonar y sincronizar.

    [:octicons-arrow-right-24: Ver guia Git](git-github.md)

</div>

```
curso-spring-hibernate/
  manuales/           20 guias dia a dia (DIA_01 a DIA_20)
  pizzeria/           Codigo esqueleto de la Pizzeria
  blueprints/         16 proyectos individuales para elegir
  entregas/           Zona de entregas (ejercicios + trabajo final)
  trabajo_final/      Enunciado + plantilla
  docs/               Este sitio web
```

---

## Tecnologias que vas a aprender

**Lenguaje:** Java 21 (LTS) con Maven 3.9+

**Backend:** Spring Boot 4, Spring Web MVC, Spring Data JPA, Hibernate 7, Lombok, SpringDoc OpenAPI (Swagger)

**Base de datos:** H2 (desarrollo), PostgreSQL 16 (produccion)

**Infraestructura:** Docker, Docker Compose, GitHub Actions, Railway

**Herramientas:** IntelliJ IDEA, DBeaver, Postman, Git + GitHub

---

## Instructor

**Juan Marcelo Gutierrez Miranda** — [@TodoEconometria](https://www.linkedin.com/in/juangutierrezconsultor/)

10+ anos en desarrollo de software y formacion. Instructor en Latinoamerica y Espana.

| | |
|---|---|
| Web | [todoeconometria.com](https://www.todoeconometria.com) |
| LinkedIn | [Juan Gutierrez](https://www.linkedin.com/in/juangutierrezconsultor/) |
| YouTube | [TodoEconometria](https://www.youtube.com/channel/UC2ok03ltDHcVo1PZ1C8mGeg) |
| GitHub | [TodoEconometria](https://github.com/TodoEconometria) |

---

<div align="center">

2025-2026 Juan Marcelo Gutierrez Miranda | Material Educativo Abierto

Licencia [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) | Uso libre no comercial con atribucion

</div>
