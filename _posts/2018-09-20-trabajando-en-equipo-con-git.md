---
layout: post
title: Trabajando en equipo con Git
tags: [Git, VCS]
---

Existen varias formas posibles de trabajar en equipo con Git, acá vamos a presentar una que es bastante simple pero también muy poderosa, normalmente conocida como [GitHub flow](https://guides.github.com/introduction/flow/) o _feature branch flow_.

![GitHub flow](/assets/img/posts/github-flow.png)

Básicamente, se guia por tres principios:
1. El código que está en la rama **master** siempre tiene que funcionar.
1. Para comenzar una nueva funcionalidad, corregir un bug o cualquier tarea, se crea una rama nueva partiendo de master. El nombre de esta rama debe ser descriptivo: `busqueda-estudiante-por-legajo`, `error-campos-numericos`, `refactor-hibernate-stores`.
1. Concluido el trabajo, se crea un _pull request_ para integrar los cambios a **master**.

Adicionalmente, podríamos configurar un [servidor de integración continua](https://es.wikipedia.org/wiki/Integraci%C3%B3n_continua) para que despliegue nuestra aplicación bajo ciertas circunstancias. Por ejemplo:

* Cuando haya cambios nuevos en **master**, publicar la aplicación en el entorno de ensayo (_staging_).
* Cuando haya un _tag_ nuevo, publicar la aplicación en el entorno de producción.
* Todos los lunes a las 9:00hs, publicar lo que haya en **master** en el entorno de producción.


### Resumen de trabajo

Asumiendo que el backlog ya está completo, estos son los pasos que haría para ponerme a trabajar en una nueva funcionalidad:

1. Elijo la _user story_ en la que me voy a poner a trabajar (debería ser la más prioritaria).
1. Me asigno la _issue_ para que el resto del equipo sepa que lo voy a hacer yo.
1. Muevo la _issue_ a la columna **En progreso**.
1. En mi computadora, creo la rama correspondiente, por ejemplo: `7-momento-de-crisis` o `23-mejorar-vista-alumno`. Es buena práctica comenzar el nombre con el número de la issue asociada.
1. Trabajo. Si en el medio se _mergea_ algún _pull request_, conviene bajar los cambios de `master` a mi rama.
1. Cuando terminé, hago un _push_ y un _pull request_.
1. Alguien mira mi trabajo, me pide cambios, los resuelvo y vuelvo a subir (el _pull request_ sigue vivo y los cambios nuevos se reflejan automáticamente).
1. Mi trabajo se aprueba y se integra en `master`.
1. En mi computadora, vuelvo a `master` y me bajo los cambios nuevos, que incluyen lo que hice yo.
1. Vuelvo al punto 1.

### Recursos adicionales

* Cómo configurar la subida por SSH en GitHub: <https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/>
* Artículo de Martin Fowler sobre integración continua (en inglés): <https://www.martinfowler.com/articles/continuousIntegration.html>
* Ejemplos de otros flujos de trabajo posibles (en inglés): <https://www.atlassian.com/git/tutorials/comparing-workflows>
* Tutorial interactivo sobre ramas (_branches_) en Git: <https://learngitbranching.js.org/>.
