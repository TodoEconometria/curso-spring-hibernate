# Spring Boot + Hibernate - De Cero a Produccion

<div align="center">

<img src="https://raw.githubusercontent.com/TodoEconometria/curso-spring-hibernate/main/docs/assets/todoeconometria_logo.png" alt="TodoEconometria" width="300">

*"Sin experiencia no hay conocimiento"*

[![Web del Curso](https://img.shields.io/badge/Web-del%20Curso-green?style=for-the-badge&logo=github-pages&logoColor=white)](https://todoeconometria.github.io/curso-spring-hibernate/)
[![GitHub Stars](https://img.shields.io/github/stars/TodoEconometria/curso-spring-hibernate?style=for-the-badge&logo=github)](https://github.com/TodoEconometria/curso-spring-hibernate/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/TodoEconometria/curso-spring-hibernate?style=for-the-badge&logo=github)](https://github.com/TodoEconometria/curso-spring-hibernate/network/members)
[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg?style=for-the-badge)](https://creativecommons.org/licenses/by-nc-sa/4.0/)
[![Java 21](https://img.shields.io/badge/Java-21-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](https://openjdk.org/)
[![Spring Boot 4](https://img.shields.io/badge/Spring%20Boot-4.0-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Docker](https://img.shields.io/badge/Docker-Ready-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)

</div>

---

## Que es este curso

Este es un curso profesional de 100 horas que te lleva desde los fundamentos de Java hasta desplegar una aplicacion real en produccion con Spring Boot, Hibernate, Docker y CI/CD.

No es un tutorial suelto. Es un camino completo: empiezas escribiendo tu primer `HelloWorld.java`, y al final del curso tienes una API REST funcionando en la nube con base de datos PostgreSQL, contenedores Docker y deploy automatico con GitHub Actions.

El hilo conductor es un proyecto de **Pizzeria** que evoluciona contigo. Arrancas con Java puro, le agregas Maven, despues Hibernate para guardar datos, luego Spring Boot para convertirla en API REST, y al final la metes en Docker y la despliegas en Railway. Cada dia construye sobre lo anterior, sin saltos.

---

## Para quien es

- **Si vienes de otro lenguaje** y quieres aprender el ecosistema Java/Spring profesional.
- **Si estas empezando** y quieres un camino estructurado, no videos sueltos de YouTube.
- **Si quieres portfolio real**: al terminar tienes un proyecto desplegado en produccion con Swagger, Docker y CI/CD.

No necesitas experiencia previa en Java. Los primeros 5 dias cubren los fundamentos desde cero.

---

## Como participar (comunidad)

Este curso fue disenado para impartirse con profesor, pero todo el material esta abierto para que lo hagas por tu cuenta. Asi funciona:

### 1. Haz fork de este repositorio

Click en el boton **Fork** arriba a la derecha. Eso crea tu copia personal.

### 2. Clona tu fork en tu maquina

```bash
git clone https://github.com/TU_USUARIO/curso-spring-hibernate.git
cd curso-spring-hibernate
git remote add upstream https://github.com/TodoEconometria/curso-spring-hibernate.git
```

### 3. Sigue los manuales en orden

Abre la carpeta `manuales/` y empieza por el dia 1. Cada guia te dice que aprender y que construir ese dia. Son 20 dias de contenido.

### 4. Elige tu proyecto personal

En los dias 13-14, eliges uno de los 16 **blueprints** disponibles (cine, zoo, peluqueria, bar, etc.) y construyes tu propia API con Spring Boot + Hibernate.

### 5. Entrega tu trabajo final

Cuando termines, copia la plantilla a tu carpeta de comunidad:

```bash
cp -r trabajo_final/plantilla/ entregas/trabajo_final/comunidad/TU_USUARIO/
```

Completa los archivos (especialmente `PROMPTS.md` donde documentas como usaste IA) y sube con `git push` a tu fork.

### 6. Mantente al dia

Si agregamos material nuevo, sincroniza tu fork:

```bash
git fetch upstream
git merge upstream/main
```

---

## Que incluye

| 100 Horas | 20 Sesiones | 16 Blueprints | 20 Guias | 8+ Tecnologias |
|:---------:|:-----------:|:-------------:|:--------:|:--------------:|
| de contenido | de clase | proyectos individuales | dia a dia | profesionales |

### Recorrido del curso

| Semana | Dias | Que aprendes |
|:------:|:----:|-------------|
| 1 | 1-5 | Java desde cero: fundamentos, POO, interfaces, herencia, arquitectura por capas, Maven |
| 2 | 6-10 | Maven avanzado, Streams, Hibernate, JPA, relaciones entre entidades, H2 |
| 3 | 11-14 | Spring Boot, REST APIs, Swagger, Lombok, proyecto personal con blueprint |
| 4 | 15-18 | Docker, Docker Compose, PostgreSQL, GitHub Actions, deploy en Railway |
| 5 | 19-20 | Preparar presentacion y Demo Day |

### La Pizzeria: el hilo conductor

Un unico proyecto que evoluciona a lo largo del curso:

```
Dia 3  - Java puro: interfaces, herencia, polimorfismo
Dia 4  - Arquitectura: paquetes, Repository, Service, excepciones
Dia 7  - Maven + Gson: exportar pedidos a JSON
Dia 10 - Hibernate + H2: Pizza, Cliente, Pedido como @Entity
Dia 12 - Spring Boot: API REST completa con Swagger
Dia 16 - Docker Compose: PostgreSQL + Adminer + app
Dia 18 - Deploy en Railway con CI/CD automatico
```

---

## Tecnologias

**Lenguaje:** Java 21 (LTS) con Maven 3.9+

**Backend:** Spring Boot 4, Spring Web MVC, Spring Data JPA, Hibernate 7, Lombok, SpringDoc OpenAPI (Swagger)

**Base de datos:** H2 (desarrollo), PostgreSQL 16 (produccion)

**Infraestructura:** Docker, Docker Compose, GitHub Actions, Railway

**Herramientas:** IntelliJ IDEA, DBeaver, Postman, Git + GitHub

---

## Estructura del repositorio

```
curso-spring-hibernate/
  manuales/           20 guias dia a dia (DIA_01 a DIA_20)
  pizzeria/           Codigo esqueleto de la Pizzeria
  blueprints/         16 proyectos individuales para elegir
  entregas/           Zona de entregas (ejercicios + trabajo final)
  trabajo_final/      Enunciado + plantilla
  docs/               Sitio web del curso
```

---

## Metodologia

- **Aprendizaje progresivo:** un unico proyecto (Pizzeria) evoluciona desde Java puro hasta Docker + CI/CD. Cada dia construye sobre lo anterior.
- **Blueprints individuales:** cada alumno aplica lo aprendido a un dominio diferente (16 proyectos unicos), evitando la copia.
- **Deploy real:** cada proyecto se despliega en Railway con PostgreSQL, no solo en entorno local.
- **Evaluacion por prompts:** los alumnos documentan como usaron IA, fomentando el uso honesto y consciente.
- **Material abierto:** todo disponible bajo licencia CC BY-NC-SA 4.0.

---

## Instructor

**Juan Marcelo Gutierrez Miranda** | [@TodoEconometria](https://www.linkedin.com/in/juangutierrezconsultor/)

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
