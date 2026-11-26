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


---

# Práctica 4. Manejo de tablas y formularios

**Responsable:** Erick Chi Calán
**Semana de ejecución:** Semana 3

## Descripción

Se agregó la página `contacto.html` con el formulario **Customer Center** de la imagen del manual.
Tiene dos pestañas: **New customer** (nombre, correo y pregunta) y **Existing customer** (usuario y
contraseña). Se usó **Bootstrap 5.3.8**, descargado dentro del proyecto en la carpeta `bootstrap/`,
para el menú superior, las pestañas, la rejilla de `div` y los campos del formulario. Los estilos
propios están en `contacto.css`. También se agregó el enlace **Customer Center** al menú de
`index.html` y `soporte.html`.

Los dos formularios envían sus datos al correo **ypech@itescam.edu.mx** con el servicio
**FormSubmit** (`action="https://formsubmit.co/ypech@itescam.edu.mx"`, `method="POST"`). El correo
llega en formato de tabla (`_template=table`) con un asunto distinto para cada formulario.

Todo el trabajo se hizo en la rama **`formulario`**, que se mezcló a `main` y **no se borró** para
que sirva de evidencia.

## Archivos nuevos o modificados

```
contacto.html   Página nueva con el formulario Customer Center
contacto.css    Estilos propios del formulario
bootstrap/      Bootstrap 5.3.8 (CSS y JS compilados)
index.html      Se agregó el enlace Customer Center al menú
soporte.html    Se agregó el enlace Customer Center al menú
```

## Cómo probar

1. Copiar los archivos a `app-laravel/public/practica2/` del entorno Docker de la Práctica 1.
2. Abrir <http://localhost:8000/practica2/contacto.html>
3. Llenar el formulario y presionar **Continue** o **Login To Support**.
4. El primer envío genera un correo de activación de FormSubmit en ypech@itescam.edu.mx; después
   de activarlo, cada envío llega como tabla a ese correo.

## Comparativa de tiempos

Tiempos registrados en TopTracker (proyecto *Practica 4 - Formularios*, una actividad por tarea).
El tiempo real está en minutos:segundos.

| #  | Tarea                                          | Estimado   | Real   | Diferencia |
|----|------------------------------------------------|------------|--------|------------|
| 1  | Clonar el repo y crear la rama `formulario`    | 15 min     | 3:37   | -11:23     |
| 2  | Descargar Bootstrap y agregarlo                | 15 min     | 4:19   | -10:41     |
| 3  | Estructura de `contacto.html` y menú superior  | 20 min     | 5:27   | -14:33     |
| 4  | Pestañas New / Existing customer               | 20 min     | 3:53   | -16:07     |
| 5  | Formulario New customer                        | 25 min     | 3:35   | -21:25     |
| 6  | Formulario Existing customer                   | 15 min     | 3:43   | -11:17     |
| 7  | Envío al correo con FormSubmit                 | 15 min     | 3:47   | -11:13     |
| 8  | Estilos para parecerse a la imagen             | 30 min     | 5:38   | -24:22     |
| 9  | Enlace en el menú de index y soporte           | 10 min     | 2:31   | -7:29      |
| 10 | Commit, push y merge a `main`                  | 20 min     | 2:42   | -17:18     |
| 11 | Prueba en Docker y envío del formulario        | 20 min     | 6:12   | -13:48     |
| 12 | Tabla comparativa y conclusiones               | 25 min     | 3:21   | -21:39     |
|    | **Total**                                      | **3 h 50 min** | **48:45** | **-3 h 01 min** |
## Conclusiones

El tiempo estimado fue de 3 horas con 50 minutos y el real fue de 48 minutos con 45 segundos, unas 3 horas menos. Todas las tareas
tardaron menos de lo calculado. La estimación se hizo pensando en escribir cada parte desde cero y
buscando la documentación, pero el trabajo se hizo siguiendo una guía paso a paso con el código ya
planeado, y Bootstrap resolvió casi todo el diseño (menú, pestañas, campos y botones) con clases ya
hechas. Las tareas más largas fueron la estructura de la página y los estilos, porque fue donde más
se revisó el resultado contra la imagen del manual.

Lo que más tiempo hizo perder fueron detalles de herramientas, no de código. En la tarea 7 se
ejecutó `git add` antes de guardar el archivo y Git respondió *nothing to commit*, así que hubo que
guardar y repetir el comando. Antes de empezar, el sitio `toptracker.com` no respondía; TopTracker
ahora está en `toptal.com/tracker` y, como no permite que el dueño del proyecto se agregue a sí
mismo como trabajador, se usó una segunda cuenta para registrar el tiempo. Ese tiempo de
configuración no aparece en la tabla porque fue antes de iniciar el registro.

Para la siguiente práctica, la estimación debe considerar las herramientas que ya se tienen
(frameworks como Bootstrap y el entorno Docker ya configurado) y separar un tiempo para preparar
las herramientas de medición y control de versiones.