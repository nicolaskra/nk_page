# Landing page Smart Business — `nk_page`

Repo da landing page institucional em produção em `https://smartbusiness.ia.br/` (deploy via GitHub Pages, CNAME custom).

## Stack
- HTML/CSS/JS vanilla single-file (`index.html`) — sem framework, sem build step.
- Deploy: GitHub Pages (push pra `main` faz deploy automático).
- Fontes: Inter + Space Grotesk via Google Fonts (font-display: swap).
- Assets em `assets/logo/` (SVG + PNG) e `assets/social/` (OG cover).
- Analytics: Cloudflare Web Analytics (privacy-first) + GA4 (events).
- Form: Web3Forms (free tier, sem backend).

## Preview local
```bash
python -m http.server 8765
# abre http://localhost:8765/
```

## Estrutura do `index.html`
1. `<head>` — meta, OG, JSON-LD (Organization + WebSite + ProfessionalService + FAQPage), Cloudflare Web Analytics, GA4
2. `<style>` inline (refactor pra `assets/css/main.css` planejado pra Fase 2 do plano de melhoria)
3. `<body>`:
   - Skip link (A11y)
   - `#hero` split-screen com ETL pipeline animada (Extract → Transform → Load)
   - `#pains` (4 dores específicas)
   - `#sobre` (Nicolas com avatar/foto, bio, facts, LinkedIn)
   - `#services` (bento grid: Engenharia featured, Análise compact, Automação wide, Landing medium)
   - `#how` (3 etapas)
   - `#numeros` (prova social anônima: 4 KPIs + 6 setores + 2 citações)
   - `#why` (3 diferenciais: você fala comigo, código fica com você, provo antes de fechar)
   - `#stack` (ferramentas + setor financeiro)
   - `#exemplo` (mockup Power BI: insight banner + 4 KPIs + sparklines + bar chart + donut + tabela)
   - `#faq` (6 perguntas com `<details>`)
   - `#diagnostico` (form Web3Forms)
   - Brand signature
   - `#contact`
   - Sticky CTA mobile + Float WhatsApp desktop

## Pendências de configuração
Após primeiro deploy, substituir placeholders:
- `YOUR_WEB3FORMS_ACCESS_KEY` — gerar em https://web3forms.com/ com email contato@smartbusiness.ia.br
- `YOUR_CLOUDFLARE_BEACON_TOKEN` — cadastrar em https://dash.cloudflare.com/?to=/:account/web-analytics
- `G-XXXXXXXXXX` (2x) — criar property em https://analytics.google.com/

## Convenções
- Bilíngue via `data-pt`/`data-en` em qualquer string visível. `setLang('pt'|'en')` cuida da troca.
- Inputs com placeholder bilíngue usam `data-pt-placeholder`/`data-en-placeholder`.
- IDs de seção em kebab-case ASCII.
- CTAs internos pro form sempre `href="#diagnostico"` (instrumentados pra tracking).
- WhatsApp links sempre `https://wa.me/5567992438271?text=...` (prefill dinâmico via JS no hover).

## Tracking de eventos disponível
Wrapper `trackEvent(name, params)` no JS — no-opa se gtag não carregou.
Eventos atuais:
- `cta_diagnostico_click` (params: `section`)
- `wa_click` (params: `section`)
- `form_submit_success` (params: `source`)
- `form_submit_error` (params: `source`)

## Workflows
- `.github/workflows/lighthouse.yml` — Lighthouse CI em PRs, comenta scores
- `.github/workflows/links.yml` — lychee link checker em PRs + cron semanal

## Checklist de PR
- [ ] Testar em mobile real (360px, 414px) — não confiar só no DevTools
- [ ] Recarregar com Ctrl+Shift+R (limpa cache)
- [ ] Verificar form em PT e EN
- [ ] Verificar prefill WhatsApp em hover de cada seção
- [ ] Lighthouse mobile ≥ 90 performance, ≥ 95 a11y, ≥ 95 SEO
- [ ] Conferir Schema.org em https://validator.schema.org/

## Plano canônico
`C:\Users\Nicolas\.claude\plans\quero-que-voce-analise-quizzical-pie.md`
Briefing atualizado: `BRIEFING.md`
