# 🧠 Google BigQuery – Prática com bq CLI

Esse documento vai mostrar todo o processo que realizei durante o laboratório bq for Google BigQuery, utilizando o BigQuery Command Line Tool (bq) para conseguir explorar os dados do GCP, tambem com criação de datasets, carregar tabelas e executar consultas.

## Task 1 — Examinar uma Tabela

Utilizei a tabela pública `samples.shakespeare`, que tem todas as palavras encontradas nas obras de Shakespeare.

Comando executado:

```bash
bq show bigquery-public-data:samples.shakespeare
```


E esse comando vai mostrar: 

- Schema

- Número de linhas

- Tamanho da tabela

