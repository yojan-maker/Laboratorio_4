# 🧪 Laboratorio 4 — Explorando el Mundo de las Comunicaciones

## 📘 Descripción General
Este laboratorio tuvo como objetivo comprender los fundamentos de las **comunicaciones en red** y la **virtualización de sistemas operativos**, mediante la configuración de un switch Cisco 2960, la interconexión de dispositivos físicos y la instalación de máquinas virtuales usando QEMU/KVM.

---

## ⚙️ Punto 1 — Configuración del Switch y Red Local

### 🔌 Conexión y configuración
- Acceso al **switch Cisco 2960** mediante conexión **serial USB–RS232** usando `minicom`, `screen` y `picocom`.
- Configuración básica del switch: hostname, VLAN, dirección IP y habilitación de puertos.
- Verificación de puertos, VLANs y tabla MAC con:
  ```bash
  show interfaces status
  show vlan brief
  show mac address-table
  ```
## 💻 Dispositivos conectados

Laptop 1, Laptop 2, Raspberry Pi y PC del laboratorio.
Asignación de direcciones IP estáticas en cada equipo (ip addr add / ipconfig).
Activación de interfaces y comprobación con ip link set ... up.

## 🌐 Pruebas de conectividad

- Verificación de comunicación entre todos los dispositivos usando ping 192.168.x.xxx
- Escaneo de red con nmap para detectar hosts activos y servicios.
- Transferencia de archivos entre equipos con:

  ```bash
  scp archivo.txt usuario@192.168.x.x:/home/usuario/
    ```

- Configuración del servicio ssh en los equipos Linux para la conexión remota.

## 💽 Punto 2 — Instalación de Máquinas Virtuales en QEMU/KVM

🛠️ Preparación
Instalación de herramientas de virtualización:
  ```bash
sudo apt install qemu-kvm libvirt-daemon-system libvirt-clients virtinst qemu-img
```
Creación de discos virtuales:
  ```bash
qemu-img create -f qcow2 images/ubuntu.qcow2 25G
```
 ## 🧩 Sistemas instalados

- Ubuntu Server – Instalación completa con red NAT y acceso SSH.
- CentOS Stream – Instalación con Anaconda, interfaz gráfica y configuración de servicios básicos.
- Alpine Linux – Instalación ligera mediante setup-alpine, con habilitación de SSH.
- Scientific Linux – Instalador basado en CentOS, configuración de red, usuarios y qemu-guest-agent.
- Cada máquina fue ejecutada con recursos ajustados (RAM, CPU, red VirtIO) y con imágenes en formato qcow2.

## 🧠 Conclusiones

- Se logró establecer comunicación entre múltiples dispositivos físicos a través del switch, aplicando comandos de red y diagnóstico.
- Se comprendió el uso de herramientas como ping, nmap, ifconfig, ip y scp para analizar y administrar redes locales.
- Se documentó el proceso de creación e instalación de máquinas virtuales en QEMU, comprendiendo los fundamentos de la virtualización y gestión de entornos Linux.
- El laboratorio integró conceptos de infraestructura física y virtual, fortaleciendo competencias en redes, sistemas operativos y administración de entornos de pruebas.


