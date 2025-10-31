# 💬 ETL de Mensagens do Telegram com AWS (Lambda, S3, Glue, Athena)
## Do Telegram à AWS

📋 Descrição do Projeto

Este projeto implementa um pipeline completo de engenharia de dados em nuvem, responsável por extrair, tratar e disponibilizar mensagens de canais públicos do Telegram utilizando serviços serverless da AWS.

As mensagens são coletadas e processadas em Python por funções AWS Lambda, salvas no formato Parquet em um bucket Amazon S3 e disponibilizadas para consulta no Amazon Athena, com o AWS Glue atuando como catálogo e orquestrador da atualização de metadados.

O pipeline é 100% automatizado:

Uma Lambda realiza o tratamento e salvamento dos dados.

Após essa execução, uma segunda Lambda, disparada via AWS Glue, atualiza a tabela do Athena para refletir as novas partições.

🧠 Arquitetura do Pipeline  
[Telegram API]   
     ↓  
[AWS Lambda #1 - Ingestão em Python]  
     ↓  
[Amazon S3 Raw - Armazenamento em JSON]  
     ↓  
[AWS Lambda #2 - ETL em Python]  
     ↓  
[Amazon S3 Enriched - Armazenamento em Parquet]   
     ↓  
[AWS Glue - Catálogo de Dados]   
     ↓  
[AWS Lambda #3 - Atualização de Catálogo]  
     ↓    
[Amazon Athena - Consulta SQL Serverless]    

🎯 Objetivos

Automatizar a coleta e o tratamento de mensagens do Telegram.

Utilizar arquitetura serverless e escalável na AWS.

Armazenar dados em formato otimizado (Parquet).

Atualizar dinamicamente as partições do Athena via Glue.

Prover um fluxo completo de ETL + Data Catalog + Query em nuvem.

⚙️ Tecnologias Utilizadas

Python 3.10+ – desenvolvimento do pipeline

Telegram API – coleta das mensagens

AWS Lambda – execução das funções de ETL e atualização

Amazon S3 – armazenamento dos dados tratados

AWS Glue – catálogo de dados e integração com Athena

Amazon Athena – consultas SQL sobre dados em Parquet

PyArrow / Pandas / Boto3 – processamento e integração Python–AWS

📊 Resultados

Pipeline totalmente automatizado e sem servidores.

Dados salvos em Parquet particionado por data e canal.

Atualização automática do catálogo de metadados no Glue após cada carga.

Consultas SQL diretas no Athena, sem necessidade de infraestrutura adicional.


Thiago Martins LK
- <a href="https://www.linkedin.com/in/thiagomartinslk" target="_blank">Meu LinkedIn</a>
- <a href="https://www.kaggle.com/thiagomartinslk" target="_blank">Meu Kaggle</a>
- <a href="https://github.com/ThiagoMSLK" target="_blank">Meu GitHub</a>
