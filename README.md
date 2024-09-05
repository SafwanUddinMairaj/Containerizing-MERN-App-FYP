## Run it local without Docker

### Prerequisite

- Install `npm`

#### Start Server:

```
cd your/path
npm install
npm start
```

#### Start Client

```
cd your/path
npm install
npm start
```

# Dockerizing the MERN Stack Application

### Create a network for the docker containers

`docker network create fyp`

### Build the client 
Update the client directory path according to your local setup.

```sh
cd E:\DevOps\FYP-Investify\FYP-Investify-main\client
docker build -t fyp-client .
```

### Run the client

`docker run --name=fclient --network=fyp -d -p 3000:3000 fyp-client`

### Verify the client is running

Open your browser and type `http://localhost:3000`

### Run the mongodb container

`docker run --network=fyp --name mongodb -d -p 27017:27017 -v ~/opt/data:/data/db mongo:latest`

### Build the server
Update the server directory path according to your local setup.

```sh
cd E:\DevOps\FYP-Investify\FYP-Investify-main\server
docker build -t mern-backend .
```

### Run the server

`docker run --name=server --network=fyp -d -p 3001:3001 fyp-server`

## Using Docker Compose

`docker compose up -d`

