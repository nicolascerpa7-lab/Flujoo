flowchart TB
    subgraph INGRESO["🔵 1. INGRESO DE SOLICITUD"]
        direction TB
        A1["👤 CLIENTE<br/>• RUT empresa<br/>• Tipo flota<br/>• Cantidad unidades<br/>• Historial siniestros 3-5 años<br/>• Rutas y zonas riesgo<br/>• Controles internos"]
        A2["📋 CORREDOR<br/>• Solicitud formal<br/>• Cuadro comparativo flota<br/>• Análisis siniestralidad<br/>• Propuesta deducibles"]
        A3["🏢 EJECUTIVO COMERCIAL<br/>• Ingreso al sistema<br/>• Crea reserva/oportunidad<br/>• Revisa otros ramos<br/>• Pre-chequeo reglas"]
        
        A1 --> A2 --> A3
    end

    subgraph SUSCRIPCION["🔵 2. PROCESO DE SUSCRIPCIÓN"]
        direction TB
        B1["📝 RESERVA<br/>Bloquea cliente en compañía"]
        B2["🔍 REVISIÓN TÉCNICA<br/>Suscriptor técnico valida"]
        
        subgraph ANALISIS["Análisis del Suscriptor"]
            direction LR
            C1["📊 Info Flota<br/>• Antigüedad<br/>• Tipología<br/>• GPS/Telemetría<br/>• Propios vs Leasing"]
            C2["📈 Siniestralidad<br/>• Frecuencia<br/>• Severidad<br/>• PT vs Parciales<br/>• Tendencias"]
            C3["⚠️ Riesgo Operacional<br/>• Tipo carga<br/>• Zonas críticas<br/>• Rutas<br/>• Conductores"]
            C4["🎭 Riesgo Moral<br/>• Estabilidad<br/>• Fraude<br/>• Conducta pago"]
        end
        
        B1 --> B2 --> ANALISIS
    end

    subgraph CONDICIONES["🔵 3. DETERMINACIÓN CONDICIONES"]
        direction TB
        D1["💰 TASA Y PARÁMETROS<br/>• Tasa base por tipo<br/>• Sobretasas<br/>• Rebajas GPS/Telemetría<br/>• Deducibles diferenciados"]
        D2["📜 CLÁUSULAS<br/>• Desgaste y deterioro<br/>• Accesorios especiales<br/>• Sin depreciación<br/>• Lucro cesante<br/>• GPS obligatorio"]
        D3["🚛 REGLAS CAMIONES<br/>• Segmentar PT/Parciales<br/>• Ajustar deducibles<br/>• GPS homologado"]
        
        D1 --> D2 --> D3
    end

    subgraph APROBACION["🔵 4. APROBACIÓN Y EMISIÓN"]
        direction TB
        E1["✅ CIERRE TÉCNICO<br/>• Condiciones finales<br/>• Exclusiones<br/>• Tasa efectiva"]
        E2["🤝 VALIDACIÓN COMERCIAL<br/>• Alinear condiciones<br/>• Vigencia<br/>• Descuentos volumen<br/>• Forma de pago"]
        E3["📄 EMISIÓN<br/>• Pólizas individuales/flotante<br/>• Carga masiva flota<br/>• Beneficiarios/Leasing<br/>• Envío digital"]
        
        E1 --> E2 --> E3
    end

    subgraph SINIESTROS["🔵 5. MANEJO DE SINIESTROS"]
        direction TB
        F1["🚨 INGRESO SINIESTRO<br/>• Fecha, lugar<br/>• Parte policial<br/>• Conductor<br/>• Detalles carga"]
        
        F2["🔧 PÉRDIDA PARCIAL<br/>• Liquidador interno<br/>• Inspección<br/>• Presupuesto<br/>• Autoriza reparación<br/>• Gestiona deducible"]
        
        F3["💥 PÉRDIDA TOTAL<br/>• Área PT Camiones<br/>• Valor comercial/convenido<br/>• Revisión documentos<br/>• Pago siniestro<br/>• Recuperos/Subasta"]
        
        F1 --> F2
        F1 --> F3
    end

    subgraph POSVENTA["🔵 7. GESTIÓN FLOTA"]
        direction TB
        G1["👨‍💼 GESTOR DE FLOTA<br/>• Altas y bajas<br/>• Actualiza valores<br/>• Monitorea siniestralidad<br/>• Medidas mitigación<br/>• Inspecciones periódicas<br/>• Reportes trimestrales"]
    end

    INGRESO --> SUSCRIPCION
    SUSCRIPCION --> CONDICIONES
    CONDICIONES --> APROBACION
    APROBACION --> SINIESTROS
    APROBACION --> POSVENTA
    SINIESTROS --> POSVENTA
