flowchart TB
    subgraph INGRESO["1. INGRESO DE SOLICITUD"]
        direction TB
        A1["CLIENTE"]
        A2["CORREDOR"]
        A3["EJECUTIVO COMERCIAL"]
        A1 --> A2 --> A3
    end

    subgraph SUSCRIPCION["2. PROCESO DE SUSCRIPCION"]
        direction TB
        B1["RESERVA"]
        B2["REVISION TECNICA"]
        B3["ANALISIS FLOTA"]
        B4["ANALISIS SINIESTRALIDAD"]
        B5["RIESGO OPERACIONAL"]
        B6["RIESGO MORAL"]
        B1 --> B2
        B2 --> B3
        B2 --> B4
        B2 --> B5
        B2 --> B6
    end

    subgraph CONDICIONES["3. DETERMINACION CONDICIONES"]
        direction TB
        C1["TASA Y PARAMETROS"]
        C2["CLAUSULAS"]
        C3["REGLAS CAMIONES"]
        C1 --> C2 --> C3
    end

    subgraph APROBACION["4. APROBACION Y EMISION"]
        direction TB
        D1["CIERRE TECNICO"]
        D2["VALIDACION COMERCIAL"]
        D3["EMISION POLIZA"]
        D1 --> D2 --> D3
    end

    subgraph SINIESTROS["5. MANEJO SINIESTROS"]
        direction TB
        E1["INGRESO SINIESTRO"]
        E2["PERDIDA PARCIAL"]
        E3["PERDIDA TOTAL"]
        E1 --> E2
        E1 --> E3
    end

    subgraph POSVENTA["6. GESTION FLOTA"]
        direction TB
        F1["GESTOR DE FLOTA"]
    end

    INGRESO --> SUSCRIPCION
    SUSCRIPCION --> CONDICIONES
    CONDICIONES --> APROBACION
    APROBACION --> SINIESTROS
    APROBACION --> POSVENTA
