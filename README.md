# Genesis

Trabajo en seguridad defensiva, sistemas Windows y software que tiene que comportarse bien cuando deja de estar en el camino feliz.

En 30 segundos: este perfil es un índice de proyectos. Cada enlace lleva al repositorio donde están el código, las pruebas y los límites de confianza. No hay una plataforma compartida detrás de esta página.

Vivo en Montevideo, Uruguay. Aprendí de forma práctica y me interesa especialmente entender el sistema que hay debajo: procesos, red, políticas, persistencia, telemetría y los límites reales de una herramienta antes de llamarla terminada.

## Proyectos

| Proyecto | Enfoque | Estado honesto |
| --- | --- | --- |
| [Threat Detection Suite](https://github.com/genesisgzdev/threat-detection-suite) | Ingeniería de detección para Windows con C/C++ y capas nativas | El ABI, los callbacks de proceso/imagen/hilo, la cola acotada y sus contadores tienen checks de contrato. La validación nativa de driver y runtime sigue siendo una etapa separada. |
| [Project MegaTicketing](https://github.com/genesisgzdev/Project-MegaTicketing) | Reservas concurrentes con Fastify, PostgreSQL, Redis, Stripe y React | PostgreSQL decide la venta y un outbox transaccional evita perder el evento entre el commit y Redis. La integración real requiere DB, Redis y Stripe. |
| [Nexus Intelligence](https://github.com/genesisgzdev/nexus-intelligence) | OSINT y análisis forense local con Python y SQLite | DNS, redirects, persistencia WAL, informes y correlación TF-IDF tienen límites explícitos. La cobertura depende de los servicios que respondan en cada entorno. |
| [CalcX Advanced](https://github.com/genesisgzdev/calcx-advanced) | Calculadora científica de consola con evaluación AST segura | CLI con allow-list, límites contra operaciones desproporcionadas, Decimal, complejos, matrices y métodos numéricos. |
| [Aegis11](https://github.com/genesisgzdev/Aegis11) | Políticas y reconciliación de estado para Windows | El WAL valida framing y deja marcada la recuperación; los tipos de registro están alineados con Win32. El comportamiento privilegiado debe validarse en una máquina aislada. |

## Cómo trabajo

Me importa que cada afirmación tenga una prueba detrás. En proyectos de seguridad eso significa distinguir entre código compilado, tests automatizados y comportamiento observado sobre el sistema real.

Mis herramientas habituales incluyen C, C++, Python, TypeScript, Node.js, PostgreSQL, Redis, Docker y GitHub Actions. El stack cambia según el problema; la exigencia de poder reproducirlo no.

Los estados de la tabla indican si el proyecto tiene tests, compilación comprobada o una prueba pendiente sobre el sistema real.

## Contacto

Puedes encontrarme en [GitHub](https://github.com/genesisgzdev) o escribirme a [genzt.dev@pm.me](mailto:genzt.dev@pm.me).

El mapa de este repositorio está en [ARCHITECTURE.md](ARCHITECTURE.md). Los detalles técnicos viven en cada proyecto enlazado.
