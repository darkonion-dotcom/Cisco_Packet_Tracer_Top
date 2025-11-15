
# Proyecto: Red LAN de 6 Nodos (3 Segmentos)
Este proyecto simula una topología de red LAN más compleja, diseñada en **Cisco Packet Tracer**. La red se compone de **seis computadoras** distribuidas en **tres grupos** o segmentos físicos.
El objetivo es demostrar cómo se pueden interconectar múltiples segmentos de red en una "cadena" utilizando una combinación de Hubs (Capa 1) y Bridges (Capa 2), y probar la conectividad de extremo a extremo.

## 🛠️ Topología y Componentes

La arquitectura de la red está estructurada como una cadena y consta de los siguientes componentes:

* **Nodos:** 6x Computadoras (PC)
* **Segmentos de Red:** 3x Hubs (Hub0, Hub1, Hub2)
* **Interconexión:** 2x Bridges (Bridge0, Bridge1)

La topología está dividida en tres segmentos:
1.  **Segmento 1:** 2 PCs conectadas al `Hub0`.
2.  **Segmento 2:** 2 PCs conectadas al `Hub1`.
3.  **Segmento 3:** 2 PCs conectadas al `Hub2`.

La interconexión se realiza de la siguiente manera: `Hub0` se conecta a `Bridge0`, `Bridge0` se conecta a `Hub1`, `Hub1` se conecta a `Bridge1`, y `Bridge1` se conecta a `Hub2`.

## 🔧 Configuración de Red

Toda la red opera en una única subred, permitiendo que todos los dispositivos se comuniquen sin necesidad de enrutamiento.

* **Esquema IP:** Se utiliza la red `195.175.0.0`.
* **Asignación:** Las 6 computadoras tienen direcciones IP estáticas (de `195.175.0.1` a `195.175.0.6`).

## 📊 Pruebas de Conectividad (Resultados)

Se realizaron pruebas de `ping` a todas las computadoras de la red.

* **Resultado:** La conectividad fue exitosa en la gran mayoría de las pruebas, con la mayoría de los pings mostrando 0% de pérdida de paquetes.
* **Observación Clave:** Se observó una **pérdida de paquetes del 25%** (1 de 4 paquetes) al hacer ping a `195.175.0.2`. Esto es un comportamiento **normal y esperado** en una red con bridges. El primer paquete (`Request timed out`) se pierde mientras los bridges "aprenden" la ruta y actualizan sus tablas de direcciones MAC. Una vez que el camino es aprendido, los paquetes restantes se entregan exitosamente.

## 🎓 Conceptos Clave Demostrados

Este proyecto expande los conceptos del proyecto anterior:

1.  **Hub (Concentrador):** Dispositivo de Capa 1 que crea un dominio de colisión.
2.  **Bridge (Puente):** Dispositivo de Capa 2 que reenvía tráfico basado en direcciones MAC.
3.  **Segmentación de Red (Dominios de Colisión):** El concepto más importante aquí. Al usar dos bridges para conectar tres hubs, la red se divide eficazmente en **tres dominios de colisión separados**. Esto significa que una colisión de tráfico en el `Hub0` no afectará a los dispositivos en `Hub1` o `Hub2`, mejorando significativamente la eficiencia y el rendimiento de la red.
