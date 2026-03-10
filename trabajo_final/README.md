# Trabajo Final: API REST con Spring Boot + Docker‌‌‌​‌​‌‌​﻿‍‍‌‍‌​​﻿‌‌‌‍​﻿‌‍​﻿‌‍​‍‌‍​‍‌‍‌‌​﻿‍‌​﻿‌﻿​﻿​‍​﻿‍​‌‍​‍‌‍‌‍​﻿‍‌​﻿‌‍‌‍​‍

**Curso:** Spring Boot + Hibernate - Prof. Juan Marcelo Gutierrez Miranda (@TodoEconometria)

---

## Objetivo

Construir **desde cero** una aplicacion web con API REST usando Spring Boot, Hibernate
y Docker. A partir de uno de los 16 blueprints (o un dominio propio), disenar
entidades con relaciones, implementar CRUD completo, y desplegarlo en contenedores.

**Lo que se evalua:** No solo el codigo, sino tu **proceso de aprendizaje**.
Pueden usar herramientas de IA (ChatGPT, Copilot, Claude, etc.) pero deben
documentar como las usaron y que aprendieron.

---

## Dominio del Proyecto

Cada alumno elige **uno** de los 16 blueprints en [`blueprints/`](../blueprints/README.md),
o propone un dominio propio (con aprobacion del profesor).

**Importante:** Cada alumno elige un blueprint diferente. Si dos alumnos eligen el mismo,
se considerara copia.

---

## Tu Proyecto como Portfolio Profesional

Ademas de la entrega formal (los bloques A-D que se describen abajo), el proyecto
que construyas puede ser **tu carta de presentacion profesional**. Para eso, te
recomendamos crear un **repositorio propio** separado del fork del curso.

### Por que dos repos?

| Repo | Para que | Quien lo ve |
|------|----------|-------------|
| Tu fork de `curso-spring-hibernate` | Seguir manuales + entrega formal (PROMPTS.md, reflexion, respuestas) | El profesor |
| **Tu repo propio** (ej: `cine-estrella`) | Codigo profesional + Docker + Swagger + README visual | Recruiters, tu CV, GitHub |

Tu fork tiene 15 manuales, 16 blueprints, material del curso... todo eso no es tu proyecto.
Un recruiter quiere ver **un repo limpio** con tu API, tu Docker Compose, tus capturas
de Swagger, y un README que explique como ejecutarlo.

### Como funciona

1. **Creas tu repo propio** en GitHub (ej: `github.com/tu_usuario/cine-estrella`)
2. **Programas ahi** durante los dias 13-18 (codigo, Docker, CI/CD, Swagger)
3. **Para la entrega**, rellenas las plantillas en tu fork y enlazas tu repo con `REPO_PROYECTO.md`

Guia completa paso a paso: **[Crear tu Repo de Portfolio](../docs/git-github/crear-repo-portfolio.md)**

### Que ganas

- Un repo **limpio** en tu GitHub que puedes poner en el CV
- `docker compose up` funciona desde la raiz del repo (no desde una subcarpeta)
- README con badges, capturas de Swagger, diagramas — visible al abrir el repo en GitHub
- GitHub Actions con badge verde en TU propio repo
- Swagger UI como "dashboard visual" de tu API (lo mas parecido a un frontend sin hacer frontend)

> **Nota:** El repo de portfolio es **opcional pero muy recomendado**. Si no lo creas,
> tu codigo puede ir directamente en la carpeta de entrega como se describe mas abajo.
> Pero si quieres que tu proyecto sirva para entrevistas de trabajo, el repo propio
> marca la diferencia.

---

## Estructura: 4 Bloques

### Bloque A: Infraestructura Docker (30%)

**Tarea:** Escribir un `docker-compose.yml` que levante:

| Servicio | Requisito |
|----------|-----------|
| PostgreSQL 16 | Base de datos para la app |
| Adminer | Interfaz web para ver la BD (puerto 8081) |
| App Spring Boot | Contenedor con la app (Dockerfile, puerto 8080) |

