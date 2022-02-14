# Web-BDE

This web site is designed for studen councils (BDE in french) to help them organise events and manage their association easily. It is still in developement, any body can participate and leave a pull request. An instance of the application is runing at [webbde.agomez.org](https://webbde.agomez.org)

## Features

### Current features

- Authentication system around student email
- Creation of challenges for the integration of new students, accomplishment submit and validation by admins
- Online shop to buy goodies with fake money earned by accomplishing challenges

### Upcomming features

- Profile system for users
- Upload of photos & videos for accomplishment proof & user avatar

## Contribute

### Requirements

- node
- docker & docker-compose

To contribute you'll need the back & front projects

### `git submodule update --remote --init`

### Initialize dev Database

In /infra run :

### `docker-compose up -d`

### In the back project :

Install dependancies & build ORM types :

### `npm install && npm run prisma`

Setup your environment (in a .env or what ever you want) :

- **DATABASE_URI** : URI to connect to DB, hint postgresql URI are formated like this : "postgresql://[user]:[password]@[host]/[database]"
- **JWT_TOKEN** : JWT secret key to cipher user id, if none provided the key will be "secrettoken"
- **JWT_EXPIRATION** : Expiration time for a user session, see [JWT doc](https://www.npmjs.com/package/jsonwebtoken) for formats, if none provided it will be "30d"
- **EMAIL_REGEX** : Regex that matches your particular student email, for example : "^[\w\-\.]+@([\w\-]+.)*umontpellier\.fr$" matches emails with umontpellier.fr domain, if none provided regex will match a classic email
- **API-URL** : URL used by the swagger to make API calls

Run the project in dev mode run :

### `npm run dev`

### In the front project :

Install dependancies & build ORM types :

### `npm install`

Setup your environment (in a .env or what ever you want) :

- **EMAIL_REGEX** : Regex that matches your particular student email, for example : "^[\w\-\.]+@([\w\-]+.)*umontpellier\.fr$" matches emails with umontpellier.fr domain, if none provided regex will match a classic email
- **API-URL** : URL used by axios ro make calls to the API, default : localhost:4000

Run the project in dev mode :

### `npm run dev`

## Deployement

These setps will show you how to deploy the application behind a reverse proxy

### Build front & back docker images

Int the front project run :

### `docker build -t webbde-front .`

Int the back project run :

### `docker build -t webbde-back .`

### Run the reverse proxy

In /infra/docker-compose/proxy run :

### `docker-compose up -d`

### Run the application

In /infra/docker-compose/app run :

### `docker-compose up -d`