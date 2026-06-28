---
execution: subagent
agent: squads/instagram-content-ia/agents/camila-criadora
inputFile: squads/instagram-content-ia/output/selected-news.md
outputFile: squads/instagram-content-ia/output/angles.md
model_tier: powerful
---

# Step 04: Geração de Ângulos

## Context Loading

Load these files before executing:
- `squads/instagram-content-ia/output/selected-news.md` — pauta selecionada pelo usuário com briefing completo
- `squads/instagram-content-ia/pipeline/data/tone-of-voice.md` — os 6 tons disponíveis para o conteúdo
- `squads/instagram-content-ia/pipeline/data/research-brief.md` — padrões de engajamento comprovados da conta
- `squads/instagram-content-ia/pipeline/data/anti-patterns.md` — o que não fazer
- `_opensquad/_memory/company.md` — voz da marca e vocabulário

## Instructions

### Process

1. Lê a pauta selecionada e extrai: tema central, dado principal, público que mais se reconhece nele, e qual tipo de conteúdo o ângulo da Rebeca sugeria.

2. Executa a task `generate-angles.md`: gera 3 ângulos genuinamente diferentes com hooks distintos. Os 3 não podem usar o mesmo tipo de hook.

3. Para cada ângulo, define claramente: o hook exato (primeira linha), o tipo de hook (dos 5 padrões da conta), o tom (1-6), o formato específico do conteúdo, a aposta criativa em 1 frase.

4. Verifica: nenhum hook usa travessão, nenhum hook é interrogação retórica, pelo menos 1 ângulo é analogia cultural ou bastidores reais.

5. Salva em `angles.md` e termina com a pergunta de seleção para o usuário.

## Output Format

```
# Ângulos de Conteúdo — [tema]

---

## Ângulo 1 — [Nome descritivo]

**Hook:** [primeira linha exata]
**Tipo de hook:** [tipo dos 5 padrões]
**Tom:** Tom [N] — [nome do tom]
**Formato:** [formato específico + estrutura]
**Aposta criativa:** [1 frase sobre o diferencial]
**Por que pode funcionar:** [2-3 linhas de justificativa]

---

## Ângulo 2 — [Nome]
[mesma estrutura]

---

## Ângulo 3 — [Nome]
[mesma estrutura]

---

Qual ângulo você quer desenvolver? (1, 2 ou 3)
```

## Output Example

```
# Ângulos de Conteúdo — Meta IA no WhatsApp Business

---

## Ângulo 1 — Dois grupos, duas escolhas

**Hook:** A Meta integrou IA ao WhatsApp Business. O mercado vai se dividir em dois grupos. Você quer saber em qual vai estar.
**Tipo de hook:** Diagnóstico de dor + antecipação
**Tom:** Tom 3 — Diagnóstico Honesto
**Formato:** Carrossel educativo (Mito vs Realidade) — 8 slides
**Aposta criativa:** Usar o lançamento como gatilho para mostrar que a decisão real é estratégica, não técnica — quando usar o nativo vs. quando manter stack própria
**Por que pode funcionar:** O público usa WhatsApp como canal principal. Qualquer novidade que afete o canal é relevante. O ângulo de "dois grupos" cria identificação imediata.

---

## Ângulo 2 — Time de futebol e atendimento automatizado

**Hook:** Um time de futebol que joga bem tem uma coisa que quase nenhum atendimento automatizado tem.
**Tipo de hook:** Ponte cultural (esporte + IA)
**Tom:** Tom 2 — Tradutora Cultural
**Formato:** Carrossel de analogia — 8 slides (treinador = orquestrador, jogadores = agentes, goleiro = escalonamento para humano)
**Aposta criativa:** Analogia que explica arquitetura de automação de WhatsApp de forma visual e que qualquer empreendedora entende sem jargão
**Por que pode funcionar:** Analogia de futebol gerou 36,4% de engagement rate na conta. Lançamento da Meta cria timing perfeito para ensinar arquitetura de automação.

---

## Ângulo 3 — O que eu mudaria se montasse do zero hoje

**Hook:** Se eu montasse meu atendimento automatizado do zero hoje, não usaria Evolution API na primeira versão.
**Tipo de hook:** Resultado próprio
**Tom:** Tom 4 — Bastidores Reais
**Formato:** Reel de bastidores — 45-60 segundos, primeira pessoa, com print do N8N
**Aposta criativa:** Mostrar a decisão técnica real com critérios específicos, sem generalizar — quando cada opção faz sentido no contexto do negócio
**Por que pode funcionar:** Posts de bastidores com ferramentas nomeadas têm credibilidade alta. Serve como pilar de autoridade e converte seguidores em leads qualificados.

---

Qual ângulo você quer desenvolver? (1, 2 ou 3)
Se nenhum servir, me conta o que falta que eu gero mais opções.
```

## Veto Conditions

Rejeitar e refazer se:
1. Dois ou mais ângulos usam o mesmo tipo de hook
2. Qualquer hook contém travessão (—) ou pergunta retórica

## Quality Criteria

- [ ] 3 ângulos com tipos de hook genuinamente diferentes
- [ ] Nenhum hook com travessão ou interrogação retórica
- [ ] Pelo menos 1 ângulo é analogia cultural ou bastidores reais
- [ ] Cada ângulo tem formato específico definido (não só "carrossel")
