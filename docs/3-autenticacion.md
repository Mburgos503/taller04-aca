# 3. Autenticación y Autorización

La API utiliza autenticación basada en tokens JWT para proteger los recursos y ofrece rutas para iniciar sesión, refrescar tokens y cerrar sesión.

## Endpoints de autenticación

| Método | Ruta                | Descripción                          |
| ------ | ------------------- | ------------------------------------ |
| POST   | `/auth/login`       | Iniciar sesión y recibir JWT         |
| POST   | `/auth/refresh`     | Refrescar token expirado             |
| POST   | `/auth/logout`      | Invalidar el token actual           |

!!! tip
    Guarda tu token JWT en un lugar seguro y no lo expongas en el cliente.

---

## Ejemplo de código con pestañas

```bash tabs="Login","Refresh","Logout"
# Login
curl -X POST http://api.example.com/auth/login \
     -H "Content-Type: application/json" \
     -d '{"email":"usuario@mail.com","password":"secret"}'

# Refresh
echo "Bearer <tu_token>" | xargs -I {} curl -X POST http://api.example.com/auth/refresh \
     -H "Authorization: {}"

# Logout
curl -X POST http://api.example.com/auth/logout \
     -H "Authorization: Bearer <tu_token>"
```

---

## Enlace interno a la Estructura de la API

Para revisar los recursos disponibles, ve a:

[Ir a Estructura de la API](1-estructura-api-libros.md)

---

!!! warning
    Si tu token ha expirado, no intentes acceder a rutas protegidas antes de refrescarlo o iniciar sesión de nuevo.
