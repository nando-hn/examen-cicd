# Proyecto CI/CD con GitHub Actions y Docker

## Descripción
Este proyecto consiste en la implementación de un pipeline de integración continua (CI) y entrega continua (CD) utilizando GitHub Actions y Docker.

## Tecnologías utilizadas
- Node.js
- Docker
- Docker Compose
- GitHub Actions

## Docker
Se creó un Dockerfile optimizado para ejecutar la aplicación Node.js.

Se utilizó docker-compose para levantar:
- Aplicación web
- Base de datos PostgreSQL

## CI (Integración Continua)
Se configuró un workflow que:
- Se ejecuta en push y pull request
- Incluye jobs de:
  - lint
  - test
  - coverage
- Usa matrix con Node.js 16 y 18
- Implementa cache de npm

## CD (Entrega Continua)
Se configuró un workflow que:
- Se ejecuta en push a main
- Usa environment "production"
- Utiliza secrets para seguridad
- Simula un deployment automático

## Evidencia
Los pipelines CI y CD se ejecutaron correctamente en GitHub Actions.

## Autor
Luis García - 614111051