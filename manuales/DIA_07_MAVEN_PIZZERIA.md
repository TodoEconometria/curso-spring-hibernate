# Dia 7: Pizzeria Maven con Dependencias Externas

**Curso IFCD0014 -- Semana 2, Dia 7**

---

## Objetivos del dia

- Agregar dependencias externas al proyecto Maven desde Maven Central
- Integrar la libreria Gson para serializar objetos Java a JSON
- Exportar pedidos de la Pizzeria a archivos JSON
- Leer archivos JSON y reconstruir objetos Java (deserializacion)
- Preparar la transicion mental de "datos en memoria" a "datos persistentes"

## Conceptos clave

Maven Central es el repositorio global de librerias Java. Para usar Gson (la libreria de Google para JSON), solo necesitas agregar su coordenada (`com.google.code.gson:gson:2.11.0`) en la seccion `<dependencies>` del `pom.xml`. Maven descarga el JAR automaticamente.

La serializacion convierte un objeto Java en un formato transportable (JSON, XML, bytes). Gson convierte `Pizza pizza = new Pizza("Margherita", 8.50)` en `{"nombre":"Margherita","precio":8.50}`. La deserializacion hace el proceso inverso. Este concepto es fundamental: las APIs REST que construiras con Spring hacen exactamente esto con Jackson.

Exportar pedidos a JSON es el primer paso hacia la persistencia. Hoy guardas en archivos, manana en base de datos con Hibernate, y despues lo expones como API REST con Spring. El objeto `Pedido` es el mismo; lo que cambia es donde se guarda.

## Que vas a construir

Pizzeria v4: el mismo sistema de pedidos, pero ahora con capacidad de exportar pedidos completos a archivos `.json` e importarlos de vuelta. El menu permite guardar y cargar pedidos.

## Arquitectura sugerida

```
pizzeria/
  pom.xml (con dependencia de Gson)
  src/main/java/com/curso/pizzeria/
    modelo/        (Pizza, Pedido, Vendible...)
    repositorio/   (PizzaRepository, PedidoRepository)
    servicio/      (PizzaService, PedidoService, ExportService)
    excepcion/     (excepciones personalizadas)
    App.java
  datos/
    pedidos.json   (generado al exportar)
```

## Ejercicios

1. Agregar la dependencia de Gson en el `pom.xml` y verificar con `mvn dependency:tree`
2. Crear `ExportService` con un metodo `exportarPedido(Pedido p, String archivo)` que serialice a JSON
3. Implementar `importarPedido(String archivo)` que lea un JSON y devuelva un objeto `Pedido`
4. Modificar el menu principal para agregar opciones "Guardar pedido" y "Cargar pedido"
5. Exportar una lista de todos los pedidos del dia en un unico archivo `resumen_diario.json`

## Verificacion

- [ ] `mvn dependency:tree` muestra Gson como dependencia
- [ ] Al exportar un pedido, el archivo JSON se genera con formato legible (pretty printing)
- [ ] Al importar el JSON, se reconstruye un objeto `Pedido` funcional con todos sus items
- [ ] El ciclo completo funciona: crear pedido > exportar > cerrar programa > importar > verificar datos
- [ ] El JSON incluye los items del pedido con sus precios y descripciones

## Profundiza con el libro

En *Arquitectura de Sistemas Enterprise* de @TodoEconometria, el capitulo "De archivos a bases de datos" explica la evolucion natural de la persistencia: archivos planos > JSON > base de datos relacional > ORM. Hoy estas en JSON; en dos dias estaras en Hibernate.

---
Curso IFCD0014 | Prof. Juan Marcelo Gutierrez Miranda | @TodoEconometria
