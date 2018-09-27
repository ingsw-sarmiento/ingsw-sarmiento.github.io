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


### Recursos adicionales

* Cómo configurar la subida por SSH en GitHub: <https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/>
* Artículo de Martin Fowler sobre integración continua (en inglés): <https://www.martinfowler.com/articles/continuousIntegration.html>
* Ejemplos de otros flujos de trabajo posibles (en inglés): <https://www.atlassian.com/git/tutorials/comparing-workflows>
* Tutorial interactivo sobre ramas (_branches_) en Git: <https://learngitbranching.js.org/>.
