# Eureka Server - Proyecto Terminal

Este servidor Eureka fue desarrollado como parte del Proyecto Terminal para la carrera de Ingeniería en Telemática. Su propósito es actuar como un servicio de descubrimiento en una arquitectura de microservicios, permitiendo el registro y la localización dinámica de servicios en el entorno distribuido.

## Desarrolladores

- **Cabrera Vázquez Itzel Berenice**
- **Flores Chavarría Diego**

## Propiedad Intelectual

Este código y los materiales relacionados están protegidos por las leyes de propiedad intelectual. Su uso, reproducción, distribución o modificación sin autorización está estrictamente prohibido.

---

## Descripción del Proyecto

Eureka Server es un servicio de descubrimiento desarrollado usando Spring Boot y Spring Cloud. Este proyecto incluye:

- Registro y localización de microservicios en tiempo real.
- Balanceo de carga y tolerancia a fallos mediante clientes configurados.
- Configuración y despliegue en Docker para facilitar su implementación en múltiples entornos.

---

## Configuración del Proyecto

### Requisitos Previos

- **Java 17 o superior**
- **Maven 3.6+**
- **Docker (opcional, para despliegue)**

### Instalación y Ejecución

1. **Clonar el Repositorio**  
   ```bash
   git clone https://github.com/dfloresc16/eurekams.git
   cd eurekams
   ```

2. **Compilar el Proyecto**  
   ```bash
   mvn clean package -DskipTests
   ```

3. **Ejecutar el Servidor Eureka**  
   ```bash
   java -jar target/eurekams.jar
   ```

### Configuración YAML

El archivo `application.yml` incluye configuraciones clave como la URL del servidor y opciones de registro de servicios. Modifícalo según tu entorno.

---

## Despliegue en Docker

1. **Construir la Imagen Docker**  
   ```bash
   docker build -t eureka-server:v1.0 .
   ```

2. **Ejecutar el Contenedor**  
   ```bash
   docker run -p 8761:8761 eureka-server:v1.0
   ```

El servidor Eureka estará disponible en `http://localhost:8761`.

---

## Licencia

Este proyecto está protegido por las leyes de propiedad intelectual. **Todo uso o distribución sin la autorización previa de los desarrolladores está prohibido.**

---
