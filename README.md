## Node, Express, Postgres, Angular - CRUD Example
 
This example was forked and used in [Docker para desenvolvedores Javascript / Node.JS](http://www.videosdeti.com.br/curso-docker-nodejs.html) course.

# Steps to prepare Docker container:

* Run postgres container and verify Ports and IP Address
```
  docker run -v $(pwd)/dados_postgres:/var/lib/postgresql/data -e POSTGRES_PASSWORD=mysecretpassword -d -P postgres
  docker port <CONTAINER ID>
  docker container inspect --format '{{.NetworkSettings.IPAddress}}' <CONTAINER ID>
```
* Run Cloud9 container
```
  docker run -d -v $(pwd)/node-express-postgres-angular-crud:/workspace -p 8181:8181 -p 3090:3090 jacksonpires/cloud9_nvm --auth username:password
```

* Browse to **http://localhost:8181** to go inside Cloud9 container

# On Cloud9 container run:

* Clone this project and enter in folder 
```
  git clone https://github.com/jacksonpires/crud-node-postgres.git
  cd crud-node-postgres
```

* Install Bower
```
  npm install -g bower
```

* Install all the node packages listed in the package.json
```
npm install
```

* Installs the front end packages listed in the bower.json file
```
  bower install
```

* Open **../server/config/database.js** and complete PostgreSQL database connection details

* Prepare the database
```
  node run prepare
```

* Start the node project
```
  node start
```

* Browse to **http://localhost:3090**

## Screenshot

<div align="center">
		<img width="95%" src="screenshot/todo1.png" alt="Todos" title="Todos"</img>
</div>
