# Evaluacion — Trabajo Final‌‌‌​‌​‌‌​﻿‍‍​﻿‌‌​﻿​‌​﻿‌​​﻿‍‌‌‍​‌​﻿​‍​﻿‌﻿​﻿‌﻿​﻿‍​​﻿‍‌‌‍​‌‌‍‌​‌‍‌‍‌‍​‌​﻿‌‌​﻿‌‌

El trabajo final integra TODO lo aprendido: Spring Boot + Hibernate + Docker.

---

## Objetivo

Construir **desde cero** una aplicacion web con API REST usando Spring Boot, Hibernate
y Docker. A partir de uno de los [16 blueprints](blueprints.md) (o un dominio propio),
disenar entidades con relaciones, implementar CRUD completo, y desplegarlo en contenedores.

!!! note "Lo que se evalua"
    No solo el codigo, sino tu **proceso de aprendizaje**. Pueden usar herramientas de IA
    pero deben documentar como las usaron y que aprendieron.

---

## Estructura: 4 Bloques

### Bloque A: Infraestructura Docker (30%)

Escribir un `docker-compose.yml` que levante:

| Servicio | Requisito |
|---|---|
| PostgreSQL 16 | Base de datos para la app |
| Adminer | Interfaz web para ver la BD (puerto 8081) |
| App Spring Boot | Contenedor con la app (Dockerfile, puerto 8080) |

**Entregables:** `docker-compose.yml` + `Dockerfile` + `02_INFRAESTRUCTURA.md`

### Bloque B: API REST Spring Boot (25%)

| Requisito | Detalle |
|---|---|
| Entidades | Minimo 3 entidades JPA con Lombok |
| Relaciones | Al menos una `@ManyToOne` y una `@ManyToMany` |
| Repositorios | `JpaRepository` con al menos 2 derived queries custom |
| Servicios | Capa `@Service` con logica de negocio |
| Controladores | `@RestController` con CRUD completo (GET, POST, PUT, DELETE) |

**Entregables:** Codigo fuente en `src/` + `pom.xml`

### Bloque C: Funcionalidad Avanzada (25%)

Elegir **UNA** opcion e implementarla:

| Opcion | Que hacer |
|---|---|
| **Validacion** | Bean Validation + `@ControllerAdvice` |
| **Queries avanzadas** | `@Query` JPQL + paginacion con `Pageable` |
| **Testing** | JUnit 5 + Mockito + tests de integracion |

**Entregables:** Codigo + capturas en `03_RESULTADOS.md`

### Bloque D: Reflexion — "3 Momentos Clave" (20%)

Para **cada bloque** (A, B, C), documentar:

| Momento | Pregunta |
|---|---|
| **Arranque** | Que fue lo primero que le pediste a la IA o buscaste? |
| **Error** | Que fallo y como lo resolviste? |
| **Aprendizaje** | Que aprendiste que NO sabias antes? |

**Entregables:** `04_REFLEXION_IA.md` + `PROMPTS.md`

---

## Rubrica Detallada

| Bloque | Peso | Nota Max | Criterios |
|---|---|---|---|
| **A. Infraestructura** | 30% | 3.0 pts | YAML funcional (1.5) + Dockerfile (0.5) + explicacion (1.0) |
| **B. API REST** | 25% | 2.5 pts | Entidades+relaciones (1.0) + CRUD completo (1.0) + codigo limpio (0.5) |
| **C. Avanzado** | 25% | 2.5 pts | Implementacion correcta (1.5) + capturas (0.5) + explicacion (0.5) |
| **D. Reflexion** | 20% | 2.0 pts | Prompts reales (0.5) + errores documentados (0.5) + aprendizaje (1.0) |
| **TOTAL** | 100% | **10.0 pts** | |

### Desglose por Nota

| Nota | Significado |
|---|---|
| 9-10 | :trophy: Sobresaliente — Todo funciona, bien documentado, reflexion profunda |
| 7-8 | :star: Notable — Funciona con detalles menores, buena documentacion |
| 5-6 | :white_check_mark: Aprobado — Funciona parcialmente, documentacion basica |
| 3-4 | :x: Insuficiente — No funciona o documentacion muy pobre |
| 0-2 | :no_entry: No presentado / copia |

---

## Bonificaciones

| Bonus | Puntos extra | Condicion |
|---|---|---|
| PROMPTS.md excelente | +0.5 | Prompts reales, con errores incluidos, reflexion profunda |
| Commits frecuentes | +0.5 | 10+ commits con mensajes descriptivos |
| Dominio creativo | +0.5 | Blueprint propio aprobado por el profesor |
| Funcionalidad extra | +0.5 | Implementar MAS de una opcion del Bloque C |
| Documentacion impecable | +0.5 | README claro que explique como ejecutar desde cero |
| **Repo de portfolio** | **+1.0** | Repo propio con README pro + Swagger UI + capturas + badge CI + Docker. [Guia](git-github/crear-repo-portfolio.md) |

