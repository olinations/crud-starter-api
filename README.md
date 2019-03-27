# CRUD Starter API

Start a CRUD API quickly using Node, Express & Postgres.

Serves four requests (get, post, put, delete) from one page with a separate function for each.

All code can be edited and replaced to fit the needs of the project being built.

**Dependencies**

We use **express** to serve the API, **body-parser** to parse responses, **postgres** for the database, **knex** as the query engine, **dotenv** to protect environment variables, **helmut** to add proper headers, **cors** to prevent/allow XSS, **morgan** as our logger, and **nodemon** as a dev dependency to watch for changes.

All dependencies are included in the cloned project.

## Instructions

**1. Clone the repo**

```
git clone https://github.com/olinations/crud-starter-api.git
```

**2. CD into the project**

```
cd crud-starter-api
```

**3. Install dependencies**

```
npm install
```

**4. Start Postgres**

```
brew services start postgresql
```

**Note:** You can use Postgres or MYSQL. We are using Postgres. If you would like to use MYSQL instead of Postgres you will need to `npm uninstall pg` and `npm install mysql`. Then edit the above command to start MYSQL started on your computer.

**5. Create a database**

Change the database name to whatever you would like to name the database. Be sure to also change the database name in server.js to whatever you name the database.

```
createdb crud-starter-api
```

**6. Create a database table**

Open pSequel and run the following command. Change the table name to whatever you would like to name the table.

```
CREATE TABLE testtable1 (
 id serial PRIMARY KEY,
 first VARCHAR(100),
 last VARCHAR(100),
 email text UNIQUE NOT NULL,
 phone VARCHAR(100),
 location VARCHAR(100),
 hobby VARCHAR(100),
 added TIMESTAMP NOT NULL
);
```

## CRUD Starter Frontend
View the [repository for the frontend](https://github.com/olinations/crud-starter-frontend) that goes along with this API. It uses React and Bootstrap to display a responsive data table. It serves as the perfect starter for the frontend, however, you can use any frontend to access this API.

## Further Information
This is just a starter kit for getting a basic API up and running. Feel free to change any and every thing about it. A production ready app with more API requests and routes should undoubtedly have much of the code abstracted to different files and folders. This repo simply eliminates the need for a dev to do a bunch of research on how to get an API setup, secure, and running in a professional manner.

An important piece that is missing from this API is an authentication API. In that case it is recommended to install bCrypt for password hashing and authentication. Then, more routes should be created for registering, logging in and logging out users. There should also be a scheme for keeping users logged in. The suggested method for persisting logins would be to use JWT for token creation, Redis to store tokens in server memory, and localStorage to save tokens on the frontend. The tokens stored in localStorage will be sent back to the API via authorization headers for protected requests and would need to be verified by the server.

## Medium Article
For full details on every piece of code in this CRUD Starter API, visit the companion [Medium article here](https://medium.com/@olinations/build-a-crud-template-using-react-bootstrap-express-postgres-9f84cc444438?source=friends_link&sk=51028bf98ff92bc659d3edbb539a82bb).
