---
layout: post
title: Publicando nuestra aplicación
tags: [SCM, Deploy, Heroku]
---

Ya programamos, probamos, le hicimos probar a nuestro hermano o prima que "no entiende de computadoras" y hasta le mostramos algo al usuario. ¿Y ahora?

Para poder cerrar el círculo es necesario **publicar** nuestro software, para que otras personas (que probablemente no programan) puedan verlo y usarlo. Esto se vuelve aún más importante cuando trabajamos bajo una [metodología ágil](https://es.wikipedia.org/wiki/Desarrollo_%C3%A1gil_de_software), porque _deberíamos_ hacerlo bastante seguido.

Previamente, tenemos que tomar una serie de decisiones:

* ¿Dónde subirlo? Puede ser un servidor nuestro o uno contratado, gestionado por alguien más.
* ¿Cómo subirlo? Depende en gran medida de lo anterior, pero podríamos hacerlo de varias formas: via [FTP](https://es.wikipedia.org/wiki/Protocolo_de_transferencia_de_archivos), via `Git`, via `scp`, llevando un pendrive hasta el servidor, etc.
* ¿Cuántos ambientes vamos a tener? Algunas opciones: testing, producción, pre-producción, desarrollo.

Sería interesante que todas esas decisiones queden documentadas, pero mejor aún: que queden automatizadas y susceptibles de ser ejecutadas lo más rápido posible _por cualquier miembro de nuestro equipo_. En un escenario ideal, incluso hasta personas sin un perfil técnico podrían subir nuevas versiones, simplemente teniendo un dominio básico de una herramienta como Git.

## Pasos previos

Hay que asegurarse de que nuestro **ambiente** sea reproducible en otra máquina que no sea la nuestra, para que las cosas funcionen como esperamos en el servidor. Este ambiente es básicamente todo lo que tenemos instalado y configurado en nuestra computadora que hace que nuestra aplicación funcione - sea porque lo instalamos adrede o porque ya venía con la instalación de nuestro sistema operativo.

Algunas cosas a tener en cuenta:

* Nuestro sistema operativo.
* Las variables de entorno. Para ver las que tenés configuradas, basta con escribir `export` en una terminal. También puede pasar que tu aplicación configure otras al ejecutarse.
* Las versiones de los programas que usamos.

Además, en lo que refiere a nuestra aplicación, probablemente haya más configuraciones que dependan del ambiente:

* Las dependencias: bibliotecas de otras personas, que usamos dentro de nuestra aplicación.
* La conexión con la base de datos.
* Rutas de archivos externos.

Para todo esto, conviene usar una herramienta que automatice gran parte de estas tareas, como por ejemplo [Maven](https://maven.apache.org/).

![Ciclo de vida de Maven](/assets/img/posts/maven-lifecycle.jpg)

## Heroku: plataforma "gratuita" para publicar aplicaciones

Heroku es una plataforma que nos permite subir nuestro código y tener en pocos minutos funcionando una versión publicada del mismo, con poca o mínima configuración. Tiene una versión gratuita que nos permite tener nuestra aplicación online, [con algunas limitaciones (bastante agresivas) de tiempo](https://devcenter.heroku.com/articles/free-dyno-hours).

De todos modos, nos sirve como ejemplo de que publicar código no siempre es una tarea _tan_ compleja como suena. Sin dudas hay escenarios donde esto es insuficiente y no es muy recomendable para una aplicación "de verdad", pero para publicar prototipos o hacer pruebas es más que suficiente.

#### Manos a la obra

Vamos a seguir [este tutorial](https://devcenter.heroku.com/articles/getting-started-with-java) para aprender algunos conceptos básicos sobre la plataforma y publicar una aplicación de ejemplo en Java.

Les dejo además algunos recursos que encontré sobre cómo subir aplicaciones Wicket a Heroku:

* Un mini tutorial, un poco desactualizado: <http://wicketinaction.com/2011/09/git-wicket-running-on-heroku/>. Adentro tiene link al repo de ejemplo que menciona y cuenta qué cosas no le funcionaron.
* Un ejemplo en GitHub, que puede usarse de base para subir la app: <https://github.com/alexo/heroku-wicket-web-app>.

Como verán, esto no es tan sencillo como el ejemplo - los percances de salirnos de las tecnologías _mainstream_ o "de moda". A fin de cuentas, alguna cosa siempre no va a ser como queremos y vamos a tener que acudir a nuestra capacidad más preciada: la de investigar y resolver problemas. ¿O no es lo que hacemos lxs técnicxs acaso? 😏

## Otras opciones

Dejo acá un pequeño listado, no exhaustivo, de opciones que exploré pero dejé afuera por distintos motivos:

* [AWS CodeDeploy](https://aws.amazon.com/es/codedeploy/)
* [Openshift](https://www.openshift.com/)
* [Visual Studio Team Services](https://visualstudio.microsoft.com/es/team-services/)
* [Now (solo para JavaScript)](https://now.sh/)
* [Netlify (solo para JavaScript)](https://www.netlify.com/)
