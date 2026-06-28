---
execution: inline
agent: squads/instagram-content-ia/agents/vera-veredito
inputFile: squads/instagram-content-ia/output/content-draft.md
outputFile: squads/instagram-content-ia/output/review-result.md
---

# Step 08: Revisão Editorial

## Context Loading

Load these files before executing:
- `squads/instagram-content-ia/output/content-draft.md` — conteúdo aprovado pelo usuário para revisão
- `squads/instagram-content-ia/pipeline/data/quality-criteria.md` — critérios de aprovação e bloqueadores
- `squads/instagram-content-ia/pipeline/data/anti-patterns.md` — padrões confirmados de baixo engajamento

## Instructions

### Process

1. Lê o conteúdo completo em `content-draft.md` uma única vez, do início ao fim, sem interrupção.

2. Executa a revisão da task `review.md`:
   - Busca bloqueadores automáticos: travessão (—), construção "não é X, é Y", vocabulário proibido, CTA ausente
   - Verifica critérios de aprovação: hook, ferramentas nomeadas, palavras por slide (40-80), legenda com hook próprio, ritmo variado
   - Busca marcadores de transição de IA como recomendação de melhoria

3. Monta o output com: veredito explícito na primeira linha, bloqueadores com trecho exato, recomendações separadas, checklist completo.

4. Se reprovado: salva o resultado e o pipeline pausa para que a Camila faça as correções.
   Se aprovado: salva o resultado e avança para a aprovação final.

## Output Format

```
# Revisão de Conteúdo

**Veredito:** [APROVADO / REPROVADO]
[Se reprovado: quantidade de bloqueadores + instrução de corrigir e reenviar]

---

## Bloqueadores (correção obrigatória)

[Nenhum bloqueador encontrado. / Lista com trecho exato e explicação]

---

## Recomendações (melhorias desejáveis)

[Nenhuma recomendação adicional. / Lista com trecho e sugestão]

---

## Checklist de Qualidade

- [x] / [ ] Nenhum travessão (—)
- [x] / [ ] Nenhuma construção "não é X, é Y"
- [x] / [ ] Vocabulário proibido ausente
- [x] / [ ] Hook declarativo
- [x] / [ ] Ferramentas citadas por nome
- [x] / [ ] CTA no slide final
- [x] / [ ] Legenda com hook próprio
- [x] / [ ] Palavras por slide dentro do range (40-80)
- [x] / [ ] Tom humano, ritmo variado
```

## Output Example

```
# Revisão de Conteúdo

**Veredito:** APROVADO

---

## Bloqueadores (correção obrigatória)

Nenhum bloqueador encontrado.

---

## Recomendações (melhorias desejáveis)

1. **Marcador de transição de IA — Slide 3**
   Trecho: "Na prática, isso significa que você precisa..."
   Sugestão: Remover "Na prática, isso significa que" e começar direto com "Você precisa..." — mais direto, menos associado a LLM. A expressão "na prática" aparece em outro contexto bom na conta, mas aqui está servindo de transição, não de âncora.

---

## Checklist de Qualidade

- [x] Nenhum travessão (—)
- [x] Nenhuma construção "não é X, é Y"
- [x] Vocabulário proibido ausente
- [x] Hook declarativo
- [x] Ferramentas citadas por nome (N8N, Evolution API)
- [x] CTA no slide final
- [x] Legenda com hook próprio
- [x] Palavras por slide dentro do range (slide 2: 52 palavras, slide 3: 61 palavras, slide 4: 48 palavras, slide 5: 44 palavras)
- [x] Tom humano, ritmo variado
```

## Veto Conditions

Rejeitar e refazer se:
1. O output não tem veredito explícito na primeira linha
2. O output de revisão contém travessão (—)

## Quality Criteria

- [ ] Veredito binário explícito na primeira linha
- [ ] Bloqueadores com trecho exato citado
- [ ] Checklist completamente preenchido
- [ ] Nenhum travessão no próprio output de revisão
