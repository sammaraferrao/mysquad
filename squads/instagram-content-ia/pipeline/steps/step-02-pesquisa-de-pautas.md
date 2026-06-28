---
execution: subagent
agent: squads/instagram-content-ia/agents/rebeca-radar
inputFile: squads/instagram-content-ia/output/research-focus.md
outputFile: squads/instagram-content-ia/output/news-options.md
model_tier: fast
---

# Step 02: Pesquisa de Pautas

## Context Loading

Load these files before executing:
- `squads/instagram-content-ia/output/research-focus.md` — foco de pesquisa definido pelo usuário
- `squads/instagram-content-ia/pipeline/data/research-brief.md` — contexto da conta, público e padrões de engajamento
- `_opensquad/_memory/company.md` — voz da marca, vocabulário e pilares de conteúdo

## Instructions

### Process

1. Lê o foco de pesquisa do usuário em `research-focus.md`. Se não houver foco específico, busca pautas amplas de IA para negócios com timing atual.

2. Executa a task `find-and-rank-news.md`: pesquisa, filtra por relevância para o público-alvo (empreendedora 30-40 anos que quer implementar IA), e gera lista ranqueada de 3-5 opções.

3. Garante que cada opção tem ângulo original — não é apenas descrição da notícia. O ângulo é o que transforma informação em conteúdo que vale publicar.

4. Salva o resultado em `news-options.md` no formato especificado na task.

## Output Format

```
# Opções de Pauta — [data]

Foco da pesquisa: [foco do usuário]

---

## Opção 1 — [Título]
**Pilar:** [pilar de conteúdo]
**Fonte:** [URL ou publicação]
**Por que agora:** [timing]
**Relevância para o público:** [conexão com a empreendedora]
**Ângulo sugerido:** [o diferencial]
**Formato recomendado:** [carrossel ou reel]
**Hook sugerido:** [primeira linha]

---

[até Opção 5]
```

## Output Example

```
# Opções de Pauta — 2026-06-28

Foco da pesquisa: automação de WhatsApp

---

## Opção 1 — Meta anuncia integração nativa de IA no WhatsApp Business

**Pilar:** Implementação
**Fonte:** https://techcrunch.com/2026/06/25/meta-whatsapp-ai-business/
**Por que agora:** Lançamento há 3 dias, pouco coberto em português
**Relevância para o público:** A maioria das empreendedoras usa WhatsApp como canal principal
**Ângulo sugerido:** O mercado vai se dividir: quem usa a integração nativa vs. quem mantém stack própria. Cada escolha tem um custo diferente
**Formato recomendado:** Carrossel educativo (Mito vs Realidade) — 8 slides
**Hook sugerido:** "A Meta integrou IA ao WhatsApp Business. O mercado vai se dividir em dois grupos. Você quer saber em qual vai estar."

---

## Opção 2 — 67% das PMEs brasileiras ainda não usaram IA em 2026

**Pilar:** Posicionamento
**Fonte:** https://sebrae.com.br/pesquisa-ia-pme-2026
**Por que agora:** Dado recente, sem cobertura qualificada ainda
**Relevância para o público:** Valida que quem segue a conta está à frente da maioria
**Ângulo sugerido:** O gargalo não é ferramenta, é ponto de partida. 67% travado não é tecnofobia, é falta de direção clara
**Formato recomendado:** Reel de alcance — 30 segundos com o dado como abertura
**Hook sugerido:** "67% das empresas brasileiras não usaram nenhuma IA em 2026. O problema não é a ferramenta."
```

## Veto Conditions

Rejeitar e refazer se:
1. Alguma opção não tem ângulo original (é só resumo da notícia sem perspectiva)
2. Algum dado citado não tem fonte verificável

## Quality Criteria

- [ ] 3-5 opções entregues, ranqueadas
- [ ] Cada opção tem os 7 campos preenchidos
- [ ] Pelo menos 1 opção é carrossel de analogia
- [ ] Nenhum dado sem fonte
