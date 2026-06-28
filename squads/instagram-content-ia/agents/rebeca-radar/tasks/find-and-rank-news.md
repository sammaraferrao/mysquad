---
task: "Find and Rank News"
order: 1
input: |
  - research_focus: Tema ou foco de pesquisa definido pelo usuário (ex: "lançamentos de ferramentas de IA", "automação de WhatsApp", "tendências de IA para pequenas empresas")
output: |
  - news_options: Lista ranqueada de 3-5 opções de pauta com briefing completo
---

# Find and Rank News

Pesquisa e ranqueia as melhores pautas do momento com base no foco definido pelo usuário. O objetivo é entregar opções de conteúdo que tenham ângulo original, relevância real para empreendedoras que querem implementar IA, e potencial de engajamento comprovado pelos padrões da conta.

## Process

1. **Lê o foco de pesquisa** em `squads/instagram-content-ia/output/research-focus.md`. Se não especificado, usa escopo amplo: lançamentos de IA relevantes para negócios, casos de automação, tendências do mercado brasileiro.

2. **Pesquisa as fontes** usando web_search com 2-3 buscas diferentes. Fontes de referência: The Verge, TechCrunch, Veja Tech, MIT Technology Review, Reddit r/LocalLLaMA, Product Hunt, Twitter/X de criadores de nicho. Para cada resultado relevante, usa web_fetch para ler o conteúdo completo antes de incluir.

3. **Filtra pelo critério de relevância:** A notícia ou tendência precisa passar neste filtro antes de entrar na lista:
   - Impacto direto na empreendedora de 30-40 anos que usa IA no negócio?
   - Tem um ângulo que ainda não foi explorado nos últimos 30 dias?
   - Existe analogia cultural ou cotidiana possível?
   - O timing é bom (últimos 14 dias ou tema perene com gancho atual)?

4. **Seleciona até 5 opções** e as ranqueia de 1 (maior potencial) a 5 (menor prioridade). Critérios de ranqueamento: potencial de engajamento dado os padrões da conta + originalidade do ângulo + fit com os pilares de conteúdo.

5. **Monta o briefing** no formato especificado abaixo e salva em `squads/instagram-content-ia/output/news-options.md`.

## Output Format

```
# Opções de Pauta — [data]

Foco da pesquisa: [foco definido pelo usuário]

---

## Opção 1 — [Título da pauta]

**Pilar:** [Implementação / Posicionamento / Bastidores / Prova Social]
**Fonte:** [URL ou publicação]
**Por que agora:** [Timing — lançamento recente, evento, comportamento emergente]
**Relevância para o público:** [Como isso impacta a empreendedora que quer implementar IA]
**Ângulo sugerido:** [O que dizer que ainda não foi dito — o diferencial]
**Formato recomendado:** [Carrossel de analogia / Carrossel educativo / Reel de alcance / Post de posicionamento]
**Hook sugerido:** [Uma linha de gancho baseada nos padrões da conta]

---

## Opção 2 — [Título]
[mesma estrutura]

---

[até Opção 5]
```

## Output Example

```
# Opções de Pauta — 2026-06-28

Foco da pesquisa: ferramentas de IA para automação de atendimento no WhatsApp

---

## Opção 1 — Meta anuncia integração nativa de IA no WhatsApp Business

**Pilar:** Implementação
**Fonte:** https://techcrunch.com/2026/06/25/meta-whatsapp-ai-business/
**Por que agora:** Lançamento anunciado há 3 dias, ainda pouco coberto em português
**Relevância para o público:** A maioria das empreendedoras usa WhatsApp como canal principal de atendimento. Integração nativa reduz a barreira de entrada para automação.
**Ângulo sugerido:** Não é sobre o lançamento da Meta — é sobre o que muda para quem já usa Evolution API hoje. O mercado vai se dividir: quem continua com stack própria e quem migra para o nativo.
**Formato recomendado:** Carrossel educativo (Mito vs Realidade)
**Hook sugerido:** "A Meta integrou IA ao WhatsApp Business. Isso muda tudo para quem já automatizava — mas não da forma que estão dizendo."

---

## Opção 2 — Pesquisa mostra que 67% das PMEs brasileiras ainda não usaram nenhuma ferramenta de IA

**Pilar:** Posicionamento
**Fonte:** https://sebrae.com.br/pesquisa-ia-pme-2026
**Por que agora:** Dado novo, lançado essa semana, ainda sem cobertura qualificada
**Relevância para o público:** A empreendedora que segue a conta está na vanguarda — esse dado valida que ela está à frente.
**Ângulo sugerido:** 67% não é problema de tecnologia, é problema de ponto de partida. Quem sabe por onde começar implementa. Quem não sabe fica testando ferramenta para sempre.
**Formato recomendado:** Reel de alcance (30-45s) com o dado como abertura
**Hook sugerido:** "67% das empresas brasileiras ainda não usaram nenhuma ferramenta de IA em 2026. O gargalo não é falta de ferramenta — é falta de por onde começar."
```

## Quality Criteria

- [ ] Mínimo 3 opções, máximo 5
- [ ] Cada opção tem todos os 7 campos preenchidos (pilar, fonte, por que agora, relevância, ângulo, formato, hook)
- [ ] Ângulo sugerido é genuinamente original — não é resumo da notícia
- [ ] Hook sugerido segue os padrões comprovados da conta (acusação direta, diagnóstico, analogia, revelação ou resultado próprio)
- [ ] Nenhum dado citado sem fonte verificável
- [ ] Pelo menos uma opção é carrossel de analogia (padrão de maior engajamento)

## Veto Conditions

Rejeitar e refazer se:
1. Alguma opção não tem ângulo original — é só descrição da notícia sem perspectiva nova
2. Algum dado ou estatística foi gerado sem fonte citada (inventado)
