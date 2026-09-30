# Práctica 2. Elementos básicos del lenguaje de marcas

**Materia:** Programación Web (AEB-1055)
**Carrera:** Ingeniería en Sistemas Computacionales - ITESCAM
**Equipo:** TacoCoders
**Semana de ejecución:** Semana 2

### Integrantes

- Josue Hilario Cab Ku
- Erick Chi Calán
- Luis Sánchez Ucán
- Mauricio Cih Koh
- Tommy Can Mut

## Descripción

En esta práctica se replican dos páginas de un sitio de hosting de WordPress usando
solo HTML5. Todavía no se aplican estilos, eso corresponde a la Práctica 3. Lo que se
cuida aquí es la estructura: títulos de distinto nivel, párrafos, listas ordenadas y
listas no ordenadas, enlaces y etiquetas semánticas.

## Archivos

```
index.html     Página 1: planes de hosting (StartUp, GrowBig, GoGeek)
soporte.html   Página 2: soporte y herramientas para webmasters
README.md      Plan de trabajo y registro de tiempos
```

## Plan de trabajo

| #  | Tarea                                                        | Página | Tiempo estimado |
|----|--------------------------------------------------------------|--------|-----------------|
| 1  | Estructura base HTML5 (doctype, head, metas, semántica)       | Ambas  | 20 min |
| 2  | Barra superior con logos                                      | Pág. 1 | 15 min |
| 3  | Sección principal: título y oferta del descuento              | Pág. 1 | 20 min |
| 4  | Tres tarjetas de planes con sus listas de características     | Pág. 1 | 45 min |
| 5  | Botones "Get Plan" y enlaces de características               | Pág. 1 | 15 min |
| 6  | Banner de soporte con sus cuatro puntos                       | Pág. 2 | 30 min |
| 7  | Sección de herramientas (seis bloques con título y párrafo)   | Pág. 2 | 45 min |
| 8  | Enlaces "Find Out More" y pie de página                       | Pág. 2 | 15 min |
| 9  | Navegación entre las dos páginas                              | Ambas  | 10 min |
| 10 | Validación en el validador del W3C y correcciones             | Ambas  | 20 min |
| 11 | Publicación en el contenedor Docker de la Práctica 1          | -      | 20 min |
| 12 | README, commits y push a GitHub                               | -      | 20 min |
|    | **Total**                                                     |        | **4 h 35 min** |

## Comparativa de tiempos

Los tiempos reales se toman de TopTracker. Llenar la última columna al terminar.

| #  | Tarea                                        | Estimado | Real | Diferencia |
|----|-----------------------------------------------|----------|------|------------|
| 1  | Estructura base HTML5                         | 20 min   |      |            |
| 2  | Barra superior con logos                      | 15 min   |      |            |
| 3  | Sección principal de la página 1              | 20 min   |      |            |
| 4  | Tarjetas de planes                            | 45 min   |      |            |
| 5  | Botones y enlaces de la página 1              | 15 min   |      |            |
| 6  | Banner de soporte                             | 30 min   |      |            |
| 7  | Sección de herramientas                       | 45 min   |      |            |
| 8  | Enlaces y pie de la página 2                  | 15 min   |      |            |
| 9  | Navegación entre páginas                      | 10 min   |      |            |
| 10 | Validación W3C                                | 20 min   |      |            |
| 11 | Publicación en Docker                         | 20 min   |      |            |
| 12 | README y control de versiones                 | 20 min   |      |            |
|    | **Total**                                     | 4 h 35 min |    |            |

## Cómo probar las páginas

Las páginas se publican dentro del entorno Docker que se armó en la Práctica 1.

1. Copiar la carpeta dentro del proyecto de Laravel:
   `cp index.html soporte.html ../practica-1-docker/app-laravel/public/practica2/`
2. Levantar los contenedores: `docker compose -p dev -f docker-compose.dev.yml up -d`
3. Abrir <http://localhost:8000/practica2/index.html>
4. Revisar que el enlace a la página de soporte funcione en los dos sentidos.

## Casos de prueba

| # | Caso                                     | Resultado esperado                          | Estado |
|---|------------------------------------------|---------------------------------------------|--------|
| 1 | Abrir index.html                         | Se ve el título y los tres planes           |        |
| 2 | Abrir soporte.html                       | Se ven los cuatro puntos y las seis tools   |        |
| 3 | Click en el menú de navegación           | Cambia entre las dos páginas                |        |
| 4 | Validar en validator.w3.org              | Sin errores                                  |        |
| 5 | Abrir desde el contenedor en el puerto 8000 | Las dos páginas cargan                   |        |

## Conclusiones

(Escribir al terminar, con los tiempos ya registrados. Borrador para ajustar:)

El tiempo estimado inicial fue de 4 horas con 35 minutos. Al medir con TopTracker me di
cuenta de que las tareas repetitivas, como las tarjetas de planes y la sección de
herramientas, se hacen más rápido de lo que pensaba porque se repite la misma estructura
con distinto contenido. En cambio, la parte de validación y acomodo del HTML me llevó más
tiempo del que había calculado, sobre todo por detalles como cerrar bien las etiquetas y
elegir el nivel correcto de encabezado.

Lo más útil de la práctica fue notar que escribir HTML sin estilos obliga a pensar primero
en la estructura del contenido. Al separar títulos, párrafos y listas desde el inicio, la
página ya se entiende aunque no tenga CSS, y eso va a facilitar el trabajo de la Práctica 3.
