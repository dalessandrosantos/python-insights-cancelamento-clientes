# Python Insights - Analisando Dados com Python

## Case – Cancelamento de Clientes

Este projeto é um estudo de análise de dados em Python com foco em **cancelamento de clientes**.  
Você foi contratado por uma empresa com mais de **800 mil clientes** para entender:

- Por que tantos clientes estão **cancelando o serviço**;
- Quais características mais influenciam o cancelamento;
- Quais ações podem ser tomadas para **reduzir a taxa de cancelamento**.

---

## Objetivos do projeto

- Explorar a base de dados de clientes (ativos e inativos);
- Limpar e tratar os dados, removendo informações irrelevantes ou incompletas;
- Calcular a **taxa de cancelamento geral**;
- Investigar como o cancelamento varia de acordo com:
  - Duração do contrato;
  - Tipo de assinatura;
  - Atrasos de pagamento;
  - Ligações ao call center;
- Utilizar gráficos para facilitar a visualização e interpretação;
- Obter **insights práticos** para o negócio.

---

## Estrutura do projeto

- `main.ipynb` – Notebook principal com toda a análise passo a passo.
- `cancelamentos.csv` – Base de dados com informações dos clientes.

---

## Tecnologias utilizadas

- Python
- Pandas
- Plotly Express
- Jupyter Notebook

---

## Passos da análise

A análise é conduzida em etapas dentro do `main.ipynb`:

1. **Importação da base de dados**

   ```python
   import pandas as pd
   tabela = pd.read_csv("cancelamentos.csv")
   ```

2. **Visualização inicial**

   - Remoção da coluna `CustomerID`, que não é relevante para a análise;
   - Exibição da tabela completa.

3. **Tratamento de dados vazios**

   - Verificação de valores nulos com `tabela.info()`;
   - Remoção de linhas com dados faltantes usando `dropna()`.

4. **Cálculo da taxa de cancelamento**

   - Contagem de clientes que cancelaram e não cancelaram;
   - Cálculo em números absolutos e em percentual.

5. **Análise por tipo de contrato**

   - Distribuição da variável `duracao_contrato`;
   - Cálculo de médias por grupo, para entender o impacto da duração do contrato no cancelamento;
   - Identificação de que **contratos mensais** têm taxa de cancelamento muito alta.

6. **Filtragem de contratos mensais**

   - Remoção dos contratos do tipo `"Monthly"` para entender o cenário sem esse perfil mais problemático;
   - Nova análise da taxa de cancelamento.

7. **Análise por tipo de assinatura**

   - Estudo da variável `assinatura`;
   - Agrupamento e cálculo de médias por tipo de plano;
   - Verificação de que as médias de cancelamento são parecidas entre os tipos, exigindo análise mais profunda.

8. **Análises gráficas**

   Uso do Plotly Express para criar histogramas comparando clientes que cancelaram e não cancelaram:

   ```python
   import plotly.express as px

   for coluna in tabela.columns:
       grafico = px.histogram(tabela, x=coluna, color="cancelou", width=600)
       grafico.show()
   ```

   Com os gráficos, foram identificados padrões importantes, como:
   - Clientes com **mais de 20 dias de atraso** tendem a cancelar;
   - Clientes com **mais de 5 ligações ao call center** também têm probabilidade muito alta de cancelamento.

9. **Filtragem por comportamento de risco**

   - Remoção de clientes com:
     - `ligacoes_callcenter` ≥ 5
     - `dias_atraso` > 20
   - Nova medição da taxa de cancelamento após essas filtragens.

10. **Conclusão**

    - Taxa inicial de cancelamento: **56,7%**  
    - Após os primeiros tratamentos: **46,1%**  
    - Após o refinamento com os gráficos (contratos, atrasos e ligações): **18,4%**

    Principais fatores associados ao cancelamento identificados na análise:

    - **Forma de contrato mensal**;
    - **Alta frequência de ligações ao call center**;
    - **Atraso no pagamento**.

---

## Como executar o projeto

1. **Clonar o repositório**

   ```bash
   git clone https://github.com/dalessandrosantos/NOME-DO-REPOSITORIO.git
   cd NOME-DO-REPOSITORIO
   ```

2. **(Opcional) Criar um ambiente virtual**

   ```bash
   python -m venv .venv
   # Windows
   .venv\Scripts\activate
   # Linux/Mac
   source .venv/bin/activate
   ```

3. **Instalar dependências**

   ```bash
   pip install pandas plotly jupyter
   ```

4. **Abrir o notebook**

   ```bash
   jupyter notebook
   ```

   Em seguida, abra o arquivo `main.ipynb` no navegador e execute as células.

---

## Possíveis melhorias

- Adicionar um modelo de Machine Learning para prever cancelamento (churn);
- Criar dashboards interativos (por exemplo, com Plotly Dash ou Power BI);
- Incluir um dicionário de dados explicando cada coluna da base;
- Automatizar a atualização da análise com novas bases de clientes.

---

Projeto desenvolvido para prática de **Análise de Dados com Python** e obtenção de **insights acionáveis** sobre cancelamento de clientes.
