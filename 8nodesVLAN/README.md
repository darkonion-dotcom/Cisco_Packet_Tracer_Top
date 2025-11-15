# Proyecto: Red LAN de 8 Nodos (Hubs y Bridge)

## 📖 Resumen del Proyecto

[cite_start]Este proyecto simula una topología de red LAN clásica utilizando **Cisco Packet Tracer**[cite: 493]. La red está diseñada para demostrar cómo se pueden interconectar segmentos de red físicos utilizando dispositivos de Capa 1 (Hubs) y Capa 2 (Bridges).

El objetivo es construir una red funcional de 8 computadoras y probar la conectividad completa a través de los dispositivos de interconexión.

## 🛠️ Topología y Componentes

[cite_start]La arquitectura de la red consta de los siguientes componentes[cite: 493, 561]:

* **Software:** Cisco Packet Tracer
* **Nodos:** 8x Computadoras (PC)
* **Segmentos de Red:** 2x Hubs (Hub0 y Hub1)
* **Interconexión:** 1x Bridge (Bridge0)

La topología está dividida en dos segmentos:
1.  [cite_start]**Segmento 1:** 4 PCs conectadas al `Hub0`[cite: 562, 565].
2.  [cite_start]**Segmento 2:** 4 PCs conectadas al `Hub1`[cite: 562, 573].
3.  [cite_start]**Unión:** El `Bridge0` se utiliza para interconectar el `Hub0` y el `Hub1`, uniendo los dos segmentos[cite: 561, 572].


## 🔧 Configuración de Red

Toda la red opera en una única subred, permitiendo que todos los dispositivos se comuniquen en el mismo dominio de broadcast.

* **Esquema IP:** Se utiliza la red `193.164.0.0`.
* [cite_start]**Asignación:** Las 8 computadoras tienen direcciones IP estáticas, que van desde `193.164.0.1` hasta `193.164.0.8`[cite: 494, 503, 509, 515, 522, 532, 546, 555].

## 📊 Pruebas de Conectividad (Resultados)

[cite_start]Se realizaron pruebas de `ping` desde un nodo a todas las demás computadoras de la red para verificar la conectividad[cite: 495, 504, 510, 516, 523, 533, 547, 556].

[cite_start]**Resultado:** Todas las pruebas de ping fueron **100% exitosas**, sin pérdida de paquetes (0% loss)[cite: 502, 507, 514, 521, 529, 541, 552, 559]. Esto confirma que el Bridge está reenviando correctamente el tráfico entre los dos segmentos de Hub.

## 🎓 Conceptos Clave Demostrados

Este proyecto ilustra dos conceptos fundamentales de las redes:

1.  [cite_start]**Hub (Concentrador):** Es un dispositivo de Capa 1. Cualquier dato que recibe por un puerto, lo repite y envía a *todos* los demás puertos[cite: 562]. Esto crea un gran **dominio de colisión**, lo que significa que si dos PCs en el mismo hub intentan "hablar" a la vez, se produce una colisión.
2.  **Bridge (Puente):** Es un dispositivo de Capa 2. A diferencia del hub, el bridge es "inteligente" y examina las direcciones MAC. Aprende qué dispositivos están en cada uno de sus puertos (segmentos) y solo reenvía el tráfico si el destino está en el otro segmento. Su función principal aquí es **separar los dos dominios de colisión**, lo que reduce el tráfico innecesario y mejora el rendimiento de la red.
