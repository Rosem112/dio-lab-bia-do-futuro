# Prompts do Agente

> [!Tip]
> ## Prompt usado para esta etapa:
> 
> Você é um agente especializado em organização financeira pessoal.
> 
> Seu objetivo é analisar os dados financeiros fornecidos no contexto e ajudar o usuário a entender sua situação financeira atual, incluindo total de gastos, saldo restante e distribuição por categoria.
> 
> ## Regras:
> 
> 1. Utilize apenas os dados presentes no contexto.
> 2. Não invente valores, categorias ou informações.
> 3. Não faça recomendações de investimento.
> 4. Não utilize conhecimento externo.
> 5. Se não houver dados suficientes, diga: "Não possuo dados suficientes para responder com base nas informações disponíveis."
> 6. Respeite o escopo de organização financeira.
>    
> Seja claro, direto e organizado na resposta.


# Pitch (3 minutos)

> [!TIP]
> Você pode usar alguns slides pra apoiar no seu Pitch e mostrar sua solução na prática.
 
## Roteiro Sugerido

### 1. O Problema (30 seg)
> Qual dor do cliente você resolve?

Muitas pessoas não sabem exatamente para onde está indo o dinheiro no final do mês.
Elas possuem renda, fazem diversos pagamentos, mas não têm clareza sobre:

- Total real de gastos

- Distribuição por categoria

- Quanto sobra no final do mês

Essa falta de organização pode levar ao endividamento e à dificuldade de planejamento financeiro.

### 2. A Solução (1 min)
> Como seu agente resolve esse problema?

O FinanBot é um agente de organização financeira pessoal que:

- Lê dados financeiros armazenados localmente (JSON/CSV)

- Calcula automaticamente:

  - Total de gastos

  - Saldo restante

  - Distribuição por categoria

- Gera respostas organizadas e claras

- Funciona 100% local com Ollama

- Não utiliza APIs externas

Ele responde apenas com base nos dados fornecidos, evitando alucinações e garantindo maior confiabilidade.

### 3. Demonstração (1 min)
> Mostre o agente funcionando (pode ser gravação de tela)

Na demonstração será mostrado:

1. Interface no Streamlit

2. Dados carregados da pasta /data

3. Pergunta do usuário, por exemplo:

   - "Qual meu saldo atual?"

   - "Quanto gastei com lazer?"

4. O agente gerando resposta estruturada com:

   - Total de gastos

   - Saldo restante

   - Gastos por categoria

5. Caso seja feita uma pergunta fora do escopo:

   - O agente responde:
     "Não possuo dados suficientes para responder com base nas informações disponíveis."

### 4. Diferencial e Impacto (30 seg)
> Por que essa solução é inovadora e qual é o impacto dela na sociedade?

O diferencial do FinanBot é:

  - Execução local com Ollama (mais privacidade)

  - Controle total sobre os dados

  - Estrutura simples e escalável

  - Uso de prompt restritivo para evitar respostas fora do contexto

Impacto:

Ajuda pessoas a terem maior consciência financeira, promovendo organização, planejamento e redução de risco de endividamento.

---

## Checklist do Pitch

- [x] Duração máxima de 3 minutos
- [x] Problema claramente definido
- [x] Solução demonstrada na prática
- [x] Diferencial explicado
- [x] Áudio e vídeo com boa qualidade

---

## Link do Vídeo

> Cole aqui o link do seu pitch (YouTube, Loom, Google Drive, etc.)

falha ao carregar o link....
