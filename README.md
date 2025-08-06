# EntregaProyectoForo
entrega de fase foros usando spring contruyendo api rest validacion y tokens 

# Proyecto Foro - API REST con Spring Boot

Este proyecto es una API REST para la gestión de tópicos en un foro, desarrollada como parte del curso de Spring Boot. Incluye operaciones CRUD, validación de datos, y persistencia en base de datos con JPA/Hibernate.
# Proyecto API REST - Foro de Tópicos

Este proyecto fue desarrollado como parte de la formación en desarrollo con **Spring Boot** dentro del curso de "Construcción de software seguro". Se trata de una API REST que gestiona los temas de un foro, permitiendo crear, consultar, actualizar e inactivar tópicos.

La actividad integró los conceptos vistos en clase, como:

- Uso de anotaciones de mapeo con **JPA (Jakarta Persistence API)**,
- Validación de datos con **Hibernate Validator** (`@NotNull`, `@Valid`, etc.),
- Implementación de **patrones de diseño REST** y controladores con `@RestController`,
- Separación de capas (`Controller`, `Domain`, `Repository`),
- Uso de **DTOs con records** para recibir y devolver datos de forma segura y estructurada,
- Gestión del estado del recurso usando enumeraciones (`Status`),
- Pruebas locales con **Postman** y manejo de errores comunes de SQL y HTTP,
- Organización del proyecto siguiendo buenas prácticas.

## Funcionalidades desarrolladas

- [x] Listar tópicos (`GET /topicos`)
- [x] Crear nuevo tópico (`POST /topicos`)
- [x] Actualizar información parcial de un tópico (`PUT /topicos`)
- [x] Inactivar un tópico (borrado lógico) (`DELETE /topicos/{id}`)

## Tecnologías utilizadas

- Java 17
- Spring Boot 3.1+
- Spring Web
- Spring Data JPA
- Hibernate
- MySQL
- Maven

## Detalles técnicos

- Se implementó el modelo de entidad `Topico`, relacionada con autor y curso.
- El campo `status` se maneja como `ENUM` en Java, y se almacena como `VARCHAR` en la base de datos.
- Se resolvieron errores comunes de Hibernate relacionados con el mapeo de nombres de columnas, validación de datos y tipo de campos (`Data truncated`, `Unknown column`).
- Se aplicó `@Column(name = "...")` para ajustar campos como `fechaCreacion`, respetando el nombre en código sin renombrar la base de datos.

## Lecciones aprendidas

Durante el desarrollo del proyecto, se logró:

- Comprender y aplicar los principios de una API REST segura.
- Identificar errores comunes durante el desarrollo backend y solucionarlos de forma efectiva.
- Utilizar herramientas modernas de desarrollo como Postman, IntelliJ, GitHub y PowerShell.
- Aplicar control de versiones y buenas prácticas de documentación y entrega.

## Autor

**Edwin Bladimir Torres Corredor**  
Desarrollador Backend | Estudiante del curso Spring Boot  
Correo: ed_blatoco@gmail.com  
GitHub: [https://github.com/Bladito77](https://github.com/Bladito77)

🛠️ Tecnologías utilizadas
Java 17

Spring Boot 3.5.4

Spring Web (REST)

Spring Data JPA

Spring Security

Spring Boot DevTools

Spring Boot Starter Test

Hibernate Validator

Flyway (migraciones de base de datos)

MySQL (driver oficial mysql-connector-j)

JWT (Java Web Token) con java-jwt de Auth0

Lombok (reducción de código repetitivo en entidades, DTOs)

SpringDoc OpenAPI (springdoc-openapi-starter-webmvc-ui) para documentación Swagger de los endpoints

IntelliJ IDEA / Visual Studio Code

Postman para pruebas manuales de la API

Git & GitHub para control de versiones y entrega

## 📦 Estructura del proyecto
src/
├── main/
│ ├── java/
│ │ └── com.topicos.api/
│ │ ├── controller
│ │ ├── domain
│ │ └── repository
│ └── resources/
│ └── application.properties



## 🛠️ Funcionalidades

- Crear, consultar, actualizar e inactivar tópicos
- Manejo de errores y validación con Bean Validation
- Uso de DTOs (`record`) para entrada y salida de datos
- Autenticación básica por login (usuario y contraseña)
- Uso de status ENUM para estado de los tópicos

## 🧪 Ejemplos de uso (JSON)

### Crear tópico (`POST /topicos`)
```json
{
  "titulo": "Error con Hibernate",
  "mensaje": "No me inserta el campo fecha",
  "fechaCreacion": "2025-08-06T14:00:00",
  "status": "NO_RESPONDIDO",
  "autor_id": 1,
  "curso_id": 2,
  "respuestas": "Aún sin respuesta"
}

{
  "id": 5,
  "titulo": "Título actualizado",
  "mensaje": "Mensaje actualizado",
  "respuestas": "Respuesta agregada"
}

Eliminar tópico (DELETE /topicos/{id})
Realiza un borrado lógico: cambia el estado activo a false.

🧠 Autor
Edwin Bladimir Torres Corredor
Desarrollador Full Stack
Contacto: ed_blatoco@gmail.com
GitHub: @Bladito77

