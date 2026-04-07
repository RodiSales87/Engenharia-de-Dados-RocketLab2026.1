# Engenharia-de-Dados-RocketLab2026.1: E-Commerce utilizando Arquitetura Medalhão

Este projeto consiste na estruturação de dados de um grande e-commerce utilizando a arquitetura Data Lakehouse no Databricks. O objetivo é implementar um pipeline de ETL completo para transformar dados brutos em Data Marts analíticos e KPIs de negócio.

## 📂 Estrutura do Projeto
O pipeline é dividido em três camadas lógicas de processamento:

**Bronze**: Ingestão dos arquivos CSV do dataset Olist e consumo da API do Banco Central para obter a cotação do dólar.
**Silver**: Limpeza, deduplicação sênior via *Window Functions*, tradução total de colunas para o português e otimização física via Delta Lake (Z-ORDER).
**Gold**: Consolidação de Data Marts para visão comercial (vendas e receitas) e qualidade (satisfação de clientes e performance de vendedores).

## 🚀 Como Rodar
Para executar a solução no Databricks, siga estes passos:

1.  **Ingestão**: Carregue os arquivos CSV originais em um **Volume** no Data Lakehouse.
2.  **Notebooks**: Importe e execute os notebooks na ordem sequencial abaixo:
    1.  `Atividade_land_to_bronze.ipynb`
    2.  `Atividade_bronze_to_silver.ipynb`
    3.  `Atividade_silver_to_gold.ipynb`
3.  **Orquestração**: Configure um **Databricks Workflow (Job)** para automatizar a execução sequencial das tarefas com agendamento diário às 13:00.

## 📦 Conteúdo do Repositório
Os 3 notebooks da solução em formato `.ipynb`.
Arquivo de configuração do Job exportado em `.yaml`.
Imagem (print) da execução de sucesso do Job exibindo as dependências.
