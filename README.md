# Python Insights - Analisando Dados com Python

Este projeto é um exercício de análise de dados em Python, focado em **cancelamento de clientes**.  
A ideia é entender, a partir de uma base de dados de mais de 800 mil clientes, quais são os principais motivos de cancelamento e quais ações podem ser tomadas para reduzir esse número.

## Tecnologias utilizadas

- Python 3
- Jupyter Notebook
- Pandas

## Arquivos do projeto

- `main.ipynb` – Notebook principal com toda a análise.
- `cancelamentos.csv` – Base de dados utilizada na análise.

## Como executar

1. Clone o repositório:

   ```bash
   git clone https://github.com/dalessandrosantos/python-insights-cancelamento-clientes.git
   cd python-insights-cancelamento-clientes
   ```

2. Crie um ambiente virtual (opcional, mas recomendado):

   ```bash
   python -m venv .venv
   source .venv/bin/activate  # Linux/Mac
   .venv\Scripts\activate     # Windows
   ```

3. Instale as dependências principais:

   ```bash
   pip install pandas jupyter
   ```

4. Abra o Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. No navegador, abra o arquivo `main.ipynb` e execute as células.

## Objetivo da análise

- Importar e tratar a base de dados de cancelamento de clientes.
- Explorar as variáveis disponíveis (idade, sexo, tempo como cliente, frequência de uso, ligações ao call center, dias de atraso, tipo de assinatura, duração do contrato, total gasto, meses desde a última interação, cancelou ou não).
- Identificar padrões e possíveis motivos que levam ao cancelamento.
- Sugerir ações que possam reduzir o número de cancelamentos.

---
Projeto de estudo para prática de análise de dados com Python.
