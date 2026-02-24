# Código da Aplicação

Esta pasta contém o código do FinanBot, agente de organização financeira pessoal que utiliza Streamlit + Ollama (modelo local).

## Estrutura Sugerida

```
src/
├── app.py                # Interface principal em Streamlit
├── agente.py             # Lógica do FinanBot (montagem de contexto + chamada ao modelo)
├── dados.py              # Funções para carregar JSON/CSV
├── prompts.py            # System prompt estruturado
├── data/
│   ├── dados_usuario.json
│   ├── gastos_mensais.json
│   └── historico_mensal.csv
└── requirements.txt      # Dependências do projeto
```
## Descrição dos Arquivos
| Arquivo      | Responsabilidade                              |
| ------------ | --------------------------------------------- |
| `app.py`     | Interface visual e interação com o usuário    |
| `agente.py`  | Monta o contexto e envia requisição ao Ollama |
| `dados.py`   | Carrega dados locais (JSON/CSV)               |
| `prompts.py` | Define o System Prompt do FinanBot            |
| `data/`      | Base de conhecimento mockada                  |

## Requirements.txt
### Como o projeto roda localmente com Ollama:
```
streamlit
pandas
requests
```

## Como Rodar

```bash
# Instalar dependências
pip install -r requirements.txt

# Certificar-se de que o Ollama está rodando
ollama run llama3

# Rodar a aplicação FinanBot
streamlit run src/app.py
```
