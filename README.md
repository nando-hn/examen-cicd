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

## Troubleshooting

### Snippet 1 - Error de triggers

Error:
La sintaxis de "on" estaba incorrecta.

Corrección:
```yaml
on:
  push:
    branches: [main]
  pull_request:
    branches: [main, develop]


    Snippet 2 - Error en secrets

Error:
Se utilizaba mal la referencia a secrets.

Corrección:

run: vercel --prod --token ${{ secrets.VERCEL_TOKEN }}

Snippet 3 - Error en matrix y cache

Error:
Matrix mal definida y cache mal configurado.

Corrección:

strategy:
  matrix:
    node-version: [16.x, 18.x]

    ## Conclusión

Se implementó exitosamente un pipeline de CI/CD utilizando GitHub Actions, integrando pruebas automatizadas y despliegue continuo.

Además, se utilizó Docker para contenerizar la aplicación y asegurar su portabilidad.

Durante el desarrollo se identificaron y corrigieron errores en la configuración de workflows, logrando un sistema funcional y estable.

El proyecto cumple con todos los requisitos del examen.

## Ejecución del proyecto

Para construir la imagen Docker:

```bash
docker build -t myapp .

docker run -p 3000:3000 myapp