# Prompts do Agente

> [!Tip]
> ## Prompt usado para esta etapa:
> 
> Você é um agente especializado em análise de dados financeiros estruturados.
> 
> Seu objetivo é interpretar corretamente os dados enviados no contexto.
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

# Base de Conhecimento

## Dados Utilizados

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `dados_usuario.json` | JSON | Personalizar recomendações |
| `gastos_mensais.json` | JSON | Sugerir produtos adequados ao perfil |
| `historico_mensal.csv` | CSV | Analisar padrão de gastos do cliente |

---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

Foram realizadas as seguintes adaptações:

- Criação de categorias fixas (Alimentação, Moradia, Transporte, Lazer, Outros)

- Padronização de datas no formato DD/MM/AAAA

- Estrutura simplificada para facilitar leitura pelo modelo

- Organização dos valores como números inteiros ou decimais (sem formatação textual)

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.

Os arquivos JSON/CSV são carregados no início da sessão do Streamlit utilizando leitura local de arquivos.

```python

import json
import pandas as pd

# funções para carregar dados

def carregar_dados_usuario(caminho_json='data/dados_usuario.json'):
    """Carrega dados básicos do usuário"""
    with open(caminho_json, 'r', encoding='utf-8') as f:
        dados = json.load(f)
    return dados

def carregar_gastos_mensais(caminho_json='data/gastos_mensais.json'):
    """Carrega gastos mensais categorizados"""
    with open(caminho_json, 'r', encoding='utf-8') as f:
        gastos = json.load(f)
    return gastos

def carregar_historico_mensal(caminho_csv='data/historico_mensal.csv'):
    """Carrega histórico de movimentações financeiras"""
    df = pd.read_csv(caminho_csv)
    return df
```

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

```text
DADOS DO USUÁRIO (dados_usuario.json):
{
  "nome": "João Silva",
  "renda_mensal": 3000,
  "perfil_financeiro": "Moderado",
  "meta_poupanca": 500
}

GASTOS MENSAIS DO USUÁRIO (gastos_mensais.json):
[
  {
    "data": "01/02/2026",
    "categoria": "Alimentação",
    "descricao": "Supermercado",
    "valor": 450
  },
  {
    "data": "03/02/2026",
    "categoria": "Lazer",
    "descricao": "Streaming",
    "valor": 55
  },
  {
    "data": "05/02/2026",
    "categoria": "Transporte",
    "descricao": "Uber",
    "valor": 120
  },
  {
    "data": "10/02/2026",
    "categoria": "Moradia",
    "descricao": "Aluguel",
    "valor": 1200
  }
]

HISTÓRICO DOS GASTOS MENAIS (historico_mensal.csv):

data,categoria,descricao,valor
01/01/2026,Alimentação,Supermercado,400
02/01/2026,Lazer,Cinema,80
05/01/2026,Transporte,Ônibus,50
10/01/2026,Moradia,Aluguel,1200
15/01/2026,Outros,Presentes,200

```

---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

```
Dados do Usuário:
- Nome: João
- Renda Mensal: R$ 3.000

Resumo Atual:
- Total de Gastos: R$ 2.400
- Saldo Restante: R$ 600

Gastos por Categoria:
- Alimentação: R$ 800
- Aluguel: R$ 1.200
- Lazer: R$ 400

Instrução:
Responda apenas com base nos dados acima.
Caso a informação não esteja disponível, informe que não possui dados suficientes.

```
