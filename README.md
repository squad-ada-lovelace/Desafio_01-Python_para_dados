![Desafio 1 - Python para Dados](imagens/Desafio_1_banner.png)  

# Desafio 1 - Python para Dados

Primeiro desafio prático desenvolvido pela **Squad Ada Lovelace** durante o **Bootcamp Data Analytics**, promovido pela **WoMakersCode**.

O objetivo deste desafio foi colocar em prática os primeiros conceitos de Python voltados para análise de dados por meio da resolução colaborativa de exercícios.


## Sobre o desafio

O desafio propôs uma Análise Exploratória de Dados (EDA) a partir de uma base fictícia sobre saúde do sono e estilo de vida, contendo informações de 373 pessoas e 13 características (colunas) cada (profissão, duração do sono, pressão sanguínea, frequência cardíaca, passos diários, entre outras).

A partir dessa base, o grupo precisou responder a 10 perguntas de investigação, usando pandas e numpy para tratar, agrupar e interpretar os dados — sem tratamento de dados faltantes, já que a base foi disponibilizada limpa.

É possível acessar o arquivo em Jupyter Notebook clicando [aqui](/Ada_Lovelace_Python_para_Dados___Bootcamp_Data_Analytics_2026_1.ipynb).

## O que foi feito

O notebook segue essa estrutura:

1. **Importação e inspeção inicial** dos dados (`shape`, `info`, `describe`).
2. **Renomeação de colunas** para nomes mais claros e em português (ex.: `ID` → `Identificador`, correção de `Pressão sanguíneaaaa` → `Pressão sanguínea`).
3. **Resolução das 10 perguntas do desafio**, cada uma com o código utilizado e a resposta redigida logo abaixo.

## Perguntas respondidas

| # | Pergunta | Resumo do código | Resposta |
|---|----------|-------------------|----------|
| 1 | Renomear colunas da base | `df.rename(columns={...})` para corrigir e traduzir nomes de colunas | Colunas ajustadas para nomes corretos e em português |
| 2 | Média, moda e mediana de sono por profissão | `groupby('Profissão')` + `agg(mean, pd.Series.mode, median)`, ordenado pela mediana | Estatísticas calculadas e ordenadas por profissão |
| 3 | % de obesos entre Engenheiros de Software | Filtro por profissão e por categoria de IMC, divisão entre os totais | 25% |
| 4 | Advogados ou representantes de vendas dormem menos? | Filtro com `isin()` + `groupby('Profissão').mean()` | Advogados dormem acima da média geral (7,13h); representantes de vendas, abaixo |
| 5 | Enfermagem x Medicina: quem dorme menos? | Filtro com `isin()` + `groupby('Profissão').mean()` | Médicos dormem em média 0,08h a menos que enfermeiros |
| 6 | Subconjunto com Identificador, Gênero, Idade, Pressão sanguínea e Frequência cardíaca | Seleção direta de colunas: `df[[...]]` | Subconjunto criado com as colunas solicitadas |
| 7 | Profissão menos frequente | `value_counts(ascending=True).head(1)` | Gerente, com apenas 1 pessoa |
| 8 | Pressão sanguínea média: homens x mulheres | `str.split('/')` para separar sistólica/diastólica, correção do tipo com `.astype()`, depois `groupby('Gênero').mean()` | Mulheres têm pressão levemente acima da média geral; homens, abaixo |
| 9 | Dormir 8h é o mais comum? | `df['Duração do sono'].mode()` | Não. A moda da duração de sono é 7,2h |
| 10 | FC acima de 70 x passos diários | `groupby(df['Frequência cardíaca'] > 70)['Passos diários'].mean()`, lógica condicional para printar a resposta | Pessoas com FC ≤ 70 dão mais passos, em média |

## Tecnologias utilizadas

- Python
- Pandas
- Numpy
- Jupyter Notebook

## Como executar

1. Clone este repositório.
2. Abra o notebook `Ada_Lovelace_Python_para_Dados___Bootcamp_Data_Analytics_2026_1.ipynb` no Jupyter ou no Google Colab.
3. Execute as células em ordem — a base de dados é carregada diretamente de uma URL, sem necessidade de download manual.

--- 

<p align="center">
  Feito com 💜 por nosso Squad!
</p>

