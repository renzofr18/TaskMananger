# Diagramas del Sistema

## Flujo: Listado de Tareas

El siguiente diagrama de secuencia muestra el flujo completo cuando un usuario solicita el listado de tareas filtradas por estado y prioridad.

```mermaid
sequenceDiagram
    participant App as React Native App
    participant API as .NET API
    participant UC as Use Case
    participant Repo as Repository
    participant DB as SQL Server

    App->>API: GET /tasks?status=&priority=
    API->>UC: Execute GetTasksUseCase
    UC->>Repo: GetTasks(filters)
    Repo->>DB: Execute Stored Procedure
    DB-->>Repo: Result Set
    Repo-->>UC: Domain Models
    UC-->>API: Task DTOs
    API-->>App: 200 OK + JSON