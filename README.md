<<<<<<< HEAD
<<<<<<< HEAD

# Final Project JAVA Back End Microservices - MetaPhorce

# LabClinico Omega - Documentación de la API

## Descripción

Este proyecto es un sistema de gestión para un laboratorio clínico que incluye módulos para gestionar pacientes, médicos, citas, muestras y análisis. La API RESTful está desarrollada utilizando Spring Boot y proporciona un conjunto completo de servicios para la gestión de estos módulos.

## Requisitos Previos

- Java 11 o superior
- Maven
- MySQL
- MongoDB

## Configuración

### Clonar el Repositorio

```bash
git clone https://github.com/tu_usuario/labclinico-omega.git
cd labclinico-omega
```

## Configurar la Base de Datos MySQL

###Crear una base de datos en MySQL:

- CREATE DATABASE labclinico;
- Configurar las credenciales de la base de datos en src/main/resources/application.properties:

### Estructura de Archivo properties
```bash
spring.datasource.url=jdbc:mysql://localhost:3306/labclinico
spring.datasource.username=tu_usuario
spring.datasource.password=tu_contraseña
spring.jpa.hibernate.ddl-auto=update
```
### Configurar MongoDB

Asegúrate de que MongoDB esté ejecutándose en tu máquina local y configurado en el puerto por defecto (27017).

## Compilar y Ejecutar la Aplicación
```bash
mvn clean install
mvn spring-boot:run
```

## Documentación de la API con Swagger

- Acceder a Swagger UI
- Una vez que la aplicación esté en ejecución, puedes acceder a Swagger UI en la siguiente URL:

```bash
http://localhost:8080/swagger-ui.html
```

## Ejemplos de Uso de los Endpoints
### Gestión de Pacientes
### Obtener Todos los Pacientes
- Endpoint: GET /api/pacientes
Respuesta Ejemplo:
```bash
json

[
  {
    "idPaciente": 1,
    "nombre": "Juan Pérez",
    "fecha_nacimiento": "1980-01-01",
    "genero": "Masculino",
    "correo": "juan.perez@example.com",
    "num_telefono": 1234567890,
    "rfc_paciente": "JUAP800101"
  }
]
```

### Crear un Paciente
- Endpoint: POST /api/pacientes
Solicitud Ejemplo:
```bash
json

{
  "nombre": "Ana López",
  "fecha_nacimiento": "1990-05-15",
  "genero": "Femenino",
  "correo": "ana.lopez@example.com",
  "num_telefono": 9876543210,
  "rfc_paciente": "ANAL900515"
}
```

### Actualizar un Paciente
- Endpoint: PUT /api/pacientes/{id}
Solicitud Ejemplo:
```bash
json

{
  "nombre": "Ana López García",
  "fecha_nacimiento": "1990-05-15",
  "genero": "Femenino",
  "correo": "ana.lopez@example.com",
  "num_telefono": 9876543210,
  "rfc_paciente": "ANAL900515"
}
```

### Eliminar un Paciente
- Endpoint: DELETE /api/pacientes/{id}

## Gestión de Médicos
### Obtener Todos los Médicos
- Endpoint: GET /api/doctores
Respuesta Ejemplo:
```bash
json

[
  {
    "id_medico": 1,
    "nombre": "Dr. Mario Gómez",
    "especialidad": "Cardiología",
    "afiliacion": "Hospital General",
    "num_telefono": 5551234567,
    "cedula_profesional": "1234567"
  }
]
```

### Crear un Médico
- Endpoint: POST /api/doctores
Solicitud Ejemplo:
```bash
json

{
  "nombre": "Dra. Laura Martínez",
  "especialidad": "Pediatría",
  "afiliacion": "Clínica Infantil",
  "num_telefono": 5557654321,
  "cedula_profesional": "7654321"
}
```

### Actualizar un Médico
- Endpoint: PUT /api/doctores/{id}
Solicitud Ejemplo:
```bash
json

{
  "nombre": "Dr. Mario Gómez",
  "especialidad": "Cardiología",
  "afiliacion": "Hospital General",
  "num_telefono": 5551234567,
  "cedula_profesional": "1234567"
}
```

