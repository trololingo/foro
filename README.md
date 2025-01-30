# 📌 Foro API

Foro API es una API REST construida con **Spring Boot** y **MySQL** para gestionar un foro en línea. Permite la creación, edición y eliminación de usuarios y temas de discusión.

## 🚀 Tecnologías Utilizadas
- **Java 17**
- **Spring Boot 3.4.2**
- **Spring Data JPA** (Hibernate)
- **Spring Security**
- **MySQL**
- **Maven**

## 📂 Estructura del Proyecto
```
foro-api/
│── src/
│   ├── main/
│   │   ├── java/com/forochallenge/foro_api/
│   │   │   ├── controller/   # Controladores REST
│   │   │   ├── model/        # Modelos de la base de datos
│   │   │   ├── repository/   # Repositorios JPA
│   │   │   ├── service/      # Servicios de lógica de negocio
│   │   │   ├── ForoApiApplication.java  # Clase principal
│   │   ├── resources/
│   │   │   ├── application.properties  # Configuración de la BD
│── pom.xml  # Dependencias del proyecto
│── README.md  # Documentación
```

## 📌 Endpoints Disponibles

### 📌 Autenticación (Spring Security)
- `POST /login` → Iniciar sesión
- `POST /register` → Registrar usuario

### 📌 Usuarios
- `GET /usuarios` → Listar usuarios
- `GET /usuarios/{id}` → Obtener usuario por ID
- `POST /usuarios` → Crear un usuario
- `PUT /usuarios/{id}` → Actualizar usuario
- `DELETE /usuarios/{id}` → Eliminar usuario

### 📌 Tópicos (Temas del foro)
- `GET /topicos` → Listar tópicos
- `GET /topicos/{id}` → Obtener un tópico por ID
- `POST /topicos` → Crear un tópico
- `PUT /topicos/{id}` → Actualizar un tópico
- `DELETE /topicos/{id}` → Eliminar un tópico

## ⚙️ Configuración y Ejecución
### 📌 1. Configurar Base de Datos
Asegúrate de que tu base de datos **MySQL** está en ejecución y que el archivo `application.properties` tiene la configuración correcta:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/foro_db
spring.datasource.username=root
spring.datasource.password=tu_contraseña
```

### 📌 2. Compilar y Ejecutar el Proyecto
```sh
mvn clean install
mvn spring-boot:run
```
La API estará disponible en `http://localhost:8080`.

## 🛠 Posibles Errores y Soluciones
1. **Error de puerto ocupado (8080)**:
   ```sh
   netstat -ano | findstr :8080
   taskkill /PID <PID> /F
   ```
   O cambia el puerto en `application.properties`:
   ```properties
   server.port=8081
   ```

2. **Problemas con la base de datos**:
   - Verifica que MySQL esté en ejecución.
   - Confirma que `foro_db` existe.

## 📝 Contribuciones
Si deseas contribuir, ¡eres bienvenido! Haz un **fork**, crea una rama y envía un **pull request**.

## 📜 Licencia
Este proyecto está bajo la licencia MIT.

