
# Proyecto: Red LAN con Router (Topología Router-on-a-Stick)
Este proyecto, simulado en **Cisco Packet Tracer**, muestra una topología de red LAN fundamental conocida como "Router-on-a-Stick". En esta configuración, múltiples dispositivos de usuario final (PCs) y un router se conectan a un mismo switch central.
El objetivo de esta simulación es construir la base física para una red que *podría* ser segmentada en VLANs, aunque en esta configuración inicial, todos los dispositivos operan en una sola red LAN.

## 🛠️ Topología y Componentes

La arquitectura de la red consta de los siguientes componentes:

* **Software:** Cisco Packet Tracer
* **Nodos:** 3x Computadoras (PC0, PC1, PC2)
* **Red:** 1x Switch (Switch0)
* **Enrutamiento:** 1x Router (Router0)

Todos los dispositivos están conectados al `Switch0`, que actúa como el punto central de la red.

## 🔧 Configuración de Red (Según las imágenes)

En esta configuración, todos los dispositivos están en una única subred, lo que permite la comunicación directa a través del switch.

* **Esquema IP:** Se utiliza la red `10.0.0.0` con una máscara de `255.0.0.0` (una red /8).
* **Configuración de PCs:**
    * **PC0:** `10.10.0.2`
    * **PC1:** `10.10.0.3`
    * **PC2:** `10.10.0.4`
* **Configuración del Switch:** Los puertos del switch están en la configuración por defecto (modo `Access` en `VLAN 1`), permitiendo que todos los dispositivos se comuniquen entre sí.

## 🎓 Conceptos Clave Demostrados

1.  **LAN Simple (Red Única):** Dado que todas las PCs están en la misma subred (`10.0.0.0 /8`), pueden comunicarse directamente entre ellas a través del `Switch0` sin necesidad de un router.
2.  **Topología "Router-on-a-Stick":** Este es el concepto más importante. La *disposición física* de la red (múltiples PCs y un solo router conectados a un switch) es la base para una de las técnicas de red más comunes: **Enrutamiento Inter-VLAN**.
3.  **Siguiente Paso Lógico:** Aunque esta red funciona como una sola LAN, el siguiente paso para este proyecto sería crear múltiples VLANs en el switch (ej. una para cada PC) y luego configurar el `Router0` con sub-interfaces para que actúe como "puerta de enlace" y permita que las diferentes VLANs se comuniquen entre sí.
