# Proceso de Titulación de Pregrado (TO BE) - UNAP

Este repositorio contiene la documentación y el modelamiento del **Proceso de Titulación de Pregrado de la Universidad Nacional del Altiplano (UNAP)**, enfocado en la propuesta de mejora **TO BE**. El objetivo es optimizar la gestión de tesis a través de la plataforma PILAR, eliminando cuellos de botella y mejorando la transparencia institucional.

## 📋 Descripción General
El proceso "TO BE" propone una transición digital completa, donde la interacción entre el tesista, los jurados y las unidades académicas se centraliza en una plataforma única. Esto reduce los tiempos de espera y automatiza tareas administrativas como el sorteo de jurados y la generación de actas.

## 👥 Actores y Roles
*   **Tesista:** Estudiante que inicia el trámite, sube el proyecto de tesis (borrador + reporte de similitud) y realiza las correcciones solicitadas.
*   **Plataforma PILAR:** Sistema que centraliza la información, valida formatos, realiza sorteos electrónicos y genera documentos oficiales.
*   **Director (Escuela Profesional):** Responsable de la primera revisión de conformidad según el plan de estudios.
*   **Unidad de Investigación (VRI):** Entidad que valida técnicamente el proyecto antes del sorteo de jurados.
*   **Jurado:** Docentes encargados de la revisión técnica, dictaminación y aprobación final del proyecto.

## 🛠️ Flujo de Datos y Proceso (TO BE)

A continuación se detalla el flujo de trabajo optimizado para la aprobación de proyectos de tesis:

### Diagrama de Flujo del Proceso
```mermaid
graph TD
    %% Estilos de nodos
    classDef inicio fill:#e1f5fe,stroke:#01579b,stroke-width:2px;
    classDef fin fill:#ffebee,stroke:#b71c1c,stroke-width:2px;
    classDef proceso fill:#fff,stroke:#333,stroke-width:1px;
    classDef decision fill:#fff9c4,stroke:#fbc02d,stroke-width:1px;

    subgraph Tesista
        A((Inicio)) --> B{¿Tiene cuenta?}
        C[Subir Proyecto]
        L[Corregir proyecto Pre-sorteo]
        Q[Corregir proyecto Post-sorteo]
    end

    subgraph Plataforma_PILAR
        D[Crear cuenta]
        E{¿Cumple formato?}
        F[Declarar proyecto no presentado]
        M[Sorteo de Jurados]
        S[Generar acta de aprobación]
        T((Fin))
    end

    subgraph Director_EP
        G{¿Conformidad?}
    end

    subgraph Unidad_Investigacion
        H{¿Valida Proyecto?}
    end

    subgraph Jurados
        N{¿Acepta Cargo?}
        O[Proceso de Revisión]
        P{¿Aprueba Proyecto?}
    end

    %% Conexiones
    A --> B
    B -- No --> D --> C
    B -- Si --> C
    C --> E
    E -- No --> L --> C
    E -- Si --> G
    G -- No/Sin Rpta --> F
    G -- Si --> H
    H -- No --> L
    H -- Si --> M
    M --> N
    N -- No --> M
    N -- Si --> O
    O --> P
    P -- No --> Q --> O
    P -- Si --> S --> T

    %% Aplicar clases
    class A inicio;
    class T fin;
    class B,E,G,H,N,P decision;
    class C,D,F,L,M,O,Q,S proceso;
```

## 🚀 Mejoras Implementadas (Propuesta TO BE)
Basado en el análisis de puntos de dolor (Pain Points), el modelo TO BE aborda:
1.  **Transparencia:** El tesista puede ver en qué estado se encuentra su trámite en tiempo real.
2.  **Agilidad:** El sorteo de jurados es automático, evitando demoras por asignaciones manuales.
3.  **Digitalización:** Se eliminan los expedientes físicos, reduciendo costos y el impacto ambiental.
4.  **Validación Continua:** Filtros previos (Director y Unidad) aseguran que solo lleguen al jurado proyectos que cumplan con los estándares mínimos.

## 📈 Impacto Académico
La implementación de este proceso garantiza:
*   Reducción significativa en el tiempo de aprobación de proyectos.
*   Mayor equidad en la carga académica de los jurados.
*   Repositorio centralizado de actas y dictámenes para auditorías de calidad académica.

---
*Documentación generada para el curso de Ingeniería de Procesos - 2025-II.*
