# Genesis profile architecture

Este repositorio no contiene un runtime de aplicación. Su unidad de ejecución es GitHub renderizando el README de perfil. La arquitectura útil aquí es la relación comprobable entre el índice y los cinco proyectos.

## Lectura rápida

El README presenta los proyectos y enlaza su release publicada. Cada repositorio explica dónde corre, cómo se prueba y qué necesita para funcionar. El perfil no añade integraciones entre ellos.

## 1. Índice y repositorios

| Proyecto | Entrada y estado persistente | Mapa completo |
| --- | --- | --- |
| TDS | Servicio Windows; JSONL; driver opcional | [Archivos y flujos](https://github.com/genesisgzdev/threat-detection-suite/blob/main/docs/REPOSITORY_MAP.md) |
| MegaTicketing | Fastify/React; PostgreSQL y Redis | [Archivos y flujos](https://github.com/genesisgzdev/Project-MegaTicketing/blob/main/docs/REPOSITORY_MAP.md) |
| Nexus | CLI Python; SQLite e informes | [Archivos y flujos](https://github.com/genesisgzdev/nexus-intelligence/blob/main/docs/REPOSITORY_MAP.md) |
| CalcX | CLI Python; configuración e historial XDG | [Archivos y flujos](https://github.com/genesisgzdev/calcx-advanced/blob/main/docs/REPOSITORY_MAP.md) |
| Aegis11 | CLI Windows; WAL y snapshots JSON | [Archivos y flujos](https://github.com/genesisgzdev/Aegis11/blob/main/docs/REPOSITORY_MAP.md) |

Nexus puede ingerir el JSONL de TDS mediante configuración explícita. No hay integración automática entre los cinco proyectos. MegaTicketing no depende de TDS ni Aegis11.

## 2. Qué debe concordar

| Campo del perfil | Fuente que debe respaldarlo | Límite |
| --- | --- | --- |
| TDS | README, CMake, WDK project and CI | driver/runtime requieren Windows + WDK |
| MegaTicketing | routes, Prisma schema, outbox, Redis and Stripe controllers | integración real requiere DB, Redis, Stripe |
| Nexus | CLI, five analysis modules, SQLite WAL and TF-IDF | respuestas dependen del objetivo/network |
| CalcX | cli.py, bounded engine, shell wrapper and tests | no certifica cálculos críticos |
| Aegis11 | main.cpp, modules, framed WAL and Windows CI | privilegios/runtime aún requieren laboratorio |

El README de perfil es un índice editorial, no una capa que pueda convertir checks de CI en validación de producción. Los detalles de cada flujo viven en el `docs/ARCHITECTURE.md` del repositorio correspondiente.

## Inventario del perfil

| Archivo | Responsabilidad |
| --- | --- |
| [README.md](README.md) | Presentación y enlaces de proyectos/releases |
| [ARCHITECTURE.md](ARCHITECTURE.md) | Relaciones, fuentes e inventario |

Las releases enlazadas son versiones publicadas; pueden ser anteriores a las correcciones de main. Los badges de CI de cada proyecto y su historial de commits determinan qué revisión fue validada.
