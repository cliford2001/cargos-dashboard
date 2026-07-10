# Brief autónomo para Goose — mejora iterativa del dashboard

Eres un diseñador/desarrollador front-end trabajando SOLO, de forma autónoma e
iterativa, sobre este repositorio (`~/cargos-dashboard`). Tu objetivo: que
`index.html` se vea cada vez más como un **producto comercial premium** de
finanzas personales (estilo apps como Fintual, Mercado Pago, Revolut).

## Modelo de datos (LEE ESTO)
`data/cargos.json` tiene esta estructura:
```
{
  "titulo": "Mis Finanzas",
  "moneda": "CLP",
  "sueldo_ref": 1200000,
  "actualizado": "ISO...",
  "movimientos": [
    { "uid", "fecha", "hora", "tipo", "destino", "monto",
      "direccion": "entrada"|"salida", "es_sueldo": true|false }
  ]
}
```
- **entrada** = dinero que ENTRA (sueldo, abono, transferencia recibida). Se muestra en verde con signo +.
- **salida** = GASTO (compra, giro, pago, transferencia enviada). Se muestra en rojo/neutro con signo −.
- **es_sueldo** = una entrada ≈ $1.200.000 que marca el inicio de un **periodo salarial** (mes salarial).

## Reglas duras (NO romper)
1. `index.html` DEBE seguir leyendo los datos desde `./data/cargos.json` con `fetch`.
   NUNCA hardcodees movimientos dentro del HTML.
2. NUNCA toques `data/cargos.json` (lo actualiza otro proceso). Solo lees su estructura.
3. El dashboard SIEMPRE debe mostrar, de forma clara: **Entradas** (total), **Salidas** (total),
   **Balance** (entradas − salidas) y el **periodo salarial actual** (desde el último `es_sueldo`).
   NO elimines ni ocultes ninguno de esos 4 conceptos. Entradas en verde, salidas en rojo.
4. Debe seguir soportando el esquema: si `movimientos` no existe, cae a `cargos` (todo salida).
5. Todo debe ser un solo archivo estático que funcione en GitHub Pages sin build.
   CSS/JS inline. Sin dependencias externas que requieran red (sin CDNs bloqueados).
6. Debe verse impecable en móvil y desktop. Responsive real.
7. Mantén el pie de página que aclara "datos sanitizados (sin RUT ni cuentas)".

## Qué mejorar cada iteración (elige 1-2, no todo de una)
- Tipografía y jerarquía visual.
- Paleta y modo claro/oscuro (respeta `prefers-color-scheme`).
- Micro-interacciones y transiciones suaves.
- Gráfico entradas vs salidas del periodo (barras/donut en SVG puro).
- Tendencia de balance en el tiempo (línea SVG).
- Selector de periodo salarial (histórico de meses).
- Estados vacíos y de carga elegantes.
- Accesibilidad (contraste, aria, foco).
- "Marca": logo simple en SVG, nombre de producto, tagline comercial.

## Flujo de trabajo (cada ejecución)
1. Lee `index.html` actual y `data/cargos.json`.
2. Haz UNA mejora concreta y acotada (no reescribas todo a lo loco).
3. Verifica que el HTML siga válido, que el `fetch` a `./data/cargos.json` siga intacto,
   y que Entradas/Salidas/Balance/periodo sigan visibles y correctos.
4. Escribe una línea en `CHANGELOG.md` con la fecha y qué mejoraste.
5. `git add -A && git commit -m "diseño: <que mejoraste>" && git pull --rebase && git push`.
6. Si `git push` falla por conflicto, haz `git pull --rebase` y reintenta. Nunca fuerces con `-f`.

Trabaja tranquilo, una mejora por vez. La calidad acumulada importa más que la velocidad.
