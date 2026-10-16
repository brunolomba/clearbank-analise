# ClearBank - Análise Financeira com Python
Desafio Final 3º módulo da Pós de IA e Automação da RocketSeat.

## Sobre o Projeto
Este projeto consiste no desenvolvimento de uma esteira completa de processamento e análise de dados financeiros para a fintech fictícia **ClearBank**. A solução foi projetada para lidar com arquivos brutos de transações bancárias (`transacoes.csv`) contendo inconsistências comuns do mundo real — como registros corrompidos, campos em branco, datas mal formatadas e dados fora do padrão de negócio.

Construído prioritariamente com os módulos nativos do Python (sem dependência inicial de bibliotecas de terceiros), o script aplica regras rigorosas de validação, organiza métricas mensais de consolidação e exporta relatórios estruturados para consumo de outros sistemas.

## Principais Funcionalidades
- **Leitura & Sanitização Silenciosa:** Processamento de dados via `csv.DictReader` com captura e descarte resiliente de linhas inválidas através de blocos `try/except` customizados.
- **Métricas Financeiras Mensais:** Agrupamento por competência (`AAAA-MM`) calculando volume total de transações, soma de créditos/débitos, saldo final, ticket médio e extremos (maior e menor movimentação).
- **Detecção de Fraudes / Transações Suspeitas:** Sinalização automática e isolamento de qualquer operação com valor superior ao teto parametrizado (`R$ 10.000,00`).
- **Relatório Estruturado em Terminal:** Apresentação formatada no padrão monetário brasileiro (`R$`), com cálculo do intervalo temporal analisado (dias decorridos).
- **Exportação JSON:** Geração automática do arquivo `relatorio.json` contendo o resumo consolidado dos dados limpos e a listagem de registros suspeitos.
- **Requisitos Opcionais (RO):** 
  - Comparativo de integridade dos cálculos via script dedicado com `pandas` (`analise_pandas.py`).
  - Geração de dashboard visual do balanço financeiro (`grafico.png`) utilizando `matplotlib`.
 
## Como Executar o Projeto

Você pode executar o notebook no **Google Colab** ou no **Jupyter Notebook local**. Todas as células devem ser executadas em sequência, do início ao fim.

---

### Opção 1: Executar no Google Colab

1. Acesse o [Google Colab](https://colab.research.google.com/).
2. Clique em **Arquivo**, **Abrir notebook** e selecione a aba **GitHub**.
3. Cole o link deste repositório e clique no arquivo **`desafio-final.ipynb`**.
4. No menu superior, vá em **Ambiente de execução** → **Reiniciar e executar tudo** (ou use o atalho `Ctrl + F9`).

---

### Opção 2: Executar no Jupyter Notebook Local

1. Com o repositório baixado e as dependências instaladas, abra o terminal na pasta do projeto e inicie o Jupyter:
   ```bash
   jupyter notebook desafio-final.ipynb

## O que o notebook gera

Ele gera os dados organizados em: relatorio.json, analise_pandas.py e um gráfico.png. (além dos resultados no terminal dentro do código).
