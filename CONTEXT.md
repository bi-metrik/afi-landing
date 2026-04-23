---
proyecto: AFI — Landing page
slug: landing
cliente: afi
linea: [23] Projects
workspace_one: false
estado: activo
inicio: 2026-01-13
---

# AFI — Landing page

## Resumen ejecutivo

Brochure digital para AFI INTERNATIONAL GROUP S.A.S. Landing estatica (HTML + Tailwind) con propuesta de valor "Fortalecemos la confianza empresarial", servicios SARLAFT/SAGRILAFT/PTEE y credenciales. Deploy en Vercel con subdominio `afi.metrik.com.co`.

Proyecto independiente del workspace `afi/one` (operacion SARLAFT) y `afi/alma` (compliance CAM).

## Infraestructura

| Recurso | Valor |
|---------|-------|
| Repo GitHub | `bi-metrik/afi-landing` (transferido desde `metrik360/afi-landing` el 2026-04-22) |
| Dominio | afi.metrik.com.co |
| Vercel project | `afi-landing` (org `team_tesWc3Bv7K2siNox1IbWtO2J`) |
| Stack | HTML estatico + Tailwind CSS |

## Alcance

Discovery: 2026-01-14. Brochure digital con secciones:
1. Hero + headline "Fortalecemos la confianza empresarial"
2. Servicios: SARLAFT/SAGRILAFT, SARLAFT sector financiero/transporte, PTEE, Compliance general, Auditoria
3. Sectores objetivo: financiero, automotor (CDAs), transporte, construccion, inversion, salud, educacion, tecnologia, inmobiliario
4. Credenciales: CEO + 50+ clientes con logos
5. Footer powered by MeTRIK

Especificacion completa en `docs/REQUIREMENTS_DOC.md` y sistema visual en `docs/DESIGN_SYSTEM.md`.

## Pendientes

- [ ] Verificar deploy Vercel sigue funcionando tras transferencia de repo (puede requerir re-link al nuevo remote `bi-metrik/afi-landing`)
- [ ] Limpiar git status: `.DS_Store` tracked (borrarlo y agregar a .gitignore) + carpetas untracked `logos/` y `marca/` (decidir commit o ignore)
- [ ] Revisar si `afi.metrik.com.co` sigue apuntando al proyecto Vercel correcto tras el move

## Contexto critico

- **Transferencia 2026-04-22:** repo migrado de org `metrik360` (sin permisos admin para transfer nativo) a `bi-metrik` creando repo nuevo y pusheando historial completo. 15 commits preservados. Vercel conserva project ID antiguo — puede requerir reconectar al nuevo repo
- **iCloud → local:** proyecto movido desde `~/Library/Mobile Documents/.../MéTRIK/Proyectos/afi-landing` a la estructura nueva `proyectos/afi/landing/` el 2026-04-22
- **Relacion con otros proyectos AFI:** independiente de `afi/one` (workspace SARLAFT interno) y `afi/alma` (compliance CAM). Comparte solo identidad del cliente

## Ultimo avance

**Sesion:** 2026-04-22

Que se hizo:
- Proyecto integrado a la estructura `proyectos/afi/landing/` desde iCloud
- Repo GitHub transferido de `metrik360/afi-landing` a `bi-metrik/afi-landing` (plan B: repo nuevo + push de historial completo, sin transfer nativo por falta de permisos admin)
- Remote local actualizado a `bi-metrik/afi-landing`
- 15 commits de historial preservados

Sesion previa 2026-01-28: ultimo cambio funcional — contador clientes 18+ → 50+

## Decisiones clave

| Fecha | Decision | Contexto |
|-------|----------|----------|
| 2026-04-22 | Integrar landing AFI a estructura `proyectos/afi/landing/` | Proyecto vivia en iCloud desde enero 2026, se mueve a sistema actual post-reestructuracion 2026-04-12 |
| 2026-04-22 | Migracion de org GitHub: `metrik360` → `bi-metrik` (plan B) | Sin permisos admin para transfer nativo. Repo nuevo + push preservando historial. Visibilidad publica conservada |
