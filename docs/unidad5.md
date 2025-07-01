# 🔐 Unidad Didáctica 5 — Redes TCP/IP y Seguridad Perimetral
![Firewall con reglas y tráfico monitorizado](img/red-tcpip-seguridad.png)

## ⏱️ Temporalización global  
- **Duración:** 24 h (14 sesiones) / 160 h  
  - **Lunes:** 2 h · **Martes:** 2 h · **Miércoles:** 1 h  
- **Bloque:** Redes y Seguridad  
- **Secuencia anual:** UT 5 / 6  

---  
> **Meta** · Diseñar, configurar y asegurar redes TCP/IP cableadas e inalámbricas aplicando políticas de seguridad perimetral y buenas prácticas de sostenibilidad.

## 🎯 ¿Qué vas a aprender?  
* Arquitectura y protocolos TCP/IP (IPv4 & IPv6).  
* Configuración estática y dinámica de interfaces de red.  
* Resolución de nombres, enrutamiento y diagnóstico.  
* Gestión de puertos, cortafuegos y detección de intrusos.  
* Diseño de VLAN y segmentación segura.  
* Monitorización y respuesta ante incidentes.

---  

## 🔎 ¿Qué haremos?  
* Simulaciones con **Packet Tracer** / **GNS3**.  
* Configuración real de routers, switches y firewalls (iptables/ufw, Windows Defender).  
* Análisis de tráfico con **Wireshark**.  
* Proyecto exprés: “Red segura de aula” con VPN, IDS y reglas de firewall.

---  

## 🎯 Criterios de evaluación y Resultados de aprendizaje

=== "RA5 — Conecta y asegura redes (avanzado)"
    - **CE 37.** Configura parámetros TCP/IP en distintos SO.  
    - **CE 38.** Gestiona tablas de enrutamiento y resolución de nombres.  
    - **CE 39.** Verifica conectividad y diagnostica incidencias.  
    - **CE 40.** Implementa segmentación VLAN y acceso remoto seguro.

=== "RA6 — Protege y monitoriza recursos de red"
    - **CE 41.** Aplica cortafuegos y sistemas IDS.  
    - **CE 42.** Monitoriza tráfico y genera informes de seguridad. :contentReference[oaicite:0]{index=0}

=== "RAT1-4 — Transversales"
    - **CE 55, 58, 61, 64.** Trabajo colaborativo, aprendizaje autónomo, ciberseguridad, sostenibilidad. :contentReference[oaicite:1]{index=1}

---  

## 📑 Competencias profesionales y para la empleabilidad  
- **a)** Configurar y explotar sistemas informáticos.  
- **b)** Aplicar técnicas y procedimientos de seguridad.  
- **o)** Elaborar y mantener documentación técnica.  
- **q)** Resolver contingencias con iniciativa y autonomía.  

---  

## 📏 ¿Cómo se evalúa?  
* **Prácticas guiadas** de red y seguridad.  
* **Cuestionarios AULES** sobre TCP/IP y hardening.  
* **Portafolio digital** con capturas, configs y scripts.  
* **Proyecto exprés** con defensa en vídeo.

---

## 🗂️ Planificación por actividades  

| # | Tipo | Actividad | RA / RAT · CE | Ses. | H |
|:-:|------|-----------|---------------|:---:|:-:|
| 1 | Intro | Kahoot “Cazando paquetes” | **RA5 · RAT2** → 37, 58 | 1 | 1 |
| 2 | Intro | Anatomía de TCP/IP con Wireshark | **RA5** → 37 | 2 | 2 |
| 3 | Intro | Laboratorio de direccionamiento IPv4/IPv6 | **RA5** → 38 | 3 | 2 |
| 4 | Des. | Configuración de clientes y diagnóstico (`ping`, `traceroute`) | **RA5** → 37, 39 | 4-5 | 3 |
| 5 | Des. | Routing estático y dinámico en Packet Tracer | **RA5** → 38 | 6 | 2 |
| 6 | Des. | Cortafuegos iptables/ufw y Windows Defender | **RA6** → 41 | 7-8 | 3 |
| 7 | Des. | IDS con Snort y alerta de intrusos | **RA6** → 41, 42 | 9-10 | 3 |
| 8 | Des. | Segmentación VLAN + ACL en switches | **RA5 · RA6** → 40, 41 | 11 | 2 |
| 9 | Ap. | Proyecto “Red segura de aula” (diseño + despliegue) | **RA5-6 · RAT1-4** | 12-13 | 4 |
|10 | Eval.| Test + checklist PRL + defensa proyecto | **RA5-6 · RAT1-4** | 14 | 2 |

