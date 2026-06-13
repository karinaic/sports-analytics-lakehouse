# Sports Analytics Lakehouse 🏟️
### Arquitectura Medallion con PySpark y Databricks para análisis deportivo de élite

---

## Descripción

Pipeline de datos end-to-end que unifica dos fuentes críticas de un club de fútbol de élite:

- **Rendimiento deportivo** — datos de tracking físico (GPS, distancia, velocidad, sprints)
- **Experiencia de aficionado** — aforo, satisfacción, NPS, tiempos de acceso

El objetivo: cruzar ambos mundos en una única capa analítica Gold lista para dashboards de producción en Power BI, permitiendo al cuerpo técnico y a la dirección tomar decisiones basadas en datos.

---

## Arquitectura

```
Fuente 1: Tracking Jugadores (GPS)        Fuente 2: Encuestas + Aforo
          |                                          |
          v                                          v
     CAPA BRONZE                              CAPA BRONZE
  (Ingesta datos crudos)                  (Ingesta datos crudos)
          |                                          |
          v                                          v
     CAPA SILVER                              CAPA SILVER
  (Limpieza + Validación)               (Limpieza + Transformación)
          |                                          |
          +------------------+------------------------+
                             |
                             v
                        CAPA GOLD
                   (JOIN + KPIs + Alertas)
                             |
                             v
                     Dashboard / Power BI
```

---

## Stack Tecnológico

| Tecnología | Uso |
|---|---|
| Python 3.14 | Lenguaje principal |
| PySpark 4.1 | Procesamiento distribuido |
| Spark SQL | Queries analíticas y JOIN |
| Arquitectura Medallion | Bronze / Silver / Gold |
| Faker | Generación de datos simulados realistas |
| Matplotlib | Visualización y EDA |
| VS Code + Jupyter | Entorno de desarrollo |

---

## Estructura del Proyecto

```
sports_analytics_lakehouse/
│
├── notebooks/
│   └── sports_analytics_lakehouse.ipynb   # Pipeline completo
│
├── data/
│   ├── bronze/    # Datos crudos
│   ├── silver/    # Datos limpios
│   └── gold/      # Tabla analítica + dashboard PNG
│
└── README.md
```

---

## Resultados

- **418 registros** de rendimiento físico (38 jornadas x 11 jugadores)
- **38 registros** de experiencia de aficionado por partido
- **19 KPIs** unificados en capa Gold
- Alertas automáticas de carga física y satisfacción de aficionado
- Correlación rendimiento deportivo vs experiencia en estadio

---

## Autor

**Karina Inche Cisneros**
Data Analyst | AI & Data Professional | DPO Certificada

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Karina_Inche-blue)](https://linkedin.com/in/karina-inche)