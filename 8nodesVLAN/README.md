
# Proyecto: Red LAN de 8 Nodos (Hubs y Bridge)
Este proyecto simula una topología de red LAN clásica utilizando **Cisco Packet Tracer**. La red está diseñada para demostrar cómo se pueden interconectar segmentos de red físicos utilizando dispositivos de Capa 1 (Hubs) y Capa 2 (Bridges).

El objetivo es construir una red funcional de 8 computadoras y probar la conectividad completa a través de los dispositivos de interconexión.

## 🛠️ Topología y Componentes

La arquitectura de la red consta de los siguientes componentes:

* **Nodos:** 8x Computadoras (PC)
* **Segmentos de Red:** 2x Hubs (Hub0 y Hub1)
* **Interconexión:** 1x Bridge (Bridge0)

La topología está dividida en dos segmentos:
1.  **Segmento 1:** 4 PCs conectadas al `Hub0`.
2.  **Segmento 2:** 4 PCs conectadas al `Hub1`.
3.  **Unión:** El `Bridge0` se utiliza para interconectar el `Hub0` y el `Hub1`, uniendo los dos segmentos.

## 🔧 Configuración de Red

Toda la red opera en una única subred, permitiendo que todos los dispositivos se comuniquen.

* **Esquema IP:** Se utiliza la red `193.164.0.0`.
* **Asignación:** Las 8 computadoras tienen direcciones IP estáticas, que van desde `193.164.0.1` hasta `193.164.0.8`.

## 📊 Pruebas de Conectividad (Resultados)

Se realizaron pruebas de `ping` desde un nodo a todas las demás computadoras de la red para verificar la conectividad.

**Resultado:** Todas las pruebas de ping fueron **100% exitosas**, sin pérdida de paquetes (0% loss). Esto confirma que el Bridge está reenviando correctamente el tráfico entre los dos segmentos de Hub.

## 🎓 Conceptos Clave Demostrados

Este proyecto ilustra dos conceptos fundamentales de las redes:

1.  **Hub (Concentrador):** Es un dispositivo de Capa 1. Cualquier dato que recibe por un puerto, lo repite y envía a *todos* los demás puertos, creando un gran dominio de colisión.
2.  **Bridge (Puente):** Es un dispositivo de Capa 2. A diferencia del hub, el bridge es "inteligente" y solo reenvía el tráfico si el destino está en el otro segmento. Su función principal aquí es **separar los dos dominios de colisión**, lo que reduce el tráfico innecesario y mejora el rendimiento.
