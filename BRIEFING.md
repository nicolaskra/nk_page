# BRIEFING — Smart Business Landing Page

Data inicial: 23/03/2026  
Atualização identidade visual: 17/04/2026 — logo oficial integrada  
Projeto: Landing page institucional para prospecção B2B

---

## Identidade Visual oficial (17/04/2026)

Logo oficial aplicada em `assets/logo/`. Brand guide canônico em:
`OneDrive - NK SMART BUSINESS/SMART_BUSINESS/VISUAL/BRAND_GUIDE.md`

- **Símbolo:** Cérebro central + rede de nós em 2 órbitas concêntricas (BI + automação + escalabilidade)
- **Nome da marca:** Smart Business (anteriormente "NK Smart Business")
- **Paleta:** Navy `#080d1a` (bg), Navy institucional `#0F2A6B`, Gold `#F5C518` (CTA/accent)
- **Tipografia web:** Inter (corpo) + Space Grotesk (display)
- **Tipografia da logomarca:** Itálico bold geométrico (fornecido como PNG)
- **Ferramentas exibidas:** GitHub, Excel, Power BI, Python, SQL
- **Subtítulo:** Data Engineer · Data Analyst · AI Automation

---

## Briefing de Produto

| Item | Decisão |
|---|---|
| Público-alvo | Empresas (B2B), qualquer segmento |
| Objetivo principal | Gerar contato via WhatsApp |
| Portfólio | Não incluído nesta versão |
| Idioma | Bilíngue: PT / EN com toggle |
| Serviços âncora | Análise de Dados, Engenharia de Dados, Automação com IA |

---

## Serviços

### 1. Análise de Dados
Transformação de dados brutos em insights acionáveis.  
Stack: Power BI, Excel, KPIs, Dashboards.

### 2. Engenharia de Dados
Pipelines, ETL e bancos de dados estruturados.  
Stack: SQL, Python, ETL, Banco de Dados.

### 3. Automação com IA
Eliminação de tarefas repetitivas com automações inteligentes.  
Stack: Python, IA, Automação, Planilhas.

---

## Tagline aprovada

> PT: *"Dados que decidem. Automação que transforma."*  
> EN: *"Data that decides. Automation that transforms."*

---

## Diferenciais comunicados

1. **Solução Completa** — Da coleta ao dashboard, sem precisar contratar múltiplos profissionais
2. **Foco em Resultado** — Soluções práticas e alinhadas ao negócio
3. **Tecnologia Atual** — Ferramentas de mercado combinadas com IA

---

## Decisões técnicas

- HTML/CSS/JS puro — sem frameworks
- Canvas API para animação de rede neural
- Toggle PT/EN via atributos `data-pt` / `data-en`
- CTA principal: link direto para WhatsApp (`wa.me`)
- Responsivo via CSS Grid + media queries
- Google Fonts: Rajdhani + Inter

---

## Contato atual (em produção)

- WhatsApp: +55 67 99243-8271
- E-mail: contato@smartbusiness.ia.br
- LinkedIn: https://www.linkedin.com/in/nicolaskleincg/
- Instagram: @smartbusiness_cg

---

## Rodada de melhorias 17/05/2026 — Conversão + UX + SEO

Plano canônico: `C:\Users\Nicolas\.claude\plans\quero-que-voce-analise-quizzical-pie.md`

### Fase 0 — Baseline (concluída 17/05)
- Removido `nk-smart-business.html` (era cópia byte-a-byte do `index.html`).
- Estrutura visual mantida; HTML continua single-file (refactor pra `assets/css|js` planejado pra Fase 2).

### Fase 1 — Conversão (concluída 17/05, aguardando keys)
Adicionado:
- **Seção `#numeros`** (prova social anônima): 4 KPIs (9+ clientes, 10+ unidades DRE, 20+ pipelines, 100% fechamentos no prazo), 6 chips de setor, 2 citações anônimas.
- **Seção `#diagnostico`** (form Web3Forms): nome, email, empresa, telefone (opcional), desafio. Honeypot anti-spam. Bilíngue PT/EN. Status inline (sem redirect).
- **Sticky CTA bar** mobile: 2 botões (Pedir diagnóstico + WhatsApp); esconde no desktop; respeita `safe-area-inset-bottom`.
- **CTAs WhatsApp reduzidos de 6 → 4** instâncias estratégicas (float-wa, hero secundário, sticky bar, contact). Todos com `?text=Olá! Vim do site smartbusiness.ia.br` prefill pra ajudar tracking manual.
- **CTAs primários (hero, nav, pains)** agora apontam pro `#diagnostico` (form), não mais pro WhatsApp.
- **Cloudflare Web Analytics** stub adicionado no `<head>` (1 linha, sem cookies, sem banner LGPD).
- **Meta tags extras**: `og:site_name`, `og:locale`, `og:locale:alternate`, `meta author`.

### AÇÕES MANUAIS PENDENTES

1. **Form (Web3Forms)** — ✅ ATIVO desde 17/05/2026:
   - Access key `e3b9a0e9-a10c-4c24-82af-a1e24b616129` vinculada ao domain `smartbusiness.ia.br`
   - Form posta direto em `https://api.web3forms.com/submit`
   - Submissões chegam em `contato@smartbusiness.ia.br` sem precisar de ativação manual
   - (FormSubmit.co foi tentado antes mas estava com HTTP 522 outage)

2. **Cloudflare Web Analytics** — DESABILITADO (stub comentado no `<head>`):
   - Pra ativar quando quiser: criar zona em https://dash.cloudflare.com/?to=/:account/web-analytics
   - "Add a site" → `smartbusiness.ia.br` → copiar token
   - Descomentar bloco no `<head>` (procurar `<!-- Cloudflare Web Analytics`) e substituir `YOUR_TOKEN`
   - Free, sem cookies, sem banner LGPD

3. **GA4 (Google Analytics)** — DESABILITADO (stub comentado no `<head>`):
   - Pra ativar quando quiser: criar property em https://analytics.google.com/
   - Copiar measurement ID (formato `G-XXXXXXXXXX`)
   - Descomentar bloco no `<head>` (procurar `<!-- GA4`) e substituir `G-XXXXXXXXXX` (2 ocorrências)
   - Necessário pra eventos `cta_diagnostico_click`, `wa_click`, `form_submit_success` etc serem registrados
   - Sem GA4, eventos disparam pra `window.gtag` stub que no-opa (sem erro de console)

### Stack atual (após Fase 1)
- HTML/CSS/JS puro single-file (`index.html`, ~1265 linhas) — refactor pra arquivos separados na Fase 2.
- Canvas API para neural-network animation (a otimizar pra mobile na Fase 3).
- Toggle PT/EN via `data-pt`/`data-en` + agora também `data-pt-placeholder`/`data-en-placeholder` para inputs.
- Google Fonts: Inter + Space Grotesk (subset pendente Fase 3).
- Web3Forms: captura de lead sem backend.
- Cloudflare Web Analytics: métricas sem cookies.

### Fases pendentes
- **Fase 2**: refactor CSS/JS em arquivos próprios + mockup Figma + hierarquia visual + micro-interações.
- **Fase 3**: subset de fontes, pausar neural-canvas em mobile, WebP, OG image dedicada 1200x630, sitemap+robots, Schema enriquecido.
- **Fase 4**: GitHub Action Lighthouse CI, lychee link checker, CLAUDE.md do repo, UptimeRobot.
- **Fase 5**: /security-review, /simplify, /review, lighthouse comparativo.
