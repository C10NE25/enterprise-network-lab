# HomeLab: Infraestructura de Red, Seguridad y Virtualización en Linux (Beta)

**Fecha de Última Actualización:** Oct 5 - 2026  
**Estado:** En desarrollo - In progress

## Disclaimer

El proyecto está siendo desarrollado como un laboratorio técnico para estudio y aplicación de conceptos relacionados con infraestructura Linux, redes, virtualización y seguridad.

Cada decisión tecnológica y arquitectónica está siendo evaluada de acuerdo con los criterios:
- Requerimientos
- Limitaciones
- Performance
- Implicaciones de seguridad
- Ventajas y Desventajas

Este proyecto no tiene intenciones de demostrar la superioridad de una tecnología sobre otra. Diferentes entornos requieren diferentes decisiones.

## ¿Sobre qué trata el proyecto?

El objetivo principal es diseñar, desplegar y documentar una infraestructura de red segmentada y un entorno de virtualización simulando un escenario empresarial con restricciones reales.  
Más allá de la configuración paso a paso, este laboratorio busca profundizar en el **por qué** y el **para qué** de cada componente dentro de la arquitectura.

## Stack Tecnológico

- **Enrutamiento y Seguridad:** OPNsense, 802.1Q VLANs, Stateful Firewalling.
- **Virtualización y SO:** KVM/QEMU, Fedora Linux, RHEL.
- **Servicios de red:** DNS, DHCP Relay, Active Directory / LDAP.
- **Redes Linux:** Linux Bridging, Network Segmentation, Virtual Interfaces.

## ¿Para qué sirve el proyecto?

- **Simulación de entorno productivo:** Recrea flujos de tráfico inter-VLAN, políticas de acceso y servicios centralizados en una escala controlada.
- **Validación de reglas de seguridad:** Permite probar políticas *Zero Trust* y análisis de tráfico sin riesgo de impactar un entorno real.
- **Documentación técnica:** Sirve como portafolio de arquitectura.

## ¿Qué problemas soluciona?

- **Aislamiento de dominios de difusión:** Mitiga el tráfico innecesario y mejora la seguridad dividiendo la red en VLANs funcionales (*Users, Servers, Management*).
- **Control de accesos centralizado:** Elimina el acceso plano entre segmentos mediante políticas de *Implicit Deny* en el firewall.
- **Gestión eficiente de recursos:** Centraliza servicios clave (como autenticación y DHCP) evitando duplicidad de configuraciones.

## ESTADO DEL PROYECTO Y ROADMAP

- [-] **Fase 0: Especificación de requerimientos y selección de Stack Tecnológico**
- [ ] **Fase 1: Topology Design y Diagramación de Red**
- [ ] **Fase 2: Despliegue de Infraestructura Base y Seguridad**
- [ ] **Fase 3: Implementación de Servicios Centralizados e Identidad**
- [ ] **Fase 4: Validación, pruebas de seguridad y baseline (v1.0)**
- [ ] **Fase 5: Evolución Futura y nuevas funcionalidades**