---
layout: post
title: Publicando nuestra aplicación
tags: [SCM, Deploy, Heroku]
---

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