**Pasos:**

1. Investigar que es Docker Compose y como se estructura un archivo YAML
2. Escribir un `Dockerfile` para la app Spring Boot (multi-stage build)
3. Escribir `docker-compose.yml` con los 3 servicios
4. Agregar `healthcheck` al menos para PostgreSQL
5. Ejecutar `docker compose up -d` y verificar que todo arranca
6. Verificar que la API responde en `http://localhost:8080/api/...`
7. Verificar que Adminer muestra las tablas en `http://localhost:8081`
8. Escribir `02_INFRAESTRUCTURA.md` explicando **cada seccion** de tu YAML con tus palabras

**Pistas:**
- Imagen PostgreSQL: `postgres:16-alpine`
- Imagen Adminer: `adminer:latest`
- Para el Dockerfile: usar `eclipse-temurin:21-jdk` como base
- La app necesita conectarse a PostgreSQL, no a H2

**Entregables del Bloque A:**
- `docker-compose.yml` (funcional)
- `Dockerfile` (funcional)
- `02_INFRAESTRUCTURA.md` (explicacion + prompts IA usados + capturas)

---

### Bloque B: API REST Spring Boot (25%)

**Tarea:** Crear el proyecto Spring Boot con CRUD completo.

**Requisitos minimos:**

| Requisito | Detalle |
|-----------|---------|
| Entidades | Minimo 3 entidades JPA con Lombok |
| Relaciones | Al menos una `@ManyToOne` y una `@ManyToMany` |
| Repositorios | `JpaRepository` con al menos 2 derived queries custom |
| Servicios | Capa `@Service` con logica de negocio |
| Controladores | `@RestController` con CRUD completo (GET, POST, PUT, DELETE) |

**Entregables del Bloque B:**
- Codigo fuente completo en `src/`
- `pom.xml` con dependencias

---

### Bloque C: Funcionalidad Avanzada (25%)

**Tarea:** Elegir UNA opcion e implementarla:

| Opcion | Que hacer | Ejemplo |
|--------|-----------|---------|
| **Validacion** | Bean Validation + `@ControllerAdvice` | Que al crear una pizza sin nombre devuelva error 400 claro |
| **Queries avanzadas** | `@Query` JPQL + paginacion con `Pageable` | Buscar pizzas por rango de precio con paginacion |
| **Testing** | JUnit 5 + Mockito + tests de integracion | Tests para verificar que el CRUD funciona |

**Requisitos minimos:**
- Implementacion funcional de la opcion elegida
- Al menos 3 capturas de Postman (o salida de tests)
- Parrafo de explicacion: que hace, por que lo eligieron, que aprendieron

**Entregables del Bloque C:**
- Codigo implementado
- Capturas en `03_RESULTADOS.md`
- Prompt usado para cada funcionalidad (pegado bajo cada captura)

---

### Bloque D: Reflexion IA - "3 Momentos Clave" (20%)

**Tarea:** Documentar tu proceso de aprendizaje Y compartir tus prompts.

Para **cada bloque** (A, B, C), responde estas 3 preguntas:

| Momento | Pregunta |
|---------|----------|
| **Arranque** | Que fue lo primero que le pediste a la IA (o buscaste en internet)? |
| **Error** | Que fallo y como lo resolviste? Pega el error si lo tienes. |
| **Aprendizaje** | Que aprendiste que NO sabias antes de empezar este bloque? |

**Ademas, para cada bloque:** Pega el **texto exacto** del prompt de IA que
mas te ayudo. No lo resumas ni lo parafrasees: copia y pega el texto tal cual.

**IMPORTANTE - Donde van los prompts:**

| Archivo | Que prompts van ahi |
|---------|---------------------|
| `02_INFRAESTRUCTURA.md` | Todos los prompts usados para Docker |
| `03_RESULTADOS.md` (bajo cada captura) | El prompt que genero cada funcionalidad |
| `04_REFLEXION_IA.md` (bajo cada bloque) | El prompt CLAVE de cada bloque (A, B, C) |

