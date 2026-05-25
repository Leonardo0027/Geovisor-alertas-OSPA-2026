# Geoviso OSPA — Alertas-Validación Incendios y Deslizamientos 2026

Visor interactivo de validación de los modelos operativos OSPA del IDEAM (incendios de la cobertura vegetal y deslizamientos detonados por lluvia) contra la base UNGRD-NAT 1991–2025, para el período 2023–2025.

**Contrato CTO-118 de 2026 · IDEAM · OSPA**

---

## Acceso en línea

Una vez publicado en GitHub Pages, el visor queda disponible en:

```
https://<tu-usuario>.github.io/<nombre-repo>/
```

Es una aplicación 100 % estática (un solo HTML autocontenido con datos embebidos): no requiere backend ni servidor.

## Cómo publicar en GitHub Pages — paso a paso

### 1. Crear el repositorio

1. Entra a <https://github.com/new>
2. **Repository name**: `geoviso-ospa-2026` (o el que prefieras)
3. **Public** (necesario para Pages gratuito; si es Pro/Org puedes usar privado)
4. **Add a README**: déjalo desmarcado (este repo ya trae uno)
5. Crear

### 2. Subir los archivos

Opción A — desde la interfaz web (más simple):

1. En el repo recién creado, clic en *"uploading an existing file"*
2. Arrastra `index.html` y `README.md` de esta carpeta
3. *Commit changes*

Opción B — desde Git CLI:

```bash
cd "<carpeta donde está esta web>"
git init
git branch -M main
git add index.html README.md
git commit -m "Publicación inicial Geoviso OSPA 2026"
git remote add origin https://github.com/<tu-usuario>/geoviso-ospa-2026.git
git push -u origin main
```

### 3. Activar GitHub Pages

1. En el repo, ve a **Settings → Pages** (menú lateral izquierdo)
2. **Source**: *Deploy from a branch*
3. **Branch**: `main` · **Folder**: `/ (root)`
4. *Save*
5. Espera 1–2 minutos; GitHub mostrará la URL pública (`https://<usuario>.github.io/<repo>/`)

### 4. (Opcional) Dominio personalizado

En *Settings → Pages → Custom domain* puedes apuntar un dominio propio (por ejemplo `geoviso-ospa.ideam.gov.co`) — requiere configurar un registro CNAME en el DNS.

---

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
