# 📈 Projeto Python IA: Previsão de Score de Crédito de Clientes

![Python](https://img.shields.io/badge/Python-3.10-blue)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Status](https://img.shields.io/badge/Status-Concluído-green)
![Machine Learning](https://img.shields.io/badge/Algoritmos-Random%20Forest%20%7C%20KNN-brightgreen)

## 🎯 Objetivo do Projeto

O objetivo principal deste projeto é desenvolver e avaliar um modelo de Machine Learning capaz de analisar diversas características de clientes e prever automaticamente o seu score de crédito. Essa capacidade preditiva pode auxiliar instituições financeiras na tomada de decisões mais assertivas sobre concessão de crédito, gerenciamento de riscos e personalização de serviços.

## 🚀 Tecnologias Utilizadas

* **Python:** Linguagem de programação principal.
* **Pandas:** Para manipulação e análise de dados.
* **Scikit-learn:** Para pré-processamento, construção e avaliação de modelos de Machine Learning.
* **Jupyter Notebook:** Ambiente interativo para o desenvolvimento do projeto.

## 📊 Estrutura dos Dados

O projeto utiliza dois arquivos CSV:

* `clientes.csv`: Dados históricos dos clientes com `score_credito` conhecido (rótulo para treinamento).
* `novos_clientes.csv`: Dados de novos clientes sem o score definido, para quem o modelo fará previsões.

As colunas principais incluem (mas não se limitam a): `idade`, `profissao`, `salario_anual`, `num_contas`, `num_cartoes`, `juros_emprestimo`, `dias_atraso`, `mix_credito`, `divida_total`, `taxa_uso_credito`, `comportamento_pagamento`, entre outras.

> 💡 As categorias de score previstas pelo modelo são:
> - **Ruim**
> - **Ok**
> - **Bom**

## 🧠 Metodologia

1. **Importação e Exploração Inicial dos Dados**
   - Leitura dos dados com `pandas`
   - Visualização e entendimento da estrutura do dataset

2. **Pré-processamento**
   - Transformação de colunas categóricas com `LabelEncoder`
   - Remoção de colunas irrelevantes (ex: `id_cliente`)
   - Preparação dos dados para modelagem

3. **Divisão dos Dados**
   - Separação em treino (70%) e teste (30%) com `train_test_split`

4. **Treinamento de Modelos**
   - `RandomForestClassifier`
   - `KNeighborsClassifier` (com dados não normalizados)

5. **Avaliação de Desempenho**
   - Comparação por `accuracy_score`
   - Random Forest obteve melhor resultado

6. **Previsão para Novos Clientes**
   - Aplicação do mesmo pipeline de pré-processamento
   - Uso do modelo final para gerar o `score_credito` previsto

## ✨ Resultados

O modelo final (`RandomForestClassifier`) alcançou uma **acurácia aproximada de 82%** no conjunto de teste. As previsões geradas para os novos clientes foram integradas ao dataset original para facilitar a análise e tomada de decisão.

## 💻 Como Executar o Projeto

1. **Clone o repositório:**
    ```bash
    git clone https://github.com/caiovinigomes/previsao-score-credito.git
    cd previsao-score-credito
    ```

2. **Crie um ambiente virtual (opcional, mas recomendado):**
    ```bash
    python -m venv venv
    # Windows:
    .\venv\Scripts\activate
    # macOS/Linux:
    source venv/bin/activate
    ```

3. **Instale as dependências:**
    ```bash
    pip install -r requirements.txt
    ```
    (Caso não tenha um arquivo `requirements.txt`, pode criar com `pip freeze > requirements.txt` ou usar `pip install pandas scikit-learn jupyter`.)

4. **Coloque os arquivos de dados na pasta do notebook:**
   - `clientes.csv`
   - `novos_clientes.csv`

5. **Execute o notebook:**
    ```bash
    jupyter notebook
    ```
    Abra o arquivo `inicial_com_markdowns.ipynb` e execute as células.

## 📁 Saída Esperada

O notebook gera um novo dataframe com os clientes e suas respectivas previsões de score. O resultado pode ser exportado para CSV para uso externo:

```python
novos_clientes['score_previsto'] = previsoes
novos_clientes.to_csv('novos_clientes_com_score.csv', index=False)
```

## 🛠️ Contribuições
Contribuições são bem-vindas! Se você quiser melhorar o projeto, corrigir algo ou adicionar funcionalidades, abra uma issue ou envie um Pull Request.

## 📄 Licença
Este projeto está sob a licença MIT License.

## 👤 Autor
**Nome:** Caio Vinicius Silva Gomes

**LinkedIn:** [www.linkedin.com/in/caiovinicius-gomes](www.linkedin.com/in/caiovinicius-gomes)