*Las sesiones y horas son orientativas; pueden ajustarse según progreso.*

---
## 1. Introducción
Las redes TCP/IP sustentan la comunicación global. Dominar su configuración y la seguridad perimetral prepara al alumnado para prevenir amenazas frecuentes y garantizar la disponibilidad de los servicios. Esta unidad profundiza en protocolos, enrutamiento y defensas activas, afianzando competencias críticas en entornos profesionales de desarrollo web. :contentReference[oaicite:2]{index=2}

---

## 2. Objetivos didácticos
* Comprender el modelo y protocolos TCP/IP.  
* Configurar interfaces y parámetros de red en distintos SO.  
* Verificar conectividad y resolver problemas de red.  
* Gestionar puertos y tablas de enrutamiento.  
* Implementar cortafuegos e IDS básicos.  
* Documentar configuraciones y medidas de seguridad. :contentReference[oaicite:3]{index=3}

---

## 3. Contenidos
* Arquitecturas de red y TCP/IP.  
* Direccionamiento IPv4/IPv6, VLSM y subredes.  
* Configuración de clientes, ficheros de red y DNS.  
* Enrutamiento estático y dinámico (RIP/OSPF básico).  
* Gestión de puertos y servicios.  
* Cortafuegos (iptables/ufw, Windows Defender), NAT y PAT.  
* Sistemas IDS/IPS (Snort), registro y alertas.  
* Seguridad en redes cableadas e inalámbricas (WPA2/WPA3).  
* Monitorización de tráfico (Wireshark, Netstat).  
* Buenas prácticas de sostenibilidad (apagado de puertos, PoE). :contentReference[oaicite:4]{index=4}

---

## 4. Actividades y secuenciación
### Fase 1: Introducción y motivación (Sesiones 1 a 3)

#### 🧠 Sesión 1: ¿Qué circula por la red?
* **Actividad:** Quiz en Kahoot + captura de tráfico real con Wireshark.  
* **Implementación:**  
  1. Kahoot diagnóstico (15 preguntas).  
  2. Captura breve y análisis de cabeceras TCP/IP.  
  3. Compartimos hallazgos en Padlet.  
* **Criterios:** 37, 58 · **Instrumentos:** Kahoot, observación directa.

#### 🔍 Sesión 2: Raquetas de paquetes
* **Actividad:** Despiece del paquete IP con filtros Wireshark.  
* **Implementación:**  
  1. Filtros `ip.addr == x.x.x.x`.  
  2. Identificamos TTL, flags y checksum.  
  3. Debate sobre rutas y latencia.  
* **Criterios:** 37 · **Instrumentos:** Rúbrica de análisis, captura en portafolio.

#### 🌐 Sesión 3: Direccionamiento sin miedo
* **Actividad:** Taller de subredes IPv4 e introducción a IPv6 SLAAC.  
* **Implementación:**  
  1. Calculadora CIDR compartida (Excel 365).  
  2. Hoja de ejercicios con 5 casos de VLSM.  
  3. Configuración práctica en VM.  
* **Criterios:** 38 · **Instrumentos:** Ficha ejercicios, checklist CLI.

---

### Fase 2: Desarrollo (Sesiones 4 a 11)

* **Sesión 4-5:** Diagnóstico de conectividad (`ping`, `traceroute`, `nslookup`).  
* **Sesión 6:** Routing estático vs RIP, actualización y prueba.  
* **Sesión 7-8:** Cortafuegos: reglas NAT y filtrado por puertos/estado.  
* **Sesión 9-10:** IDS Snort + generación de alerta ante escaneo Nmap.  
* **Sesión 11:** VLAN y ACL para segmentar red de aula (admin vs alumnado).

---

### Fase 3: Aplicación y evaluación (Sesiones 12 a 14)

#### 🚀 Sesiones 12-13: Proyecto “Red segura de aula”
* **Objetivo:** Diseñar y desplegar red con VLAN, VPN y firewall.  
* **Roles:** network engineer, security lead, documenter.  
* **Entrega:** Diagrama, configs, log de IDS y vídeo 5 min.

#### 📝 Sesión 14: Evaluación final
* Test AULES (20 ítems), checklist PRL y defensa del proyecto.

---
## 5. Instrumentos de evaluación (resumen)

