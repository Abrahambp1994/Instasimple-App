# InstaSimple APP Backend

# Instalar 馃敟

> abierta la carpeta de backend en VSC, comenzar instalando los node modules

```
npm install
```

> renombrar el .env.example a .env y rellenar todos los campos

DATABASE_NAME se llamar谩 instasimple

> crear la DB

```
npm run initDb
```

> introducir datos de prueba en la DB (users, posts y likes)

```
npm run populateDb
```

> una vez hecho todo esto, iniciar el server

```
node src/server.js o npm start o npm run dev
```

# Base de datos 馃捑

## Tablas

users

- id
- email
- password
- name

posts

- id
- image
- description
- userId
- creationDate

likes

- id
- userId
- postId

# API 馃摎

La colecci贸n de endpoints funcionando para postman: [est谩 aqu铆](./Instasimple.postman_collection.json).

// USUARIOS P脷BLICOS

**GET /**

- Responde con las 煤ltimas fotos publicadas por los usuarios registrados.
- /?description= podemos realizar b煤squedas filtrando por la descripci贸n de las publicaciones mediante query.params

**GET /post/:id**

- Responde con un 煤nico post seg煤n su id.

**GET /users/:id**

- Responde con el perfil de un usuario (que no es lo mismo que MI usuario) con su galer铆a de fotos

**POST /login**

- Inicia sesi贸n a trav茅s del email y la password y nos devuelve un token.

**POST /register**

- Registra a cualquier usuario an贸nimo medante su name, email y password

//USARIOS REGISTRADOS

**GET /user**

- Iniciada la sesi贸n, nos devuelve nuestra galeria de posts publicados por nosotros mismos, es decir MI perfil

**POST /post**

- Iniciada la sesi贸n, crea una publicaci贸n introduciendo una description y una foto, ambas obligatorias

**POST /posts/:id/like**

- Iniciada la sesi贸n, alterna dar/quitar like al post indicado en el param "id"
