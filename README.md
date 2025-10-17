# EV-Parcial-2
2do Parcial DEVOPS

## Workflow de CI/CD con GitHub Actions

Este proyecto utiliza un pipeline automatizado (ci-cd-pipeline.yml) que se activa con cada push a la rama main. El objetivo es asegurar la calidad y estabilidad del código antes de desplegarlo.

El flujo de trabajo ejecuta los siguientes pasos en secuencia:

1. Checkout Repository: Descarga la última versión del código de la rama.
2. Set up Node.js: Configura el entorno con la versión de Node.js especificada (v18).
3. Install Dependencies: Instala todas las dependencias del proyecto de forma limpia usando npm ci.
4. Run Tests: Ejecuta la suite de pruebas unitarias con npm test para asegurar que no hay regresiones.
5. Lint Code: Analiza el código con npm run lint para verificar que cumple con los estándares de estilo definidos.
6. Snyk Security Scan: Escanea las dependencias en busca de vulnerabilidades de seguridad conocidas.
7. SonarCloud Quality Scan: Realiza un análisis estático del código para detectar bugs, "code smells" y problemas de mantenibilidad.
8. Build and Push Docker Image: Si todos los pasos anteriores son exitosos, construye una imagen de Docker de la aplicación y la sube a Docker Hub, dejándola lista para el despliegue.

## Despliegue con Contenedores (Docker)

El proyecto está configurado para ser ejecutado dentro de un contenedor de Docker, lo que garantiza un entorno consistente y aislado.

### Pasos para Levantar los Contenedores

Construir la Imagen de Docker:
Navega a la raíz del proyecto (donde se encuentra el Dockerfile) y ejecuta el siguiente comando. Reemplaza tu-usuario-docker con tu nombre de usuario de Docker Hub.

docker build -t tu-usuario-docker/actividad-con-decimas:latest .

docker build: El comando para construir la imagen.
-t: Asigna un "tag" o nombre a la imagen.
.: Indica que el contexto de construcción es el directorio actual.

### Ejecutar el Contenedor:
Una vez que la imagen ha sido construida, puedes crear y ejecutar un contenedor a partir of ella:

docker run -p 3000:3000 tu-usuario-docker/actividad-con-decimas:latest

## Tecnologías Utilizadas

Frontend: React, React Router, Bootstrap
Pruebas: Jasmine, Karma
Calidad y Seguridad: ESLint, SonarCloud, Snyk
Entorno y Despliegue: Node.js, Docker, GitHub Actions