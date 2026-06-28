# Pattern Analysis: @asamferrao (Instagram)

Analyzed: 2026-06-28
Source: Windsor AI — dados reais da API do Instagram
Sample size: 11 posts
Period: 2026-04-29 a 2026-06-27

---

## Executive Summary

A conta está em fase inicial de construção de audiência, com reach médio de 340 por post (puxado pelo outlier da NASA). Excluindo o outlier, o reach médio é de ~84. O padrão mais claro: **analogias com cultura popular superam conteúdo técnico direto**. Reels geram mais reach; carrosséis geram mais engajamento relativo (engagement rate). O copywriting dos posts de melhor performance é curto, declarativo e usa contraste cultural ("enquanto vocês querem o hexa, a gente quer implementar IA"). O post de maior reach absoluto (Reel NASA, 2.917) fugiu completamente do tema de IA — foi pura descoberta/curiosidade. O segundo e terceiro melhores em engajamento relativo são ambos carrosséis com analogia (Copa do Mundo, academia). Isso aponta uma direção clara: o conteúdo técnico precisa de uma ponte emocional ou cultural para performar.

---

## Structural Patterns

### Content Mix

| Type | Count | % | Avg. Reach | Avg. Engagement |
|------|-------|---|-----------|-----------------|
| Carousel | 6 | 55% | 49 reach | 15 engagement |
| Reel | 5 | 45% | 709 reach | 31 engagement |

> Reels têm 14x mais reach médio, mas o outlier NASA distorce. Sem ele: Reels = 129 reach vs Carrosséis = 49.

### Highest Performing Posts (por engagement rate = engagement/reach)

| Rank | Post | Type | Reach | Eng. Rate | Diferencial |
|------|------|------|-------|-----------|-------------|
| 1 | Reel NASA | Reel | 2.917 | 4,5% | Curiosidade pura, sem IA |
| 2 | Copa do Mundo | Carousel | 99 | 36,4% | Analogia cultural + humor |
| 3 | Quem treina | Carousel | 67 | 31,3% | Analogia cotidiana |
| 4 | Claude errado | Carousel | 28 | 14,3% | Título declarativo + estrutura clara |
| 5 | Por onde começar | Carousel | 38 | 39,5% | Problema real nomeado direto |

### Posting Cadence
- Período analisado: 60 dias
- Total de posts: 11
- Média: ~1,8 posts/semana
- Concentração: rajadas (2 posts no mesmo dia, depois silêncio)

---

## Language Patterns

### Tone Profile
Dois tons distintos aparecem nos posts — um que performa bem e um que não:

**Tom que performa:** Declarativo, direto, com contraste. "Você está usando o Claude errado." "A maioria das pessoas que quer usar IA passa meses sem implementar nada." Começa com problema nomeado, desenvolve com lógica, fecha com CTA específico.

**Tom que não performa (Conteúdo 10 — colecionador de ferramentas):** Começa com ❌ e palavras em caps, usa superlativo ("invencíveis"), promete "fluxos" sem mostrar nada concreto, termina com "não fique de fora dessa onda" — exatamente o que o company.md proíbe.

### Hook Patterns (dos posts de maior performance)

1. "Você está usando o Claude errado." — Padrão: **Acusação direta sem culpa** (implica que a pessoa está perdendo algo, não que ela é burra)
2. "Como explicar IA usando a Seleção como exemplo 🇧🇷⚽" — Padrão: **Ponte cultural** (assunto familiar + tema técnico)
3. "A maioria das pessoas que 'quer usar IA no negócio' passa meses testando ferramenta..." — Padrão: **Diagnóstico do problema do público**
4. "Quem treina já entende de IA. Só não sabia ainda." — Padrão: **Revelação** (você já sabe, só não sabia que sabia)
5. "Tá cansada de pedir algo pra IA e se arrepender?" — Padrão: **Dor específica em forma de pergunta** (exceção à regra — funcionou porque a dor é muito real)

### Call-to-Action Patterns

1. **"Salva antes de fechar."** — usado em 4 de 11 posts. Direto, funcional.
2. **"Me conta nos comentários: [pergunta específica]"** — usado em 3 posts. Funciona quando a pergunta é concreta ("qual tarefa repetitiva você eliminaria primeiro?").
3. **"Salva pra usar mais tarde."** — variante do salva. Adiciona urgência de utilidade.

### Vocabulary Signature

- "implementar" — aparece em 3 posts, sempre no contexto de fazer vs. só aprender
- "automação" — presente em posts de bastidores/técnicos
- "agente de IA" — aparece naturalmente nos posts de resultado prático
- "sem jargão" / "sem pular etapa" — linguagem que humaniza o técnico
- "por onde começar de verdade" — posicionamento de orientação prática

### Style Notes
- Legendas curtas nos posts de analogia (2-4 linhas) performam melhor do que legendas longas estruturadas
- Emojis: sparingly nos melhores posts (1-2 por legenda), excessivo nos piores (❌ + bullets)
- Hashtags: colocadas no final, 4-6 tags temáticas, sem abuso
- Quebra de linha: frequente nos carrosséis educativos, inexistente nos de analogia (que são mais corridos)

---

## Engagement Patterns

### Engagement Drivers

1. **Analogia com cultura popular**: Copa + academia = engagement rate 36% e 31%. O público reconhece, ri e salva.
2. **Diagnóstico de problema real nomeado**: "passa meses sem implementar" — a dor é tão real que a pessoa se reconhece e engaja.
3. **Revelação/insight simples**: "Quem treina já entende de IA" — o WTF inicial vira AHA depois de ler.
4. **Prova de execução real**: Reel do agente de calorias — N8N + Evolution API nomeados = credibilidade.

### Underperforming Patterns

1. **Tom hype/motivacional**: Conteúdo 10 (colecionador de ferramentas) — linguagem de coach, sem prova, sem dado. 1 like, 108 reach = 0,9% engagement rate.
2. **Técnico sem ponte emocional**: Conteúdo 2 (Claude 3 modos) — estrutura correta, linguagem adequada, mas sem hook emocional ou cultural. 28 reach, 4 engagement.
3. **Humor vago**: Conteúdo 11 ("quero parar mas quero continuar") — pessoal demais, sem contexto. 133 reach, 2 likes.

---

## Recommendations for Squad

1. **Priorizar carrosséis de analogia cultural**: O padrão Copa + Academia prova que o público responde quando a IA é traduzida por algo familiar. A squad deve ter um agente dedicado a encontrar analogias (esporte, culinária, séries, comportamentos cotidianos) para cada conceito técnico.

2. **Reels de alcance, carrosséis de engajamento**: Usar reels para distribuição (alcançar novos perfis) com hooks simples e visuais fortes, e carrosséis para aprofundamento e saves. A squad deve produzir os dois formatos de forma complementar.

3. **Legendas curtas nos posts de impacto**: Os posts de analogia têm 2-4 linhas. A squad não deve forçar legendas longas em todo conteúdo — brevidade + impacto supera estrutura longa.

4. **Banir vocabulário hype do squad**: "invencível", "onda que veio pra ficar", "não fique de fora" — qualquer output que contenha essas expressões deve ser rejeitado automaticamente pelo agente revisor.

5. **Incluir provas de execução em bastidores**: O post do agente de calorias (N8N + Evolution API nomeados) tem baixo reach mas alta credibilidade. Usar como pilar de autoridade — não para viralização, mas para conversão de seguidores em leads.