### Eliminar un Médico
- Endpoint: DELETE /api/doctores/{id}

## Gestión de Citas
### Obtener Todas las Citas
- Endpoint: GET /api/citas
Respuesta Ejemplo:
```bash
json

[
  {
    "id_cita": 1,
    "fecha_hora": "2023-07-20T10:00:00",
    "paciente": {
      "idPaciente": 1,
      "nombre": "Juan Pérez"
    },
    "medico": {
      "id_medico": 1,
      "nombre": "Dr. Mario Gómez"
    },
    "notas": "Revisión general"
  }
]
```

### Crear una Cita
- Endpoint: POST /api/citas
Solicitud Ejemplo:
```bash
json

{
  "fecha_hora": "2023-07-21T14:00:00",
  "id_paciente": 1,
  "id_medico": 2,
  "notas": "Consulta de seguimiento"
}
```

### Actualizar una Cita
Endpoint: PUT /api/citas/{id}
Solicitud Ejemplo:
```bash
json

{
  "fecha_hora": "2023-07-21T16:00:00",
  "id_paciente": 1,
  "id_medico": 2,
  "notas": "Consulta de seguimiento - Actualizada"
}
```

### Eliminar una Cita
- Endpoint: DELETE /api/citas/{id}

## Gestión de Muestras
### Obtener Todas las Muestras
- Endpoint: GET /api/muestras
Respuesta Ejemplo:
```bash
json

[
  {
    "id_muestra": 1,
    "fecha_recoleccion": "2023-07-19",
    "tipo": "Sangre",
    "paciente": {
      "idPaciente": 1,
      "nombre": "Juan Pérez"
    },
    "estado": "Pendiente"
  }
]
```

### Crear una Muestra
- Endpoint: POST /api/muestras
Solicitud Ejemplo:
```bash
json

{
  "fecha_recoleccion": "2023-07-20",
  "tipo": "Orina",
  "id_paciente": 1,
  "estado": "Pendiente"
}
```

### Actualizar una Muestra
- Endpoint: PUT /api/muestras/{id}
Solicitud Ejemplo:
```bash
json

{
  "fecha_recoleccion": "2023-07-20",
  "tipo": "Orina",
  "id_paciente": 1,
  "estado": "Procesando"
}
```

### Eliminar una Muestra
- Endpoint: DELETE /api/muestras/{id}

## Gestión de Análisis
### Obtener Todos los Análisis
- Endpoint: GET /api/analisis
Respuesta Ejemplo:
```bash
json

[
  {
    "id_analisis": 1,
    "fecha_realizacion": "2023-07-20",
    "tipo": "Hemograma Completo",
    "resultado": "Normal",
    "muestra": {
      "id_muestra": 1,
      "tipo": "Sangre"
    }
  }
]
```

### Crear un Análisis
- Endpoint: POST /api/analisis
Solicitud Ejemplo:
```bash
json

{
  "fecha_realizacion": "2023-07-21",
  "tipo": "Hemograma Completo",
  "resultado": "Normal",
  "id_muestra": 1
}
```

### Actualizar un Análisis
- Endpoint: PUT /api/analisis/{id}
Solicitud Ejemplo:
```bash
json

{
  "fecha_realizacion": "2023-07-21",
  "tipo": "Hemograma Completo",
  "resultado": "Anormal",
  "id_muestra": 1
}
```

### Eliminar un Análisis
- Endpoint: DELETE /api/analisis/{id}


# Contribuciones

Si deseas contribuir a este proyecto, por favor abre un issue o envía un pull request.

# Licencia

Este proyecto está bajo la licencia MIT. Consulta el archivo LICENSE para más detalles.
=======
# MetaPhorce_Final_Omega
>>>>>>> 6ebdec54bc6b01a4c2625cd40ac8eb2be0c923e3
=======
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
>>>>>>> 7102f9342314cd10ec8e9c9bc770a9d19f94612e
