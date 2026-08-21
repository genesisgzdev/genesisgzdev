# Genesis

Trabajo en seguridad defensiva, sistemas Windows y software que tiene que comportarse bien cuando deja de estar en el camino feliz.

En 30 segundos: este perfil es un índice de proyectos. Cada enlace lleva al repositorio donde están el código, las pruebas y los límites de confianza. No hay una plataforma compartida detrás de esta página.

Vivo en Montevideo, Uruguay. Aprendí de forma práctica y me interesa especialmente entender el sistema que hay debajo: procesos, red, políticas, persistencia, telemetría y los límites reales de una herramienta antes de llamarla terminada.

## Proyectos

| Proyecto | Enfoque | Estado honesto |
| --- | --- | --- |
| [Threat Detection Suite](https://github.com/genesisgzdev/threat-detection-suite) | Ingeniería de detección para Windows con C/C++ y capas nativas | La base de compilación y los contratos de CI están cubiertos. La validación nativa de driver y runtime sigue siendo una etapa separada. |
| [Project MegaTicketing](https://github.com/genesisgzdev/Project-MegaTicketing) | Reservas concurrentes con Fastify, PostgreSQL, Redis, Stripe y React | La reserva usa PostgreSQL como autoridad y tiene pruebas de carrera e integración para ejecutar con servicios reales. |
| [Nexus Intelligence](https://github.com/genesisgzdev/nexus-intelligence) | OSINT y análisis forense local con Python y SQLite | La canalización funciona de forma local con DNS, TLS, web, mail y correlación TF-IDF. La cobertura depende de los servicios que respondan en cada entorno. |
| [CalcX Advanced](https://github.com/genesisgzdev/calcx-advanced) | Calculadora científica de consola con evaluación AST segura | CLI estable con precisión Decimal, complejos, matrices y métodos numéricos. |
| [Aegis11](https://github.com/genesisgzdev/Aegis11) | Políticas y reconciliación de estado para Windows | Tiene baseline de compilación Windows. El comportamiento privilegiado debe validarse en una máquina aislada antes de considerarlo operativo. |

## Cómo trabajo

Me importa que cada afirmación tenga una prueba detrás. En proyectos de seguridad eso significa distinguir entre código compilado, tests automatizados y comportamiento observado sobre el sistema real.

Mis herramientas habituales incluyen C, C++, Python, TypeScript, Node.js, PostgreSQL, Redis, Docker y GitHub Actions. El stack cambia según el problema; la exigencia de poder reproducirlo no.

Los estados de la tabla indican si el proyecto tiene tests, compilación comprobada o una prueba pendiente sobre el sistema real.

## Contacto

Puedes encontrarme en [GitHub](https://github.com/genesisgzdev) o escribirme a [genzt.dev@pm.me](mailto:genzt.dev@pm.me).

El mapa de este repositorio está en [ARCHITECTURE.md](ARCHITECTURE.md). Los detalles técnicos viven en cada proyecto enlazado.
