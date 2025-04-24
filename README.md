# Coleta e Armazenamento de Cotações de Moedas

Este projeto realiza um processo simples de engenharia de dados para coletar, processar, armazenar e exportar cotações de moedas estrangeiras utilizando Python.

## Objetivo

Automatizar a coleta de cotações de moedas e armazenar os dados em um banco de dados local para posterior análise ou integração com outras aplicações.

## Tecnologias Utilizadas

- Python
- Pandas
- Requests
- SQLAlchemy
- SQLite
- Excel (exportação via `.to_csv` com extensão `.xlsx`)

## Fontes de Dados

Os dados de câmbio são obtidos da API pública da [AwesomeAPI - Economia](https://docs.awesomeapi.com.br/api-de-moedas).

## Etapas do Processo

1. **Coleta de Dados**  
   É feita uma requisição à API para obter as cotações das moedas: USD-BRL, EUR-BRL, BTC-BRL, e ARS-BRL.

2. **Transformação**  
   Os dados brutos são transformados em um DataFrame estruturado com as colunas: `moeda`, `cotacao`, `alta`, `baixa`, `data_hora`.

3. **Armazenamento**  
   Os dados são inseridos em uma base de dados SQLite chamada `cotacoes.db` na tabela `cotacoes_moedas`.

4. **Exportação**  
   Os dados da tabela são lidos do banco e exportados para um arquivo `.xlsx`.

## Como Executar

1. Clone o repositório ou baixe o notebook `api.ipynb`.
2. Certifique-se de ter as bibliotecas necessárias instaladas:
   ```bash
   pip install pandas requests sqlalchemy
