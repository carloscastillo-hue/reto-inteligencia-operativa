# 🚀 Solución Inteligente de Inteligencia Operativa y Despacho – Ecosistema Movilidad

## 1. Problema y Objetivo de Negocio (KPIs)
El ecosistema de Movilidad enfrenta cuellos de botella en la asignación de asistencias y gestión operativa, generando altos tiempos de espera y sobrecostos por asignaciones subóptimas de aliados.

* **KPI Principal 1:** Reducir el tiempo promedio de asignación y arribo (ETA) en un **20% - 25%**.
* **KPI Principal 2:** Disminuir el costo medio por servicio (severidad operativa) en un **15%** mediante optimización geoespacial y control de tarifas.
* **KPI Principal 3:** Reducir errores de cobertura y reprocesos manuales a **< 2%**.

---

## 2. Arquitectura de la Solución (Enfoque Híbrido)
Combinamos analítica geoespacial y modelos determinísticos para cálculos numéricos/rutas, junto con IA Generativa (RAG + Tool Calling) para comprensión de lenguaje natural y consulta segura de reglas de negocio.

```mermaid
flowchart TD
    A[Cliente / Canal Digital / Voz] -->|Reporte no estructurado| B(Triaje IA: LLM Ligero + JSON Estricto)
    B -->|Extracción: Placa, Falla, GPS| C{Motor de Decisión Híbrido}
    C -->|Consulta Metadatos Póliza/Tarifas| D[(Base Vectorial - RAG Manuales PDF)]
    C -->|Tool Calling Seguro / API| E[(Base Transaccional SQL - Aliados y Disponibilidad)]
    C -->|Cálculo Distancia / Tráfico / Scoring| F[Motor Geoespacial y ML]
    F --> G{¿Cumple Umbral de Riesgo y Costo?}
    G -->|Sí - Alta Confianza| H[Asignación Automática + Notificación Aliado]
    G -->|No - Excepción / Alto Monto| I[Human-in-the-Loop: Validación Operador]
    H & I --> J[Tablero de Observabilidad: Latencia, Costo Tokens, SLA]
