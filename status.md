# LP Barbara — Status

**Última actualización:** 2026-06-22

## Estado: EN PROGRESO

### Completado ✅
- [x] Análisis de assets y template HTML
- [x] Configuración Lovable MCP (`claude mcp add --transport http lovable`)
- [x] Compresión de 5 imágenes (7MB → ~300KB c/u)
- [x] Sustitución de 6 imágenes base64 placeholder con fotos reales de Barbara
- [x] Remoción de PDF embedded (7.6MB) → handler con Google Drive placeholder
- [x] HTML final: 3.39MB, todas las secciones verificadas
- [x] Estructura de proyecto creada

### Completado ✅ (continuación)
- [x] GitHub repo creado: https://github.com/GPezzuti/homebyabba
- [x] index.html pushed a GitHub (main branch)
- [x] Cloudflare Pages deploy: https://homebyabba.gerardopezzuti.workers.dev ✅ LIVE

### Pendiente ⏳
- [x] PDF URL cargada: https://drive.google.com/file/d/1JK2_CO_CnNkYNDlGt1raMT7dvJZ0XP1b/view — abre en vista previa (no descarga)
- [x] Dominio homebyabba.com adquirido (2026-06-25)
- [ ] Conectar homebyabba.com como dominio custom en Cloudflare Pages + DNS
- [ ] Prueba final de QA (música, WhatsApp, PDF, mobile)

## Hosting
- **URL temporal:** https://homebyabba.gerardopezzuti.workers.dev
- **GitHub:** https://github.com/GPezzuti/homebyabba
- **Cloudflare Pages:** conectado a GitHub, auto-deploy en cada push a main
- **Plataforma:** Cloudflare Pages (static HTML, no build step)

## Flujo de actualización (para cuando llegue la URL del PDF)
1. Editar `deliverables/index.html` → reemplazar `TODO_REPLACE_WITH_GOOGLE_DRIVE_URL`
2. Push al repo: `homebyabba-deploy` en scratchpad o directamente en el repo
3. Cloudflare auto-deploya en ~30 segundos

## Blocker actual
**Ninguno.** PDF live, dominio adquirido. Siguiente: conectar DNS en Cloudflare Pages.
