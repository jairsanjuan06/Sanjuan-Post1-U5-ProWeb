# Gestión de Tareas — Servlet & JSP

Aplicación web Java para gestionar una lista de tareas en memoria,
desarrollada con Servlets, JSP y el patrón Post/Redirect/Get (PRG).

## Tecnologías

- Java JDK 26
- Jakarta EE (Servlets 6.0)
- JSP + JSTL 3.0
- Apache Tomcat 10.1.54
- Maven 3.8+

## Estructura del proyecto

```
gestion-tareas/
├── pom.xml
└── src/main/
    ├── java/com/ejemplo/
    │   ├── model/Tarea.java               # Modelo POJO
    │   └── servlet/TareasServlet.java     # Controlador HTTP
    └── webapp/
        ├── index.jsp                      # Redirección inicial
        └── WEB-INF/
            ├── web.xml
            └── views/tareas.jsp           # Vista principal
```

## Requisitos previos

- JDK 26 instalado
- Apache Tomcat 10.x descargado y descomprimido
- IntelliJ IDEA Ultimate
- Maven 3.8+

## Pasos para ejecutar

1. Clonar el repositorio:
   ```bash
   git clone https://github.com/jairsanjuan06/Sanjuan-Post1-U5-ProWeb.git
   cd Sanjuan-Post1-U5-ProWeb/gestion-tareas
   ```

2. Compilar el proyecto:
   ```bash
   mvn clean package
   ```

3. En IntelliJ IDEA:
   - `Run → Edit Configurations → Tomcat Server → Local`
   - En **Deployment** → `+` → `External Source` → seleccionar la carpeta:
     `target/gestion-tareas-1.0-SNAPSHOT`
   - **Application context:** `/gestion-tareas`
   - En **Server** → URL: `http://localhost:8080/gestion-tareas/tareas`
   - Clic en **Run**

4. Abrir en el navegador:
   ```
   http://localhost:8080/gestion-tareas/tareas
   ```

## Funcionalidades

| Acción | Método HTTP | Descripción |
|--------|-------------|-------------|
| Ver tareas | GET | Lista todas las tareas en tabla |
| Agregar tarea | POST | Valida título y agrega a la lista |
| Eliminar tarea | POST | Elimina por ID con `removeIf` |

## Patrón PRG (Post/Redirect/Get)

Después de cada POST exitoso el servidor responde con un redirect 302
hacia GET `/tareas`. Esto evita el reenvío del formulario al presionar F5.

## Validaciones

- Título vacío o solo espacios → mensaje de error en pantalla
- Encoding UTF-8 forzado en el POST → soporte de tildes y ñ

## Capturas de pantalla


## Autor

**Jair Sanjuan** — Ingeniería de Sistemas, UDES 2026
