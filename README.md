<p align="center">
  <img width="400" src="https://es.fictionexpress.com/static/images/logo/fiction-express.svg" alt="Fiction Express Logo">
</p>

# Fiction Express Reader App

### Demo: 

url: https://fiction-express-reader-8o8y6jq9l-julioale21s-projects.vercel.app/

__user:__ 12345678

__password:__ fictionexpress

## Descripción del Proyecto

Este proyecto es una aplicación web para niños que permite la selección y lectura de libros. Está compuesto por dos partes principales:

1. **API RESTful (Backend)**: Construida con NestJS, simula un servidor real que proporciona:
   - Array de libros mock
   - Autenticación utilizando número de documento y contraseña
   - JWT para manejo de sesiones
   - Decoradores personalizados para control de acceso basado en roles
   - Documentación Swagger (disponible en `http://localhost:3002/api/v1` al correr localmente)

2. **Aplicación Frontend**: Desarrollada con Next.js 14, utilizando el nuevo sistema de app router. Características:
   - NextAuth para manejo de autenticación
   - React Query (TanStack) para gestión de estado y caché
   - Material UI (MUI) como biblioteca de componentes UI
   - Diseño responsive para dispositivos móviles y escritorio

## Tecnologías Utilizadas

- **Backend**: NestJS, JWT
- **Frontend**: Next.js 14, React, NextAuth, React Query, Material UI
- **Autenticación**: JWT, NextAuth
- **Documentación API**: Swagger

## Instrucciones para Ejecutar la Aplicación

1. Clona el repositorio como se indica arriba.
2. Navega a cada una de las carpetas de las aplicaciones (backend y frontend).
3. Sigue las instrucciones detalladas en el README de cada aplicación para su configuración y ejecución.

## Documentación Adicional

- La documentación Swagger de la API está disponible en `http://localhost:3002/api/v1` cuando se ejecuta localmente.
- Para más detalles sobre la implementación y estructura del proyecto, consulta los README individuales en las carpetas del backend y frontend.

---

## Fiction Express Reader App - Test Técnico


## Objetivos:

Webapp para niños: Selección y Lectura de Libros
Requisitos Técnicos
Frontend: React.js
Backend: Node.js
Base de datos: Fake API utilizando json-server
Diseño Responsive: La webapp debe ser accesible desde dispositivos móviles y navegadores web.
Bonus: Métricas sobre el tiempo de lectura por usuario y libro.


### Parte 1: Desarrollo Práctico

#### Requisitos Funcionales

1. Login de Usuario:
Crear un sistema de login básico (no es necesario implementar autenticación completa, pero puede ser con local storage, mock data o un simple formulario que valide el acceso de los usuarios).
Cada usuario puede ser identificado con un ID único (puede ser generado o ingresado manualmente).
2. Catálogo de libros:
Utilizar un json-server que simule una API y provea un JSON con un listado de 2 libros de texto.
El JSON debe contener la siguiente información sobre cada libro:
Título del libro
Autor
Contenido (dividido por páginas, con una estructura como un array de strings o párrafos)
Identificador único del libro
Ejemplo de JSON para libros:

```
{
  "books": [
    {
      "id": 1,
      "title": "Las aventuras de Juan",
      "author": "Autor Ficticio",
      "pages": [
        "Capítulo 1: Había una vez en un lugar muy lejano...",
        "Capítulo 2: Continuaron las aventuras de Juan...",
        "Capítulo 3: El final de la historia se acercaba..."
      ]
    },
    {
      "id": 2,
      "title": "El viaje de la imaginación",
      "author": "Escritor Desconocido",
      "pages": [
        "Capítulo 1: La imaginación puede llevarte a lugares increíbles...",
        "Capítulo 2: A medida que el viaje continuaba, las posibilidades parecían infinitas...",
        "Capítulo 3: El fin de la aventura."
      ]
    }
  ]
}
```

3. Selección del libro:
Crear una interfaz para que el usuario pueda seleccionar uno de los libros disponibles.
Mostrar el título, autor y una pequeña descripción o resumen del libro.
4. Lector de texto:
Una vez que el libro sea seleccionado, debe haber una vista de lector de texto donde el contenido se muestre página por página.
Debe haber botones de "Siguiente página" y "Página anterior" para navegar entre las páginas del libro.
5. Métricas de lectura:
Registrar cuánto tiempo pasa el usuario en cada página (en milisegundos).
Registrar el tiempo total que el usuario pasa leyendo un libro.
Al final de la lectura, mostrar las métricas de:
Tiempo de lectura total del libro.
Tiempo promedio por página.


#### Detalles adicionales:

La aplicación debe ser responsive y funcionar tanto en dispositivos móviles como en navegadores de escritorio.
El diseño puede ser sencillo, pero debe ser funcional y fácil de usar.
La API con json-server debe simular correctamente la funcionalidad de un servidor, proveyendo datos de los libros y permitiendo consumirlos.

#### Herramientas sugeridas:

