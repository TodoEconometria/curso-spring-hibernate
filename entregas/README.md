# Zona de Entregas‌‌‌​‌​‌‌​﻿‍‍‌‍‌​​﻿‌‌‌‍​﻿‌‍​﻿‌‍​‍‌‍​‍‌‍‌‌​﻿‍‌​﻿‌﻿​﻿​‍​﻿‍​‌‍​‍‌‍‌‍​﻿‍‌​﻿‌‍‌‍​‍

Esta carpeta es para que entreguen sus ejercicios y el trabajo final.

## Estructura

```
entregas/
├── ejercicios/
│   ├── maven/           # Ejercicios dias 6-8
│   ├── hibernate/       # Ejercicios dias 9-10
│   └── spring_boot/     # Ejercicios dias 11-12
└── trabajo_final/
    ├── 2026-T1/         # Primera promocion (Marzo 2026)
    │   └── apellido_nombre/
    └── comunidad/       # Quienes hacen el curso por su cuenta
        └── apellido_nombre/
```

## Promociones

Las entregas del trabajo final se organizan por **promocion** (año + trimestre).
Cada grupo de alumnos que cursa con un profesor pertenece a una promocion.
Si haces el curso por tu cuenta, usa `comunidad/`.

| Promocion | Periodo | Notas |
|-----------|---------|-------|
| `2026-T1` | Marzo 2026 | Primera promocion |

## Como Entregar

### Ejercicios diarios

1. Crear carpeta con tu nombre: `entregas/ejercicios/spring_boot/garcia_maria/`
2. Poner tus archivos ahi
3. Commit y push a tu fork

### Trabajo final

1. Copiar la plantilla a tu carpeta de promocion:
   ```bash
   cp -r trabajo_final/plantilla/ entregas/trabajo_final/2026-T1/apellido_nombre/
   ```
2. Completar los archivos
3. Commit y push a tu fork

## Autoevaluación automática (también si vienes del libro)

Cada vez que subes un `PROMPTS.md` dentro de `entregas/` a tu fork, una GitHub Action lo evalúa con los
criterios del curso ([evaluacion-prompts-ia](https://github.com/TodoEconometria/evaluacion-prompts-ia)):
número de prompts, capturas, blueprint y extensión. El informe, con consejos para mejorar, sale en la
pestaña **Actions** de tu fork. Sin modelos de IA y sin coste. Es una orientación, no una nota oficial.

1. En tu fork, pestaña **Actions** → «I understand my workflows, go ahead and enable them» (una sola vez).
2. Si haces el curso por tu cuenta o vienes del libro *Arquitectura de Sistemas Enterprise*, entrega en
   `entregas/trabajo_final/comunidad/apellido_nombre/`.
3. Haz push: el informe aparece en unos segundos. También puedes lanzarlo a mano («Run workflow»).

## Reglas

1. Trabaja en TU fork
2. NO subas `.class` ni `target/` ni `.idea/`
3. Documenta tus prompts en `PROMPTS.md`
4. Commits descriptivos
