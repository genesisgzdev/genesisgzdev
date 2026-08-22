# Genesis

Trabajo en seguridad defensiva, sistemas Windows y software que tiene que comportarse bien cuando deja de estar en el camino feliz.

En 30 segundos: este perfil es un índice de proyectos. Cada enlace lleva al repositorio donde están el código, las pruebas y los límites de confianza. No hay una plataforma compartida detrás de esta página.

Vivo en Montevideo, Uruguay. Aprendí de forma práctica y me interesa especialmente entender el sistema que hay debajo: procesos, red, políticas, persistencia, telemetría y los límites reales de una herramienta antes de llamarla terminada.

## Proyectos

| Proyecto | Enfoque | Estado honesto |
| --- | --- | --- |
| [Threat Detection Suite](https://github.com/genesisgzdev/threat-detection-suite) | Ingeniería de detección para Windows con C/C++ y capas nativas | El ABI, los callbacks de proceso/imagen/hilo, los campos de red WFP y las dos colas acotadas tienen checks de contrato. Las respuestas usan el PID objetivo cuando el evento lo entrega; la validación nativa de driver y ETW sigue siendo una etapa separada. |
| [Project MegaTicketing](https://github.com/genesisgzdev/Project-MegaTicketing) | Reservas concurrentes con Fastify, PostgreSQL, Redis, Stripe y React | PostgreSQL decide la venta, el outbox conserva eventos y reclama filas con lease recuperable entre réplicas. El ticket guarda importe, moneda y PaymentIntent; los webhooks repetidos no vuelven al camino de refund. La integración real requiere DB, Redis y Stripe. |
| [Nexus Intelligence](https://github.com/genesisgzdev/nexus-intelligence) | OSINT y análisis forense local con Python y SQLite | DNS, redirects y cada solicitud HTTP se fijan a destinos públicos validados; TLS/SMTP, persistencia WAL, informes y correlación TF-IDF tienen límites explícitos. La cobertura depende de los servicios que respondan en cada entorno. |
| [CalcX Advanced](https://github.com/genesisgzdev/calcx-advanced) | Calculadora científica de consola con evaluación AST segura | CLI con allow-list, presupuestos para AST, matrices, integración y DFT, Decimal, complejos y métodos numéricos. La precisión configurable no convierte las funciones `math`/`cmath` en aritmética arbitraria. |
| [Aegis11](https://github.com/genesisgzdev/Aegis11) | Políticas y reconciliación de estado para Windows | El WAL valida framing y reconstruye el último estado durable por transacción antes de recuperar; el CLI puede capturar un baseline de servicios y tareas soportados. La tarea de reinforcement está limitada y no solapa ejecuciones. La restauración completa y el comportamiento privilegiado deben validarse por separado en una máquina aislada. |

## Cómo trabajo

Me importa que cada afirmación tenga una prueba detrás. En proyectos de seguridad eso significa distinguir entre código compilado, tests automatizados y comportamiento observado sobre el sistema real.

Mis herramientas habituales incluyen C, C++, Python, TypeScript, Node.js, PostgreSQL, Redis, Docker y GitHub Actions. El stack cambia según el problema; la exigencia de poder reproducirlo no.

Los estados de la tabla indican si el proyecto tiene tests, compilación comprobada o una prueba pendiente sobre el sistema real.

La tabla se actualiza cuando cambia una frontera importante. No sustituye los checks ni las arquitecturas de cada repositorio: allí están los comandos, versiones y límites exactos que respaldan cada estado.

## Contacto

Puedes encontrarme en [GitHub](https://github.com/genesisgzdev) o escribirme a [genzt.dev@pm.me](mailto:genzt.dev@pm.me).

El mapa de este repositorio está en [ARCHITECTURE.md](ARCHITECTURE.md). Los detalles técnicos viven en cada proyecto enlazado.
