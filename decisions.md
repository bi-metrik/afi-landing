# Decisiones — AFI Landing

| Fecha | Decision | Contexto |
|-------|----------|----------|
| 2026-04-22 | Integrar landing AFI a estructura `proyectos/afi/landing/` | Proyecto vivia en iCloud desde enero 2026, se mueve al sistema actual post-reestructuracion 2026-04-12 |
| 2026-04-22 | Migracion de org GitHub: `metrik360` → `bi-metrik` (plan B) | Sin permisos admin para transfer nativo. Repo nuevo + push preservando historial completo. Visibilidad publica conservada |
| 2026-04-23 | Recrear proyecto Vercel en team `metrik-one` | El proyecto Vercel original estaba en cuenta ajena (inaccesible desde `bi-metrik`). Creacion limpia en team correcto |
| 2026-04-23 | Pausar migracion completa de nameservers a Vercel | Riesgo alto de romper correo Hostinger (~14 registros). Mantener registrar y NS en Hostinger; solo cambiar 2 registros web |
| 2026-04-23 | No transferir ownership del dominio por ahora | Transfer-in a Vercel implica costo de renovacion + ventana de 5-7 dias. Se pospone hasta que haya claridad sobre migracion de correo |
| 2026-04-23 | Logos locales en vez de bucket Supabase para los nuevos #26-#36 | Bucket antiguo `hcxyowictswpibzqxwyj` esta en cuenta Supabase ajena sin credenciales. Path local es simple, versionado en git, deployado por Vercel |
