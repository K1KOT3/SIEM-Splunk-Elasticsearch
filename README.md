# Implementación de SIEM con Splunk y Elasticsearch

📊 **Monitorización y análisis de eventos de seguridad en múltiples plataformas con SIEM**  

Este repositorio contiene el informe del **Laboratorio de SIEM**, donde se han desplegado y configurado **Splunk y Elasticsearch** para la recolección, análisis y visualización de eventos de seguridad en sistemas Linux y Windows.

## 🔍 Descripción

El objetivo de este laboratorio es aprender a utilizar **Splunk y Elasticsearch** como herramientas SIEM para la monitorización en tiempo real de eventos de seguridad, incluyendo:
- **Captura de eventos de inicio de sesión y actividad sospechosa** en Windows y Linux.
- **Configuración de Splunk Forwarders** para enviar logs de diferentes sistemas al SIEM.
- **Creación de reglas en Snort para detectar accesos no autorizados** y visualizar alertas en Splunk.
- **Despliegue de un entorno ELK (Elasticsearch, Logstash, Kibana, Filebeat)** para análisis avanzado de eventos.

## 📁 Contenido del Repositorio

- `SIEM_SPLUNK_EnriqueGarciaCuadradoCarlosGarridoJunco.pdf` → Informe completo con configuración y pruebas.
- **Dashboards y queries de visualización** (próximamente).

## 🛠 Herramientas Utilizadas

### 🔹 **Configuración de Splunk**
- **Instalación en ZorinOS y Ubuntu** (`dpkg -i splunk.deb`).
- **Implementación de Splunk Universal Forwarder** en Windows para envío de logs.
- **Configuración de Snort con Splunk**:
  - **Regla para detectar conexiones SSH no autorizadas**.
  - **Integración con Splunk Forwarder para envío de alertas**.
- **Visualización de eventos de inicio de sesión exitosos y fallidos** (`EventCode 4624 / 4625` en Windows).

### 🔹 **Despliegue de Elasticsearch y Kibana**
- **Instalación de Elasticsearch, Logstash y Kibana (ELK)** en Linux.
- **Configuración de Filebeat** para capturar logs y enviarlos a Elasticsearch.
- **Visualización de datos en Kibana**:
  - Análisis de eventos de seguridad en servidores y estaciones de trabajo.
  - Gráficos de conexiones por IP y método de autenticación.

### 🔹 **Consultas y Dashboards**
- **Filtros en Splunk**:
  - `index=main source="/var/log/auth.log" | stats count by user status`
- **Visualizaciones en Kibana**:
  - Evolución de eventos de inicio de sesión.
  - Distribución de logs por sistema operativo y usuario.
  - Identificación de picos de actividad sospechosa.

## 🚀 Resultados y Hallazgos

| Evento Detectado  | Plataforma | Acción Realizada |
|------------------|------------|------------------|
| **Inicio de sesión SSH no autorizado** | Splunk + Snort | Alerta generada en Splunk |
| **Eventos de login exitoso y fallido** | Windows + Linux | Visualización en Splunk y Kibana |
| **Monitoreo de tráfico en Snort** | Snort | Registro de intentos de conexión sospechosos |
| **Análisis de logs en Elasticsearch** | Kibana | Dashboards con actividad en tiempo real |

📊 **Conclusión:**  
- **Splunk es ideal para la monitorización centralizada en tiempo real**, mientras que **Elasticsearch permite un análisis más flexible y visualización avanzada de logs**.
- La combinación de **Snort + Splunk** proporciona un entorno robusto de **detección y respuesta ante incidentes**.
- **Habilitar autenticación y cifrado en Elasticsearch mejora la seguridad** del entorno SIEM.

## 📌 Posibles Mejoras

- **Automatización del despliegue de SIEM** con Ansible y Docker.
- **Integración con herramientas de threat intelligence** para correlación de eventos con bases de datos de amenazas.
- **Implementación de reglas de detección avanzadas** en Suricata y Snort.
- **Mejoras en seguridad de Elasticsearch** (TLS y autenticación de usuarios).

## 🤝 Contribuciones

Si deseas mejorar este análisis, agregar nuevas reglas de detección o optimizar la configuración del SIEM, haz un **fork**, añade tus cambios y envía un **Pull Request**.

## 📜 Licencia

Este proyecto se distribuye bajo la licencia **MIT**. Consulta el archivo `LICENSE` para más detalles.