**Se evalua:**
- Que tus prompts sean **reales** (pegados tal cual, no inventados despues)
- Que tus respuestas sean **especificas** (no "aprendi Spring" sino "aprendi que @PathVariable extrae el {id} de la URL porque...")
- Que los errores sean **reales** (todos cometemos errores, documentarlos no baja nota)
- Que el proceso sea **coherente** con tu codigo

**Nota:** No importa si usaste IA o no. Lo que importa es que demuestres
que ENTIENDES lo que entregaste. Un alumno que usa IA bien y lo explica
saca mejor nota que uno que copia y no puede explicar nada.

**Entregable del Bloque D:**
- `04_REFLEXION_IA.md`

---

## Preguntas de Comprension (obligatorias)

Responde en `05_RESPUESTAS.md`:

1. **Infraestructura:** Si tu app necesita conectarse a PostgreSQL pero el contenedor de la BD tarda 30 segundos en arrancar, que pasa? Como lo solucionarias?
2. **JPA:** Por que `findAll()` de JpaRepository puede ser lento con 100,000 registros? Que alternativa usarias?
3. **API REST:** Explica la diferencia entre un error 400 (Bad Request) y un error 500 (Internal Server Error). Da un ejemplo de cada uno en tu proyecto.
4. **Escalabilidad:** Si tu aplicacion pasa de 100 usuarios a 10,000, que cambiarias en tu infraestructura Docker?

---

## Entrega

### Promociones

Cada grupo de alumnos se identifica por **promocion** (año + trimestre).
Las entregas se organizan por promocion para mantener el historial del curso.

| Promocion | Periodo | Alumnos |
|-----------|---------|---------|
| **2026-T1** | Marzo 2026 | Primera promocion |

Si estas haciendo el curso por tu cuenta (sin pertenecer a una promocion),
usa la carpeta `comunidad/`.

### Formato

```
entregas/trabajo_final/
├── 2026-T1/                       <- Promocion (tu profesor te dira cual)
│   └── apellido_nombre/
│       ├── PROMPTS.md             <- LO MAS IMPORTANTE (tus prompts de IA)
│       ├── REPO_PROYECTO.md       <- Enlace a tu repo de portfolio (si lo creaste)
│       ├── 01_README.md           <- (1) Tu dominio + entidades + relaciones
│       ├── 02_INFRAESTRUCTURA.md  <- (2) Explicacion Docker
│       ├── 03_RESULTADOS.md       <- (3) Capturas Postman + explicacion
│       ├── 04_REFLEXION_IA.md     <- (4) 3 Momentos Clave x 3 bloques
│       ├── 05_RESPUESTAS.md       <- (5) 4 preguntas de comprension
│       ├── docker-compose.yml     <- Tu YAML funcional
│       ├── Dockerfile             <- Para la app Spring Boot
│       ├── src/                   <- Codigo fuente del proyecto
│       ├── pom.xml                <- Dependencias Maven
│       └── .gitignore             <- Excluir target/, .idea/, etc.
└── comunidad/                     <- Para quienes hacen el curso por su cuenta
    └── apellido_nombre/
        └── (misma estructura)
```

> **Si creaste un repo propio:** El codigo (`src/`, `pom.xml`, `Dockerfile`,
> `docker-compose.yml`) ya esta en tu repo de portfolio. En la carpeta de entrega
> solo necesitas los documentos de reflexion (PROMPTS.md, 01-05) y el `REPO_PROYECTO.md`
> con el enlace. No hace falta duplicar el codigo en ambos sitios.

Copia la plantilla desde `trabajo_final/plantilla/` a tu carpeta de entrega.

### Proceso (SIN Pull Request)

1. Sincroniza tu fork: `git fetch upstream && git merge upstream/main`
2. Crea tu carpeta de entrega dentro de tu promocion:
   ```bash
   cp -r trabajo_final/plantilla/ entregas/trabajo_final/2026-T1/apellido_nombre/
   ```
