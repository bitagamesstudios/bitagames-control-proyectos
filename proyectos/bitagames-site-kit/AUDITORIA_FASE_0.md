# AUD-001 — Auditoría inicial BITAGAMES SITE KIT
Fecha: 2026-11-10 · Estado: preliminar · Versión: planificación 0.1

## Arquitectura aprobada
- Biblioteca modular interna y Builder futuro separados. Sitios exportables y autónomos.
- Monorepo ligero con `packages/core`, `design-tokens`, `ui`, `sections`, `catalog`, `marketing`, `seo`, `templates` y `apps/playground`, `apps/showcase`.
- Cinco niveles: elementos → componentes → secciones → páginas → sitios.
- Configuración con registro de variantes y esquema versionado; temas con design tokens.
- Datos separados de interfaz; JSON primero, adaptadores a API/CMS después.
- Seguridad, accesibilidad, rendimiento, SEO y responsive desde el inicio.
- NO implementar todos los componentes ni comenzar Builder en Fase 0.

## Fuentes verificadas
| Proyecto | GitHub privado | Entradas árbol Git | Evidencia |
|---|---|---:|---|
| Amparo's | [amparos-floristeria-web](https://github.com/bitagamesstudios/amparos-floristeria-web) | 121 | index.html v1.6.5 (~891 KB) vs docs v1.8.01 del 10/11/2026 |
| Calas | [floristeria-calas-web](https://github.com/bitagamesstudios/floristeria-calas-web) | 105 | README V1.25; scripts y CSS separados |
| Cariguaná | [cariguana-web](https://github.com/bitagamesstudios/cariguana-web) | 62 | código raíz y carpeta Cariguana_Web_v0.4; formularios demo |

Conteos incluyen archivos y carpetas; no se han ejecutado pruebas en navegador.

## Matriz de componentes
Leyenda: ✓ identificado; ◐ parcialmente identificado/no verificado; — no identificado.
| Componente | Amparo's | Calas | Cariguaná | Prioridad |
|---|---|---|---|---|
| Header, Footer, Hero | ✓ | ✓ | ✓ | P1 |
| Carrusel campañas | ✓ | ✓ | — | P1 |
| Minitarjetas | ✓ | ✓ | ◐ | P2 |
| Product Card y Catálogo | ✓ | ✓ | ✓ | P1 |
| Filtros | ✓ | ✓ | ✓ | P1 |
| Buscador | ✓ | ✓ | ◐ | P1 |
| Favoritos | ✓ | ◐ | — | P2 |
| Mi selección | — | — | ✓ | P2 |
| Zoom/Lightbox | ✓ | ✓ | ✓ | P1 |
| WhatsApp | ✓ | ✓ | — | P1 |
| Formularios | ◐ | ✓ | ✓ | P2 |
| Idiomas ES/EN | ✓ | — | — | P2 |
| GA4/UTMs | ✓ | ◐ | — | P2 |
| SEO | ✓ | ✓ | ◐ | P1 |
| Galería editorial | ◐ | ✓ | ✓ | P2 |
| Responsive | ✓ | ✓ | ✓ | P1 |

## Inventario focalizado
### Amparo's
`index.html`, `docs/ARQUITECTURA.md`, `docs/INTEGRACIONES.md`, `docs/ESTADO_WEB_v1.8.01_2026-11-10.md`, `docs/QA_CHECKLIST.md`, `CHANGELOG.md`. Conciliar versión código, ZIP último, producción Cloudflare y registros.
### Calas
`js/main.js` (WhatsApp, lightbox, carruseles), `js/catalogo.js` (filtros y búsqueda), `js/campanas.js`, `css/style.css`, `css/mobile-fixes.css`, `catalogo.html`, `README.md`.
### Cariguaná
`Cariguana_Web_v0.4/assets/app.js`, `Cariguana_Web_v0.4/assets/styles.css`, `assets/app.js`, `assets/styles.css`, `producto.html`, `seleccion.html`, `docs/plan-tecnico-v03.md`. Decidir versión canónica; no asumir formularios operativos.

## Hallazgos / riesgos
1. Amparo's: gran archivo HTML monolítico y discrepancia de versiones; extraer lógica sin modificar producción.
2. Calas: imágenes y textos comerciales hardcodeados dentro de rotadores; desacoplar.
3. Cariguaná: arreglo PRODUCTS en JavaScript, estado local de selección y formularios demo; separar datos y lógica.
4. IDs de analítica, teléfonos, API keys y recursos de clientes nunca deben formar parte del Kit. Configuraciones separadas y secretos fuera del repositorio.
5. Analytics web, atribución UTM y estadísticas externas de redes son ámbitos diferentes.

## Orden de ejecución / checklist
- [x] Aprobar arquitectura
- [x] Localizar los tres repositorios y árboles
- [x] Inventario inicial y matriz preliminar
- [ ] Conciliar versiones, backups, Cloudflare y archivos reales
- [ ] Revisar acoplamientos y dependencias de cada módulo
- [ ] Comparar y probar en navegador responsive/teclado/errores
- [ ] Definir contratos y criterios de extracción para los primeros componentes
- [ ] Crear repositorio privado independiente `bitagames-site-kit`
- [ ] Implementar MVP en Fase 1 tras aprobación de auditoría

## Roadmap
F0 Auditoría → F1 Arquitectura v0.1.0 → F2 tokens/UI v0.2.0 → F3 catálogo v0.3.0 → F4 marketing v0.4.0 → F5 plantillas v0.5.0 → F6 estabilización → F7 Builder.

## Bitácora
2026-11-10: arquitectura aprobada; AUD-001 creado en Notion y documentado provisionalmente en el repositorio de control. Sin componentes implementados ni cambios a las webs piloto.