| Instrumento          | Evidencias                                   | Sesiones |
|----------------------|----------------------------------------------|:--------:|
| Observación directa  | Participación, PRL, roles                    | Todas    |
| Rúbricas prácticas   | TCP/IP, cortafuegos, IDS, VLAN               | 2-11     |
| Cuestionarios AULES  | Protocolos y seguridad de red                | 1, 6, 14 |
| Portafolio digital   | Markdown + capturas + configs                | 2-13     |
| Rúbrica de proyecto  | Diseño, implementación, seguridad, docu      | 12-13    |
| Auto/co-evaluación   | Reflexión individual y feedback de equipo    | 11, 14   |

## 🛠️ Ejemplos

### ✅ Checklist PRL · Laboratorio de red
| Ítem de seguridad | Sí | No | N/A |
|-------------------|:--:|:--:|:---:|
| Orden de cables y etiquetado correcto | □ | □ | □ |
| No se trabaja con tensión en dispositivos PoE | □ | □ | □ |
| Se documentan cambios en un registro de red | □ | □ | □ |
| Uso de cuentas sin privilegios root/admin | □ | □ | □ |
| Copias de configuración salvadas en Git before cambios | □ | □ | □ |

---

### 🗂️ Rúbrica · Configuración IPv4/IPv6  
| Criterio | Excelente (9-10) | Notable (7-8) | Aprobado (5-6) | Insuficiente (<5) |
|----------|------------------|---------------|----------------|-------------------|
| Subred / VLSM | Calcula y aplica subredes complejas sin error | ≤ 1 error menor | Errores conceptuales leves | Cálculo incorrecto |
| Configuración CLI | Interfaces activas y persistentes | Persistentes con 1 aviso | Config temporal | Interfaces sin configurar |
| Diagnóstico | `ping`, `traceroute`, `nslookup` sin fallos | 1 fallo menor | 2 fallos | Sin pruebas |
| Documentación | Capturas + tabla de subredes | Capturas parciales | Sólo comandos | Sin evidencias |

---

### 🔥 Rúbrica · Cortafuegos e IDS  
| Dimensión | Excelente (9-10) | Notable (7-8) | Aprobado (5-6) | Insuficiente (<5) |
|-----------|------------------|---------------|----------------|-------------------|
| Reglas firewall | Filtrado por estado + NAT + logging | 2 de 3 elementos | 1 elemento | Sin reglas |
| IDS Snort | Firma personalizada + alerta | Firma default + alerta | Firma default sin alerta | IDS inoperativo |
| Hardening VLAN/ACL | VLAN + ACL coherentes y probadas | VLAN sin ACL o viceversa | Config parcial | Sin segmentación |
| Evidencias | Logs + capturas | Logs sin capturas | Capturas sin logs | Sin evidencias |

---

### 🚀 Rúbrica · Proyecto “Red segura de aula”
| Área | Peso | Excelente (9-10) | Notable (7-8) | Aprobado (5-6) | Insuficiente (<5) |
|------|:---:|------------------|---------------|----------------|-------------------|
| Diseño de red | 20 % | Diagrama claro y escalable | Diagrama completo | Diagrama básico | Incompleto |
| Implementación | 25 % | VLAN, VPN, IDS, FW operativos | 3 de 4 operativos | 2 de 4 | ≤ 1 operativo |
| Seguridad | 20 % | Sin vulnerabilidades críticas | 1 vulnerabilidad leve | 2 vulnerabilidades | > 2 críticas |
| Sostenibilidad | 15 % | Puertos PoE y ahorro energía | 2 medidas | 1 medida | 0 medidas |
| Documentación | 20 % | Markdown + vídeo + Git | Markdown completo | Markdown parcial | Sin docu |

---

### 🎯 Cuestionario AULES · TCP/IP & Seguridad  
*(Banco autogenerado de 25 ítems — muestra)*  
1. **¿Qué campo del encabezado IPv4 indica la prioridad de entrega?**  
2. Empareja *OSI capa 3*, *TCP puerto 443*, *DNS A* con su función.  
3. **Respuesta breve:** Ventajas de VLAN frente a subredes físicas.  
4. *Arrastra y suelta:* Ordena el flujo de filtrado iptables (PREROUTING → … ).  
5. **Hotspot:** Identifica en la captura de Snort la dirección IP atacante.

---

### 📂 Portafolio digital · Lista de cotejo
- [ ] Carpeta `ud5/` en OneDrive clase  
- [ ] Capturas Wireshark y CLI numeradas (≥ 10)  
- [ ] Configs (`*.cfg`, `iptables.rules`) en repo Git  
- [ ] Fichero `README.md` con topología y reglas  
- [ ] Vídeo demo ≤ 4 min enlazado  

---

**¡Puertos asegurados, tráfico bajo control!** 🚦
