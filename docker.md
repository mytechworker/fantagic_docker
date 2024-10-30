# How to Start the Project 

## Prerequisites

Make sure you have the following installed:
- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Project Structure
The project is organized as follows:

```
├── salesPhase1-admin/
│   ├── Dockerfile
│   ├── README.md
│   ├── .env (if needed)
│   └── src/ (Admin project files)
├── salesPhase1-backend/
│   ├── Dockerfile
│   ├── README.md
│   ├── .env (if needed)
│   └── src/ (Backend project files)
├── salesPhase1-webapp/
│   ├── Dockerfile
│   ├── README.md
│   ├── .env (if needed)
│   └── src/ (Webapp project files)
├── docker-compose.yml
├── nginx.conf
```

# Project Setup Guide

## Step 1: Clone Repositories
First, clone all three repositories and place them in the root directory alongside the docker-compose.yml and nginx.conf files.

## Step 2: Insert Environment Variables
Add the necessary environment variables for each repository in their respective .env files.

salesPhase1-admin .env

```bash
VITE_API_URL="http://localhost:8080"
```

salesPhase1-backend .env

```bash
PORT=8000
MONGODB_URI=mongodb+srv://olixlab8:n9NUXqEWFXmz7o50@cluster0.qqywqup.mongodb.net/fantagic?retryWrites=true&w=majority&appName=Cluster0
JWT_SECRET_ACCESSTOKEN=1979c4d63643e48231da16c6ccfdaaa1de814d835712ce301f337649951b2a37
JWT_SECRET_REFRESHTOKEN=d06d403837db0d2c95fc8690e99c3c07216470ce7484c590e4963c81841bc24d
EMAIL_USER=mytechworker@gmail.com
EMAIL_PASS=jkuaebshpvgszaua
CRYPTO_SECRET_KEY=972B897DB9A16FDB689D49CFC2D9D
JWT_ACCESSTOKEN_EXPIRE="1d"
JWT_REFRESHTOKEN_EXPIRE="1y"
STRIPE_SECRET_KEY="sk_test_51Ppp6wRrUGPFJ7lS5UGLyNy0becbJ9yDixp4eAevw4meyi7jiGFUA6PhHuQ03ch9PkV2lWoWGFKBI92tNpBsZBMk00Pa9W5DUk"
STRIPE_WEBHOOK_KEY="whsec_b8bbfafd77c0dc728f377a67cd626245e50cf79a43d77a5ae39347ad36d42941"
```
salesPhase1-webapp .env

```bash
VITE_BASE_URL="http://localhost:3000"
VITE_API_URL="http://localhost:8080"
VITE_STRIPE_PUBLIC_KEY="pk_test_51Ppp6wRrUGPFJ7lSj4O3SSimeCp6Jvul3DsN0mdvKoqp92mD57xZqvKqVdxlgskNvmuOaMN61IK7o6dWR120nf9400enXytzmE"
VITE_CRYPTO_SECRET_KEY=972B897DB9A16FDB689D49CFC2D9D

```
Step 3: Start Docker

Start Docker on your local machine and run the following command to start all services:
```bash
docker compose up -d
```

Then,Accessing the Project
Once the project is running, you can access each service via the following URLs:

- Frontend (SalesPhase1 Web App): http://localhost:8080/
- Admin Panel: http://localhost:8080/admin
- Backend API: http://localhost:8080/api



This command will:

- Build and start each service in detached mode.
- Set up the network and link all containers based on `docker-compose.yml`.

### Notes
- Verify that each service is up and running by checking the logs with:

```bash
docker compose logs -f
```

- To stop all running containers, use:

```bash
docker compose down 
```
This will stop and remove containers, networks, and any volumes created by docker compose up.

- Remove specific Images for Docker

```
docker rmi <imageid>
```

- Remove All Images

To remove all images, use:
```
docker rmi $(docker images -q)
```

also you can see video Here
[Watch the video](https://www.awesomescreenshot.com/video/33101520?key=97a35451ff88607c075bfaf4cbc0487e)