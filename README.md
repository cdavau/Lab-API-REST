# Laboratorio: API REST con PHP y JWT

**Asignatura:** Desarrollo de Software VII  
**Grupo:** 1GS132
**Instructor:** Ing. Irina Fong  
**Estudiante:** Carlos Abadia  
**Semestre:** I Semestre 2026

---

## 📌 Introducción

En este laboratorio se desarrolló una API REST en PHP con autenticación segura mediante tokens JWT (JSON Web Tokens). Se implementó un CRUD completo para la gestión de productos, protegido bajo una arquitectura stateless que impide el acceso a los recursos sin un token válido. Las pruebas se realizaron con la herramienta Postman.

---

## Tecnologías utilizadas

- PHP 7+
- MySQL
- Apache (WAMP)
- Composer
- Firebase PHP-JWT
- Postman

---


## Pruebas con Postman

### 1. Registro de usuario
Registro del usuario admin con contraseña encriptada usando `password_hash()`.

> **POST** `http://localhost/EJEMPLOTOKENS/login.php`

<img width="729" height="745" alt="image" src="https://github.com/user-attachments/assets/0c60d6e7-277a-4e22-8980-6cb21ba6093a" />

---

### 2. Login y obtención del token
Login con credenciales válidas. El servidor responde con un token JWT firmado.

> **POST** `http://localhost/EJEMPLOTOKENS/login.php`

<img width="921" height="777" alt="image" src="https://github.com/user-attachments/assets/ca5f25a4-2c06-43e3-8476-8a1c3f14644f" />

---

### 3. Crear producto (POST)
Creación de un nuevo producto enviando el token en el header `Authorization`.

> **POST** `http://localhost/EJEMPLOTOKENS/index.php?ruta=productos`

<img width="835" height="715" alt="image" src="https://github.com/user-attachments/assets/ea7ef723-e472-4940-ba8c-efb824b62a0c" />

---

### 4. Consultar productos (GET)
Listado de todos los productos registrados en la base de datos.

> **GET** `http://localhost/EJEMPLOTOKENS/index.php?ruta=productos`

<img width="750" height="632" alt="image" src="https://github.com/user-attachments/assets/8ec5355d-d221-4ab2-94c7-a3614d08087e" />


---

### 5. Actualizar producto (PUT)
Actualización de un producto existente usando su ID en la URL.

> **PUT** `http://localhost/EJEMPLOTOKENS/index.php?ruta=productos&id=1`

<img width="790" height="740" alt="image" src="https://github.com/user-attachments/assets/a23c9bae-2116-4dce-97cd-223b9b2218ad" />

---

### 6. Eliminar producto (DELETE)
Eliminación de un producto por ID.

> **DELETE** `http://localhost/EJEMPLOTOKENS/index.php?ruta=productos&id=2`

<img width="921" height="797" alt="image" src="https://github.com/user-attachments/assets/78a6a83c-1bad-4ee5-935f-06f6b4364013" />

---

### 7. ❌ Escenario Negativo — Sin token
Intento de acceso sin token. El servidor responde con un error `401 Unauthorized`.

> **GET** `http://localhost/EJEMPLOTOKENS/index.php?ruta=productos`

<img width="921" height="806" alt="image" src="https://github.com/user-attachments/assets/5772a98b-0a44-41a5-aeb4-7275eefa9017" />


---

## ✅ Conclusión

A través de este laboratorio se logró implementar una API REST segura en PHP, aplicando buenas prácticas de desarrollo como el hashing de contraseñas con BCRYPT, la centralización del enrutamiento mediante un Front Controller y la protección de endpoints con tokens JWT. Se comprobó que sin un token válido la API rechaza cualquier solicitud, garantizando la seguridad de los recursos.

---


