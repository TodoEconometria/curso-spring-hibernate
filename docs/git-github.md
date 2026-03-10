# Git y GitHub — Referencia Rapida‌‌‌​‌​‌‌​﻿‍‍​﻿​﻿‌‍‌‌‌‍​﻿​﻿‍​‌‍​﻿​﻿‍‌​﻿‍‌​﻿‍​​﻿​﻿​﻿‌﻿​﻿‌﻿​﻿​​‌‍​﻿‌‍‌​‌‍‌‍​﻿‌‌

Comandos esenciales para trabajar con el repositorio del curso.

---

## Fork y Clone

### 1. Hacer fork

En GitHub, clic en **Fork** en el repositorio del profesor.

### 2. Clonar tu fork

```bash
git clone https://github.com/TU_USUARIO/curso-spring-hibernate.git
cd curso-spring-hibernate
```

### 3. Configurar upstream

```bash
git remote add upstream https://github.com/TodoEconometria/curso-spring-hibernate.git
```

### 4. Verificar remotes

```bash
git remote -v
# origin    https://github.com/TU_USUARIO/curso-spring-hibernate.git (fetch)
# origin    https://github.com/TU_USUARIO/curso-spring-hibernate.git (push)
# upstream  https://github.com/TodoEconometria/curso-spring-hibernate.git (fetch)
# upstream  https://github.com/TodoEconometria/curso-spring-hibernate.git (push)
```

---

## Sincronizar tu fork

Cuando el profesor publique material nuevo:

```bash
# 1. Traer los cambios del profesor
git fetch upstream

# 2. Fusionar con tu rama main
git checkout main
git merge upstream/main

# 3. Subir a tu fork
git push origin main
```

!!! tip "Hazlo seguido"
    Sincroniza tu fork **antes de cada clase** para tener el material mas reciente.

---

## Comandos del dia a dia

### Ver estado

```bash
git status          # Que archivos cambiaron?
git log --oneline   # Historial de commits
git diff            # Que cambio exactamente?
```

### Guardar cambios

```bash
git add archivo.java       # Agregar un archivo
git add .                  # Agregar todo
git commit -m "mensaje"    # Crear commit
git push                   # Subir a GitHub
```

### Crear rama

```bash
git checkout -b mi-rama    # Crear y cambiar a nueva rama
git checkout main          # Volver a main
```

---

## Flujo de entrega

### Ejercicios diarios

```bash
# 1. Crea tu carpeta de entrega
mkdir -p entregas/ejercicios/maven/apellido_nombre

# 2. Copia tus archivos ahi
cp mi-archivo.java entregas/ejercicios/maven/apellido_nombre/

# 3. Commit y push
git add entregas/
git commit -m "Ejercicio Maven - Apellido Nombre"
git push
```

### Trabajo final

```bash
# 1. Copia la plantilla
cp -r trabajo_final/plantilla/ entregas/trabajo_final/2026-T1/apellido_nombre/

# 2. Completa los archivos (PROMPTS.md, 01_README.md, etc.)

# 3. Commit y push
git add entregas/trabajo_final/2026-T1/apellido_nombre/
git commit -m "Trabajo Final - Apellido Nombre"
git push
```

!!! warning "No crear Pull Request"
    El profesor revisa tu fork directamente. **NO necesitas crear PR.**

---

## Repo de portfolio (proyecto propio)

Cuando llegues al trabajo final (dia 13+), ademas de tu fork vas a crear un
**repo propio** para tu proyecto. Es tu pieza de portfolio profesional.

Guia completa: [Crear tu Repo de Portfolio](git-github/crear-repo-portfolio.md)

---

## Errores comunes

| Error | Causa | Solucion |
|---|---|---|
| `fatal: not a git repository` | No estan dentro del repo | `cd curso-spring-hibernate` |
| `error: failed to push` | Tu rama esta desactualizada | `git pull` antes de `git push` |
| `CONFLICT` en merge | Dos personas cambiaron lo mismo | Pedir ayuda al profesor |
| `Permission denied` | No tienes acceso | Verificar que clonaste TU fork, no el del profesor |

---

## .gitignore

Estos archivos y carpetas **nunca** se deben subir:

```
target/         # Compilados de Maven
.idea/          # Configuracion de IntelliJ
*.class         # Bytecode Java
*.jar           # Archivos compilados
.env            # Variables de entorno con credenciales
out/            # Carpeta de salida
```
