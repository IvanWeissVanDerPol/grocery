# Image Curation - Galeria del Sitio

> Hoy la galeria usa placeholders SVG con gradiente verde/terracota. Para la Fase 2,
> reemplazar con estas fotos curadas desde `02_Shopping_Guide/images/`.

## Seleccion recomendada (9 fotos - grid 3x3)

| # | Archivo fuente | Categoria | Alt text sugerido |
|---|---|---|---|
| 1 | `bife_de_chorizo_raw_1767901164253.png` | Cortes de Carne | Bife de chorizo enterro cortado a mano sobre tabla de madera |
| 2 | `ojo_de_bife_raw_1767901189358.png` | Cortes de Carne | Ojo de bife premium, corte grueso, listo para sellar al vacio |
| 3 | `picanha_raw_1767901217990.png` | Cortes de Carne | Picanha brasileno, corte completo con capa de grasa intacta |
| 4 | `matambre_vacuno_raw_correction_1767904122442.png` | Mercado | Matambre vacuno mostrando veteado natural |
| 5 | `bondiola_raw_1767901583239.png` | Cortes de Carne | Bondiola de cerdo, ideal para estofado o sellado |
| 6 | `panceta_cerdo_raw_1767901568241.png` | Mercado | Panceta de cerdo con capa magra y grasa, corte grueso |
| 7 | `pollo_casero_raw_1767901683573.png` | Mercado | Pollo casero entero proveniente de productor local |
| 8 | `lechon_mitad_raw_1767901614665.png` | Cortes de Carne | Media res de lechon, corte para porcionar durante la semana |
| 9 | `costillar_raw_1767901103232.png` | Mise en Place | Costillar vacuno entero, listo para porcionar en casa del cliente |

## Fotos adicionales recomendadas (para la Fase 2 con plata)

Si Ivan quiere una galeria mas "servicio" (no solo producto crudo), considerar contratar fotografo para:

- **Prep en accion:** manos porcionando, sellado al vacio, freezer organizado en casa del cliente.
- **Entrega:** conservadoras en el auto, saludo en la puerta, heladera organizada.
- **Mercado:** puestos de Abasto, negociacion con proveedor, cajon de verduras de temporada.
- **Portrait del founder:** Ivan en la cocina o en el mercado, natural, sin pose.

Estas fotos de proceso comunican el servicio ("hacemos esto por vos") mejor que solo cortes crudos ("tenemos buenos ingredientes"). Ambas son utiles: cortes crudos para la seccion de calidad, proceso para hero/how-it-works.

## Especificaciones tecnicas para paragu-ai-builder

- Formato: WebP o JPG optimizado (< 200 KB cada una).
- Resolucion: 1200x900 (4:3) para cards, 1200x1200 (1:1) para galeria grid.
- Ubicacion en repo: `paragu-ai-builder/web/public/assets/businesses/de-abasto-a-casa/gallery-01.webp` ... `-09.webp`.
- Wiring: agregar array `gallery` al tenant entry en `web/lib/engine/demo-data.ts`:

```ts
gallery: [
  { src: '/assets/businesses/de-abasto-a-casa/gallery-01.webp', alt: 'Bife de chorizo...', category: 'Cortes de Carne' },
  // ...
]
```

Cuando `gallery` tenga items, los placeholders SVG desaparecen automaticamente (logica existente en `compose.ts` - `generatePlaceholderGallery` solo actua si `business.gallery` es vacio).

## Fotos a NO publicar (por ahora)

- `lechon_mitad` puede generar impresion fuerte en quien no consume carne; considerar si se muestra en galeria publica o se deja solo en documentacion interna.
- `pollo_industrial_raw_1767901697605.png` (contraste con `pollo_casero`) - util para comparativa pedagogica, pero sola puede dar impresion contraria. Usar solo junto a la del casero, con comparacion educativa.
- `pato_crudo`, `gallina`, `entrana` - visualmente pueden alejar a clientes primerizos. Reservar para clientes ya convencidos que pidan el catalogo completo.
