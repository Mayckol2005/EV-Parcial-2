==============================================
PRIMEROS PASOS Y CONFIGURACIÓN DEL ENTORNO
==============================================

A continuación se detalla el procedimiento para la configuración inicial del entorno de desarrollo.

1.1. Instalación del Proyecto

1. Clonar el repositorio: git clone <URL-del-repositorio> cd EV-Parcial-2

2. Instalar dependencias:
El proyecto utiliza 'npm' como gestor de paquetes. Es un requisito tener instalado Node.js v18 o superior, según se especifica en el archivo Dockerfile.

npm install

3. Iniciar el servidor de desarrollo: npm start
La aplicación se ejecutará en la dirección http://localhost:3000.

FLUJO DE TRABAJO CON GIT (GITFLOW) =====================================

El proyecto adopta el modelo de ramas GitFlow para la gestión del código fuente. Las ramas principales son:

main: Contiene el código en producción estable.

develop: Es la rama principal de integración donde convergen las nuevas funcionalidades y correcciones.

2.1 Creación de Ramas de Trabajo

Toda nueva contribución debe realizarse en una rama específica creada a partir de 'develop'.

Para Nuevas Funcionalidades (feature), usar el prefijo feature/:
git checkout develop
git pull
git checkout -b feature/nombre-de-la-funcionalidad

Para Corrección de Errores (bugfix), usar el prefijo bugfix/:
git checkout develop
git pull
git checkout -b bugfix/descripcion-del-error

ESTÁNDARES Y CALIDAD DEL CÓDIGO ===================================

3.1 Guía de Estilo con ESLint

Se utiliza ESLint para mantener un código limpio y consistente. Es mandatorio que todo el código cumpla con las reglas definidas en el archivo .eslintrc.json.

Indentación: Usar tabs (\t).

Comillas: Usar comillas dobles (").

Punto y coma: Siempre al final de cada sentencia.

Nomenclatura: Usar camelCase para variables y funciones.

Para verificar el código, se puede ejecutar el siguiente comando:
npm run lint

3.2 Análisis de Calidad con SonarCloud

El proyecto está integrado con SonarCloud para el análisis estático de código. Los Pull Requests son analizados automáticamente para detectar vulnerabilidades, bugs y "Code Smells". Las contribuciones no deben introducir nuevos problemas de calidad.

PRUEBAS UNITARIAS ====================

Las pruebas son una parte fundamental del ciclo de desarrollo. Se utiliza el framework Jasmine con el ejecutor de pruebas Karma.

Ubicación de Archivos: Las pruebas deben ubicarse en el directorio 'src/' y seguir la nomenclatura '.test.js' o '.test.jsx'.

Ejecución de Pruebas: Para correr la suite de pruebas completa, se utiliza el comando:
npm test

Los resultados se mostrarán en la consola, ejecutándose en un entorno sin interfaz gráfica con Chrome.