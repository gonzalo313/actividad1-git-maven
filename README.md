# actividad1-git-maven
Repositorio de la Actividad 1 – Configuración inicial de un proyecto Java con Maven.  Incluye flujo de ramas definido (GitFlow), dependencias para pruebas automatizadas (JUnit y Selenium)  y base para la integración continua con pipelines CI/CD.
Proyecto CI/CD con Maven y Jenkins/GitHub Actions

Descripción del Proyect
El proyecto corresponde a una implementación de un pipeline con integración y despliegue continuo (CI/CD)
para una aplicación en visual studio code Java 17 + Maven.  
El objetivo es automatizar las siguientes etapas:
- Compilación del proyecto.
- Ejecución de pruebas: unitarias,integración y de aceptación.
- Despliegue automático en un ambiente de prueba (Docker).

Pruebas
Se implementaron al menos 2 tipos de pruebas:
Unitarias → verifican métodos y componentes individuales (`Test.java`).
Integración → validan interacción entre componentes (`IT.java`).
Aceptación (extra) → validan flujos completos de negocio (`AT.java`).

Herramientas utilizadas:
- [JUnit 5](https://junit.org/junit5/) para pruebas unitarias.
- [Maven Surefire Plugin](https://maven.apache.org/surefire/maven-surefire-plugin) → ejecuta Test.java.
- [Maven Failsafe Plugin](https://maven.apache.org/surefire/maven-failsafe-plugin) → ejecuta IT.java 
   y pruebas de aceptación (AT.java).
- Opcional: [Selenium](https://www.selenium.dev/) o [RestAssured](https://rest-assured.io/) para acceptance tests.

Ejecución de Pruebas Localmente
Clonar el repositorio y ejecutar:

Pruebas unitarias
mvn test

Pruebas de integración
mvn verify

Pruebas de aceptación (perfil especial)
mvn verify -Pacceptance
Los reportes se generan en:

target/surefire-reports/ (unitarias)

target/failsafe-reports/ (integración y aceptación)

Ejecución del Pipeline

GitHub Actions
El pipeline está definido en .github/workflows/deploy.yml
Cada vez que se hace push a main o develop, se ejecutan los siguientes stages:

Jenkins
El pipeline está definido en el archivo Jenkinsfile en la raíz del proyecto.
Stages configurados:(Checkout,Build & Unit Tests,Integration Tests,Acceptance Tests,Package & Deploy)
Se ejecuta automáticamente en cada push.

Evidencias de Ejecución
Ejecución en GitHub Actions
Reporte de pruebas unitarias
Reporte de pruebas de integración
Despliegue en ambiente de prueba

Estructura del Proyecto
Copiar código

src
   main/java/...        -Código fuente
   test/java/...        -Pruebas unitarias e integración
Jenkinsfile             -Pipeline Jenkins
   .github/workflows    -Pipeline GitHub Actions
deploy.yml
    pom.xml              -Configuración Maven
README.md
