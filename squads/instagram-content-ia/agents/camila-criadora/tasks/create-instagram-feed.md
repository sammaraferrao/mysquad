---
task: "Create Instagram Feed"
order: 2
input: |
  - selected_angle: Ângulo aprovado pelo usuário com hook e formato definidos
  - selected_tone: Tom escolhido pelo usuário (Tom 1-6)
  - company_context: Contexto da empresa e voz da marca
output: |
  - carousel_content: Conteúdo completo do carrossel com todos os slides, legenda e hashtags
---

# Create Instagram Feed

Cria o conteúdo completo de um carrossel para o feed do Instagram com base no ângulo aprovado. Cada slide tem hierarquia dupla (headline + suporte), a narrativa progride do slide 1 ao final, e a legenda tem hook próprio que não repete os slides.

## Process

1. **Lê o ângulo selecionado** em `squads/instagram-content-ia/output/selected-angle.md`. Extrai: hook definitivo, tipo de formato (carrossel de analogia, educativo, posicionamento), número de slides sugerido, tom.

2. **Lê os arquivos de referência:** `pipeline/data/tone-of-voice.md` para o tom selecionado, `pipeline/data/anti-patterns.md` para os padrões a evitar, `pipeline/data/output-examples.md` para referência de qualidade.

3. **Escreve o carrossel completo** seguindo o formato de output abaixo. Regras críticas:
   - Mínimo 40 palavras, máximo 80 por slide (headline + suporte combinados)
   - Hierarquia dupla em todo slide: headline em destaque + texto de suporte menor
   - Cada slide avança a narrativa — nenhum filler ou repetição
   - Slide 1 para o scroll: título provocativo, máximo 20 palavras
   - Slide final: CTA específico e acionável

4. **Escreve a legenda** com hook próprio (diferente do slide 1), desenvolvimento de 2-4 parágrafos para posts educativos ou 2-3 linhas para posts de analogia, e CTA de encerramento.

5. **Seleciona as hashtags:** 5-8 tags, mix de nicho (#iaparnegócios, #agenteia) + alcance médio (#inteligenciaartificial, #empreendedora) + amplo (#produtividade).

6. **Revisa o output completo** contra os critérios de qualidade antes de salvar.

## Output Format

```
=== FORMATO ===
[Nome do formato: Analogia / Educativo / Mito vs Realidade / Tutorial / Posicionamento]

=== SLIDES ===
Slide 1 (Cover):
  Título: [máx. 20 palavras — provocativo, declarativo]
  Subtítulo: [1 linha de contexto ou promessa]
  Fundo: [cor hex ou descrição]

Slide 2 ([Papel na narrativa]):
  Headline: [claim principal em destaque — 10-15 palavras]
  Suporte: [contexto ou dado de apoio — 25-50 palavras]
  Palavras em destaque: [termos para destacar na cor accent]
  Fundo: [claro / escuro / accent]

[...continua até o slide final...]

Slide N (CTA):
  Texto: [CTA específico — "Salva antes de fechar." ou "Me conta nos comentários: [pergunta]"]
  Fundo: [cor]

=== LEGENDA ===
[Hook próprio — diferente do slide 1]

[Desenvolvimento — parágrafos com quebra de linha]

[CTA de encerramento]

=== HASHTAGS ===
#hashtag1 #hashtag2 #hashtag3 #hashtag4 #hashtag5
```

## Output Example

```
=== FORMATO ===
Analogia (Esporte e IA)

=== SLIDES ===
Slide 1 (Cover):
  Título: Quem treina já entende de IA. Só não sabia ainda.
  Subtítulo: A lógica por trás das duas coisas é a mesma.
  Fundo: #0D0D0D (preto) com título em #C9A96E (dourado)

Slide 2 (Ponto de partida):
  Headline: Todo mundo começa igual.
  Suporte: Na academia, ninguém carrega 100kg no primeiro dia. Na IA, ninguém monta um agente complexo na primeira semana. O ponto de partida é o mesmo: fazer o básico consistente até que vire automático.
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
  Palavras em destaque: "N8N", "ferramenta certa"
  Fundo: claro (#E8DDD0)

Slide 5 (Programa):
  Headline: Alguém precisa criar o programa.
  Suporte: Você pode treinar sozinha, mas um programa estruturado chega mais rápido. Com IA é a mesma coisa. Você pode tentar do zero, ou usar um sistema já testado e que funciona.
  Palavras em destaque: "sistema já testado"
  Fundo: accent (#7C2D3E)

Slide 6 (Resultado):
  Headline: Os resultados aparecem no mês 2. Sempre.
  Suporte: Quem treina sabe que os primeiros resultados vêm depois de 30-45 dias. Com IA no negócio é igual. A primeira automação parece pequena. Em 90 dias, você não consegue imaginar trabalhar sem ela.
  Palavras em destaque: "90 dias"
  Fundo: escuro (#0D0D0D)

Slide 7 (CTA):
  Texto: Salva pra mostrar pra quem ainda acha IA difícil.
  Pergunta: Qual parte da academia você transferiria pra sua rotina com IA?
  Fundo: #C9A96E (dourado)

=== LEGENDA ===
Quem treina já entende de IA.
Só não sabia ainda.
Salva pra mostrar pra quem ainda acha difícil.

=== HASHTAGS ===
#iaparnegócios #agenteia #automação #inteligenciaartificial #empreendedora #produtividade
```

## Quality Criteria

- [ ] Nenhum travessão (—) em qualquer slide, legenda ou hashtag
- [ ] Nenhuma construção "não é X, é Y"
- [ ] Nenhuma frase de transição de IA ("na verdade", "isso significa que")
- [ ] Todos os slides têm hierarquia dupla (headline + suporte)
- [ ] Cada slide tem mínimo 40 palavras e máximo 80 (headline + suporte somados)
- [ ] Slide 1 tem título máximo 20 palavras, declarativo, que para o scroll
- [ ] Slide final tem CTA específico e acionável
- [ ] Legenda tem hook próprio (diferente do slide 1)
- [ ] 5-8 hashtags, mix de nicho e alcance médio

## Veto Conditions

Rejeitar e refazer se:
1. Qualquer slide contém travessão (—) ou a construção "não é X, é Y"
2. Algum slide tem menos de 40 palavras sem justificativa (post de analogia pode pedir slides mais curtos — checar com o usuário)
3. O slide final não tem CTA específico
4. A legenda é resumo dos slides em vez de ter hook e desenvolvimento próprios
