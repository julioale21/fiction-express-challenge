<p align="center">
  <img width="400" src="https://es.fictionexpress.com/static/images/logo/fiction-express.svg" alt="Fiction Express Logo">
</p>

# Fiction Express Reader App

### Demo:

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

### Opción 1: Utilizando Docker y Docker Compose

1. Asegúrate de tener Docker instalado y en ejecución.
2. Clona el repositorio:
   ```
   git clone [URL_DEL_REPOSITORIO]
   ```
3. Navega al directorio del proyecto.
4. Ejecuta:
   ```
   docker-compose up --build
   ```
5. Una vez finalizado, la aplicación estará disponible en: `http://localhost:3000`

### Opción 2: Ejecución Manual

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

