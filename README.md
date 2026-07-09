# cargos-dashboard

Dashboard web **autónomo** de gastos personales.

- Los cargos se extraen desde correos del banco por una **Raspberry Pi** usando el modelo **qwen3-30b** (llama.cpp).
- La Pi actualiza `data/cargos.json` y hace `git push` **apenas entra un gasto nuevo**.
- El diseño (`index.html`) lo mejora **Goose** de forma iterativa y autónoma (ver `GOOSE_PROMPT.md`).
- Datos **sanitizados**: sin RUT ni números de cuenta.

Sitio: https://cliford2001.github.io/cargos-dashboard/
