# Diagrama de la Estructura IT / OT e Impacto de la IA

**Empresa:** AgroIndustrial Mediterránea S.L.  
**Alumno:** Marcos Martín Reinón – 1º DAW A  

---

## Captura del diagrama

![Diagrama IT/OT e impacto de la IA](imagenes/diagrama.png)

---

## Código Mermaid utilizado

```mermaid
flowchart TB
    Direccion["Dirección General<br/>Toma de decisiones estratégicas"]

    subgraph OT["OT - Operational Technology (Planta)"]
        direction TB
        subgraph ProcesosPlanta["Procesos de Planta"]
            Recepcion["Recepción de materia prima"]
            Procesado["Procesado y elaboración"]
            Envasado["Envasado y etiquetado"]
            Calidad["Control de Calidad"]
            Almacen["Almacén de producto terminado"]
        end
        subgraph SistemasOT["Sistemas OT"]
            SCADA["SCADA / PLC"]
            Sensores["Sensores IoT"]
            Automatismos["Automatismos de línea"]
        end
    end

    subgraph IT["IT - Information Technology (Negocio)"]
        direction TB
        subgraph ProcesosNegocio["Procesos de Negocio"]
            Comercial["Gestión Comercial y Pedidos"]
            Planificacion["Planificación de la Producción"]
            Compras["Compras y Aprovisionamiento"]
            Logistica["Logística y Distribución"]
            Admin["Administración y Finanzas"]
        end
        subgraph SistemasIT["Sistemas IT"]
            ERP["ERP"]
            CRM["CRM"]
            BI["Business Intelligence"]
        end
    end

    subgraph IA["Tecnologías de Inteligencia Artificial"]
        direction LR
        Vision["1. Visión Artificial<br/>(Control de Calidad)"]
        Predictivo["2. Mantenimiento Predictivo<br/>(IoT + IA)"]
        Gemelo["3. Gemelo Digital"]
        Demanda["4. Predicción de Demanda"]
        Analitica["5. Plataforma Analítica IT/OT"]
    end

    Recepcion --> Procesado --> Envasado --> Calidad --> Almacen
    Sensores --> Procesado
    Sensores --> Envasado
    SCADA --> Procesado
    SCADA --> Envasado
    Automatismos --> Envasado
    Vision --> Calidad
    Vision --> Envasado
    Predictivo --> Sensores
    Predictivo --> SCADA
    Gemelo --> Procesado
    Gemelo --> Envasado
    Gemelo --> SCADA
    Demanda --> Planificacion
    Demanda --> Compras
    Demanda --> Comercial
    Analitica --> ERP
    Analitica --> BI
    Analitica --> Planificacion
    Analitica -.->|Integra datos| SCADA
    Analitica -.->|Integra datos| ERP
    Analitica --> Direccion
    Comercial --> Planificacion
    Planificacion --> Procesado
    Compras --> Recepcion
    Almacen --> Logistica
    ERP --> Admin
    ERP --> Comercial
    CRM --> Comercial

    classDef ot fill:#e1f5fe,stroke:#0277bd,stroke-width:2px
    classDef it fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px
    classDef ia fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px
    classDef dir fill:#fff3e0,stroke:#ef6c00,stroke-width:2px

    class OT,ProcesosPlanta,SistemasOT,Recepcion,Procesado,Envasado,Calidad,Almacen,SCADA,Sensores,Automatismos ot
    class IT,ProcesosNegocio,SistemasIT,Comercial,Planificacion,Compras,Logistica,Admin,ERP,CRM,BI it
    class IA,Vision,Predictivo,Gemelo,Demanda,Analitica ia
    class Direccion dir
```

---

## Explicación del diagrama

### Estructura principal

- **OT (Operational Technology)**: Representa todo lo relacionado con la planta de producción (líneas, sensores, SCADA, control de calidad, etc.).
- **IT (Information Technology)**: Representa los sistemas y procesos de negocio (ERP, comercial, planificación, compras, etc.).
- **Capa de IA**: Muestra las 5 tecnologías propuestas y cómo impactan en los diferentes procesos.

### Impacto de las tecnologías de IA

| Tecnología                        | Afecta principalmente a                          | Resultado esperado                          |
|-----------------------------------|--------------------------------------------------|---------------------------------------------|
| Visión Artificial                 | Control de Calidad y Envasado                    | Menos defectos y mermas                     |
| Mantenimiento Predictivo          | Sensores y SCADA                                 | Menos paradas no planificadas               |
| Gemelo Digital                    | Procesado, Envasado y SCADA                      | Mejor optimización y simulación             |
| Predicción de Demanda             | Planificación, Compras y Comercial               | Mejor ajuste oferta-demanda                 |
| Plataforma Analítica IT/OT        | Integra OT + IT y alimenta a Dirección           | Visibilidad completa y mejores decisiones   |

Este diagrama permite visualizar de forma clara cómo la Inteligencia Artificial actúa como puente entre el mundo de la planta (**OT**) y el mundo del negocio (**IT**).
