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
- [x] Conectar homebyabba.com como dominio custom en Cloudflare Pages + DNS (2026-06-27)
- [x] Toggle ES/EN + traducción completa del sitio, default español (2026-07-05)
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

## Estado final
**PROYECTO COMPLETO.** Site live en homebyabba.com. DNS conectado 2026-06-27. QA pendiente (opcional — si Barbara lo pide).

## Toggle ES/EN (2026-07-05)
- Botón en el header (`#langToggle`) alterna todo el sitio entre español (default) e inglés.
- Motor de traducción: diccionario `window.I18N` + atributos `data-i18n*` + `setLang()`, todo inline en `index.html`. Persiste la preferencia en `localStorage`.
- Incluye: copy estático, las 3 modales de formulario (labels, placeholders, chips, selects), mensajes de WhatsApp/correo, widget de sonido, botón flotante de WhatsApp, barra móvil sticky.
- De paso se corrigió un drift: el commit anterior (PDF preview + labels "Ver") solo había tocado `deliverables/index.html`, nunca `index.html` (el que sirve Cloudflare) — quedó sin desplegar. Ya está aplicado y sincronizado en ambos archivos.
- Nota: los campos/chips del formulario se envían a Barbara en el idioma que el visitante elija (ES o EN) — ella responde en español siempre, solo cambia el idioma de la pregunta recibida.
