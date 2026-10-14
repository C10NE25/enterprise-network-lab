# PRODUCTO MÍNIMO VIABLE

El producto mínimo viable son los requisitos mínimos escogidos teniendo en cuenta espacios físicos, costos y requisitos del centro de salud I-3.

## Acerca del hardware

El producto mínimo viable a nivel de hardware es:
- 1 unidad de UPS básica de escritorio (650 VA como mínimo)
- 1 unidad de mini-PC - 2 tarjetas de red
- 1 unidad de AP PoE (*Access Point*)
- 1 unidad de switch administrable - 8 puertos
- 1 unidad de disco duro externo para respaldo de 1 TB
- Cables Ethernet y conectores RJ45 (sujetos a evaluación de infraestructura física real)

**Autonomía**: *Se asume que el centro médico cuenta con dispositivos finales móviles (tablets, laptops, celulares) debido a que la infraestructura por parte del servidor se encuentra respaldada por el UPS. La adquisición de esos dispositivos permite la continuidad operativa en caso de que dispositivos finales estáticos, como sería una PC de escritorio, no puedan seguir operando en cortes de luz.*

**Delimitaciones físicas**: *Los espacios físicos están asumidos por la Norma Técnica de Salud N° 113 (NTS N° 113-MINSA/DGIEM), de la cual se interpreta que son espacios compactos.*

Para más detalles: [hardware-stack.md](/docs/02-architecture-design/hardware-stack.md)

## Acerca del software

El producto mínimo viable a nivel de software es:
- **Capa de virtualización y aislamiento**: Un hipervisor tipo 1 que permita aislar y administrar los recursos físicos del servidor para ejecutar múltiples servicios de forma segura.
- **Capa de enrutamiento y seguridad lógica**: Un componente encargado de la gestión del tráfico de la red local, aislar segmentos y proveer reglas de cortafuegos sin necesidad de hardware externo.
- **Capa de datos y persistencia local**: Motor de base de datos robusto con diseño orientado a funcionar *offline-first* y capacidad de encolamiento y sincronización para cuando la WAN esté disponible.
- **Capa de sincronización**: Mecanismo automatizado para encolar transacciones durante la desconexión de la red WAN y asegurar su posterior envío.

Para más detalles: [software-stack.md](/docs/02-architecture-design/software-stack.md)

## Limitaciones y mitigaciones

Es importante entender los riesgos que conlleva el producto mínimo viable (en el proyecto tratamos de reducir al mínimo el SPOF):
1. La disposición de un solo equipo físico como servidor orienta al SPOF (*Single Point of Failure*) e impide la retención de datos históricos pesados.
2. El UPS absorbe microcortes y permite un apagado controlado o sostener la mini-PC/red por un periodo corto (aprox. 15 a 30 min). Un apagón prolongado pausará el nodo local.
3. La sincronización de datos depende críticamente de que la red se restablezca periódicamente (CASO B y C). Caso contrario, existe la solución propuesta para el CASO A. -> [Problematica.md](/docs/about/01-Problematica.md)
4. El equipo está expuesto a variaciones de voltaje, acceso físico no autorizado y acumulación de polvo.
5. La infraestructura del centro de salud puede interferir con el único AP existente dependiendo de su construcción.
6. El personal es rotativo y no cuenta con un perfil técnico IT.
7. El disco de respaldo está expuesto a desgaste mecánico o térmico, inestabilidad del bus USB y riesgos de falla de escritura o lectura.

*MITIGACIONES:*
1. El sistema se diseña estrictamente para datos transaccionales de atenciones médicas (historia clínica en formato liviano JSON/texto), delegando el almacenamiento histórico masivo y el procesamiento intensivo al servidor central en la nube.
2. El diseño *offline-first* permite que toda transacción registrada localmente antes de que el UPS agote su energía (sosteniendo el servidor y la red local) permanezca íntegra y segura en el almacenamiento persistente, evitando la pérdida de información del paciente.
3. La base de datos local gestiona colas transaccionales eficientes e identificadores únicos (como UUIDs y código RENAES) para evitar colisiones al momento del envío.
4. Se implementa cifrado de discos en caso de extracción física y la implementación de un gabinete con llave dentro de la posta, lo que minimiza el riesgo de manipulación por terceros.
5. Se impide el uso de ancho de banda para dispositivos personales, priorizando el alcance a dispositivos autorizados. El AP es colocado en una zona central de cobertura preferencial.
6. Se implementa la autorrecuperación y arranque automático en caso de cortes de energía, eliminando la intervención manual del personal médico.
7. El disco externo de 1 TB opera únicamente para copias de seguridad incrementales en horarios de baja exigencia; de esta manera reduce el desgaste y prioriza la unidad SSD interna para la operación en tiempo real.

*Se da por entendido que para su implementación se siguen buenas prácticas realizadas y evaluadas por un profesional acorde a la estructura del ambiente; es por eso que solo se incluyen riesgos esenciales.*

## Acerca del escalamiento

Este proyecto puede ser escalado a nivel conceptual; los principios que usa permiten la evolución natural del mismo. Sin embargo, otras áreas como la infraestructura física, el costo de la misma y la tecnología, entre otras, sí pueden cambiar. 
¿A qué nos referimos con esto? Por ejemplo, el requerimiento de respaldo de un I-3 se mantiene en un hospital de alta complejidad; por el contrario, el software y el hardware son efímeros y pueden variar según los otros requerimientos. 

*En este proyecto se toma en cuenta el escalamiento, pero no se entra en profundidad en él.*