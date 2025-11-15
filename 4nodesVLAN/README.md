

# Proyecto: Red LAN Simple de 4 Nodos (Hub)
Este proyecto es una simulación fundamental realizada en **Cisco Packet Tracer**. Presenta una de las topologías de red más básicas: una red LAN simple (en topología de estrella) donde cuatro computadoras están conectadas a un único concentrador (Hub) central.
El objetivo es demostrar la conectividad total en una red física simple y verificar la comunicación entre todos los nodos.

## 🛠️ Topología y Componentes

La arquitectura de la red es una topología de estrella centralizada en el Hub.

* **Software:** Cisco Packet Tracer
* **Nodos:** 4x Computadoras (PC0, PC1, PC2, PC3)
* **Interconexión:** 1x Hub (Hub0)
* **Cables:** Se utilizaron cables de cobre directos (Copper Straight-Through) para conectar cada PC al Hub.

## 🔧 Configuración de Red

La configuración de red es simple, con todos los dispositivos en la misma subred.

* **Esquema IP:** Se utilizó un direccionamiento de red privada de Clase B, en el rango `172.152.1.0`.
* **Asignación:** Se asignó una dirección IP estática a cada una de las cuatro computadoras, desde `172.152.1.1` hasta `172.152.1.4`.

## 📊 Pruebas de Conectividad (Resultados)

Se utilizó el comando `ping` desde un nodo a todos los demás para comprobar la comunicación.

* **Resultado:** Las pruebas fueron **100% exitosas**. Todas las computadoras pudieron comunicarse entre sí sin ninguna pérdida de paquetes (4 enviados, 4 recibidos, 0% de pérdida).

## 🎓 Conceptos Clave Demostrados

Este proyecto ilustra el funcionamiento de los dispositivos de Capa 1 más básicos:

1.  **Hub (Concentrador):** Es un dispositivo "no inteligente" de Capa 1. Actúa como un repetidor: cualquier señal eléctrica (datos) que recibe por un puerto, la repite y la reenvía a *todos los demás puertos* de la red.
2.  **Dominio de Colisión Único:** Debido a que el Hub reenvía todo a todos, esta topología crea un **único dominio de colisión**. Si PC0 y PC1 intentan enviar datos exactamente al mismo tiempo, se producirá una colisión que afectará a toda la red. Esta es la principal desventaja de los Hubs en comparación con los Switches.
