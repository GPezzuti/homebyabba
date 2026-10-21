# LP Barbara — Next Actions

**Actualizado 2026-10-21:** dominio custom conectado desde 2026-06-27, ya no es pendiente. Proyecto en mantenimiento puntual — ver `CLAUDE.md`.

## QA final (opcional, solo si Barbara lo solicita)
- [ ] Abrir URL en Chrome y mobile
- [ ] Primer click activa música de fondo
- [ ] Navegar los 4 capítulos del recorrido sensorial
- [ ] Descargar guía gratis → abre Google Drive
- [ ] Click WhatsApp → abre chat de Barbara
- [ ] Verificar en móvil (responsive)

## Decisión pendiente: wrangler y rama del bot (requiere push = deploy)
- [ ] Opción A (recomendada): adoptar `wrangler.jsonc` del PR #1 con `"not_found_handling": "404-page"` y crear `.assetsignore` (`.git`, `.gitignore`, `.assetsignore`, `wrangler.jsonc`, `*.md`). Corta la regeneración del bot y saca `.git` y `*.md` del sitio. Confirmar antes en el dashboard (Workers > homebyabba > Settings > Build) que la rama de producción es main.
- [ ] Verificar el deploy: `/status.md`, `/.gitignore` y `/.git/config` deben dar 404 (hoy dan 200, verificado 2026-10-21) y `/no-existe` debe mostrar el 404.html de marca.
- [ ] Después, borrar la rama remota `cloudflare/workers-autoconfig` (tag de backup pusheado antes).
- [ ] Nota: `assets/images/terraza6_web.jpg` y 3 `.ttf` (~940 KB) no se usan y se despliegan igual.
