# Contribuir al Curso

## Para estudiantes de la comunidad

Si haces el curso por tu cuenta (no en una promocion con profesor), sigue estos pasos:

### 1. Haz fork del repositorio

Click en **Fork** arriba a la derecha en GitHub.

### 2. Clona y configura

```bash
git clone https://github.com/TU_USUARIO/curso-spring-hibernate.git
cd curso-spring-hibernate
git remote add upstream https://github.com/TodoEconometria/curso-spring-hibernate.git
```

### 3. Sigue los manuales en orden

Empieza por `manuales/DIA_01_FUNDAMENTOS_JAVA.md` y avanza dia a dia.

### 4. Entrega tu trabajo final

Copia la plantilla a tu carpeta en comunidad:

```bash
cp -r trabajo_final/plantilla/ entregas/trabajo_final/comunidad/TU_USUARIO/
```

Completa todos los archivos, especialmente `PROMPTS.md`.

### 5. Sincroniza tu fork

```bash
git fetch upstream
git merge upstream/main
```

## Reglas

- **NO abras Pull Requests.** Trabaja en tu fork.
- **Documenta tus prompts** honestamente (sin limpiar errores).
- **No subas** archivos compilados (`.class`, `target/`, `.idea/`).
- **Commits descriptivos** en cada avance.

## Preguntas

Abre un **Issue** en el repositorio original con tu duda.

---

Curso IFCD0014 | Prof. Juan Marcelo Gutierrez Miranda | @TodoEconometria
