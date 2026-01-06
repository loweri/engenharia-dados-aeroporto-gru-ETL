# ✈️ Pipeline de Engenharia de Dados: Aeroporto de Guarulhos (GRU)

![Status](https://img.shields.io/badge/Status-Concluído-success)
![Python](https://img.shields.io/badge/Python-3.9+-blue?logo=python)
![Spark](https://img.shields.io/badge/Spark-PySpark-orange?logo=apachespark)
![Databricks](https://img.shields.io/badge/Databricks-Community-red?logo=databricks)
![License](https://img.shields.io/badge/License-MIT-green)

> 📊 Pipeline ETL automatizado processando dados reais da ANAC com arquitetura Medallion (Bronze, Silver, Gold).

---

## 📌 Sobre o Projeto
Este projeto desenvolve um pipeline de dados completo (ETL) para analisar as operações de voo do **Aeroporto Internacional de Guarulhos (GRU)**. Utilizando dados públicos da **ANAC**, foi construída uma arquitetura **Medallion (Bronze, Silver, Gold)** no Databricks para transformar dados brutos em inteligência de negócios.

O objetivo principal é demonstrar competências em **Engenharia de Dados**, **Qualidade de Dados** e **Analytics**, respondendo perguntas sobre horários de pico, atrasos e cancelamentos.

## 📂 Estrutura do Projeto & Arquitetura

O projeto segue a arquitetura *Multi-hop* (Medallion). Abaixo, os links para o código e a visualização rápida (HTML):

| Etapa | Notebook | Descrição | Visualização |
|:---:|---|---|:---:|
| 🥉 | `Extract` | **Ingestão (Raw -> Bronze)**<br>Leitura de CSV e padronização Snake Case. | [📄 Ver HTML](./Extract~etl_gru_airport_(bronze-layer)-HTML.html) |
| 🥈 | `Transform` | **Limpeza (Bronze -> Silver)**<br>Filtro de escopo (GRU), Tipagem de Datas e tratamento de nulos. | [📄 Ver HTML](./Transform~etl_gru_(silver-layer)-HTML.html) |
| 🥇 | `Load` | **Agregação (Silver -> Gold)**<br>Cálculo de KPIs: Picos, Market Share, Atrasos e Cancelamentos. | [📄 Ver HTML](./Load~etl_gru_(gold-layer)-HTML.html) |

## 🛠️ Stack Tecnológico
* **Plataforma:** Databricks (Community Edition)
* **Processamento:** Apache Spark (PySpark) & SQL
* **Armazenamento:** Delta Lake
* **Formato de Dados:** CSV (Fonte) -> Delta (Tabelas Otimizadas)

---

## 📊 Resultados e Insights

### 1. Fluxo de Horários (Picos)
Identificação visual dos picos de tráfego aéreo (Manhã e Noite) vs. Janelas de baixa (Madrugada).
![Fluxo de Horarios](./images/Flights_daily-24h.png)

### 2. Market Share (Domínio de Mercado)
A **LATAM** e a **GOL** representam a vasta maioria das operações em GRU, seguidas pela Azul.
![Market Share](./images/top_delay_airlines.png)

### 3. Ranking de Cancelamentos
Volume absoluto de voos cancelados por companhia aérea.
![Cancelamentos](./images/top_cancelledflights_airline.png)

### 4. Média de Atrasos (Minutos)
Empresas de **Carga** (ex: Atlas Air) tendem a ter médias de atraso maiores que as companhias comerciais de passageiros.
![Atrasos](./images/avg_delay.png)

---

<details>
<summary>🇺🇸 <strong>Click here for English Version</strong></summary>

# ✈️ Data Engineering Pipeline: Guarulhos Airport (GRU)

## 📌 Project Overview
This project builds an end-to-end data pipeline (ETL) to analyze flight operations at **Guarulhos International Airport (GRU)**. Using public data from **ANAC (Brazilian Civil Aviation Agency)**, a **Medallion Architecture (Bronze, Silver, Gold)** was implemented on Databricks to transform raw data into business intelligence.

The main goal is to demonstrate proficiency in **Data Engineering**, **Data Quality**, and **Analytics**, answering business questions regarding peak hours, delays, and cancellations.

## 📂 Project Structure

| Stage | Notebook | Description | Quick View |
|:---:|---|---|:---:|
| 🥉 | `Extract` | **Ingestion Phase**<br>Raw data ingestion and schema normalization. | [📄 View HTML](./Extract~etl_gru_airport_(bronze-layer)-HTML.html) |
| 🥈 | `Transform` | **Cleaning Phase**<br>Scope filtering (GRU only), Date typing, and null handling. | [📄 View HTML](./Transform~etl_gru_(silver-layer)-HTML.html) |
| 🥇 | `Load` | **Aggregation Phase**<br>Creating analytical tables and KPIs using SQL/PySpark. | [📄 View HTML](./Load~etl_gru_(gold-layer)-HTML.html) |

## 📊 Key Insights

### 1. Peak Hour Traffic
Visual identification of traffic peaks (Morning/Evening) vs. maintenance windows.
![Peak Hours](./images/Flights_daily-24h.png)

### 2. Market Share
LATAM and GOL account for the vast majority of operations at GRU.
![Market Share](./images/top_delay_airlines.png)

### 3. Cancellation Ranking
Total volume of cancelled flights by airline.
![Cancellations](./images/top_cancelledflights_airline.png)

### 4. Average Delay
Cargo airlines tend to have higher average delays compared to commercial passenger airlines.
![Average Delay](./images/avg_delay.png)

</details>

---
*Project developed for Data Engineering portfolio purposes.*
