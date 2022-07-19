---
title: "Git Workflow"
date: 2022-07-18T22:05:52-04:00
description: "Como empezar a trabajar en equipo con Git y GitHub"
draft: false
---

Cuando empezamos a usar Git lo usamos para tener un historial del avance de nuestros proyectos, hacemos nuestros commits por cada avance que tenemos. Eventualmente  aprendemos de repositorios remotos y de GitHub para guardar nuestros proyectos en la nube. 

Cuando vamos comenzando es normal solo usar una rama `main` para ir subiendo nuestros cambios un commit después de otro, todo en la misma rama, bastante sencillo y no tendremos mayores conflictos. Pero llega un día en que tenemos un proyecto en equipo y es momento de de organizarnos para que cada uno pueda hacer aportes sin tener conflictos, así que necesitamos pensar en alguna estrategia para que todo fluya

Nuestra expectativa a la hora de trabajar en equipo, todos aportando en el proyecto con una armonía perfecta.

Pero eso de tener una sola rama principal Main para todo desarrollo del proyecto puede funcionar cuando trabajábamos solos, ahora quizás necesitemos de una mejor estrategia. Mientras mas integrantes haya en el proyecto mas complicado será trabajar en equipo, y si no tomamos las medidas necesaria.

Cada uno accidentalmente borrando los avances de otro, creando conflictos y errores.

Pero para trabajar en armonía no tenemos que crear una estrategia perfecta, no hay necesidad de recrear la rueda, existen estrategias bastante conocidas como:

- Git Flow
- GitHub Flow
- GitLab Flow
- Microsoft Flow
- Trunk based development

Cada una teniendo sus pros y contras dependiendo del contexto en el que nos encontremos, así podemos tomar en cuenta algunos factores como:

- el tamaño del proyecto
- El numero de integrantes del equipo
- La confianza y experiencia de cada dev

En este caso nosotros tomaremos la de Trunk based development, ya que es una estrategia bastante sencilla para nuestro caso sin hacer burocrático el procedimiento.

Debemos tomar en cuenta que existen diferentes áreas en nuestras ramas, como ser:

- Development
- Release
- Feature branch

Entonces lo que vamos a hacer es acordar que la rama principal (main) será nuestra rama de referencia. 

También quedamos en que para cada tarea (una funcionalidad de nuestro proyecto) se creará una nueva rama destinada únicamente para elaborarse esa tarea. Cuando la tarea asignada a alguien este terminada, el encargado de la tarea hará un `pull request` a la rama principal para fusionar las ramas, una vez hecho esto alguien encargado de aceptar los pull requests y fusionarlas

![trunk_git.jpg](./trunk_git.jpg)

Al crear una rama por cada tarea del proyecto nos evitamos conflictos al momento de trabajar en equipo. El la imagen anterior vemos con líneas segmentadas cuando cada rama se une a la rama principal main (tronco) esto hace referencia al merge que hacemos.

Y con esta estrategia de git workflow podremos trabajar tranquilamente. Claro, siempre puede existir algún conflicto a la hora de hacer fusionar las ramas y siempre que vamos a hacer cambios debemos sincronizar nuestro repositorio local con el remoto con el comando `git pull` o `git pull origin main`.

Y eso es todo por ahora, iré actualizando esta publicación y cualquier duda, consulta o comentario lo pueden hacer en el servidor de Discord o cualquiera de las otras redes sociales. Hasta Luego 👋