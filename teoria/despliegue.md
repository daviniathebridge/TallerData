![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Despliegue de aplicaciones en Heroku

![img](../assets/heroku.png)

Heroku es una plataforma de servicios en la nube (conocidos como PaaS o Platform as a Service) que permite manejar los servidores y sus configuraciones, escalabilidad y administración. Su popularidad ha crecido en los últimos años debido a su facilidad de uso y versatilidad para distintos proyectos.

Heroku es uno de los PaaS más utilizados en la actualidad en entornos empresariales por su fuerte enfoque en resolver el despliegue de una aplicación. 

Los pasos para poder desplegar una app en Heroku son los siguentes: 

1. Crea una cuenta en GitHub

2. Descarga e instala git (control de versiones más usado en la actualidad y usado en concreto por Heroku)

[GIT](https://git-scm.com/downloads)

A partir de aquí te dejo la información que nos ha facilitado tu Lead, para que dispongas de ella: 

```
Ahora vamos a trabajar con git y con Heroku.
Este documento es un texto plano para que puedas copiar y pegar parte del texto plano que te hará falta en un apartado.

Referencia para el ejercio:
https://stackabuse.com/deploying-a-flask-application-to-heroku/

Pasos:

3) Usa estos pasos para tener conectividad entre git y GitHub

Importante: la clave pública y privada déjalas guardadas en el directorio que te propone
por defecto

C:\Users\MI_USUARIO\.ssh

4) Instala gunicorn en la consola de anaconda
pip install gunicorn

5) Crea un archivo sin extensión de texto plano que se llame Procfile
escribe dentro:

web: gunicorn app:app

el segundo "app" es el nombre de la aplicación, se suele llamar siempre app

6) Crea requirements.txt

Aquí hay 2 opciones:
opción difícil: lee todas las librerías instaladas y elimina aquellas que no sean necesarias para el ejercicio
Es necesario borrar librerías porque Heroku no soporta todas las librerías que puedas tener instaladas.
Como no vas a usar todas, Heroku solo necesita saber cuáles sí necesita el ejercicio.

opción fácil (te digo con qué librerías y versiones funciona el ejercicio)
Escribe dentro:

Flask==1.1.1
Flask-WeasyPrint==0.6
gunicorn==20.0.4
numpy==1.19.4
numpydoc==0.9.1
pandas==1.1.1
pandas-datareader==0.9.0
pandas-profiling==2.9.0
pandocfilters==1.4.2
pickleshare==0.7.5
requests==2.24.0
requests-oauthlib==1.3.0
scikit-image==0.15.0
scikit-learn==0.24.0
anaconda-client==1.2.2

7) Crea una cuenta en Heroku gratuita

8) Elige el nombre de tu aplicación (créalo en Heroku en la web)

9) Instala el CLI  de Heroku

10) Abre git bash

ve al directorio /Flask donde tienes los archivos

git init .

git add app.py Procfile requirements.txt static templates iri.pkl

git commit -m "this is a commit"

11) Abre un terminal cmd (Windows), llega hasta la carpeta donde tengas los ficheros del ejercicio y lógate en heroku

heroku --version
heroku login

12)  Desde gitbash ejecuta con el mismo nombre que elegiste cuando creaste la aplicación en la web de Heroku (sin las llaves)

heroku git:remote -a {your-project-name}

13) Desde el terminal de gitbash también

git push heroku master

14) Cuando acabe, te dará una URL.
Pruébala en un navegador. ¡Ya tienes listo tu clasificador en internet!


```

## Código para acceder al contenido de una API que devuelve JSON

```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="script.js"></script>
</head>
<body>
    
</body>
</html>

```

```javascript
  fetch('https://api.github.com/users/daviniathebridge')
            .then(res=>res.json())
            .then(json=>console.log(json));

```