---

## Penalizaciones

| Infraccion | Penalizacion |
|---|---|
| Mismo blueprint que otro alumno | -50% |
| YAML que no funciona sin explicacion | -15% |
| Reflexion ausente o generica | -20% |
| Prompts limpiados (demasiado perfectos) | -15% |
| Sin capturas de Postman/tests | -10% |
| Archivos prohibidos en el repo (target/, .idea/) | -5% |

---

## Sistema Anti-Copia

Tu entrega sera analizada para detectar similitud con otras entregas.

| Nivel | Similitud | Accion |
|---|---|---|
| **COPIA** | > 80% | RECHAZADO — 1 oportunidad mas |
| **Muy similar** | 50-80% | Penalizacion -30% |
| **Similar parcial** | 25-50% | Penalizacion -10% |
| **Original** | < 25% | Sin penalizacion |

!!! danger "Si tu entrega es rechazada"
    1. Recibiras un mensaje explicando por que
    2. Tienes **1 oportunidad** para rehacer con otro blueprint
    3. Si la segunda entrega tambien es similar: nota 0

---

## Ranking del Curso

Al finalizar las entregas, se publicara un **ranking** con las mejores puntuaciones.

### Categorias

| Categoria | Que premia |
|---|---|
| :1st_place_medal: **Mejor Infraestructura** | Docker Compose mas robusto y bien documentado |
| :2nd_place_medal: **Mejor API REST** | Entidades, relaciones y controladores mas completos |
| :3rd_place_medal: **Mejor Reflexion** | Documentacion de prompts mas honesta y profunda |
| :trophy: **Codigo mas Limpio** | Mejor estructura, nombres, separacion de capas |
| :bulb: **Proyecto mas Creativo** | Dominio mas original e interesante |
| :star: **MVP del Curso** | Mayor puntuacion total (bloques + bonificaciones) |

El ranking es **publico** — se publica en el repositorio al finalizar cada promocion.

---

## Promociones

Las entregas se organizan por **promocion** (año + trimestre). Cada grupo de alumnos
que cursa con un profesor pertenece a una promocion. El ranking se publica por promocion.

| Promocion | Periodo | Notas |
|-----------|---------|-------|
| `2026-T1` | Marzo 2026 | Primera promocion |

Si haces el curso por tu cuenta (sin profesor), usa la carpeta `comunidad/`.

---

## Formato de Entrega

```
entregas/trabajo_final/
├── 2026-T1/                       <- Tu promocion
│   └── apellido_nombre/
│       ├── PROMPTS.md             <- LO MAS IMPORTANTE
│       ├── REPO_PROYECTO.md       <- Enlace a tu repo de portfolio
│       ├── 01_README.md           <- Tu dominio + entidades + relaciones
│       ├── 02_INFRAESTRUCTURA.md  <- Explicacion Docker
│       ├── 03_RESULTADOS.md       <- Capturas Postman + explicacion
│       ├── 04_REFLEXION_IA.md     <- 3 Momentos Clave x 3 bloques
│       ├── 05_RESPUESTAS.md       <- 4 preguntas de comprension
│       ├── docker-compose.yml
│       ├── Dockerfile
│       ├── src/
│       ├── pom.xml
│       └── .gitignore
└── comunidad/                     <- Para quienes hacen el curso por su cuenta
```

> **Si creaste un repo de portfolio:** El codigo ya esta en tu repo propio.
> En la carpeta de entrega solo necesitas los documentos de reflexion (PROMPTS.md, 01-05)
> y el `REPO_PROYECTO.md` con el enlace. Ver [guia de portfolio](git-github/crear-repo-portfolio.md).

### Proceso de Entrega

1. Sincroniza tu fork: `git fetch upstream && git merge upstream/main`
2. Copia la plantilla a tu promocion:
   ```bash
   cp -r trabajo_final/plantilla/ entregas/trabajo_final/2026-T1/apellido_nombre/
   ```
3. Completa `PROMPTS.md` mientras trabajas
4. Completa los demas archivos (01 al 05) + Docker + codigo
5. Sube a tu fork: `git add . && git commit -m "Trabajo Final" && git push`

!!! info "Sin Pull Request"
    El profesor revisa tu fork automaticamente. **No necesitas crear PR.**

---

## Calendario

| Dia | Que hacer |
|---|---|
| 13 | Elegir blueprint, disenar entidades, empezar Bloque B |
| 14 | Completar API REST (Bloque B) |
| 15-16 | Docker (Bloque A) |
| 17 | CI/CD + Bloque C |
| 18 | Integrar todo + pulir |
| 19 | Preparar presentacion |
| 20 | Demo Day — presentar al grupo |
