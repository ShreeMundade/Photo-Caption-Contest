# caption-contest

Simple Node/Express API to retrieve and caption photos. Users can view a list of photos, then register to leave captions on photos.

This app was initialized with express-generator.

## Dependencies
- NPM
- NodeJS/Express.js
- PostgreSQL Server
- Sequelize

## Running the app locally
Install project dependencies using `npm install`

Before you can run the project locally, you will need to setup the database:
```
psql postgres --u postgres

postgres-# CREATE ROLE root WITH LOGIN PASSWORD 'p@ssw0rd!';
postgres-# ALTER ROLE root CREATEDB;
postgres-# \q

psql postgres -U root

postgres=> CREATE DATABASE node_sequelize;
postgres=> GRANT ALL PRIVILEGES ON DATABASE node_sequelize TO root;
postgres=> \q
```

Run the Sequelize migration scripts using `sequelize db:migrate`

You can then run the project with `DEBUG=myapp:* npm start`

Once the app is running locally, you can access the API at `http://localhost:3000/`

## Testing with Swagger
Swagger documentation and testing available at `http://localhost:3000/docs`

To test with Swagger:
 - Add photos using `GET /photos`
 - Create a user using `POST /users`
 - Login as new user using `POST /users/login`
 - Authorize Swagger requests
   - Copy token returned from login
   - Click the Authorize button at the top
   - Paste in the auth token
   - Click Login.
 - Create a caption using `POST /captions`
 - Retrieve photos, captions, and user data using other endpoints.
   - endpoints with a Lock icon require a login token

## Resources
- [NodeJS, Express, Sequelize, PostgreSQL RESTful API](https://www.djamware.com/post/5b56a6cc80aca707dd4f65a9/nodejs-expressjs-sequelizejs-and-postgresql-restful-api)
- [Handling Auth with Node](https://medium.com/quick-code/handling-authentication-and-authorization-with-node-7f9548fedde8)
- [Optimize Node with Simple Caching Strategies](https://scotch.io/tutorials/how-to-optimize-node-requests-with-simple-caching-strategies)
- [Documenting your API with Swagger](https://levelup.gitconnected.com/swagger-time-to-document-that-express-api-you-built-9b8faaeae563)
- [Swagger Specification](https://swagger.io/docs/specification/basic-structure/)

Photos included in the source code of this project are from [Comedy Wildlife Photos](https://www.comedywildlifephoto.com/gallery/comedy-widlife-2020-competition-winners.php).

## Options for extension
- Implement admin role for users, capable of curating photos and managing users
- Create web front-end
- Implement voting feature for ranking captions
