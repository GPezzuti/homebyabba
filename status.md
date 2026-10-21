# LP Barbara — Status

**Última actualización:** 2026-10-21 (limpieza de ramas)

## Estado: COMPLETO — mantenimiento puntual

Entregado y en producción desde 2026-06-25. Dominio custom conectado 2026-06-27. Fuente de verdad operativa: `CLAUDE.md` (no este archivo).

### Hecho ✅
- [x] Análisis de assets y template HTML
- [x] Configuración Lovable MCP (`claude mcp add --transport http lovable`)
- [x] Compresión de 5 imágenes (7MB → ~300KB c/u)
- [x] Sustitución de 6 imágenes base64 placeholder con fotos reales de Barbara
- [x] Remoción de PDF embedded (7.6MB) → handler con Google Drive placeholder
- [x] HTML final verificado (index.html pesa ~260 KB; el dato de 3.39MB es obsoleto)
- [x] Estructura de proyecto creada

### Hecho ✅ (continuación)
- [x] GitHub repo creado: https://github.com/GPezzuti/homebyabba
- [x] index.html pushed a GitHub (main branch)
- [x] Cloudflare Workers deploy: https://homebyabba.gerardopezzuti.workers.dev ✅ LIVE

### Pendiente ⏳
- [x] PDF URL cargada: https://drive.google.com/file/d/1GgAc8aJGp4_26MPWyTKdHaNojshnFhqn/view — abre en vista previa (no descarga), actualizada 2026-07-22
- [x] Dominio homebyabba.com adquirido (2026-06-25)
- [x] Conectar homebyabba.com como dominio custom en Cloudflare + DNS (2026-06-27)
- [x] Toggle ES/EN + traducción completa del sitio, default español (2026-07-05)
- [ ] Prueba final de QA (música, WhatsApp, PDF, mobile)

## Hosting
- **URL temporal:** https://homebyabba.gerardopezzuti.workers.dev
- **GitHub:** https://github.com/GPezzuti/homebyabba
- **Cloudflare Workers (static assets):** Workers Builds despliega en cada push a main
- **Plataforma:** Cloudflare Workers, HTML estático sin build step
- **Rama de producción:** main (política de rama única)

## Estado final
**PROYECTO COMPLETO.** Site live en homebyabba.com. DNS conectado 2026-06-27. QA pendiente (opcional — si Barbara lo pide).

## Toggle ES/EN (2026-07-05)
- Botón en el header (`#langToggle`) alterna todo el sitio entre español (default) e inglés.
- Motor de traducción: diccionario `window.I18N` + atributos `data-i18n*` + `setLang()`, todo inline en `index.html`. Persiste la preferencia en `localStorage`.
- Incluye: copy estático, las 3 modales de formulario (labels, placeholders, chips, selects), mensajes de WhatsApp/correo, widget de sonido, botón flotante de WhatsApp, barra móvil sticky.
- De paso se corrigió un drift: el commit anterior (PDF preview + labels "Ver") solo había tocado `deliverables/index.html`, nunca `index.html` (el que sirve Cloudflare) — quedó sin desplegar. Ya está aplicado y sincronizado en ambos archivos.
- Nota: los campos/chips del formulario se envían a Barbara en el idioma que el visitante elija (ES o EN) — ella responde en español siempre, solo cambia el idioma de la pregunta recibida.

## 2026-09-22: hardening
- SEO 32 a 95, HTML semántico, a11y, JSON-LD, YouTube diferido, `_headers`, `robots.txt`, `sitemap.xml`, `404.html`, renders nuevos de chapter1/chapter2.

## 2026-10-21: política de rama única
- Solo `main`. Rama local `claude/audit-2026-09` eliminada (ya estaba en main). La rama del bot `cloudflare/workers-autoconfig` sigue abierta (PR #1) hasta decidir sobre `wrangler.jsonc`.
