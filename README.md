# Base de Conocimiento Empresarial — FinOps / TBM (piloto)

## Estado actual (2026-07-01)

**Capa 02 — product-docs: COMPLETA para este piloto.**
227 documentos de IBM Cloudability Premium (carpetas `admin/` y `product/`, más release notes)
normalizados a Markdown con front-matter, en 3 idiomas nativos de IBM (en/es/pt-br) — 681
archivos en total. Imágenes (573) extraídas a `03-media/cloudability-premium/` con rutas
relativas corregidas. Fuente: export offline `SSSVH06_20260629.zip`.

**Capa 00 — taxonomy: PILOTO, no completa.**
Solo se modeló una capacidad (`finops.optimize.rate-optimization`) para probar el pipeline
completo de punta a punta. El framework FinOps completo (todos los dominios Inform/Optimize/
Operate, personas, niveles de madurez) y la Taxonomía TBM v5.0.1 todavía no están capturados.

**Capa 04 — generated: 1 capability brief de prueba.**
`capability-briefs/finops-optimize-rate-optimization.md` — construido 100% a partir de
contenido real normalizado (con citas a los documentos fuente), no inventado ni parafraseado
de memoria.

## Qué falta para cerrar la Capa 1 por completo

1. Completar `00-taxonomy/finops-framework.yaml` con el framework completo de FinOps Foundation.
2. Agregar `00-taxonomy/tbm-taxonomy-v5.yaml` + crosswalk v4→v5.
3. Enriquecer los 681 documentos normalizados: generar `summary` y `capability_ids` por
   documento (paso de IA económico, con hash-diffing para no reprocesar todo en cada release).
4. Ampliar `capability-product-map.yaml` a todas las capacidades reales del framework.
5. Generar el resto de capability briefs (uno por capacidad × producto relevante), en los 3 idiomas.
6. Repetir la normalización (capa 02) para el resto de productos: Cloudability Essentials/Standard,
   Apptio Costing Essentials/Standard, Planning, Billing, Benchmarking, TBM Studio, Turbonomic,
   Kubecost, Targetprocess — cada uno con su propio adapter de harvester según cómo se descargue
   su documentación.

## Estructura de carpetas

```
00-taxonomy/            Frameworks canónicos versionados + crosswalk capacidad->producto
01-practice-sources/    Contenido normativo (FinOps Foundation, FOCUS, TBM Council) — pendiente
02-product-docs/        Documentación técnica normalizada, por producto e idioma
03-media/                Imágenes extraídas, referenciadas por los .md de 02 y 04
04-generated/            Entregables curados listos para RFP/presentaciones — esto es lo que
                          se sube a Claude Projects / ChatGPT Knowledge / (futuro) servidor MCP
```
