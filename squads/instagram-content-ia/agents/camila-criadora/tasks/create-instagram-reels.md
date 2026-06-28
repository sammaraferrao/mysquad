---
task: "Create Instagram Reels"
order: 3
input: |
  - selected_angle: Ângulo aprovado pelo usuário com hook e formato definidos
  - selected_tone: Tom escolhido pelo usuário (Tom 1-6)
  - company_context: Contexto da empresa e voz da marca
output: |
  - reel_content: Roteiro completo do reel com narração, indicações de corte, legenda e hashtags
---

# Create Instagram Reels

Cria o roteiro completo de um Reel para o Instagram. O objetivo do reel é alcance (novos perfis), então o hook dos primeiros 3 segundos é crítico. O roteiro é escrito para ser falado em voz natural, com indicações de corte, texto de tela e timing.

## Process

1. **Lê o ângulo selecionado** em `squads/instagram-content-ia/output/selected-angle.md`. Identifica o hook verbal de abertura, a demonstração ou analogia do corpo, e o CTA verbal de encerramento.

2. **Define o formato do reel:**
   - Reel de alcance curto: 15-30 segundos, fato ou dado impactante + revelação + CTA
   - Reel de bastidores: 45-60 segundos, narrativa em primeira pessoa + demo visual + CTA de conversa
   - Reel de analogia: 30-45 segundos, paralelo cultural + conceito de IA + CTA

3. **Escreve o roteiro completo** com:
   - Narração palavra por palavra (escrita como se estivesse sendo falada, com contrações e ritmo natural)
   - Indicações de [CORTE], [TEXTO NA TELA], [PAUSA] em momento-chave
   - Timing estimado por bloco
   - Descrição de visual sugerido por bloco

4. **Verifica o timing total:** máximo 60 segundos para reels de profundidade, máximo 30 segundos para reels de alcance curto.

5. **Escreve a legenda** curta (2-4 linhas) com hook próprio e CTA de conversa.

## Output Format

```
=== FORMATO ===
[Reel de alcance curto / Reel de bastidores / Reel de analogia] — duração estimada: [X] segundos

=== ROTEIRO ===

[0:00-0:03] HOOK
Narração: "[primeiras palavras — deve parar o scroll]"
Visual: [o que aparece na tela]
Texto na tela: "[texto sobreposto se houver]"

[0:03-0:XX] DESENVOLVIMENTO
Narração: "[corpo do reel]"
Visual: [descrição do visual]
[CORTE] — indicações de edição

[0:XX-0:XX] FECHAMENTO
Narração: "[conclusão + CTA verbal]"
Visual: [visual de encerramento]
Texto na tela: "[CTA escrito na tela]"

=== LEGENDA ===
[Hook curto — 1 linha]

[Contexto em 2-3 linhas]

[CTA de conversa]

=== HASHTAGS ===
#hashtag1 #hashtag2 #hashtag3 #hashtag4 #hashtag5
```

## Output Example

```
=== FORMATO ===
Reel de bastidores — duração estimada: 50 segundos

=== ROTEIRO ===

[0:00-0:03] HOOK
Narração: "Eu sofria contando calorias. Não por preguiça."
Visual: câmera frontal, expressão natural, sem filtro
Texto na tela: nenhum

[0:03-0:12] PROBLEMA
Narração: "Cada refeição, cinco passos. Abrir app, procurar alimento, estimar quantidade, calcular, registrar. Cinco minutos que eu nunca tinha."
Visual: corte rápido mostrando sequência de telas do app de dieta
[CORTE]

[0:12-0:28] SOLUÇÃO
Narração: "Então eu construí meu próprio agente de IA no WhatsApp. Mando foto do prato. Ele identifica os alimentos, calcula as calorias e registra no histórico do dia. Automático."
Visual: tela do WhatsApp mostrando a conversa — foto do prato, resposta do bot com calorias
Texto na tela: "foto do prato" seta "calorias calculadas"
[CORTE]

[0:28-0:40] BASTIDORES
Narração: "Por trás: N8N, Evolution API e uma camada de IA para reconhecimento de imagem. Não é simples de montar."
Visual: print da interface do N8N com o fluxo
Texto na tela: "N8N + Evolution API + IA de visão"

[0:40-0:50] CTA
Narração: "Mas é exatamente o tipo de solução que eu construo, pra mim e pra negócios. Me conta nos comentários: qual tarefa repetitiva você eliminaria primeiro?"
Visual: câmera frontal, olhando direto
Texto na tela: "qual tarefa você eliminaria?"

=== LEGENDA ===
Você sofre com alguma tarefa repetitiva no negócio?

Eu sofria contando calorias. Então construí meu próprio agente de IA no WhatsApp. Mando a foto, ele registra tudo. Por trás: N8N + Evolution API + reconhecimento de imagem.

Me conta nos comentários: qual tarefa você eliminaria primeiro?

=== HASHTAGS ===
#agenteia #automação #n8n #iaparnegócios #inteligenciaartificial
```

## Quality Criteria

- [ ] Hook dos primeiros 3 segundos é declarativo e para o scroll (testado mentalmente: se você ouvisse isso enquanto scrollava, pararia?)
- [ ] Nenhum travessão (—) na narração ou legenda
- [ ] Nenhuma construção "não é X, é Y"
- [ ] A narração soa como fala natural, com contrações e ritmo conversacional
- [ ] Timing total dentro do limite (30s para alcance curto, 60s para bastidores)
- [ ] CTA verbal está no roteiro e CTA escrito aparece na tela no encerramento
- [ ] Legenda tem hook próprio (não repete a narração literalmente)

## Veto Conditions

Rejeitar e refazer se:
1. O hook dos primeiros 3 segundos é uma pergunta retórica ou começa com "Você sabia que"
2. A narração contém travessão (—) ou a construção "não é X, é Y"
