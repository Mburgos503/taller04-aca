# 1. Estructura de la API de Gestión de Libros

La API de Gestión de Libros permite interactuar con los recursos principales: Libros, Autores y Usuarios. A continuación se describen los endpoints disponibles.

## Endpoints disponibles

| Método   | Ruta                   | Descripción                                  |
| -------- | ---------------------- | -------------------------------------------- |
| GET      | `/books`               | Obtener lista de todos los libros            |
| GET      | `/books/{id}`          | Obtener detalles de un libro por su ID       |
| POST     | `/books`               | Crear un nuevo libro                         |
| PUT      | `/books/{id}`          | Actualizar un libro existente                |
| DELETE   | `/books/{id}`          | Eliminar un libro por ID                     |

!!! tip
    Usa siempre el parámetro `?fields=` en tus GET para limitar los campos recibidos y optimizar las respuestas.

---

## Ejemplo de llamada con pestañas

```bash tabs="Listar Libros","Crear Libro"
curl -X GET http://api.example.com/books

curl -X POST http://api.example.com/books \
     -H "Content-Type: application/json" \
     -d '{"title":"Cien Años de Soledad","author_id":2}'
```

---

## Enlace interno a Operaciones CRUD

Para ver ejemplos de payload y respuestas, visita la sección de Operaciones CRUD:

[Ir a Operaciones CRUD](2-crud-recursos.md)

!!! warning
    Asegúrate de reemplazar `api.example.com` por el dominio real de tu servidor.