3. **Completa PROMPTS.md** mientras trabajas (documenta tus prompts de IA)
4. Completa los demas archivos (01 al 05) + `docker-compose.yml` + `Dockerfile`
5. Sube a tu fork: `git add . && git commit -m "Trabajo Final" && git push`
6. **Listo!** El profesor revisa tu fork automaticamente (no necesitas crear PR)

### IMPORTANTE: Sistema de Evaluacion por Prompts

**El archivo PROMPTS.md es lo que se evalua principalmente.**

Este archivo tiene 2 partes:

| Parte | Que poner | Como debe verse |
|-------|-----------|-----------------|
| **PARTE 1** | Tus 3 prompts reales (A, B, C) | Con errores, informal, TAL CUAL lo escribiste |
| **PARTE 2** | Blueprint generado por IA | Perfecto, profesional (lo genera la IA al final) |

**REGLA CRITICA:** Los prompts de la Parte 1 deben ser COPIA EXACTA de lo que
escribiste. NO los corrijas. Si escribiste "como ago un controlador rest" con errores,
pega ESO. **El sistema detecta si limpiaste tus prompts.**

### Prohibido incluir

- Carpetas `target/`, `.idea/`, `out/`
- Archivos `.class`, `.jar`
- Archivos `.env` con credenciales reales
- Carpetas de herramientas IA (`.claude/`, `.qodo/`, `.copilot/`)

---

## Evaluacion

### Rubrica Detallada

| Bloque | Peso | Nota Max | Criterios |
|--------|------|----------|-----------|
| **A. Infraestructura** | 30% | 3.0 pts | YAML funcional (1.5) + Dockerfile (0.5) + explicacion clara (1.0) |
| **B. API REST** | 25% | 2.5 pts | Entidades+relaciones (1.0) + CRUD completo (1.0) + codigo limpio (0.5) |
| **C. Avanzado** | 25% | 2.5 pts | Implementacion correcta (1.5) + capturas (0.5) + explicacion (0.5) |
| **D. Reflexion IA** | 20% | 2.0 pts | Prompts reales (0.5) + errores documentados (0.5) + aprendizaje especifico (1.0) |
| **TOTAL** | 100% | **10.0 pts** | |

### Desglose por Nota

| Nota | Significado | Que se espera |
|------|------------|---------------|
| 9-10 | Sobresaliente | Todo funciona, bien documentado, prompts reales, reflexion profunda |
| 7-8 | Notable | Funciona con detalles menores, buena documentacion |
| 5-6 | Aprobado | Funciona parcialmente, documentacion basica |
| 3-4 | Insuficiente | No funciona o documentacion muy pobre |
| 0-2 | No presentado / copia | No entregado o similitud mayor a 80% |

### Bonificaciones

| Bonus | Puntos extra | Condicion |
|-------|-------------|-----------|
| PROMPTS.md excelente | +0.5 | Prompts reales, con errores incluidos, reflexion profunda |
| Commits frecuentes | +0.5 | 10+ commits con mensajes descriptivos |
| Dominio creativo | +0.5 | Blueprint propio aprobado por el profesor |
| Funcionalidad extra | +0.5 | Implementar MAS de una opcion del Bloque C |
| Documentacion impecable | +0.5 | README claro que explique como ejecutar desde cero |
| **Repo de portfolio** | **+1.0** | Repo propio con: README profesional + Swagger UI + capturas incrustadas + badge CI verde + Docker funcional. [Guia completa](../docs/git-github/crear-repo-portfolio.md) |

### Penalizaciones

| Infraccion | Penalizacion |
|------------|-------------|
| Mismo blueprint que otro alumno | -50% |
| YAML que no funciona sin explicacion | -15% |
| Reflexion IA ausente o generica | -20% |
| Prompts limpiados (demasiado perfectos) | -15% |
| Sin capturas de Postman/tests | -10% |
| Archivos prohibidos en el repo (target/, .idea/) | -5% |

