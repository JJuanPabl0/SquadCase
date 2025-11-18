# 🧠 Google BigQuery – Prática com bq CLI

Esse documento vai mostrar todo o processo que realizei durante o laboratório bq for Google BigQuery, utilizando o BigQuery Command Line Tool (bq) para conseguir explorar os dados do GCP, tambem com criação de datasets, carregar tabelas e executar consultas.

Link do Labotario:
[BQ FOR GOOGLE BIGQUERY](https://www.skills.google/focuses/113704?parent=catalog)

---

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

## Task 2 — Executar consultas SQL

Consulta para buscar palavras contendo "raisin":

```bash
bq query --use_legacy_sql=false     
'SELECT word, SUM(word_count) AS count
 FROM bigquery-public-data.samples.shakespeare
 WHERE word LIKE "%raisin%"
 GROUP BY word'
```

Consulta para buscar a palavra "huzzah":

```bash
bq query --use_legacy_sql=false \
'SELECT word
 FROM bigquery-public-data.samples.shakespeare
 WHERE word = "huzzah"'
```
