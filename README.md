Entorno de Desarrollo para .NET 9 y PostgreSQL con Dev Containers

Este repositorio configura un entorno de desarrollo listo para usar con **.NET 9 (SDK y Runtime)** y **PostgreSQL 14.3**, ideal para crear, ejecutar y depurar aplicaciones backend en C# dentro de contenedores Dev Containers de VS Code.

---

## 🚀 Características principales

- 🛠️ Basado en **Dev Containers** con `devcontainer.json` para facilitar la integración con **Visual Studio Code** y **GitHub Codespaces**.
- 🐳 Utiliza `docker-compose` para levantar un contenedor de aplicación con .NET 9 y otro de base de datos PostgreSQL.
- 📁 Soporte de **volumen compartido** para mantener sincronizado tu código entre el host y el contenedor (`/workspaces`).
- 💤 La aplicación inicia en modo `sleep infinity` para permitir la exploración del entorno antes de compilar o ejecutar proyectos.
- 🔌 Red compartida (`network_mode: service:db`) que simplifica la conexión entre la app y la base de datos.

---

## 📂 Estructura del entorno

- `Dockerfile`: Basado en la imagen oficial de Microsoft para .NET 9:
```Dockerfile
  FROM mcr.microsoft.com/devcontainers/dotnet:1-9.0
```
- `docker-compose.yml`: Define los servicios app (entorno C#) y db (PostgreSQL 14.3) con volumen persistente.
- `devcontainer.json`: Configura el entorno para que VS Code se conecte automáticamente al contenedor app.

---

## ✅ Requisitos

- Docker
- Visual Studio Code
- Extensión Dev Containers de Microsoft
- Git (opcional)

---

## ▶️ Uso rápido

1. Clona este repositorio:
```bash
git clone https://github.com/tu-usuario/tu-repo.git
```
2. Abre el proyecto en Visual Studio Code.
3. Cuando se te indique, selecciona:
**“Reopen in Container”**
4. Una vez dentro del contenedor, crea tu proyecto:
```bash
dotnet new console -o MyApp
cd MyApp
dotnet run
```

### Flujo de Trabajo con Dev Container
![](https://code.visualstudio.com/assets/docs/devcontainers/create-dev-container/container-edit-loop.png)

---

## 🗃️ Base de Datos PostgreSQL

- Hostname (dentro del contenedor): `localhost` (gracias a `network_mode: service:db`)
- Usuario: `postgres` *cambia al usuario*
- Contraseña: `postgres` *cambia la contraseña*
- Base de datos: `postgres` *cambia la base de datos*
- Puerto expuesto: `5433` *cambia el puerto al HOST si es requerido*


---

## 🧪 Estado del entorno

- .NET 9 SDK
- PostgreSQL 14.3
- Listo para pruebas, compilación y ejecución en desarrollo local o Codespaces


---

## 📝 Licencia
Este proyecto es de uso libre para entornos de desarrollo educativo o profesional.
