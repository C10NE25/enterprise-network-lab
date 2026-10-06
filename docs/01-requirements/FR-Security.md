### Que medidas de seguridad debe tener?

## Outbond
- El firewall OPNsense debe aplicar una politica de denegacion implicita bloqueando todo el trafico entre VLANs por defecto, salvo aquel que este explicitamente permitido mediante reglas.

- El firewall debe denegar todo trafico iniciado desde la VLAN Users hacia la VLAN management, permitiendo unicamente el trafico de salida hacia el internet y hacia servicios especificos de la VLAN servers (DNS, HTTPS, DHCP).

- El firewall debe bloquear el trafico iniciado desde la subred Management hacia la VLAN users

## Inbound
- El firewall debe permitir el acceso a las interfaces de administracion unicamente desde la VLAN Management.

- El firewall OPNsense debe permitir el trafico iniciado desde la subred Users hacia la IP del servidor web en la VLAN servers, unicamente a traves del puerto TCP 443 (HTTPS)

- El firewall debe permitir el trafico iniciado desde la subred Management hacia la VLAN server a traves del puerto TCP 443 y SSH 22. 

- El firewall debe permitir el trafico DHCP relay iniciado desde la interfaz VLAN Users hacia la IP del servidor DHCP en la VLAN server exclusivamente a traves del puerto UDP 67 y 68.

- 