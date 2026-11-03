Crear archivo Dockerfile:

FROM python:3.12-slim

WORKDIR /app

COPY index.html .

USER 10001:10001

EXPOSE 8000

CMD ["python", "-m", "http.server", "8000", "--bind", "0.0.0.0"]



1. Construir y ejecutar:

  docker build -t pps-web:v1 .
  docker run -d --name pps-s01-web -p 127.0.0.1:8080:8000 pps-web:v1
  docker ps
  docker logs pps-s01-web
