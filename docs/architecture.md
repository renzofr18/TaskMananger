# Arquitectura del Backend

## Visión General

El backend del proyecto está diseñado siguiendo los principios de **Clean Architecture**, con el objetivo de lograr:
- Separación clara de responsabilidades
- Bajo acoplamiento entre capas
- Alta testabilidad
- Facilidad de mantenimiento y escalabilidad

La aplicación se expone como un microservicio RESTful desarrollado en .NET 6+.

---

## Diagrama de Arquitectura

```mermaid
graph TD
    A[React Native App] --> B[API Controllers]
    B --> C[Use Cases]
    C --> D[Domain Entities]
    C --> E[Repository Interfaces]
    E --> F[Repository Implementations]
    F --> G[(SQL Server)]
