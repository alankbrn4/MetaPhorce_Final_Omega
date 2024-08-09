# MetaPhorce_Final_Omega

# Omega - Sistema de Gestión para Laboratorio Clínico

Omega es un sistema diseñado para la gestión de información en un laboratorio clínico. Proporciona capacidades de almacenamiento, consulta y manejo de datos tanto en bases de datos relacionales como no relacionales.

## **Requisitos**

- **Java 21**
- **Maven 3.8.1 o superior**
- **Docker** (opcional)

## **Instalación**

### **1. Clonar el Repositorio**

```sh
git clone https://github.com/tu_usuario/omega.git
cd omega
```
### **2. Configuración**
Configura el archivo src/main/resources/application.properties con las credenciales y URLs de tus bases de datos.

### **3. Construir el Proyecto**
```sh
mvn clean install
```

### **4. Ejecución**
* Ejecición Local
```sh
mvn spring-boot:run
```
* Despliegue en Docker:
```sh
docker build -t omega-lab:latest .
docker run -d -p 8080:8080 omega-lab:latest
```

## **Swagger UI**

Accede a Swagger UI en http://localhost:8080/swagger-ui.html.

## **Licencia**
Este proyecto está bajo la Licencia MIT. Ver el archivo LICENSE para más detalles.

## **Contribuciones**
Las contribuciones son bienvenidas. Por favor, sigue las directrices del proyecto para contribuir.

## **Contacto**
Para preguntas o soporte, contacta a Alan Blanco en ablancom@utleon.edu.mx.
