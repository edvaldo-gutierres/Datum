# Projeto Datum 

Olá Datum, espero que esteje tudo bem com vocês.

Eu sou Edvaldo Gutierres - [LinkedIn](https://www.linkedin.com/in/edvaldo-gutierres-6b4a5768/)

📊 Este repositório contém todos os notebooks e scripts utilizados no meu teste técnino  para a vaga de Desenvolvedor Python (Engenheiro de Dados).

**Objetivo**: O projeto foca na análise de dados de vendas do dataset Olist E-commerce disponível no Kaggle, seguindo as melhores práticas de ETL (Extract, Transform, Load) e preparação de dados para analise de dados.

![!\[worflow/olist.png)](Worflows/olist.png)

## 📁 Estrutura do Projeto

O projeto está organizado em várias pastas correspondentes às camadas de processamento de dados: `Ingestion`, `Bronze`, `Silver`, e `Gold`, além de uma pasta `Data Mining` para exploração de dados e `Worflow` para detalhar as job criadas.

---
### 🔗 Ingestion
Aqui realizamos a conexão com a API do Kaggle para baixar o dataset Olist E-commerce. Os dados são inicialmente salvos na camada `Raw` no DBFS do Databricks, com possibilidade de armazenamento em soluções de nuvem como Azure Data Lake Storage Gen2.

---
### 🔄 Bronze
Após a ingestão dos dados na camada `Raw`, processamos e adicionamos a coluna `row_ingestion_timestamp`. Os dados são então armazenados em formato Parquet na camada `Bronze`. Importante: em um ambiente de produção, consideraríamos estratégias de carga avançadas e o particionamento de dados para otimizar a gestão de dados.

---
### 🔍 Silver
Nesta etapa, aplicamos técnicas de qualidade de dados, como remoção de duplicatas e tratamento de nulos, e armazenamos os dados limpos na camada `Silver` em formato Parquet ou Delta, conforme a função escolhida. Também incluímos uma tabela intermediária `inter_sales` para auxiliar na modelagem dos dados.

---
### 🏆 Gold
Para o desenvolvimento da camada `Gold`, foi definido perguntas simples com foco em responder questões de negócio como a quantidade de pedidos por diferentes dimensões. 
Sendo elas:
    - Quantidade de Pedidos por:
        - Status
        - Tempo
        - Cliente
        - Produto

 Preparamos os dados para serem consumidos por ferramentas de visualização, seguindo as boas práticas de modelagem para Power BI (schema em estrela). Foi aplicados conceitos de modelagem starschema propostos por Ralph Kimball.

---
### ⛏️ Mining
Realizamos uma exploração de dados para entender melhor os padrões e validar as transformações. Criamos visualizações e relatórios para comunicar insights, como a tendência de pedidos ao longo do tempo e flutuações sazonais.

---
## 🚀 Workflows
Todas as etapas de processamento de dados foram implementadas e agendadas como jobs no Databricks, assegurando a automação e a execução eficiente do pipeline de dados. As jobs estão configuradas para garantir que a ingestão, o processamento e a modelagem dos dados sejam realizados sequencialmente, com a garantia de integridade e atualização dos dados.

As jobs do Databricks também facilitam a colaboração entre membros da equipe e a escalabilidade do projeto, permitindo ajustes e expansões conforme necessário. A configuração detalhada e os logs de execução das jobs podem ser encontrados na pasta.

---
## 🙏 Agradecimentos
---

Agradeço pela oportunidade, qualquer dúvida estou sempre a disposição.
