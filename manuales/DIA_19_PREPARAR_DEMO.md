# Dia 19: Preparar la Demo

**Curso IFCD0014 -- Semana 5, Dia 19**

---

## Objetivos del dia

- Completar el checklist tecnico del proyecto antes de presentar
- Asegurar que el README esta completo y profesional
- Preparar la estructura de la presentacion (5-7 minutos)
- Practicar la demo en vivo con un guion preparado
- Resolver problemas de ultimo minuto

## Conceptos clave

La preparacion de una demo tecnica tiene dos partes: la tecnica y la comunicativa. La parte tecnica consiste en verificar que todo funciona (la app arranca, los endpoints responden, el CI/CD esta verde, Railway esta activo). La parte comunicativa es estructurar una presentacion clara que muestre el proyecto sin perderse en detalles.

La estructura recomendada para una presentacion de 5-7 minutos: (1) Que problema resuelve tu proyecto - 1 min, (2) Arquitectura y tecnologias usadas - 1 min, (3) Demo en vivo de 3-4 endpoints clave - 3 min, (4) Que aprendiste y proximos pasos - 1 min. No intentes mostrar todo; elige los endpoints mas interesantes.

El plan B es esencial: si Railway esta caido, ten Docker Compose listo para ejecutar localmente. Si la demo en vivo falla, ten capturas de Swagger UI preparadas. Siempre hay un plan B.

## Que vas a construir

No se construye codigo nuevo. Este dia es para verificar, pulir y practicar. El entregable es tu proyecto listo para presentar y un guion de demo que hayas practicado al menos dos veces.

## Checklist tecnico

```
REPOSITORIO
- [ ] README completo con descripcion, tecnologias, instrucciones y capturas
- [ ] Badge de CI/CD en el README (verde)
- [ ] Codigo limpio, sin archivos temporales ni credenciales
- [ ] .gitignore configurado correctamente
- [ ] Ultimo commit en main con todo funcionando

APLICACION
- [ ] mvn clean verify pasa sin errores localmente
- [ ] docker compose up levanta el stack completo
- [ ] Swagger UI muestra todos los endpoints
- [ ] Los endpoints CRUD funcionan correctamente
- [ ] data.sql carga datos de prueba

DEPLOY
- [ ] Railway despliega sin errores
- [ ] La URL publica responde
- [ ] Los endpoints funcionan en produccion
```

## Ejercicios

1. Recorrer el checklist tecnico punto por punto y resolver lo que falte
2. Tomar capturas de Swagger UI para el README y como backup de la demo
3. Escribir un guion de presentacion con tiempos por seccion
4. Practicar la demo completa cronometrada (maximo 7 minutos)
5. Preparar el plan B: Docker Compose funcionando + capturas de respaldo

## Verificacion

- [ ] Todo el checklist tecnico esta completo (sin items pendientes)
- [ ] El README tiene capturas de la API funcionando
- [ ] Puedes explicar tu proyecto en 1 minuto (elevator pitch)
- [ ] Has practicado la demo al menos una vez completa
- [ ] Tienes plan B preparado por si falla la demo en vivo

## Profundiza con el libro

En *Arquitectura de Sistemas Enterprise* de @TodoEconometria, el apendice "Presentar proyectos tecnicos" ofrece consejos para comunicar decisiones arquitectonicas a audiencias tecnicas y no tecnicas, y como manejar preguntas inesperadas durante una demo.

---
Curso IFCD0014 | Prof. Juan Marcelo Gutierrez Miranda | @TodoEconometria
