---
task: "Review Content"
order: 1
input: |
  - content_draft: Conteúdo completo produzido pela Camila (carrossel ou reel)
  - quality_criteria: Critérios de qualidade do squad
  - anti_patterns: Anti-patterns confirmados pelos dados
output: |
  - review_result: Veredito (aprovado/reprovado), lista de problemas encontrados por gravidade, e recomendações opcionais
---

# Review Content

Revisa o conteúdo produzido pela Camila Criadora aplicando os critérios de qualidade e anti-patterns do squad. Entrega veredito binário com lista de problemas classificados por gravidade.

## Process

1. **Lê o conteúdo** em `squads/instagram-content-ia/output/content-draft.md` na íntegra, do slide 1 ao CTA final, incluindo a legenda e as hashtags.

2. **Busca bloqueadores automáticos** (qualquer um desses = reprovado imediato):
   - Travessão (—): buscar em todo o texto, incluindo subtítulos e suportes
   - Construção "não é X, é Y": buscar variações ("não é sobre X, é sobre Y", "não é falta de X, é falta de Y")
   - Vocabulário proibido: incrível, revolucionário, fluxos invencíveis, não fique de fora, onda que veio pra ficar, vamos aprender juntas
   - CTA ausente no slide final

3. **Verifica critérios de aprovação** (não bloqueadores mas obrigatórios):
   - Hook: declarativo, sem interrogação retórica, sem emoji de alerta com caps
   - Ferramentas: citadas por nome específico (N8N, Claude, Evolution API), nunca "uma ferramenta de IA"
   - Palavras por slide: contar headline + suporte por slide. Flaggar slides abaixo de 40 ou acima de 80 palavras
   - Legenda: tem hook próprio (diferente do slide 1)?
   - Tom: soa humano? Tem ritmo variado (frases curtas e longas)?

4. **Verifica marcadores de transição de IA** (recomendação de correção):
   - "na verdade", "isso significa que", "em outras palavras", "sendo mais específico", "em resumo"
   - Citar cada ocorrência com o trecho completo

5. **Monta o veredito** no formato especificado: aprovado ou reprovado, bloqueadores listados com o trecho exato, recomendações separadas dos bloqueadores.

## Output Format

```
# Revisão de Conteúdo

**Veredito:** [APROVADO / REPROVADO]
[Se reprovado: "X bloqueador(es) encontrado(s). Corrigir e reenviar."]

---

## Bloqueadores (correção obrigatória para aprovação)

[Se nenhum: "Nenhum bloqueador encontrado."]

1. **[Tipo de bloqueador]**
   Trecho: "[trecho exato onde aparece]"
   Problema: [explicação do por que é um bloqueador]

---

## Recomendações (melhorias desejáveis, não bloqueadoras)

[Se nenhuma: "Nenhuma recomendação adicional."]

1. **[Tipo de melhoria]**
   Trecho: "[trecho]"
   Sugestão: [o que melhoraria e por quê]

---

## Checklist de Qualidade

- [x] / [ ] Nenhum travessão (—) encontrado
- [x] / [ ] Nenhuma construção "não é X, é Y"
- [x] / [ ] Vocabulário proibido ausente
- [x] / [ ] Hook declarativo (não interrogativo)
- [x] / [ ] Ferramentas citadas por nome específico
- [x] / [ ] CTA presente no slide final
- [x] / [ ] Legenda com hook próprio
- [x] / [ ] Palavras por slide dentro do range (40-80)
- [x] / [ ] Tom humano, ritmo variado
```

## Output Example

```
# Revisão de Conteúdo

**Veredito:** REPROVADO
2 bloqueadores encontrados. Corrigir e reenviar.

---

## Bloqueadores (correção obrigatória para aprovação)

1. **Travessão**
   Trecho: "A ferramenta certa — e só ela — muda tudo."
   Problema: Travessão proibido em qualquer parte do copy. Substitua por ponto final ou reescreva: "A ferramenta certa muda tudo. Só ela."

2. **Construção "não é X, é Y"**
   Trecho: "Não é sobre ferramenta, é sobre processo."
   Problema: Estrutura associada a output de IA. Diga a verdade diretamente: "O problema é o processo, não a ferramenta."

---

## Recomendações (melhorias desejáveis, não bloqueadoras)

1. **Marcador de transição de IA**
   Trecho: "Na verdade, o que a maioria das empreendedoras precisa..."
   Sugestão: Remover "Na verdade" e começar diretamente com "O que a maioria das empreendedoras precisa..." — mais direto e menos associado ao estilo de IA.

2. **Slide 4 abaixo do mínimo de palavras**
   Trecho: Headline "Ferramenta errada." + Suporte "Não adianta usar a errada." (31 palavras total)
   Sugestão: Expandir o suporte com exemplo concreto para chegar nos 40 palavras mínimos.

---

## Checklist de Qualidade

- [ ] Nenhum travessão (—) encontrado — FALHOU (slide 3 e slide 5)
- [ ] Nenhuma construção "não é X, é Y" — FALHOU (slide 2)
- [x] Vocabulário proibido ausente
- [x] Hook declarativo (não interrogativo)
- [x] Ferramentas citadas por nome específico (N8N, Claude)
- [x] CTA presente no slide final
- [x] Legenda com hook próprio
- [ ] Palavras por slide dentro do range (40-80) — slide 4 com 31 palavras
- [x] Tom humano, ritmo variado
```

## Quality Criteria

- [ ] Veredito explícito na primeira linha ("APROVADO" ou "REPROVADO")
- [ ] Todos os travessões identificados com o trecho exato
- [ ] Todas as construções "não é X, é Y" identificadas com o trecho exato
- [ ] Checklist de qualidade preenchido completamente
- [ ] Bloqueadores separados de recomendações
- [ ] Nenhum travessão no próprio output de revisão

## Veto Conditions

Rejeitar e refazer se:
1. O output de revisão não tem veredito explícito na primeira linha
2. O output de revisão contém travessão (—) — a revisora não pode cometer o mesmo erro que está revisando
