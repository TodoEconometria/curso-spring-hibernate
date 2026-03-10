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

## Reglas

1. Trabaja en TU fork
2. NO subas `.class` ni `target/` ni `.idea/`
3. Documenta tus prompts en `PROMPTS.md`
4. Commits descriptivos
