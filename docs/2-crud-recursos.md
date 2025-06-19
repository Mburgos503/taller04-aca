# 2. Operaciones CRUD para Libros

En esta sección describimos cómo crear, leer, actualizar y eliminar recursos de **Libros** en la API.

## Tabla de operaciones y campos

| Operación | Método HTTP | Ruta             | Campos requeridos       | Campos opcionales       |
| --------- | ----------- | ---------------- | ----------------------- | ----------------------- |
| Crear     | POST        | `/books`         | `title`, `author_id`    | `description`, `isbn`   |
| Listar    | GET         | `/books`         | —                       | `?page`, `?limit`       |
| Obtener   | GET         | `/books/{id}`    | —                       | —                       |
| Actualizar| PUT         | `/books/{id}`    | al menos un campo       | —                       |
| Eliminar  | DELETE      | `/books/{id}`    | —                       | —                       |

!!! tip
    Al listar libros, usa `?page=` y `?limit=` para paginar los resultados y evitar respuestas muy pesadas.

---

## Bloque de código con pestañas

```bash tabs="Crear","Actualizar","Eliminar"
# Crear un libro
curl -X POST http://api.example.com/books \
     -H "Content-Type: application/json" \
     -d '{"title":"1984","author_id":3}'

# Actualizar un libro
curl -X PUT http://api.example.com/books/5 \
     -H "Content-Type: application/json" \
     -d '{"description":"Distopía clásica"}'

# Eliminar un libro
curl -X DELETE http://api.example.com/books/5
```

---

## Enlace interno a Autenticación

Para gestionar tokens y permisos, consulta la sección de Autenticación y Autorización:

[Ir a Autenticación y Autorización](3-autenticacion.md)

---


!!! warning
    Asegúrate de enviar siempre un token válido en el header `Authorization` antes de ejecutar cualquier operación.
