# Sitio Web "De Abasto a Casa" - Plan Operativo

> Fecha: abril 2026
> Repo tecnico: `ai-whisperers/paragu-ai-builder` (rama `claude/grocery-website-plan-MerSn`)
> Slug publico: `/de-abasto-a-casa` en paragu-ai.com
> Tipo nuevo: `meal_prep` (agregado al page-builder para este cliente y futuros similares)

---

## Contexto

"Grocery" paso de documentacion interna a un sitio publico que permite a clientes nuevos entender la propuesta y escribir directo por WhatsApp. El sitio vive dentro de paragu-ai-builder (motor Next.js + Supabase que ya aloja a Salon Maria, GymFit, Spa Serenidad, etc.). No duplicamos infraestructura ni pagamos hosting adicional: aprovechamos el builder compartido.

## Que existe ya (Fase 1 - MVP)

Todo el MVP esta implementado y pasa validacion de schemas + tokens + typecheck + build. La pagina esta viva en dev contra localhost:3000/de-abasto-a-casa.

### Secciones publicadas

| # | Seccion | Contenido | Fuente del copy |
|---|---|---|---|
| 1 | Header + nav | Servicios, Calculadora, Galeria, FAQ, Contacto | Registro del builder |
| 2 | Hero | "Convertimos el caos del mercado en comida lista" | `04_Business_Model/00_Master_Plan.md` |
| 3 | Servicios | 3 Niveles + add-ons (10 entradas con precios) | `01_Core_Business/01_Matriz_de_Servicio.md` + pricing acordado |
| 4 | Calculadora de Ahorro | Widget interactivo (plata + tiempo vs nuestro servicio) | `06_Marketing_and_Brand/Mensaje_Valor_Cliente_Template.md` |
| 5 | Galeria | Grid 3 col, placeholders tematizados (pendiente subir fotos reales) | `02_Shopping_Guide/images/` |
| 6 | Equipo | Ivan Weiss van der Pol (fundador) | `09_Active_Clients/001_Ivan_Weiss/` |
| 7 | Testimonios | 3 citas ilustrativas (labeled) | Placeholders hasta obtener permisos |
| 8 | FAQ | 8 preguntas honestas | Secciones F/G/H/I del value template |
| 9 | Contacto | WhatsApp primero, horarios de compra mar/jue, cobertura | Resumen del master plan |
| 10 | CTA Banner + float | WhatsApp persistente | Plantilla del builder |

### Precios publicados en el sitio

| Nivel | Tier | Precio |
|---|---|---|
| 1 Raw | Basico | 250.000 Gs/semana |
| 1 Raw | Completo | 400.000 Gs/semana |
| 2 Prep (mas elegido) | Individual | 400.000 Gs/semana |
| 2 Prep | Pareja | 650.000 Gs/semana |
| 2 Prep | Familia | 900.000 Gs/semana |
| 3 Cocido (INAN en curso) | 10 comidas | desde 1.200.000 Gs/sem |
| 3 Cocido (INAN en curso) | 15 comidas | desde 1.700.000 Gs/sem |
| Add-on | Desayunos / Postres / Bebidas | +400/+200/+300.000 Gs/mes |

Nota: precios referenciales, ajustables por cliente. Declarado en el disclaimer del calculador.

### Calculadora de ahorro - como funciona

Inputs (todos en Gs., mensuales, con defaults sensatos):
- Super + carniceria + feria
- Delivery + comer afuera
- Comida tirada + compras impulsivas
- Gas/luz extra cocinando
- Personas en el hogar
- Valor de tu hora (default 25.000)
- Horas/mes cocinando + comprando (default 60)
- Dropdown: Nivel a comparar (Nivel 2 Individual/Pareja/Familia, o Nivel 1 Completo)

Outputs en vivo (sin submit):
- Plata real hoy = suma de 4 primeros
- Valor del tiempo = hs x valor hora
- Costo TOTAL hoy = plata + tiempo
- Nuestro servicio (mes) = monto del tier elegido
- Ahorro mensual = TOTAL hoy - nuestro servicio
- Horas recuperadas = hs - 8 (coordinacion + recepcion)

Logica honesta:
- Si ahorro > 0 → copy positivo + boton WhatsApp con los numeros pre-llenados.
- Si ahorro < 0 → copy "hoy ya sos muy eficiente, probablemente no te conviene" + invitacion a probar igual.

CTA final: `wa.me/{{whatsapp}}?text=<numeros personalizados del usuario>` - cumple la regla del template de valor: el cliente llega con su propio calculo.

### Branding actual

- **Nombre:** De Abasto a Casa
- **Tagline:** Mercado, prep y comidas listas. Puerta a puerta, en San Lorenzo.
- **Paleta:** Verde Mercado `#3a6b4a` + Terracota `#c2663a` + Crema `#f6f1e7`.
- **Tipografias:** Fraunces (headings, serif) + Inter (body, sans).
- **Logo:** wordmark + icono SVG pendiente (ver `02_Brand_Guidelines.md`).

### Items pendientes de Ivan (Fase 2)

1. **Numero de WhatsApp real.** Ahora publicado como `+595 000 000000` (placeholder). Reemplazar en `demo-data.ts` entrada `de-abasto-a-casa.whatsapp` y `.phone`.
2. **Autorizacion de testimonios** (Fran, Junior, Emilio & Lucia). Los placeholders actuales van labeled "Testimonio ilustrativo".
3. **Fotos reales de la galeria.** Hoy usa placeholders SVG con gradiente verde/terracota. Seleccion recomendada en `03_Image_Curation.md`.
4. **Bio extendida de Ivan.** Actualmente 2 frases; ampliar si queres mostrar mas historia.
5. **Logo.** Decidir si wordmark tipografico o contratar icono.
6. **Email de contacto real** (hoy `hola@deabastoacasa.com.py` como placeholder).
7. **Cobertura especifica** si querria comunicar barrios prioritarios.

### Verificacion local

```bash
cd paragu-ai-builder/web
npm install
npm run validate:schemas      # OK
npm run validate:tokens       # OK
npm run typecheck             # OK
npm run build                 # OK (66/66 paginas generadas)
npm run dev                   # abrir http://localhost:3000/de-abasto-a-casa
```

### Verificacion en paragu-ai.com despues del merge

1. `/` → la tarjeta "De Abasto a Casa" aparece en la seccion "Proyectos".
2. `/de-abasto-a-casa` → pagina completa con las 10 secciones, paleta verde/crema.
3. Calculadora: cambiar inputs → totales recalculan en vivo; boton WhatsApp abre `wa.me/...` con el mensaje personalizado.
4. Boton flotante WhatsApp visible en todas las secciones.

### Items no incluidos (Fase 3 - proximamente)

- Formulario de contacto con email (hoy solo WhatsApp, por decision de producto).
- Widget de calendario estacional (proximamente desde `05_Market_Intelligence/07_Calendario_Estacional_Paraguay.md`).
- Nivel 3 (comidas cocidas) como servicio activo → cuando llegue habilitacion INAN.
- Panel cliente / tracking de pedidos → cuando se justifique por volumen.
