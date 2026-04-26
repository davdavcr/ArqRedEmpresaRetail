## Descripción del Proyecto

Este proyecto consiste en el diseño e implementación de una arquitectura de red empresarial orientada a una empresa del sector retail. La solución integra segmentación mediante VLANs, enrutamiento dinámico y servicios centralizados, con el objetivo de garantizar conectividad, organización y seguridad en la red corporativa.

La arquitectura fue diseñada bajo un modelo centralizado, donde los servicios principales de red se encuentran alojados en la sede central, permitiendo una administración más eficiente de recursos y políticas de seguridad.

---

## Objetivo General

Diseñar e implementar una arquitectura de red empresarial segura y escalable que permita la interconexión entre la sede central y una sucursal, utilizando protocolos de red, segmentación lógica y servicios centralizados.

---

## Objetivos Específicos

* Implementar segmentación de red mediante VLANs.
* Configurar direccionamiento IP utilizando VLSM.
* Centralizar los servicios de red en la sede principal.
* Implementar DHCP Relay para distribución de direcciones IP entre sedes.
* Configurar OSPF para enrutamiento dinámico.
* Aplicar medidas de seguridad en la infraestructura de red.

---

## Arquitectura de Red

La infraestructura propuesta está compuesta por:

* 3 routers: ISP, Router de sede central (HQ) y Router de sucursal.
* Switches administrables para segmentación mediante VLANs.
* Access Points para conectividad inalámbrica.
* Un servidor central ubicado en la sede principal.

La red fue diseñada bajo un enfoque centralizado, donde la sede principal administra los servicios y recursos para toda la infraestructura, mientras que la sucursal se conecta mediante enlaces WAN para acceder a dichos servicios.

---

## Segmentación de Red

Se implementó segmentación lógica mediante VLANs para separar los diferentes departamentos y servicios de la empresa:

* VLAN 10 – Ventas
* VLAN 20 – Administración
* VLAN 30 – Servidores
* VLAN 50 – WiFi empleados
* VLAN 60 – WiFi invitados
* VLAN 99 – Management

Esta segmentación permite mejorar la organización de la red, reducir dominios de broadcast y aplicar políticas de seguridad específicas según cada área.

---

## Direccionamiento IP

Se utilizó la red base **192.168.0.0/16**, aplicando subnetting con VLSM para optimizar la asignación de direcciones IP según las necesidades de cada segmento.

Además, se configuraron enlaces WAN dedicados para la comunicación entre sedes:

* HQ – Sucursal: 10.0.0.0/30
* HQ – ISP: 10.0.1.0/30

---

## Servicios Centralizados

Los servicios principales fueron centralizados en la sede principal mediante un servidor corporativo, el cual provee:

* DHCP para asignación automática de direcciones IP.
* DNS para resolución de nombres.
* HTTP para servicios web internos.

Este modelo centralizado facilita la administración, mantenimiento y escalabilidad de la red.

---

## Implementación de DHCP Relay

Debido a que el servidor DHCP se encuentra centralizado en la sede principal, se implementó **DHCP Relay** en los routers para permitir que los dispositivos ubicados en otras VLANs y en la sucursal puedan obtener direcciones IP desde el servidor central.

Los routers reenvían las solicitudes DHCP broadcast hacia el servidor DHCP utilizando el mecanismo de relay, permitiendo una asignación centralizada sin necesidad de desplegar servidores adicionales en cada segmento.

Esta implementación mejora la administración de direcciones IP y simplifica la gestión de la red empresarial.

---

## Enrutamiento Dinámico

Se implementó **OSPF** como protocolo de enrutamiento dinámico entre los routers de la sede central, sucursal e ISP.

Esto permite:

* Propagación automática de rutas.
* Escalabilidad de la red.
* Mejor adaptación ante cambios en la topología.
* Administración más eficiente del enrutamiento.

---

## Seguridad de la Red

Se implementaron medidas básicas de seguridad, entre ellas:

* Segmentación mediante VLANs.
* ACL para control de acceso entre redes.
* Aislamiento de la red inalámbrica de invitados.
* Administración remota segura mediante SSH.
* NAT para ocultamiento de direcciones privadas.

Estas medidas fortalecen la seguridad lógica de la infraestructura y protegen los recursos críticos de la organización.

---

## Presupuesto Estimado

El costo estimado de implementación de la infraestructura propuesta es de **$21,000 USD**, contemplando:

* Routers empresariales
* Switches administrables
* Access Points
* Servidor central
* Seguridad perimetral
* Infraestructura y configuración

---

## Contenido del Repositorio

* `proyecto_David_Andres.pkt`: topología e implementación de la red en Cisco Packet Tracer.
* `Progra_proyectoRedes_II.txt`: configuraciones aplicadas a los dispositivos de red.

---

## Integrantes del Proyecto

**David Arturo Brenes Angulo**
Ingeniero en Sistemas Computacionales
Responsable del diseño de la topología de red y de la implementación/configuración de la infraestructura en Cisco Packet Tracer.

**Andrés Solano Contreras**
Ingeniero en Sistemas Computacionales
Responsable de la elaboración de la documentación escrita y estructuración técnica del proyecto.

---

## Conclusión

El proyecto presenta una arquitectura de red empresarial funcional, organizada y escalable para una empresa de retail, integrando segmentación lógica, servicios centralizados, DHCP Relay y enrutamiento dinámico.

La solución propuesta permite una administración eficiente de la infraestructura, mejora la seguridad de la red y sienta una base sólida para el crecimiento futuro de la organización.
