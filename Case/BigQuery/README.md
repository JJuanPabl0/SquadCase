# 🧠 Google BigQuery – Prática com bq CLI

Esse documento vai mostrar todo o processo que realizei durante o laboratório bq for Google BigQuery, utilizando o BigQuery Command Line Tool (bq) para conseguir explorar os dados do GCP, tambem com criação de datasets, carregar tabelas e executar consultas.

Link do Labotario:
[BQ FOR GOOGLE BIGQUERY](https://www.skills.google/focuses/113704?parent=catalog)


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


## Task 4 — Criar Dataset e Carregar Tabela

Listar datasets existentes

```bash
bq ls
```

Listar datasets públicos

```bash
bq ls bigquery-public-data:
```

Criar dataset chamado babynames

```bash
bq mk babynames
```


Download e extração dos arquivos

```bash
wget http://www.ssa.gov/OACT/babynames/names.zip
ls
unzip names.zip
ls
```

Carregar tabela names2010 no dataset

```bash
bq load babynames.names2010 yob2010.txt \
name:string,gender:string,count:integer
```

Verificar schema

```bash
bq show babynames.names2010
```

