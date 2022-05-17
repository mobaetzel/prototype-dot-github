<p align="center">
  <a href="https://aivot.de" target="_blank"><img width="150" src="https://aivot.de/img/aivot-logo.svg" alt="Aivot logo"></a>
</p>

<h1 align="center">Gover</h1>
<h3 align="center">Das Fundament für moderne digitale Verwaltungsleistungen</h3>

<p>Our Mission is... / What we are...Digitaler Brückenbau zwischen Verwaltung und Bürger:innen</p>
<!-- Badges go here -->

# What is Gover?
Gover is an efficient low-code eGovernment platform for creating and managing user-centric online applications.  
We enable administrations to:
- build and manage visually stunning online applications fast
- document changes reliably and automatically
- ensure quality
- comply with all legislation (at least in Germany 😅)

All this while putting user experience (for citizens and administration staff) first.

For more information visit us at <https://aivot.de/gover>




# Who uses Gover?
Currently top secret. If you want to get an introduction into using Gover contact us at <https://aivot.de/kontakt>.




# Setup
Gover was developed as a cloud native application and works best with Docker.
You can find more Information on the [DockerHub page of Gover](https://hub.docker.com/repository/docker/mobaetzel/oam-view-engine).
If you want to deploy Gover without docker, read more at the [native setup section](./README.md#setup-native).


## Docker Setup
If you have docker-compose installed, simply start the `docker-compose.yml` below by running `docker-compose up`.
Gover is now available at <http://localhost:8000>.

```yaml
# docker-compose.yml
version: "3"
services:
  mongo:
    image: mongo:5.0.8
    restart: always
  backend:
    image: mobaetzel/oam-view-engine:latest
    restart: always
    depends_on:
      - mongo
    environment:
      OAM_HOST: localhost
      OAM_PORT: 8000
      OAM_MONGO_HOST: mongo
      OAM_MONGO_PORT: 27017
    ports:
      - '8000:80'
```


## Native Setup

### Prerequisites
The native setup includes compiling the project and running it afterwards behind a nginx reverse proxy.
Gover depends on a set of open source tools and technologies to compile and run.

- Golang >= 1.17
- Node.js >= 17.0
- MongoDB >= 5.0
- nginx >= 1.18

**Please note, that the guide for a native setup was created with a unix platform in mind**


### Building Gover
After cloning this repository, open up a shell inside the root of the project.
You have to compile the `backend` of Gover first.
Run the following commands in your shell.

```bash
cd backend
go mod download
go build -o ../gover.run
```

You can then build the frontend applications `app` and `admin` by running the following commands.

```bash
npm install
npm run build:app
mv ./build /var/www/app/html
PUBLIC_URL="/admin/" npm run build:admin
mv ./build /var/www/admin/html
```


### Configure nginx
Replace you default nginx config file at `/etc/nginx/http.d/default.conf` with the following content:

```
upstream backend {
  server localhost:8000;
}

server {
  listen 80      default_server;
  listen [::]:80 default_server;

  location /admin {
    alias     /var/www/admin/html/;
    try_files $uri $uri/ /index.html;
  }

  location /api {
    proxy_pass       http://backend;
    proxy_set_header Host      $host;
    proxy_set_header X-Real-IP $remote_addr;
  }

  location / {
    root      /var/www/app/html;
    try_files $uri $uri/ /index.html;
  }
}
```


### Running Gover
First, launch the mongodb server locally and make sure, that it is available through port **27017**.
There is no need to expose the mongodb server to the outside.
Then, execute the previously built executable to launch the Gover server.
Gover should now be available at <http://localhost>.




# Documentation
Code documentation is stored in the project's [GitHub wiki](../../wiki) so that it is as close to the code as possible.

If you are looking for end user documentation visit our [documentation overview](https://aivot.de/docs) and select
the respective project.




# Contributing
Anyone can support us. There are many different ways to contribute to Gover. There is certainly one for you as well.

| Support opportunity               | Remark                                                                                                                                                                                                                           |
|-----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Spread the word                   | Share your thoughts on this project on social media. Feel free to link to our website or this GitHub repository.                                                                                                                 |
| Share your ideas or give feedback | Share your ideas with us or report a bug. With GitHub Issues and our templates, you can easily bring something up for discussion. Ideally you should read the [contributing guideline](./CONTRIBUTING.md) first.                 |
| Develop                           | Develop together with us on the project. Contributions are managed via GitHub. Please read the [contributing guideline](./CONTRIBUTING.md) first.                                                                                |
| Write out a Bounty                | "Share your ideas" on steroids. If you have a business critical idea and want to see it implemented, you have the chance to set a bounty and accelerate a possible development.                                                  |
| Support us financially            | Donate via [GitHub Sponsors](https://github.com/sponsors/aivot-digital) or [open collective](https://opencollective.com/aivot-digital). All funds are managed transparently and go directly into the development of the project. |

❤ Thank you for contributing! ❤




# Changelog
Please refer to the [changelog](./CHANGELOG.md) for details of what has changed.




# Roadmap
Future functionalities and improvements in prioritized order can be found in the project's [roadmap](https://aivot.de/roadmaps).




# License
This project is licensed under the terms of the [Business Source License](./LICENSE.md).




# Sponsoring services
These great services sponsor Aivot's core infrastructure:

[<img loading="lazy" alt="GitHub" src="https://github.githubassets.com/images/modules/logos_page/GitHub-Logo.png" height="25">](https://github.com/)

GitHub allows us to host the Git repository and coordinate contributions.