# Diagramas

## 0.5: Diagrama de aplicación de una sola página

```mermaid
graph TD;
    A[Usuario] -->|Acceso| B[Aplicación de notas (SPA)];
    B -->|Solicitud de notas| C[Servidor];
    C -->|Respuesta JSON| B;
    B -->|Renderización| A;


sequenceDiagram
    participant browser
    participant server
    participant database

    browser->>server: Nueva nota (texto)
    activate server
    server->>database: POST /new_note
    activate database
    database-->>server: OK
    deactivate database
    server-->>browser: OK
    deactivate server
    Note right of browser: Actualización de interfaz
```
