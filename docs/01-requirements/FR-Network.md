### Como deberia funcionar la red?

- OPNsense debe actuar como el Default Gateway Layer 3 para las subredes de las VLANs de Managment, Users y Servers, enrutando el trafico entre ellas segun la topologia.

- OPNsense debe aplicar traduccion de direcciones de salida en su interfaz WAN para ocultar las IP privadas internas y traducirlas a la IP publica al acceder a Internet.

- El puente de red br0 debe transportar el trafico de las VLANs etiquetadas (802.1Q) hacia el router OPNsense a traves de un enlace troncal virtual.

- El puente br0 debe aislar los dominios de difusion mediante el filtrado de VLANs, garantizando que el trafico ARP o de difusion de un segmento no sea visible para los demas.

- OPNsense debe actuar como un Agente DHCP Relay en la VLAN de Users, esuchando las peticiones de difusion de los clientes y retransmitiendo mediante paquetes unicast hacia la direccion IP del contenedor DHCP en el servidor RHEL.

- El puente br0 debe asociar la interfaz virtual de cada maquina virtual a su ID de VLAN correspondiente etiquetando o desetiquetando el trafico de acceso segun corresponda al entrar o salir de la VM.