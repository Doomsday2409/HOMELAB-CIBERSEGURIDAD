# Homelab de Ciberseguridad

Laboratorio de ciberseguridad sobre Proxmox VE con segmentación por VLAN,
SOC (Wazuh) y entorno de ataque aislado.

## Objetivos
- Aprender segmentación de redes con PFsense
- Montar un SOC de práctica
- Documentar todo el proceso

## Estado
- [X] Instalacion proxmox
- [X] PFsense + puentes
- [X] Ubuntu Server
- [ ] DMZ
- [ ] DNS
- [ ] Base de datos
- [ ] Wazuh y herramientas SOC
- [ ] Pruebas de vulnerabilidades

## Documentación
- [Instalación de Proxmox](docs/01-proxmox.md)
- [Gestion Bridge](docs/02-PFsense.md)
- [Levantar UBUNTU SERVER](docs/03-ubuntu_server.md)

```mermaid
flowchart TB
    INET(["Internet"]) --> FW["OPNsense<br/>Firewall / Router"]
    FW --> DMZ
    FW --> SRV
    FW --> SOC
    FW --> ATK

    subgraph DMZ["VLAN 10 - DMZ"]
        WEB["Ubuntu Server<br/>Nginx / app"]
    end

    subgraph SRV["VLAN 20 - Servidores"]
        DB[("Base de datos")]
        DNS["Technitium DNS"]
        PBS["Backups PBS"]
    end

    subgraph SOC["VLAN 30 - SOC / Gestión"]
        WAZ["Wazuh"]
        IDS["Suricata / Zeek"]
        GRA["Grafana / Prometheus / Loki"]
    end

    subgraph ATK["VLAN 50 - Ataque"]
        KALI["Kali"]
    end

    WEB -->|"solo 3306/5432"| DB
```
