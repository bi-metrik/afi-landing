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

Brochure digital para AFI INTERNATIONAL GROUP S.A.S. Landing estatica (HTML + Tailwind) con propuesta de valor "Fortalecemos la confianza empresarial", servicios SARLAFT/SAGRILAFT/PTEE y credenciales. Dominio final: `afiinternationalgroup.com` (en proceso de propagacion DNS desde Hostinger hacia Vercel).

Proyecto independiente del workspace `afi/one` (operacion SARLAFT) y `afi/alma` (compliance CAM).

## Infraestructura

| Recurso | Valor |
|---------|-------|
| Repo GitHub | `bi-metrik/afi-landing` (migrado desde `metrik360/afi-landing` el 2026-04-22) |
| Dominio | `afiinternationalgroup.com` + `www.afiinternationalgroup.com` |
| Registrar | Hostinger (sigue ahi por ahora) |
| Vercel project | `afi-landing` en team `metrik-one` (recreado 2026-04-22; proyecto viejo estaba en cuenta ajena) |
| URL de Vercel | https://afi-landing-nine.vercel.app |
| Stack | HTML estatico + Tailwind CSS (CDN) |

## Alcance

Discovery: 2026-01-14. Brochure digital con secciones:
1. Hero + headline "Fortalecemos la confianza empresarial"
2. Servicios: SARLAFT/SAGRILAFT, SARLAFT sector financiero/transporte, PTEE, Compliance general, Auditoria
3. Sectores objetivo: financiero, automotor (CDAs), transporte, construccion, inversion, salud, educacion, tecnologia, inmobiliario
4. Credenciales: CEO + 50+ clientes con logos (36 activos al 2026-04-23)
5. Footer powered by MeTRIK

Especificacion completa en `docs/REQUIREMENTS_DOC.md` y sistema visual en `docs/DESIGN_SYSTEM.md`.

## Pendientes

### En cancha del admin DNS de Hostinger
- [ ] Aplicar 2 cambios DNS: `ALIAS @` → `cname.vercel-dns.com` y `CNAME www` → `cname.vercel-dns.com` (instrucciones ya entregadas)
- [ ] Confirmar si el subdominio `email.afiinternationalgroup.com` se usa activamente para correo (3 registros MX/TXT rechazados por Vercel por conflicto CNAME+MX)
- [ ] Confirmar si existe el DKIM `hostingermail-a._domainkey.email` (asimetria en la config visible)

### Decisiones pendientes
- [ ] ¿Transfer-in del dominio a Vercel (ownership) o mantener registrar en Hostinger? — pausado por riesgo de romper correo

### Housekeeping
- [ ] Logos 01-25 en Supabase (bucket `hcxyowictswpibzqxwyj/AFI`) — no tenemos credenciales de esa cuenta. Evaluar migrar a local o a bucket en cuenta `bi-metrik`
- [ ] Carpetas untracked `logos/Screenshot_*`, `logos/logos_procesados/`, `marca/` — decidir commit o ignore

### Completados 2026-04-22/23
- [x] Proyecto integrado a `proyectos/afi/landing/`
- [x] Repo migrado a `bi-metrik/afi-landing`
- [x] Proyecto Vercel recreado en team `metrik-one` con auto-deploy desde GitHub
- [x] Deploy live en https://afi-landing-nine.vercel.app
- [x] Dominios asignados al proyecto Vercel
- [x] 15 registros DNS replicados en Vercel
- [x] 11 logos nuevos agregados a seccion clientes (#26 al #36)

## Contexto critico

- **Origen del proyecto:** creado en enero 2026 dentro de iCloud (`~/Library/Mobile Documents/.../MéTRIK/Proyectos/afi-landing/`), asociado a cuenta GitHub `metrik360` y cuenta Vercel paralela. Toda la stack estaba en orgs viejas.
- **Migracion 2026-04-22:** folder → repo `bi-metrik/afi-landing` (plan B: nuevo repo + push historial, sin transfer nativo por falta de permisos admin en org viejo). 15 commits preservados.
- **Migracion Vercel 2026-04-23:** proyecto recreado en team `metrik-one`. El dominio `afiinternationalgroup.com` quedo bloqueado con error `domain_not_owned (403)` hasta que Mauricio lo libero en Team Settings de la cuenta vieja (no basta quitar del proyecto).
- **DNS pausado:** la migracion completa de nameservers a Vercel se pospuso para evitar riesgo con el correo Hostinger (~14 registros MX/SPF/DMARC/DKIM). Estrategia actual: mantener registrar + nameservers en Hostinger, solo cambiar 2 registros web.
- **Correo NO se toca:** MX, SPF, DMARC, DKIM del dominio viven en Hostinger y siguen funcionando igual.

## Ultimo avance

**Sesion:** 2026-04-23

Que se hizo:
- Recreacion del proyecto Vercel en team `metrik-one` (antiguo estaba en cuenta ajena, bloqueando dominio)
- Liberacion del dominio en cuenta Vercel vieja (Team Settings) + asignacion a nuevo proyecto
- Replicacion de 15 registros DNS en Vercel (A ftp, 10 CNAMEs correo Hostinger, 2 MX apex, 2 TXT SPF/DMARC + ALIAS * default + CAAs SSL)
- Agregados 10 logos nuevos a la seccion Clientes del landing (Taxis FM, Sumicarga, CDA Autocheck Montana, Cenda, Transcrudollano, CDA Morato, CDA Occidente, Certimotos La 44, CDA San German, CDA J&L Motors) — plus #26 Concesion Alto Magdalena agregado previamente
- Commit `c339756` pusheado a `bi-metrik/afi-landing/main`
- Entrega de instrucciones al admin DNS Hostinger para los 2 cambios web finales
- Pausa consciente en la migracion completa de nameservers (riesgo de romper correo)

Sesion previa 2026-04-22: integracion a estructura `proyectos/afi/landing/` + migracion repo GitHub.

## Decisiones clave

Ver `decisions.md` para historial completo.
