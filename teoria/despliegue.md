![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# Despliegue de aplicaciones en Heroku

![img](../assets/heroku.png)

Heroku es una plataforma de servicios en la nube (conocidos como PaaS o Platform as a Service) que permite manejar los servidores y sus configuraciones, escalabilidad y administración. Su popularidad ha crecido en los últimos años debido a su facilidad de uso y versatilidad para distintos proyectos.

Heroku es uno de los PaaS más utilizados en la actualidad en entornos empresariales por su fuerte enfoque en resolver el despliegue de una aplicación. 

Los pasos para poder desplegar una app en Heroku son los siguentes: 

1. Descarga e instala git (control de versiones más usado en la actualidad y usado en concreto por Heroku)

[GIT]()

2. Crea un repositorio en local con el siguiente comando: 

```

```

3. 


4. 


5. 




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