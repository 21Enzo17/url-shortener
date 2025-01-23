# URL Shortener API

![Build Status](https://img.shields.io/badge/build-passing-brightgreen)
![Java Version](https://img.shields.io/badge/Java-17-blue)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-2.7.5-brightgreen)
![License](https://img.shields.io/badge/License-MIT-yellow)

## Descripción

La **URL Shortener API** es una solución para simplificar la compartición de enlaces, transformando URLs largas en enlaces cortos. Además, permite analizar estadísticas detalladas sobre las visitas, garantizando seguridad y escalabilidad.

## Características Principales

- **Acortamiento de URLs**: Genera enlaces cortos únicos y fáciles de usar.
- **Redirección**: Redirige a los usuarios desde un enlace corto a la URL original.
- **Estadísticas avanzadas**: Rastrea visitas por país, ciudad, fecha y hora.
- **Autenticación y autorización**: Implementación de seguridad basada en **JWT (JSON Web Tokens)**.
- **Control de usuarios**: Gestión de roles y permisos.
- **Soporte multibase de datos**: Compatible con **H2 Database** (desarrollo) y **MySQL/PostgreSQL** (producción).
- **Escalabilidad y rendimiento**: Preparado para manejar altos volúmenes de tráfico.

## Tecnologías Utilizadas

- **Lenguaje**: Java 17
- **Framework**: Spring Boot 2.7.5
- **Base de Datos**:
  - **H2 Database** (para pruebas y desarrollo local).
  - **MySQL** o **PostgreSQL** (para entornos de producción).
- **Seguridad**:
  - **JWT (JSON Web Tokens)** para autenticación y autorización.
  - **Spring Security** para protección de endpoints.
- **Otros**:
  - **Spring Data JPA**: Abstracción para interactuar con la base de datos.
  - **Lombok**: Eliminación de código repetitivo como getters y setters.
  - **Validation**: Validación de datos de entrada.
  - **GeoIP2**: Para obtener datos geográficos de las visitas.

## Instalación

1. Clona el repositorio:

```bash
https://github.com/tu-usuario/url-shortener-api.git
```

2. Navega al directorio del proyecto:

```bash
cd url-shortener-api
```

3. Configura las variables de entorno en `application.properties` o un archivo `.env` (ejemplo incluido en el proyecto).

4. Construye y ejecuta la aplicación:

```bash
./mvnw spring-boot:run
```

## Endpoints Principales

| Operación                        | Método HTTP | Endpoint                          | Descripción                                    |
|-----------------------------------|---------------|-----------------------------------|------------------------------------------------|
| Crear enlace corto                | POST          | `/links`                         | Genera un enlace corto a partir de una URL larga. |
| Redirigir a URL original          | GET           | `/links/{shortUrl}`              | Redirige a la URL original.                     |
| Obtener estadísticas de enlace    | GET           | `/links/{shortUrl}/statistics`   | Devuelve estadísticas de visitas.              |
| Registrar usuario                 | POST          | `/users/register`                | Registra un nuevo usuario.                     |
| Iniciar sesión                    | POST          | `/auth/login`                    | Autentica un usuario y devuelve un JWT.         |

## Pruebas

Ejecuta las pruebas unitarias con el siguiente comando:

```bash
./mvnw test
```

## Próximas Mejoras

- **Soporte para caducidad de enlaces**: Los enlaces cortos tendrán una fecha de vencimiento opcional.
- **Gestion de Cache**: Se agregara Redis para manejar la cache y asi mejorar las consultas frecuentes.

## Licencia

Este proyecto está bajo la licencia MIT.

---
