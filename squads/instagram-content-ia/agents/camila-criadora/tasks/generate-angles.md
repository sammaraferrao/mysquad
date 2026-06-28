---
task: "Generate Angles"
order: 1
input: |
  - selected_news: Pauta selecionada pelo usuário com briefing completo (de news-options.md)
  - tone_options: Arquivo de tom de voz com os 6 tons disponíveis
output: |
  - angles: 3 ângulos diferentes para o conteúdo, cada um com hook, formato sugerido e aposta criativa
---

# Generate Angles

Gera 3 ângulos genuinamente diferentes para transformar a pauta selecionada em conteúdo de Instagram. Cada ângulo é uma aposta criativa distinta — não variações do mesmo hook com palavras trocadas. O objetivo é dar ao usuário escolhas reais, com trade-offs claros.

## Process

1. **Lê a pauta selecionada** em `squads/instagram-content-ia/output/selected-news.md` e extrai: o tema central, o dado principal, o ângulo sugerido pela Rebeca, e o público que mais vai se reconhecer nele.

2. **Lê o arquivo de tom de voz** em `squads/instagram-content-ia/pipeline/data/tone-of-voice.md` e identifica qual dos 6 tons melhor serve cada ângulo possível.

3. **Gera 3 ângulos** usando estruturas de hook comprovadamente diferentes:
   - Ângulo 1: padrão de maior engajamento comprovado para esse tipo de tema (analogia cultural se possível, diagnóstico de dor se não)
   - Ângulo 2: virada de perspectiva ou posicionamento de tese — algo que vai contra o que a maioria acredita
   - Ângulo 3: bastidor ou resultado próprio — execução real, não teoria

4. **Para cada ângulo especifica:** tipo de hook usado, formato do conteúdo (carrossel ou reel, com qual estrutura), tom recomendado, a aposta criativa em 1 frase, e por que esse ângulo pode funcionar para esse público específico.

5. **Salva o output** em `squads/instagram-content-ia/output/angles.md`.

## Output Format

```
# Ângulos de Conteúdo — [tema]

---

## Ângulo 1 — [Nome descritivo do ângulo]

**Hook:** [Primeira linha exata do conteúdo]
**Tipo de hook:** [Acusação direta / Ponte cultural / Diagnóstico de dor / Revelação / Resultado próprio]
**Tom:** [Tom 1-6 do arquivo de tom de voz]
**Formato:** [Carrossel de analogia / Carrossel educativo / Reel de alcance / Post de posicionamento] — [estrutura específica: 8 slides, 6 slides, 45s, etc.]
**Aposta criativa:** [Em 1 frase: o que torna esse ângulo único]
**Por que pode funcionar:** [2-3 linhas de justificativa baseada nos padrões da conta]

---

## Ângulo 2 — [Nome]
[mesma estrutura]

---

## Ângulo 3 — [Nome]
[mesma estrutura]

---

Qual ângulo você quer desenvolver? (1, 2 ou 3)
Se nenhum servir, me conta o que falta que eu gero mais opções.
```

## Output Example

```
# Ângulos de Conteúdo — Meta IA no WhatsApp Business

---

## Ângulo 1 — O campo de batalha que ninguém está vendo

**Hook:** A Meta integrou IA ao WhatsApp Business. O mercado vai se dividir em dois grupos. Você quer saber em qual você vai estar.
**Tipo de hook:** Diagnóstico de dor + antecipação
**Tom:** Tom 3 (Diagnóstico Honesto)
**Formato:** Carrossel educativo (Mito vs Realidade) — 8 slides
**Aposta criativa:** Usar a notícia como gatilho para mostrar que o real desafio não é a ferramenta, é saber quando usar a nativa vs. a stack customizada
**Por que pode funcionar:** O público já usa WhatsApp como canal principal. Qualquer novidade que afete o canal chama atenção. E o ângulo de "dois grupos" cria identificação — a empreendedora quer saber em que grupo ela está.

---

## Ângulo 2 — Time de futebol e atendimento automatizado

**Hook:** Um time de futebol que joga bem tem uma coisa que quase nenhum atendimento automatizado tem.
**Tipo de hook:** Ponte cultural
**Tom:** Tom 2 (Tradutora Cultural)
**Formato:** Carrossel de analogia — 8 slides (paralelo: posições do time vs. camadas da automação de WhatsApp)
**Aposta criativa:** Treinador = orquestrador, atacantes = agentes de conversão, zagueiros = filtros de qualificação, goleiro = IA de escalonamento para humano
**Por que pode funcionar:** Analogia de futebol gerou 36% de engagement rate na conta. Lançamento da Meta cria o timing perfeito para um conteúdo que explica arquitetura de automação de forma visual e familiar.

---

## Ângulo 3 — O que eu mudaria no meu atendimento se estivesse começando hoje

**Hook:** Se eu montasse meu atendimento automatizado do zero hoje, com a integração nativa da Meta, eu não usaria Evolution API na primeira versão.
**Tipo de hook:** Resultado próprio
**Tom:** Tom 4 (Bastidores Reais)
**Formato:** Reel de alcance — 45-60 segundos, primeira pessoa
**Aposta criativa:** Mostrar a decisão técnica real (quando usar o nativo vs. quando construir stack própria), com critérios específicos que a empreendedora pode aplicar
**Por que pode funcionar:** Posts de bastidores com ferramentas nomeadas têm credibilidade alta na conta, mesmo com reach menor. Serve como pilar de autoridade e converte seguidores em leads.

---

Qual ângulo você quer desenvolver? (1, 2 ou 3)
Se nenhum servir, me conta o que falta que eu gero mais opções.
```

## Quality Criteria

- [ ] Os 3 ângulos são genuinamente diferentes (tipos de hook distintos, não variações do mesmo)
- [ ] Nenhum hook usa travessão (—)
- [ ] Nenhum hook é pergunta retórica
- [ ] Cada ângulo tem formato específico definido (não só "carrossel")
- [ ] A aposta criativa de cada ângulo é única — não poderia se aplicar a outro ângulo do mesmo output
- [ ] Ao menos 1 dos 3 ângulos é analogia cultural ou bastidor real (padrões de maior engajamento comprovado)

## Veto Conditions

Rejeitar e refazer se:
1. Dois ou mais ângulos usam o mesmo tipo de hook — não são ângulos diferentes, são variações
2. Qualquer ângulo usa travessão (—) ou construção "não é X, é Y" no hook ou na descrição
