![logotipo de The Bridge](https://user-images.githubusercontent.com/27650532/77754601-e8365180-702b-11ea-8bed-5bc14a43f869.png  "logotipo de The Bridge")


# [Bootcamp Web Developer Full Stack](https://www.thebridge.tech/bootcamps/bootcamp-fullstack-developer/)

### HTML, CSS,  JS, ES6, Node.js, Frontend, Backend, Express, React, MERN, testing, DevOps

# ¿Qué papel tiene desarrollo en el deafío y en la empresa?

Durante nuestro Bootcamp vemos: 

1. Frontend: HTML, CSS, Javascript y React.js
2. Backend: Node.js, Express, MySQL/PostgreSQL, Fireabse y MongoDB
3. En el camino: Muchas librerías y herramientas que permiten hacer aplicaciones de principio a fin.

¿Qué sabemos de Bases de Datos?

- Relacionales: 

1. Vemos nociones de diseño de BD.
2. Aprendemos a crear las BD sin entorno gráfico
3. Disponemos de conocimientos básicos acerca de consultas, subconsultas y JOINS
4. Disponemos de conocimientos básicos de administración de usuarios y permisos
5. Integración de BD en nuestras aplicaciones (con y sin sequelize)

- No SQL (Mongo y Firebase/Firestore):

1. Vemos nociones de diseño de BD.
2. Aprendemos a crear las BD con y sin entorno gráfico
3. Aprendemos a aplicar filtros 
4. Integración de BD en nuestras aplicaciones (con y sin mongoose)


## ¿Qué necesitamos de Data?

- Un diseño de la arquitectura de datos lo más cerrado y estable posible, lo antes posible.

- Que no se realicen modificaciones en los nombre de campos y claves sin aviso y sin justificación, ya que afecta al desarrollo de la aplicación

- Comunicación y colaboración para solucionar los problemas que surjan.

## Ejemplo scripts de acceso e interacción con BD

### MySQL sin sequelize

```SQL

    #DROP DATABASE prueba;
    CREATE DATABASE prueba;
    USE prueba;
    CREATE TABLE tabla1(
        id INT AUTO_INCREMENT,
        campoTexto VARCHAR(100),
        PRIMARY KEY(id)
    ); 

    INSERT INTO tabla1 VALUES(NULL, "Valor 1 CampoTexto");
    INSERT INTO tabla1 VALUES(NULL, "Valor 2 CampoTexto");
    INSERT INTO tabla1 VALUES(NULL, "Valor 3 CampoTexto");

```

```javascript

    const mysql = require('mysql');
    const connection = mysql.createConnection({
        host: 'localhost',
        user: 'root',
        password: 'root',
        database: 'prueba'
    });
    
    connection.connect((err)=> {
        if(!err){
            console.log('Connection Established Successfully');
            //connection.end();
        }else{
            console.log('Connection Failed!'+ JSON.stringify(err,undefined,2));
        }
    });
    
    let query = 'SELECT * from tabla1';
    connection.query(query, (err, rows) => {
        if(err) throw err;
        console.log('Datos de tabla1: \n', rows);
        connection.end();
    });
    


```

### MySQL con sequelize

```SQL


    #DROP DATABASE test;
    CREATE DATABASE test;
    USE test;
    CREATE TABLE users(
        id INT AUTO_INCREMENT,
        firstname VARCHAR(100),
        lastname VARCHAR(200),
        PRIMARY KEY(id)
    ); 
    
    INSERT INTO users VALUES(NULL, "Davinia", "de la Rosa");


```

```javascript


    const Sequelize = require('sequelize')

    const sequelize = new Sequelize('test', 'root', 'root', {
        host: 'localhost',
        dialect: 'mysql',
        port: 3306
    })

    sequelize.authenticate()
        .then(() => {
            console.log('Conectado')
        })
        .catch(err => {
            console.log('No conectado: '+ err)
        });

    const Users = sequelize.define('users', {
        id: { type: Sequelize.INTEGER, primaryKey: true },
        firstname: Sequelize.STRING,
        lastname: Sequelize.STRING
    });

    Users.findAll({ attributes: ['id', 'firstname', 'lastname'] })
        .then(users => {
            console.log(users[0].dataValues)
        })
        .catch(err => {
            console.log(err)
        });



```


### Firebase

```javascript


    // Import the functions you need from the SDKs you need
    import { initializeApp } from "https://www.gstatic.com/firebasejs/9.6.1/firebase-app.js";
    import { getFirestore, collection, getDocs, doc, setDoc, deleteDoc  } from 'https://www.gstatic.com/firebasejs/9.6.1/firebase-firestore.js';
    // TODO: Add SDKs for Firebase products that you want to use
    // https://firebase.google.com/docs/web/setup#available-libraries

    // Your web app's Firebase configuration
    const firebaseConfig = {
        apiKey: "AIzaSyBLJ35A6HuDHkuprTuVYQc4QWa2L0ZMzEM",
        authDomain: "primer-proyecto-c744f.firebaseapp.com",
        projectId: "primer-proyecto-c744f",
        storageBucket: "primer-proyecto-c744f.appspot.com",
        messagingSenderId: "160376708376",
        appId: "1:160376708376:web:499217c74f6dc9304dd26d"
    };

    // Initialize Firebase
    export const app = initializeApp(firebaseConfig);
    export const db = getFirestore(app);
    export const querySnapshot = await getDocs(collection(db, "tasks"));
    ...


    export async function insertTask(task) {
        await setDoc(doc(db, "tasks", generateRandomIdTask(20)), task);
        alert("Insertada la tarea: "+task.title);
    }

    export async function deleteTask(id){
        await deleteDoc(doc(db, "tasks", id));   
        alert("Borrada la tarea: "+id);
    }

```


### Mongo DB sin mongoose

```javascript

    const mongo = require('mongodb');
    const MongoClient = mongo.MongoClient;

    const mydb = "Empresa";
    const coleccion = "Clientes";

    const url = "mongodb://localhost:27017/";

    const myobj = { "nombre": "Ana", "direccion": "C/Alcalá 1" };

    //Creacion de una BD 
    MongoClient.connect(url+mydb, function(err, db) {
    if (err) throw err;
    console.log("Base de datos creada");
    db.close();
    });

    //Creacion de una coleccion dentro de una BD
    MongoClient.connect(url, function(err, db) {
    if (err) throw err;
    var dbo = db.db(mydb);
    dbo.createCollection(coleccion, function(err, res) {
        if (err) throw err;
        console.log("Colección creada");
        db.close();
    });
    });

    //Insertar dentro de una coleccion de una BD
    MongoClient.connect(url, function(err, db) {
    if (err) throw err;
    var dbo = db.db(mydb);
    
    dbo.collection(coleccion).insertOne(myobj, function(err, res) {
        if (err) throw err;
        console.log("Documento insertado");
        db.close();
    });
    });

```

### Mongo DB con mongoose

```javascript
   
    const mongoose = require("mongoose");

    const url = "mongodb://localhost:27017/test";

    mongoose.connect(url, function(err){
        if (err) throw err;
        console.log("Conexión correcta");
    });

    const objectSchema = {
        _id: mongoose.Schema.Types.ObjectId,
        name: {
            firstName: String,
            lastName: String
        }, 
        created: Date, 

    };
    const userSchema = mongoose.Schema(objectSchema);

    let User = mongoose.model('User', userSchema);
    let davinia = {
        _id: new mongoose.Types.ObjectId(),
        name: {
            firstName: 'Davinia',
            lastName: 'de la Rosa'
        }, 
        created: Date.now()
    };
    let userDavinia = new User (davinia);

    userDavinia.save(function(err){
        if (err) throw err;
        console.log("Inserción correcta");
        mongoose.disconnect();
    });



```

