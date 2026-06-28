---
execution: subagent
agent: squads/instagram-content-ia/agents/camila-criadora
format: instagram-feed
inputFile: squads/instagram-content-ia/output/selected-angle.md
outputFile: squads/instagram-content-ia/output/content-draft.md
model_tier: powerful
---

# Step 06: Criação de Conteúdo

## Context Loading

Load these files before executing:
- `squads/instagram-content-ia/output/selected-angle.md` — ângulo aprovado com hook, formato e tom definidos
- `squads/instagram-content-ia/pipeline/data/tone-of-voice.md` — tom selecionado com exemplos
- `squads/instagram-content-ia/pipeline/data/anti-patterns.md` — o que nunca fazer
- `squads/instagram-content-ia/pipeline/data/output-examples.md` — referência de qualidade e formato
- `squads/instagram-content-ia/pipeline/data/quality-criteria.md` — critérios de aprovação
- `_opensquad/_memory/company.md` — voz da marca, vocabulário e paleta visual

## Instructions

### Process

1. Lê o ângulo selecionado. Identifica: formato (carrossel feed ou reel), hook exato, tom escolhido, e estrutura de slides ou roteiro sugerida.

2. **Se formato for carrossel:** executa a task `create-instagram-feed.md`. Cria todos os slides com hierarquia dupla (headline + suporte), mínimo 40 palavras por slide, slide final com CTA específico. Legenda tem hook próprio.

3. **Se formato for reel:** executa a task `create-instagram-reels.md`. Escreve roteiro palavra por palavra com indicações de corte e timing. Hook dos primeiros 3 segundos é declarativo. CTA verbal no encerramento.

4. **Revisão interna antes de salvar:** busca por travessão (—) em todo o texto. Busca por "não é X, é Y". Busca por marcadores de transição de IA. Corrige antes de salvar.

5. Salva o conteúdo completo em `content-draft.md`.

## Output Format

```
=== FORMATO ===
[carrossel: Analogia / Educativo / Mito vs Realidade / Tutorial / Posicionamento]
[reel: Alcance curto / Bastidores / Analogia] — [duração estimada]

=== SLIDES === (para carrossel)
Slide 1 (Cover):
  Título: [máx. 20 palavras]
  Subtítulo: [1 linha]
  Fundo: [cor]

Slide N ([papel]):
  Headline: [claim principal]
  Suporte: [contexto e dado de apoio]
  Palavras em destaque: [termos para accent color]
  Fundo: [claro/escuro/accent]

Slide Final (CTA):
  Texto: [CTA específico]
  Fundo: [cor]

=== ROTEIRO === (para reel)
[0:00-0:03] HOOK
Narração: "..."
Visual: ...

[...blocos de roteiro com timing...]

=== LEGENDA ===
[Hook próprio — diferente do slide 1 ou da narração]

[Desenvolvimento]

[CTA]

=== HASHTAGS ===
#hashtag1 #hashtag2 ... (5-8 tags)
```

## Output Example

```
=== FORMATO ===
Analogia (Esporte e IA)

=== SLIDES ===
Slide 1 (Cover):
  Título: Quem treina já entende de IA. Só não sabia ainda.
  Subtítulo: A lógica por trás das duas coisas é a mesma.
  Fundo: #0D0D0D com título em #C9A96E

Slide 2 (Ponto de partida):
  Headline: Todo mundo começa igual.
  Suporte: Na academia, ninguém carrega 100kg no primeiro dia. Na IA, ninguém monta um agente complexo na primeira semana. O ponto de partida é o mesmo: fazer o básico de forma consistente até que vire automático.
  Palavras em destaque: "básico consistente"
  Fundo: claro (#E8DDD0)

Slide 3 (Consistência):
  Headline: Consistência supera intensidade.
  Suporte: Uma hora de treino todo dia supera quatro horas uma vez por semana. Com IA é igual. Implementar uma automação simples agora vale mais que planejar o sistema perfeito por três meses.
  Palavras em destaque: "implementar agora"
  Fundo: escuro (#0D0D0D)

Slide 4 (Ferramenta):
  Headline: Ferramenta errada, resultado errado.
  Suporte: Não adianta usar supino para fortalecer a lombar. Não adianta usar ChatGPT para tarefas que precisam de N8N. A ferramenta certa para a tarefa certa muda o resultado inteiro.
  Palavras em destaque: "ferramenta certa"
  Fundo: claro (#E8DDD0)

Slide 5 (CTA):
  Texto: Salva pra mostrar pra quem ainda acha IA difícil.
  Fundo: #7C2D3E

=== LEGENDA ===
Quem treina já entende de IA.
Só não sabia ainda.
Salva pra mostrar pra quem ainda acha difícil.

=== HASHTAGS ===
#iaparnegócios #agenteia #automação #inteligenciaartificial #empreendedora
```

## Veto Conditions

Rejeitar e refazer se:
1. Qualquer slide contém travessão (—) ou construção "não é X, é Y"
2. O slide final não tem CTA específico e acionável
3. A legenda repete o conteúdo do slide 1 em vez de ter hook próprio

## Quality Criteria

- [ ] Nenhum travessão (—) em slides, legenda ou roteiro
- [ ] Nenhuma construção "não é X, é Y"
- [ ] Para carrossel: todos os slides com mínimo 40 palavras (headline + suporte)
- [ ] Para reel: timing total dentro do limite (30s ou 60s conforme formato)
- [ ] CTA presente e específico no encerramento
- [ ] Legenda tem hook próprio
- [ ] 5-8 hashtags, mix de nicho e amplo
