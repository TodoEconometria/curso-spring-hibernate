# Dia 1: Fundamentos de Java

**Curso IFCD0014 -- Semana 1, Dia 1**

---

## Objetivos del dia

- Instalar JDK 21 y configurar las variables de entorno (JAVA_HOME, PATH)
- Comprender la arquitectura de la JVM: compilacion (.java a .class) y ejecucion
- Escribir, compilar y ejecutar programas Java desde la terminal
- Dominar variables, tipos primitivos, operadores y control de flujo
- Trabajar con arrays y recorridos basicos

## Conceptos clave

Java es un lenguaje compilado e interpretado. El compilador `javac` transforma el codigo fuente (.java) en bytecode (.class), que la JVM ejecuta en cualquier sistema operativo. Esto es lo que significa "write once, run anywhere".

Los tipos primitivos (`int`, `double`, `boolean`, `char`) se almacenan directamente en memoria. Los tipos referencia (`String`, arrays, objetos) almacenan una direccion de memoria. Esta distincion es fundamental para entender como Java maneja los datos.

El control de flujo (`if/else`, `switch`, `for`, `while`) permite tomar decisiones y repetir operaciones. Los arrays son estructuras de tamano fijo que almacenan elementos del mismo tipo.

## Que vas a construir

Un programa `HolaMundo.java` compilado desde terminal, y una calculadora por consola que use `Scanner` para leer entrada del usuario, aplique operaciones aritmeticas y muestre resultados formateados con `System.out.printf`.

## Arquitectura sugerida

```
mi-primer-proyecto/
  HolaMundo.java
  Calculadora.java
  TablaMultiplicar.java
  EjerciciosArrays.java
```

Todos los archivos en un solo directorio. Compilacion manual con `javac` y ejecucion con `java`.

## Ejercicios

1. Escribir `HolaMundo.java`, compilar con `javac` y ejecutar con `java`
2. Crear una calculadora que lea dos numeros y una operacion (+, -, *, /) por consola
3. Generar la tabla de multiplicar de un numero dado por el usuario (usando `for`)
4. Declarar un array de 10 enteros, llenarlo con valores aleatorios (`Math.random()`) y encontrar el maximo, minimo y promedio
5. Implementar un `switch` que clasifique notas (0-4: suspenso, 5-6: aprobado, 7-8: notable, 9-10: sobresaliente)

## Verificacion

- [ ] `java -version` muestra JDK 21
- [ ] `javac HolaMundo.java` genera `HolaMundo.class` sin errores
- [ ] La calculadora lee entrada del usuario y muestra el resultado correcto
- [ ] El programa de arrays recorre los elementos y calcula estadisticas
- [ ] Puedes explicar la diferencia entre `int` y `Integer`

## Profundiza con el libro

Consulta el capitulo "Fundamentos de Java y el ecosistema JVM" en *Arquitectura de Sistemas Enterprise* de @TodoEconometria, donde se explica la relacion entre la JVM, el bytecode y por que Java sigue siendo el lenguaje dominante en aplicaciones empresariales.

---
Curso IFCD0014 | Prof. Juan Marcelo Gutierrez Miranda | @TodoEconometria
