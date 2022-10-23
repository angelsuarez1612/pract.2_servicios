# Práctica: Práctica: Protocolo DHCP
## Descripción:
Vamos a continuar trabajando en el escenario que desarrollamos en la Práctica: Creación y configuración de un escenario router-nat.

Para evitar los problemas que nos puede causar vagrant a la hora de trabajar con el DHCP (los clientes tendrían dos servidores DHCP, el que estamos configurando y el de la red de mantenimiento por eth0), os sugiero:

    Que montéis el mismo escenario pero en kvm/libvirt, en relación a las redes:
        No tendríamos la interfaz conectada a la red de mantenimiento de vagrant.
        Conectaríamos las máquinas a una red aislada sin dhcp (con IP estática) que utilizaríamos para configurar las máquinas por ansible. Esto soluciona el problema de que las direcciones IP cambien en vagrant y tengamos que cambiar el inventario cada vez que creemos el escenario.
    Ejecutamos el playbook de la práctica anterior y comprobamos que las máquinas tienen el funcionamiento esperado.

A partir de esta configuración podríamos seguir con esta práctica.

Queremos instalar un servidor DHCP en la máquina router para que configure de forma automática las máquinas que se conectan en la red interna. Tenemos que tener en cuenta lo siguiente:

    La máquina cliente de la práctica anterior, que tiene instalado el servidor web, debe tener la misma IP que la que le asígnate estáticamente, por lo tanto haremos una reserva para que tenga la misma IP.
    Al añadir una nueva máquina a la red local (recuerda que no se le instalará el servidor web) se configurará de forma dinámica.
    Crea un nuevo rol en el playbook de ansible llamado dhcp que configure el servidor DHCP de forma correcta. Quizás sea necesario modificar el comportamiento de algún rol de la práctica anterior.
    Todos los parámetros que reparta el servidor DHCP, así como cualquier otro dato, por ejemplo la dirección MAC del cliente se guardarán en variables.
    Añade una nueva máquina al escenario conectada a la red interna muy aislada. Vuelve a ejecutar el playbook y comprueba que todo funciona de forma correcta.