---

## IMPORTANTE: Sistema Anti-Copia

Tu entrega sera analizada para detectar similitud con otras entregas.

| Elemento | Que detecta |
|----------|-------------|
| **Blueprint** | Si dos alumnos usan el mismo blueprint |
| **Entidades** | Si las entidades son identicas a otra entrega |
| **Controladores** | Si la estructura del codigo es copiada |
| **PROMPTS.md** | Si los prompts son inventados o copiados |

### Niveles de similitud y consecuencias

| Nivel | Similitud | Accion |
|-------|-----------|--------|
| **COPIA** | mayor a 80% | RECHAZADO - 1 oportunidad mas |
| **Muy similar** | 50-80% | Penalizacion -30% |
| **Similar parcial** | 25-50% | Penalizacion -10% |
| **Original** | menor a 25% | Sin penalizacion |

### Si tu entrega es rechazada por similitud

1. Recibiras un mensaje explicando por que
2. Tienes **1 oportunidad** para rehacer con otro blueprint
3. Si la segunda entrega tambien es similar: nota 0

---

## Ranking del Curso

Al finalizar las entregas, se publicara un **ranking** con las mejores puntuaciones.

### Categorias del Ranking

| Categoria | Que premia |
|-----------|------------|
| **Mejor Infraestructura** | Docker Compose mas robusto y bien documentado |
| **Mejor API REST** | Entidades, relaciones y controladores mas completos |
| **Mejor Reflexion IA** | Documentacion de prompts mas honesta y profunda |
| **Codigo mas Limpio** | Mejor estructura, nombres, separacion de capas |
| **Proyecto mas Creativo** | Dominio mas original e interesante |
| **MVP del Curso** | Mayor puntuacion total (bloques + bonificaciones) |

### Como funciona

1. El profesor evalua cada entrega segun la rubrica
2. Se calcula la puntuacion total (max 10.0 + bonificaciones)
3. Se publica el ranking en el repositorio
4. Los 3 primeros de cada categoria reciben mencion especial

**El ranking es publico** - se publica en el README del repositorio al finalizar el curso.

---

## Recursos

- **Manuales del curso:** `manuales/` (dias 6-20)
- **Spring Boot Docs:** https://docs.spring.io/spring-boot/reference/
- **Spring Web MVC Controllers:** https://docs.spring.io/spring-framework/reference/web/webmvc/mvc-controller.html
- **Spring Data JPA:** https://docs.spring.io/spring-data/jpa/reference/
- **Docker Compose:** https://docs.docker.com/compose/
- **Postman:** https://www.postman.com/downloads/

---

## Calendario

| Dia | Que hacer |
|-----|-----------|
| 13 | Elegir blueprint, disenar entidades, empezar Bloque B |
| 14 | Completar API REST (Bloque B) |
| 15-16 | Docker (Bloque A) |
| 17 | CI/CD + Bloque C |
| 18 | Integrar todo + pulir |
| 19 | Preparar presentacion |
| 20 | Demo Day - presentar al grupo |

---

-------------------------
Autor original/Referencia: @TodoEconometria
Profesor: Juan Marcelo Gutierrez Miranda
Metodologia: Cursos Avanzados de Big Data, Ciencia de Datos,
             Desarrollo de aplicaciones con IA y Econometria Aplicada.
Hash ID de Certificacion: 7a3f1b9c4d8e2f5a6b0c9d8e7f1a2b3c4d5e6f7a8b9c0d1e2f3a4b5c6d7e8f9a
Repositorio: https://github.com/TodoEconometria/certificaciones

REFERENCIA ACADEMICA:
- Walls, C. (2022). Spring in Action (6th ed.). Manning Publications.
- Bauer, C., King, G., & Gregory, G. (2015). Java Persistence with Hibernate (2nd ed.). Manning.
- Merkel, D. (2014). Docker: Lightweight Linux Containers for Consistent Development and Deployment. Linux Journal.
-------------------------
