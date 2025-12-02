# Flujo de Suscripcion de Vehiculos - Flotas

## Diagrama General del Proceso

```mermaid
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
```

## Detalle por Etapa

### 1. Ingreso de Solicitud

| Actor | Informacion |
|-------|-------------|
| Cliente | RUT empresa, Tipo flota, Cantidad unidades, Historial siniestros 3-5 anos, Rutas y zonas riesgo, Controles internos |
| Corredor | Solicitud formal, Cuadro comparativo flota, Analisis siniestralidad, Propuesta deducibles |
| Ejecutivo Comercial | Ingreso al sistema, Crea reserva, Revisa otros ramos, Pre-chequeo reglas |

### 2. Analisis del Suscriptor

| Tipo Analisis | Elementos |
|---------------|-----------|
| Info Flota | Antiguedad, Tipologia, GPS y Telemetria, Propios vs Leasing |
| Siniestralidad | Frecuencia, Severidad, PT vs Parciales, Tendencias |
| Riesgo Operacional | Tipo carga, Zonas criticas, Rutas, Conductores |
| Riesgo Moral | Estabilidad, Fraude, Conducta pago |

## Flujo de Siniestros

```mermaid
flowchart LR
    A["SINIESTRO REPORTADO"] --> B{"Evaluar dano"}
    B -->|"Menor 75%"| C["PERDIDA PARCIAL"]
    B -->|"Mayor 75%"| D["PERDIDA TOTAL"]
    
    C --> C1["Inspeccion"]
    C1 --> C2["Presupuesto"]
    C2 --> C3["Reparacion"]
    C3 --> C4["Cobro deducible"]
    
    D --> D1["Confirmacion PT"]
    D1 --> D2["Tasacion"]
    D2 --> D3["Pago asegurado"]
    D3 --> D4["Recupero"]
```

## KPIs de Suscripcion

| Metrica | Formula | Valor Aceptable |
|---------|---------|-----------------|
| Frecuencia | Siniestros / Vehiculos | Menor a 15% |
| Severidad | Monto total / Siniestros | Controlada |
| PT vs Parciales | PT / Total perdidas | Menor a 25% |

## Resumen Visual

```mermaid
flowchart LR
    A[Cliente] --> B[Corredor]
    B --> C[Ejecutivo]
    C --> D[Reserva]
    D --> E[Suscripcion]
    E --> F[Condiciones]
    F --> G[Aprobacion]
    G --> H[Emision]
    H --> I[Gestion Flota]
    H --> J[Siniestros]
```
