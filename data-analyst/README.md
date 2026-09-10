# Query & Criterio

Página de práctica para aprender análisis de datos. Un solo archivo, sin build ni backend:
abrí `index.html` en el navegador y funciona.

**Publicada en:** https://claude.ai/code/artifact/f67ca4b8-1522-4989-ac2f-94e30a2f4a50

## Qué tiene

- **Ruta** — 6 niveles con criterio de salida concreto y la trampa típica de cada uno.
- **Lab SQL** — SQLite real corriendo en el navegador (build asm.js de sql.js, sin descarga
  de wasm). Dos bases generadas con semilla fija y 15 ejercicios de nivel 1 a 4.
  La corrección **ejecuta tu query y compara el resultado** contra la solución de
  referencia: si llegás al mismo cuadro por otro camino, cuenta igual.
- **Criterio** — 8 casos donde el SQL está bien y la conclusión está mal
  (supervivencia, Simpson, comparaciones múltiples, instrumentación, Goodhart...).
- **Terreno 2026** — qué piden los avisos, qué automatizó la IA y qué no, con fuentes.

## Las bases

| `mercado` | `tienda` |
|---|---|
| `assets`, `prices`, `dividends`, `positions` | `customers`, `orders`, `order_items`, `products`, `marketing_spend` |
| 8 instrumentos, 263 ruedas diarias | 620 clientes, ~1.000 órdenes |

Ambas se generan en el cliente con un PRNG sembrado, así que son idénticas para
cualquiera que abra la página y se rearman en cada recarga.

**Los precios son sintéticos**, generados con un modelo calibrado (deriva, volatilidad y
beta por tipo de activo) porque no había acceso a datos de mercado reales. La mecánica de
análisis es la misma; los números no sirven para decidir una inversión.

## Progreso

Se guarda en `localStorage` del navegador — es local a ese equipo y no se sincroniza.
