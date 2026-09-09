# Proyecto final

El proyecto intermodular es una experiencia integradora en la que el alumnado aplica, de forma práctica, lo aprendido en programación, sistemas, redes y servicios. A lo largo de varias fases —requisitos y criterios de aceptación, diseño, despliegue en entornos virtuales, seguridad, pruebas y operación— los equipos desarrollan un producto realista: puede ser un proyecto de configuración (p. ej., web+BD, SMB, AD, HTTPS, microcontroladores) o un proyecto de desarrollo de software. 

El trabajo culmina con memoria técnica, evidencias verificables y defensa pública. Se evalúan la calidad técnica, la trazabilidad requisito→prueba, la documentación y el trabajo en equipo. El objetivo es que el alumnado demuestre autonomía profesional, buenas prácticas y capacidad para diseñar, implementar, asegurar y mantener soluciones en entornos reales o virtualizados cercanos a la realidad.

## Entrega

Estructura mínima:

- Formato: un único zip con el nombre `PI_2SMRA_NOMBREPROYECTO.zip`.
- Estructura mínima:

```bash
PI_2SMRA_NOMBREPROYECTO.zip
├─ Memoria.pdf
├─ Presentacion.pdf
├─ Evidencias/            # capturas con nombre y fecha
├─ Diagramas/             # PNG/PDF (red/arquitectura)
├─ Config/                # ficheros .conf, .yaml, .reg, etc.
├─ Scripts/               # .sh, .ps1, .bat, SQL, etc.
└─ README.md              # cómo revisar rápidamente el proyecto
```

A continuación se desgranarán algunos de los documentos obligatorios que se deberán entregar.

### Memoria

1. Portada
    - Título del proyecto, alumnos, fecha, centro, módulo, curso
2. Introducción
    - Pequeño resumen en español e inglés
    - Contexto y problema
    - Resumen de la solución
    - Tecnologías principales
3. Objetivos y alcance
    - Objetivos medibles
4. Requisitos y criterios de aceptación
    - Requisitos funcionales y no funcionales
    - Criterios de aceptación claros y testeables
5. Diseño
6. Entorno, implementación y seguridad
    - Entorno donde se desarrolla
    - Pasos clave de configuración e implementación
    - Seguridad mínima
7. Pruebas
    - Matriz de trazabilidad Requisito -> CA -> Prueba -> Evidencia
    - Resultados esperados
8. Despliegue
    - Prerrequisitos
    - Pasos reproducibles
    - Validación
9. Manual de usuario y manual de administrador
    - Tareas típicas de cada usuario
10. Incidencias y resolución de problemas
    - Síntomas -> causa probable -> acciones
11. Conclusiones y trabajo futuro
    - Qué funciona, qué mejorarías, lecciones aprendidas

### Presentación

El archivo de presentación será el que se usará el día de la defensa del proyecto. Esta defensa durará 15 minutos, donde el alumnado realizará una presentación de su proyecto y una posterior demostración de uso del mismo, siendo equilibrado el tiempo empleado entre ambas partes. El equipo educativo, una vez finalizada la defensa, podrá realizar cualquier tipo de cuestión al alumnado en relación a dicho proyecto.

La presentación contendrá, al menos, los siguientes apartados:

1. Introducción (en inglés)
2. Objetivos
3. Requisitos
4. Diseño
5. Implementación
6. Objetivos alcanzados y trabajo futuro
7. Conclusiones

## Criterios de evaluación

La evaluación final del proyecto se realizará en base a:

- Seguimiento: 15%
    - Planificación
    - Asistencia a las reuniones de seguimiento telemático
    - Cumplimiento de hitos
- Producto final entregado: 60%
    - Funcionamiento
    - Calidad técnica e implementación
    - Documentación
    - Pruebas y trazabilidad
- Defensa: 25%
    - Estructura y claridad
    - Demo funcional
    - Preguntas y justificación