# HomeLab: Infraestructura de Red, Seguridad y Virtualización en Linux (Beta)

**Fecha de Última Actualización:** Oct 6 - 2026  
**Estado:** En desarrollo - In progress

## Disclaimer

El proyecto se encuentra en proceso de desarrollo, sirve como un laboratorio técnico para estudio y aplicación de conceptos relacionados con infraestructura Linux, redes, virtualización y seguridad.

Cada decisión tecnológica y arquitectónica está siendo evaluada de acuerdo con los criterios:
- Requerimientos
- Limitaciones
- Performance
- Implicaciones de seguridad
- Ventajas y Desventajas

Este proyecto no tiene intenciones de demostrar la superioridad de una tecnología sobre otra. Diferentes entornos requieren diferentes decisiones.

## Planteamiento de la problematica

El area de salud representa un sector importante dentro de la vida diaria del ser humano. En el Peru, generalmente en zonas rurales, existen las postas medicas que sirven como centros de prevencion y atencion de casos menores. 
  * Limitaciones internas: Dentro de sus limitaciones estan que sus procesos operativos son manuales, la infraestructura es limitada y disponen de un presupuesto reducido. -> Impiden la adquisicion de software comercial costoso y generan cuellos de botella en la atencion.
  * Limitaciones externas: Tenemos a la disponibilidad de Internet (inestable/inexistente), disponibilidad de la energia (inconsistente/inexistente). -> comprometen la disponibilidad de las historias clinicas en emergencia y las exponen a fallos.

[Problematica.md](/docs/about/01-Problematica.md)

## Objetivo

**Objetivo principal:** 
Diseñar, desplegar y documentar una infraestructura de red critica segmentada (ZeroTrust) y un entorno de virtualización de alta disponibilidad, utilizando un stack tecnologico 100% Open Source, para demostrar la viabilidad de una solucion de bajo costo, segura y de alta disponibilidad en entornos con limitaciones como una posta rural.

**Objetivos secundarios:**
- Segmentacion  de red: Separar el trafico sensible mediante VLANs y reglas de firewall.
- Virtualizacion y alta disponibilidad: Optimizar los recursos de virtualizacion para asegurar que el servidor pueda seguir operando aunque no disponga de Internet.
- Gestion de identidad y accesos: Implementar un control de accesos para que solo el personal autorizado pueda ingresar a la informacion critica
- Validacion de restricciones: Documentar los *trade-offs* del modelo Open Source frente a los recursos del hardware utilizado.

Más allá de la configuración paso a paso, este laboratorio busca profundizar en el **por qué** y el **para qué** de cada componente dentro de la arquitectura.

## ESTADO DEL PROYECTO Y ROADMAP

- [ ] **Fase 0: Especificación de requerimientos y selección de Stack Tecnológico**
- [ ] **Fase 1: Topology Design y Diagramación de Red**
- [ ] **Fase 2: Despliegue de Infraestructura Base y Seguridad**
- [ ] **Fase 3: Implementación de Servicios Centralizados e Identidad**
- [ ] **Fase 4: Validación, pruebas de seguridad y baseline (v1.0)**
- [ ] **Fase 5: Evolución Futura y nuevas funcionalidades**