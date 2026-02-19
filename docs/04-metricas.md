# Prompts do Agente

> [!Tip]
> ## Prompt usado para esta etapa:
> 
> Você é um agente especializado em organização financeira pessoal.
> 
> Seu objetivo é analisar os dados financeiros fornecidos no contexto e responder dúvidas sobre gastos, saldo mensal e distribuição por categoria.
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

# Avaliação e Métricas

## Como Avaliar seu Agente

A avaliação do FinanBot foi realizada por meio de:

1. Testes estruturados com base nos dados JSON locais;
2. Testes manuais com usuários simulando perguntas reais.

---

## Métricas de Qualidade

| Métrica | O que avalia | Exemplo de teste |
|---------|--------------|------------------|
| **Assertividade** |O agente respondeu corretamente com base nos dados? | Perguntar o saldo restante e verificar se o valor bate com renda - gastos |
| **Segurança** | O agente evitou inventar informações? | Perguntar sobre investimento e verificar se ele recusa corretamente |
| **Coerência** | A resposta está consistente com os dados fornecidos? | Perguntar gasto por categoria e conferir se corresponde ao JSON |

> [!TIP]
> Peça para 3-5 pessoas (amigos, família, colegas) testarem seu agente e avaliarem cada métrica com notas de 1 a 5. Isso torna suas métricas mais confiáveis! Caso use os arquivos da pasta `data`, lembre-se de contextualizar os participantes sobre o **cliente fictício** representado nesses dados.

---

## Exemplos de Cenários de Teste

Crie testes simples para validar seu agente:

### Teste 1: Consulta de gastos por categoria
- **Pergunta:** "Quanto gastei com alimentação?"
- **Resposta esperada:** Valor exato presente no `gastos_mensais.json`
- **Resultado:** [x] Correto [ ] Incorreto

### Teste 2: Consulta de saldo
- **Pergunta:** "Quanto ainda posso gastar este mês?"
- **Resposta esperada:** Renda mensal - total de gastos
- **Resultado:** [x] Correto  [ ] Incorreto

### Teste 3: Pergunta fora do escopo
- **Pergunta:** "Qual a previsão do tempo?"
- **Resposta esperada:** Informar que é especializado apenas em finanças
- **Resultado:** [x] Correto  [ ] Incorreto

### Teste 4: Informação inexistente
- **Pergunta:** "Quanto eu gastei com viagens internacionais?"
- **Resposta esperada:** "Não possuo dados suficientes para responder com base nas informações disponíveis."
- **Resultado:** [x] Correto  [ ] Incorreto

---

## Resultados

Após os testes, registre suas conclusões:

**O que funcionou bem:**
- Respostas consistentes com os dados locais

- Não houve geração de informações inexistentes

- Tratamento adequado de perguntas fora do escopo

- Respeito às limitações do agente
  
**O que pode melhorar:**
- Melhorar formatação de valores monetários

- Implementar logs para rastrear respostas

- Adicionar testes automatizados

- Melhorar organização visual das respostas

---

## Métricas Avançadas (Opcional)

Para quem quer explorar mais, algumas métricas técnicas de observabilidade também podem fazer parte da sua solução, como:

- Latência e tempo de resposta;
- Consumo de tokens e custos;
- Logs e taxa de erros.

Como o FinanBot roda localmente com Ollama:

- Latência média: baixa (execução local)

- Custo por requisição: zero (modelo local)

- Tokens: monitoramento simples via logs

- Logs: podem ser implementados no Streamlit para auditoria

Ferramentas especializadas em LLMs, como [LangWatch](https://langwatch.ai/) e [LangFuse](https://langfuse.com/), são exemplos que podem ajudar nesse monitoramento. Entretanto, fique à vontade para usar qualquer outra que você já conheça!
