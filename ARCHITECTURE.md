# Genesis profile architecture

Este repositorio no contiene un runtime de aplicación. Su unidad de ejecución es GitHub renderizando el README de perfil. La arquitectura útil aquí es la relación comprobable entre el índice y los cinco proyectos.

## Lectura rápida

El README presenta los proyectos y enlaza su release publicada. Cada repositorio explica dónde corre, cómo se prueba y qué necesita para funcionar. El perfil no añade integraciones entre ellos.

## 1. Índice y repositorios

~~~mermaid
flowchart TB
    GH[GitHub profile renderer] --> README[genesisgzdev README]
    README --> TDS[threat-detection-suite]
    README --> MEGA[Project-MegaTicketing]
    README --> NEXUS[nexus-intelligence]
    README --> CALCX[calcx-advanced]
    README --> AEGIS[Aegis11]
    TDS -. optional JSONL .-> NEXUS
    MEGA -. operationally separate .-> TDS
~~~

Las líneas punteadas no representan una integración automática entre repositorios: TDS puede producir un JSONL que Nexus sabe ingerir si se configura `TDS_LOG_PATH`; MegaTicketing y Aegis no son dependencias de runtime del perfil.

Para que el dibujo siga siendo legible, solo muestra la relación opcional que existe en el código. Las herramientas, lenguajes y servicios de cada proyecto viven en su propio README.

## 2. Qué debe concordar

| Campo del perfil | Fuente que debe respaldarlo | Límite |
| --- | --- | --- |
| TDS | README, CMake, WDK project and CI | driver/runtime requieren Windows + WDK |
| MegaTicketing | routes, Prisma schema, outbox, Redis and Stripe controllers | integración real requiere DB, Redis, Stripe |
| Nexus | CLI, five analysis modules, SQLite WAL and TF-IDF | respuestas dependen del objetivo/network |
| CalcX | cli.py, bounded engine, shell wrapper and tests | no certifica cálculos críticos |
| Aegis11 | main.cpp, modules, framed WAL and Windows CI | privilegios/runtime aún requieren laboratorio |

El README de perfil es un índice editorial, no una capa que pueda convertir checks de CI en validación de producción. Los detalles de cada flujo viven en el `docs/ARCHITECTURE.md` del repositorio correspondiente.
