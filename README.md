# Red Nacional (Proyecto de Conmutación y Enrutamiento)

Este repositorio contiene el diseño, configuración y simulación de la infraestructura de red nacional para una empresa. El proyecto aborda la reestructuración y optimización de la red dividida en cuatro regiones geográficas, implementando soluciones de conectividad, redundancia, seguridad y movilidad utilizando Cisco Packet Tracer.

## Descripción del Proyecto

El objetivo principal es realizar cambios en la infraestructura de red existente (148.60.0.0/16) para cumplir con nuevos requerimientos de escalabilidad y seguridad. El diseño se ha modularizado por regiones, permitiendo la colaboración mediante la función **Multiuser** de Packet Tracer.

### Requerimientos Generales y Tecnologías
El proyecto implementa las siguientes tecnologías y protocolos con base en los requerimientos de la compañía:

* **Enrutamiento:** Protocolo RIP para toda la red y ruteo estático donde convenga.
* **Conmutación (Switching):** VLANs, VTP, EtherChannel (PAgP) y STP para minimizar enlaces subutilizados.
* **Redundancia:** Implementación de HSRP.
* **Direccionamiento:**
    * **IPv4:** Subnetting eficiente.
    * **IPv6:** Implementación de Dual Stack en regiones específicas.
    * **DHCP:** Servidores DHCPv4 y DHCPv6.
* **Seguridad:**
    * SSH en todos los dispositivos de comunicación.
    * Seguridad en puertos (Port Security).
* **Inalámbrico:** WLAN con WLC (Wireless LAN Controller) y Access Points autónomos.

---

## Topología y Regiones

El repositorio está organizado en cuatro carpetas principales, correspondiendo a cada región geográfica de la topología nacional.

### NOROESTE
Configuración de la región noroeste enfocada en la implementación híbrida de IP.
* **Características clave:**
    * Implementación de **Dual Stack (IPv4/IPv6)**.
    * Network ID IPv6: `2006:AFEA:B0CA::/48`.
    * Configuración de VTP y VLANs (Gestión TI, Mkt, Ventas, Compras).

### NORESTE
Región enfocada en redundancia y conectividad inalámbrica autónoma.
* **Características clave:**
    * HSRP para alta disponibilidad en el Gateway.
    * Configuración de Access Point autónomo.
    * Optimización de STP.
    * VLANs: 97 (Gestión TI), 98 (Ventas), 99 (Compras), 100 (Servicios).

### CENTRO
El núcleo de la red que conecta dos edificios principales (Principal y Anexo).
* **Características clave:**
    * **WLC (Wireless LAN Controller)** gestionando el acceso WLAN en ambos edificios.
    * Seguridad avanzada: Port Security para evitar la conexión de dispositivos no autorizados.
    * VLANs: 33 a 37, incluyendo gestión y usuarios inalámbricos.

### SURESTE
Región con alta densidad de conmutación y redundancia.
* **Características clave:**
    * Configuración de EtherChannel.
    * Redundancia de Gateway con HSRP.
    * Acceso híbrido (WiFi y Cable) gestionado por controlador.
    * VLANs: 65 (Ventas), 66 (TI), 67 (Compras), 68 (Mkt).

---

## Estructura del Repositorio

```text
/
│
├── CENTRO/
│   ├── centro.pkt
│   └── [Scripts de configuración]
│
├── NORESTE/
│   ├── noreste.pkt
│   └── [Scripts de configuración]
│
├── NOROESTE/
│   ├── noroeste.pkt
│   └── [Scripts de configuración]
│
├── SURESTE/
│   ├── sureste.pkt
│   └── [Scripts de configuración]
│
└── README.md