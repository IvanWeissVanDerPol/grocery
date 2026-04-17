# Brand Guidelines - De Abasto a Casa

## Nombre y tono

**Nombre comercial:** De Abasto a Casa
**Tagline:** Mercado, prep y comidas listas. Puerta a puerta, en San Lorenzo.
**Origen:** "Abasto" como referencia al mercado mayorista de Asuncion (fuente de nuestros ingredientes). "a Casa" cierra el loop: del mercado directo a tu heladera/freezer.

### Reglas de comunicacion (from `06_Marketing_and_Brand/Mensaje_Valor_Cliente_Template.md`)

1. **Numeros honestos, no inflados.** Si su gasto real es Gs. 4M y no Gs. 7M, usar Gs. 4M. La credibilidad vale mas que cerrar 1 venta.
2. **Nunca criticar como cocina hoy.** Solo mostrar el costo completo.
3. **Escribir los numeros con punto separador** (Gs. 1.600.000 no "1.6 millones" ambiguo).
4. **Nunca comparar con restaurantes caros** salvo que el cliente lo traiga. Comparar con su propia realidad.
5. **Cerrar siempre con "vos decidis con info completa"** - la decision es de ellos.

Tono: honesto, sin marketing humo, comunidad, numeros reales. Evitar superlativos vacios ("el mejor", "increible"). Preferir datos concretos ("4 meses en freezer", "2 entregas por mes", "hasta 15 productos").

---

## Paleta (token `meal_prep.tokens.json`)

### Option A (default) - Mercado Verde
- Primary: `#3a6b4a` (verde bosque / mercado)
- Secondary: `#c2663a` (terracota calido)
- Accent: `#d4a15a` (ocre dorado)
- Background: `#f6f1e7` (crema / papel kraft)
- Surface: `#ffffff`
- Text: `#1f1f1f`
- Text Light: `#5a5246`
- Success / Error: `#3a6b4a` / `#b0453e`

### Option B (alternativa) - Abasto Terracota
- Primary: `#b04b2a` - invertido: terracota manda, verde apoya
- Background: `#faf5eb`

La version A (verde) es la activa en el sitio. Cambiar editando `defaultPalette` en `src/tokens/meal_prep.tokens.json`.

---

## Tipografia

- **Headings:** Fraunces (serif elegante, moderna, con personalidad). Peso 600 default.
- **Body:** Inter (sans-serif, alta legibilidad en pantalla).
- **Fuentes cargadas desde Google Fonts** via el token (`googleFonts` field).

Reglas:
- No mezclar mas fuentes. Dos familias alcanzan.
- Headings en `600` (semi-bold), body en `400`.
- Evitar MAYUSCULAS completas salvo en microcopy (labels de boton).

---

## Logo (MVP)

**Wordmark + icono SVG simple.**

Propuesta inicial (pendiente de implementar como SVG inline en `public/assets/businesses/de-abasto-a-casa/logo.svg`):

- Wordmark: "De Abasto a Casa" en Fraunces 600, color primary (`#3a6b4a`).
- Icono a la izquierda: simple, monocromatico, verde primary. Opciones:
  1. Bolsa de mercado (`shopping-bag` outline).
  2. Hoja de albahaca o vegetal.
  3. Olla con vapor.
  4. Cuchillo + cuchara cruzados (mas restaurantero, menos mercado).

Recomendacion: **bolsa de mercado estilizada** (alineada con "Abasto" y con el icono ShoppingCart que usa el tile del homepage de paragu-ai.com).

Especificaciones:
- SVG monochrome, 200x50px landscape (wordmark + icono).
- Version square 100x100px solo icono (para favicon).
- Fondo transparente (se adapta a surface crema y a header blanco).

---

## Imageneria

- **Sourcing:** usar las 23 fotos de `02_Shopping_Guide/images/` como base. Ver `03_Image_Curation.md` para la seleccion recomendada.
- **Estilo:** luz natural, fondos neutros (madera, metal, manteles crudos). Evitar filtros saturados o stock generico.
- **Ratio:** 4:3 para cards de servicio, 1:1 para galeria grid, 16:9 para hero.
- **Alt text:** siempre en espanol, describir el contenido y la accion ("Bife de chorizo enterro sobre tabla de madera", no "comida bonita").

---

## Voz en WhatsApp

Plantillas vivas en `06_Marketing_and_Brand/02_Guiones_Ventas_WhatsApp.md`.
El sitio respeta ese tono en los mensajes pre-llenados:
- Saludo corto ("Hola!").
- Contexto claro ("Vi el sitio de De Abasto a Casa y quiero saber mas sobre Nivel 2").
- Sin presion, sin emojis gratuitos.

---

## No hacer

- No usar fotos stock de supermercado industrial.
- No usar el verde fluor/neon tipicos de apps de delivery.
- No prometer "el mejor" ni "100% organico" sin evidencia.
- No mostrar testimonios sin permiso explicito del cliente.
- No mezclar castellano "tu" y "vos" en una misma seccion. Usar "vos" (rioplatense / paraguayo).
