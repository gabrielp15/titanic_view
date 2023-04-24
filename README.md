# Titanic - Análise e visualização de dados
Projeto de visualização de dados básicas da tragédia do Titanic com Python/Pandas/Matplotlib/Power BI



Para montar todo esse projeto, seguiremos os seguintes passos:
- Obtenção básica dos dados (Aquisição dos dados);
- Tratamento dos dados;
- Análise dos dados;
- Construção da visualização básica
- Visualização dos dados com o Power BI


## Introdução
  Opa, bom dia! Boa Tarde! Boa noite!
Como primeiro projeto básico de todos que estão na carreira de dados, sejam engenheiros, cientistas, ou analistas, temos o famoso "Titanic Database", muito utilizado para fazer as primeiras explorações e manipulações básicas de dados, com diversas ferramentas como o Pandas, Numpy, Matplotlib, Seaborn, etc.

  Diante disso, vamos fazer algo um pouco diferente. Vamos catalogar todos os dados da tragédia do Titanic, explorando números de pessoas embarcadas, classes, valores pagos por cabine, sexo, idade, etc, fazer o tratamento desses dados, e gerar insights através de visualizações rápidas com gráficos pelo Matplotlib/Seaborn, e montar também visualizações interativas com o Power BI.

Dito isso, vamos aos dados!

### 1 - Obtenção básica dos dados
  Para Obtenção dos dados que serão utilizados no projeto, temos databases já prontos na internet. Vamos utilizar um disponibilizado no [Kaggle](https://www.kaggle.com/competitions/titanic/data?select=train.csv), e disponibilizá-lo através deste [arquivo](https://github.com/gabrielp15/titanic_view/blob/539eaaf020681f1d3a2cbd277c5e60a0daf0a603/databse.csv) no nosso repositório. Para trabalharmos nos dados no primeiro momento, vamos utilizar o Google Colab, visto sua praticidade de uso por ser totalmente online - na nuvem - e não requerer a instalação de nenhum software na nossa máquina, além claro, de nos oferecer uma quantidade considerável de poder computacional de forma gratuita. É a solução que julgo ser mais dinânica no momento (Nada impede de montar todo esse projeto no Jupyter notebook, etc. Mas como meu objetivo aqui é sair do "comum", vamos experimentar novas soluções")
  Vamos carregar as bibliotecas que vamos utilizar durante essa parte inicial do projeto, o Pandas, MatplotLib, o Numpy, e atribuir **alias** para eles.
```
import pandas as pd
import numpy as np
import matplotlib as mlt
```
 A partir daí, podemos carregar nossa base de dados, e começar nossas análises de fato.
```
dados = 'https://raw.githubusercontent.com/gabrielp15/titanic_view/539eaaf020681f1d3a2cbd277c5e60a0daf0a603/databse.csv' 
data = pd.read_csv(dados)
data
 ```
> Importante: Atribui o nome **Data** para nossos dados, a partir daí todos os comandos vão ser construídos com essa variável.

![image](https://user-images.githubusercontent.com/104700476/233997634-0c1b1cbd-bde1-43ec-a4f8-4c740e047662.png)
  
Com o comando `data.shape`, podemos verificar que temos uma considerável quantidade de dados, distribuidas em 12 colunas, e 891 linhas, com diversos dados, e em diversos formatos. Vemos diversas informações disponiveis nas colunas, como nome do passageiro, sexo, idade, n° do Ticket, se sobreviveu ou não, entre outros.

![image](https://user-images.githubusercontent.com/104700476/233997946-f5adb7dd-fbca-47c0-8227-94e8460e5c11.png)

Diante desses dados disponíveis, vamos seguir adiante para nossa próxima etapa.


### 2 - Tratamento dos dados
Vamos visualizar o seguinte cenário: Temos todos esses dados disponíveis para nossa utilização, entretanto queremos ver o relacionamento entre as mais diversas tabelas, como a porcentagem de sobreviventes/vítimas por sexo/idade/classe em que embarcou, preço médio da tarifa que foi paga, quantidade de passageiros por porto de embarque, etc.
Mas, para criarmos nossos relatórios com informações objetivas, e criarmos visualizações dinâmicas e precisas, precisamos executar uma limpeza nesses dados.
Dito isso, vamos adiante!

#### Células vazias no nosso DB
Através do comando `data.count()`podemos verificar a quantidade de células vazias que existem em cada coluna.
![image](https://user-images.githubusercontent.com/104700476/233999734-455ed2c8-11ef-4c56-be80-593de9cd0d7a.png)
Feito isso, vamos utilizar o comando 

