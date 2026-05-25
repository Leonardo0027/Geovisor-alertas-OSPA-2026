## Estructura

```
web/
├── index.html      # Visor (HTML autocontenido, ~1.3 MB con datos embebidos)
└── README.md       # Este archivo
```

El visor incluye datos embebidos para no depender de servicios externos. Las únicas dependencias en línea son librerías CDN abiertas:

- Leaflet 1.9.4 — mapa interactivo
- Chart.js 4.4.0 — gráficos
- CARTO Light — basemap (atribución incluida)

## Datos y metodología

- **Eventos observados**: UNGRD, Base Nacional Ajustada (NAT) 1991–2025.
- **Alertas modeladas**: salidas operativas del Sistema OSPA (modelos ICV de incendios y IDD de deslizamientos).
- **Episodios ENSO/ONI**: NOAA CPC ERSSTv5.
- **Cartografía**: capas oficiales municipal y departamental del IDEAM, normalización DIVIPOLA.
- **Métricas**: POD, FAR, Bias, HSS, ORSS y PSS (estándar OMM para verificación categórica de pronósticos).

## Controles del visor

| Control | Efecto |
|---|---|
| **Temática** (🔥 Incendios / 🌧 Deslizam.) | Cambia métricas, gráficos, mapa y top municipios |
| **Año** (2023 / 2024 / 2025) | Filtra todos los paneles al año seleccionado |
| **Métrica visualizada** | Define qué se colorea en el mapa: eventos, alertas, aciertos o alertas altas |
| **Coropleta** (Apagada/Municipal/Depto) | Cambia el nivel de la agregación cromática |
| **Centroides proporcionales** | Activa puntos cuyo tamaño es proporcional al valor |
| **Bordes departamentales** | Muestra/oculta el contorno departamental |
| **Pestañas Métricas/Niveles/Top** | Navega entre gráficos del panel derecho |

Cada cambio en un control actualiza todos los paneles correspondientes. El indicador superior central del mapa muestra siempre la combinación de métrica, año y temática actualmente activa.

## Licencia y uso

Producto técnico desarrollado en el marco del Contrato CTO-118 de 2026 entre el IDEAM y el contratista. Uso institucional. Citar como:

> IDEAM (2026). *Geoviso OSPA — Alertas-Validación Incendios y Deslizamientos 2026*. Contrato CTO-118 de 2026.
