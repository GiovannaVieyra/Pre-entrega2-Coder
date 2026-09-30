# Mi primer laboratorio seguro de ciberseguridad

Reporte técnico de configuración de una máquina virtual (Ubuntu Server) en VirtualBox, aplicando prácticas básicas de hardening.

## 1. La Fundación: VirtualBox y Red Aislada

![Red NAT](Red%20NAT.png)

Configuré el adaptador de red en modo **NAT**. Con NAT, la VM sale a internet a través de mi máquina real (host), pero no es visible como un dispositivo independiente en la red local. Esto protege mi Host porque la VM queda aislada de la red de mi casa/oficina, a diferencia del modo Bridge, que expondría la VM directamente en el Wi-Fi.

## 2. Capa Windows/Linux: Usuarios y Actualizaciones

![Usuario estándar](Usuario%20estándar.png)
![Usuario estándar - Welcome](Usuario%20estándar%20-%20Welcome.png)

Creé un usuario (`vboxuser`) sin privilegios de administrador para usar en las prácticas, en vez de trabajar como root/admin todo el tiempo. Esto reduce el riesgo de que un error o una herramienta maliciosa dañe el sistema completo.

## 3. Capa Linux: Permisos y Gestión

![Permisos y actualizaciones](Permisos%20y%20actualizaciones.png)

Usé `ls -l` para ver los permisos del archivo creado, y `sudo apt update` para buscar actualizaciones de paquetes disponibles. Mantener el sistema actualizado cierra vulnerabilidades conocidas.

## 4. La Red de Seguridad: Snapshot Inicial

![Snapshot](Snapshot.png)

Creé un snapshot llamado **"Clean Install - Hardening applied"** una vez aplicadas las configuraciones básicas de seguridad. Esto permite volver a este estado limpio si algo sale mal más adelante.
