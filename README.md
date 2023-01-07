# Use nginx as a procy for a gunicorn project
* Write a docker-compose file that names the gunicorn service as
   `gunicorn_project`, such as:
```
services:
  gunicorn_project:
    image: docker.io/USERNAME/IMAGE-REPO-NAME

  nginx:
    image: docker.io/andylytical/nginx-as-gunicorn-proxy
    pull_policy: always
    ports:
      - "8080:80"
    depends_on:
      - gunicorn_project
```
* `docker-compose pull`
* `docker-compose up`
