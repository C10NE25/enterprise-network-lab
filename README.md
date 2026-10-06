# HomeLab: Infraestructura de Red, Seguridad y Virtualizacion en Linux (Beta)

**Fecha de Ultima Actualizacion** Oct 5 - 2026
**Estado: En desarrollo - In progress**

### Disclaimer

El proyecto esta siendo desarrollado como un laboratorio tecnico para estudio y aplicacion de conceptos relacionados con infraestructura Linux, redes, virtualizacion y seguridad.

Cada decision tecnologica y arquitectonica esta siendo evaluada de aceurdo los criterios:
- Requerimientos
- Limitaciones
- Performance
- Implicaciones de seguridad
- Ventajas y Desventajas

Este proyecto no tiene intenciones de demostrar la superioridad de una tecnologia sobre otra. Diferentes entornos requieres diferentes decisiones.

## Sobre que trata el proyecto

El objetivo principal es disenar desplegar y documentar una infraestructura de red segmentada y un entorno de virtualizacion simulando un escenario empresarial con restricciones reales.
Mas alla de la configuracion paso a paso, este laboratorio busca profundizar en el **por que** y el **para que** ded cada componente dentro de la arquitectura.

## Stack Tecnologico

- **Enrutamiento y Seguridad:** OPNsense, 802.1Q VLANs, Stateful Firewalling.
- **Virtualizacion y SO:** KVM/QEMU, Fedora Linux, RHEL.
- **Servicios de red:**DNS, DHCP Relay, Active Directory / LADP.
- **Redes Linux:**Linux Brindging, Network Segmentation, Virtual Interfaces.

## Para que sirve el proyecto?

- **Simulación de entorno productivo:** Recrea flujos de tráfico inter-VLAN, políticas de acceso y servicios centralizados en una escala controlada.
- **Validación de reglas de seguridad:** Permite probar políticas *Zero Trust* y análisis de tráfico sin riesgo de impactar un entorno real.
- **Documentación técnica:** Sirve como portafolio de arquitectura.

## Que problemas soluciona?

- **Aislamiento de dominios de difusión:** Mitiga el tráfico innecesario y mejora la seguridad dividiendo la red en VLANs funcionales (*Users, Servers, Management*).
- **Control de accesos centralizado:** Elimina el acceso plano entre segmentos mediante políticas de *Implicit Deny* en el firewall.
- **Gestión eficiente de recursos:** Centraliza servicios clave (como autenticación y DHCP) evitando duplicidad de configuraciones.

## ESTADO DEL PROYECTO Y ROADMAP

- [-] **Fase 0: Especificacion de requerimiento y seleccion de Stack Tecnologico**
- [] **Fase 1: Topology Desing y Diagramacion de Red**
- [] **Fase 2: Despliegue de Infraestructura Base y Seguridad**
- [] **Fase 3: Implementacion de Servicios Centralizados e Identidad**
- [] **Fase 4: Validacion, pruebas de seguridad y baseline (v1.0)**
- [] **Fase 5: Evolucion Futura y nuevas funcionalidades**