- Frontend: React.js
- Backend (para métricas y usuarios): Node.js + json-server para simular una API.
- Estado en el frontend: Utilizar React hooks, Context API o Redux.
- Base de datos mock (Fake API): json-server o cualquier otra herramienta que permita crear una fake API rápidamente.
- Métricas: Pueden ser guardadas en memoria local (localStorage o state del frontend). No es necesario persistir los datos en una base de datos.



### Parte 2: Preguntas Teóricas

#### Preguntas: 
Considerando que 1 millón de niños utilizan esta plataforma para leer
libros y reportar métricas de tiempo de lectura, ¿cómo gestionarías esto a nivel
técnico? Responde las siguientes preguntas:

1. ¿Qué tipo de base de datos utilizarías para almacenar las métricas de
lectura de los usuarios? ¿Por qué?

2. ¿Cómo garantizamos la escalabilidad del sistema para soportar una
carga de 1M de usuarios simultáneos?

3. ¿Has trabajado con alguna base de datos o infraestructura que soporte
un volumen alto de usuarios y datos? Si es así, cuéntanos tu experiencia y
qué tecnologías utilizaste.

#### Respuestas: 

1. Para almacenar las métricas de lectura de los usuarios, yo elegiría MongoDB u alguna otra base de datos no relacional. En este caso, MongoDB es una base de datos que se adapta bien a este tipo de datos. MongoDB es flexible, lo que nos permite guardar diferentes tipos de métricas sin tener que cambiar la estructura de la base de datos cada vez. Esto es útil porque podríamos querer añadir nuevas métricas en el futuro. Además, MongoDB es buena manejando muchos datos a la vez, lo cual es importante si tenemos muchos usuarios leyendo al mismo tiempo. Es rápida para guardar información, que es lo que necesitamos al registrar constantemente las métricas de lectura. También nos permite hacer búsquedas y análisis de datos de forma eficiente, lo que nos ayudará a entender cómo leen nuestros usuarios. Si el proyecto crece, MongoDB puede expandirse fácilmente. Y si queremos, podemos usarla en la nube con MongoDB Atlas, lo que facilita su gestión.

2. 
Podriamos usar una arquitectura de microservicios lo cual nos permite dividir el sistema en partes más pequeñas y manejables que pueden escalar de forma independiente según sea necesario. (Esto es mucho mas eficiente pero tambien agrega complejidad)
Podriamos implementar un sistema de balanceo de carga para distribuir el tráfico entre múltiples servidores. Esto ayuda a prevenir que un solo servidor se sobrecargue.
Podriamos utilizar una base de datos distribuida como MongoDB que puede manejar grandes volúmenes de datos y escalar horizontalmente añadiendo más servidores.
Podriamos aprovechar los servicios en la nube como AWS o Azure, que ofrecen escalado automático y pueden aumentar o disminuir los recursos según la demanda en tiempo real.
Seria util un sistema de caché, como Redis, para almacenar datos frecuentemente accedidos y reducir la carga en la base de datos principal.
Si tenemos contenido estatico podriamos utilizar un CDN para distribuir contenido estático, reduciendo la carga en nuestros servidores principales.
Seria importante optimizar las consultas de base de datos y el código de la aplicación para mejorar la eficiencia.
Tambien es importante implementar un sistema de monitoreo para identificar y resolver cuellos de botella rápidamente. Aqui es util por ejemplo Datadog, tambien sistemas de logs como Sentry que nos permita tener un track de todo lo que ocurre.

3. Actualmente, estoy trabajando en un sistema que se espera sea utilizado por cerca de 8 millones de usuarios. Aunque los servicios principales están a cargo del cliente, hemos tenido que implementar varias estrategias para optimizar los tiempos de respuesta, ya que algunos de estos servicios son bastante lentos. Nuestro backend funciona como un puente entre estos servicios y nuestro frontend. Una de las estrategias clave ha sido el uso de caché, específicamente con Redis, para almacenar datos frecuentemente accedidos y reducir la carga en los servicios más lentos.
En un proyecto anterior para una empresa australiana, trabajé con una plataforma educativa que manejaba millones de usuarios. La infraestructura era extensa y compleja. Una de nuestras principales estrategias fue aprovechar la generación estática de contenido con Next.js. El contenido se gestionaba desde un CMS (Sistema de Gestión de Contenidos, en este caso Prismic pero tambien se empezo a implementar para algunos casos Builder.io) y, cada vez que había un cambio, se activaba un webhook que iniciaba el proceso de generación de contenido estático con Next.js.
Usábamos pipelines para automatizar este proceso, generando el contenido estático y almacenándolo en buckets (almacenamiento en la nube). En el entorno de desarrollo utilizábamos AWS, mientras que en producción usábamos Azure. Este contenido estático se distribuía a través de un CDN (Red de Distribución de Contenidos) con réplicas en diferentes regiones geográficas, lo que reducía significativamente la latencia de acceso para los usuarios.
La combinación de páginas estáticas servidas desde un CDN, junto con la ejecución de ciertas tareas en procesos separados utilizando servicios serverless como Azure Functions o AWS Lambda, nos permitió manejar grandes volúmenes de datos y alta concurrencia de usuarios de manera eficiente. Este enfoque distribuido y orientado al rendimiento fue clave para soportar la escala masiva de usuarios de la plataforma