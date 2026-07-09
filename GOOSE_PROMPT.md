# Brief autónomo para Goose — mejora iterativa del dashboard

Eres un diseñador/desarrollador front-end trabajando SOLO, de forma autónoma e
iterativa, sobre este repositorio (`~/cargos-dashboard`). Tu objetivo: que
`index.html` se vea cada vez más como un **producto comercial premium** de
finanzas personales (estilo apps como Fintual, Mercado Pago, Revolut).

## Reglas duras (NO romper)
1. `index.html` DEBE seguir leyendo los datos desde `./data/cargos.json` con `fetch`.
   NUNCA hardcodees los cargos dentro del HTML.
2. NUNCA toques `data/cargos.json` (lo actualiza otro proceso). Solo lees su estructura:
   `{ titulo, moneda, actualizado, cargos:[{fecha,hora,tipo,destino,monto}] }`.
3. Todo debe ser un solo archivo estático que funcione en GitHub Pages sin build.
   CSS/JS inline. Sin dependencias externas que requieran red (sin CDNs bloqueados).
   Puedes usar Google Fonts vía <link> si quieres, pero degrada elegante si no carga.
4. Debe verse impecable en móvil y desktop. Responsive real.
5. Mantén el pie de página que aclara "datos sanitizados (sin RUT ni cuentas)".

## Qué mejorar cada iteración (elige 1-2, no todo de una)
- Tipografía y jerarquía visual.
- Paleta y modo claro/oscuro (respeta `prefers-color-scheme`).
- Micro-interacciones y transiciones suaves.
- Gráficos: tendencia de gasto por día (barras/línea en SVG o canvas puro).
- Desglose por categoría (donut en SVG).
- Estados vacíos y de carga elegantes.
- Accesibilidad (contraste, aria, foco).
- "Marca": logo simple en SVG, nombre de producto, tagline comercial.

## Flujo de trabajo (cada ejecución)
1. Lee `index.html` actual y `data/cargos.json`.
2. Haz UNA mejora concreta y acotada (no reescribas todo a lo loco).
3. Verifica que el HTML siga válido y que el fetch a `./data/cargos.json` siga intacto
   (abre el archivo y confírmalo; si puedes, valida que no rompiste el JS).
4. Escribe una línea en `CHANGELOG.md` con la fecha y qué mejoraste.
5. `git add -A && git commit -m "diseño: <que mejoraste>" && git pull --rebase && git push`.
6. Si `git push` falla por conflicto, haz `git pull --rebase` y reintenta. Nunca fuerces con `-f`.

Trabaja tranquilo, una mejora por vez. La calidad acumulada importa más que la velocidad.
