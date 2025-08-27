# previsao-de-resultados-do-brasileirao
Projeto de Machine Learning para prever resultados de jogos do Campeonato Brasileiro utilizando odds de apostas.

# Previsão de Resultados do Campeonato Brasileiro

![Data-Football](https://www.football-data.co.uk/brazil.php)
![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-1.0+-orange.svg)

## 📖 Visão Geral

Este projeto utiliza técnicas de Machine Learning para prever os resultados de partidas de futebol da Série A do Campeonato Brasileiro. A partir de um conjunto de dados históricos contendo informações sobre jogos e odds de apostas, foi desenvolvido um modelo de classificação K-Nearest Neighbors (KNN) para determinar a probabilidade de um dos dois resultados: "Vitória do Time da Casa" ou "Empate ou Vitória do Time Visitante".

O objetivo é demonstrar um fluxo completo de um projeto de ciência de dados, desde a limpeza e preparação dos dados até o treinamento, otimização e implementação de um modelo preditivo.

##  dataset

O conjunto de dados utilizado, `BRA.csv`, contém registros de jogos da Série A do Brasil desde 2012. As colunas mais importantes para este projeto foram:

* `Season`: O ano da temporada.
* `Res`: O resultado final da partida (H: Vitória da Casa, D: Empate, A: Vitória do Visitante).
* `PSCH`, `PSCD`, `PSCA`: As odds de fechamento da casa de apostas Pinnacle para vitória do time da casa, empate e vitória do time visitante, respetivamente.

## ⚙️ Metodologia

A análise e construção do modelo foram realizadas no notebook Jupyter `PRES_2.ipynb` e seguiram os seguintes passos:

1.  **Carregamento e Limpeza de Dados**: Os dados foram carregados e as colunas irrelevantes para o modelo foram removidas.
2.  **Engenharia de Features**: A coluna de resultado (`Res`) foi transformada numa variável alvo numérica (`Res_num`), onde `0` representa a vitória do time da casa e `1` representa empate ou vitória do visitante.
3.  **Filtragem de Dados**: Para tornar o modelo mais relevante para o cenário atual do futebol, foram utilizados apenas os dados a partir da temporada de 2020.
4.  **Balanceamento de Classes**: Como o número de vitórias do time da casa era significativamente maior, foi aplicada a técnica de *downsampling* na classe majoritária para evitar que o modelo se tornasse tendencioso.
5.  **Treinamento do Modelo**: Foi escolhido e treinado um classificador K-Nearest Neighbors (KNN). O número de vizinhos (`k`) foi otimizado para `k=29` após testes.
6.  **Previsão**: O modelo treinado é capaz de receber as odds de uma partida futura e retornar a previsão de resultado com as respetivas probabilidades.

## 🚀 Como Usar

Para executar este projeto e fazer as suas próprias previsões, siga os passos abaixo.

### Pré-requisitos

Certifique-se de que tem o Python 3 instalado. As bibliotecas necessárias estão listadas no ficheiro `requirements.txt`.

### Instalação

1.  Clone o repositório:
    ```bash
    git clone [https://github.com/SEU-NOME-DE-USUARIO/previsao-futebol-brasileirao.git](https://github.com/SEU-NOME-DE-USUARIO/previsao-futebol-brasileirao.git)
    cd previsao-futebol-brasileirao
    ```


### Fazendo uma Previsão

Para prever o resultado de um jogo, pode usar o script `previsao_de_resultados_do_brasileirao`. Abra o ficheiro, insira as odds da Pinnacle para a partida desejada e execute-o.

```python
# Dentro de previsao_de_resultados_do_brasileirao

# 1. Encontre as odds da Pinnacle para o jogo.
# 2. Substitua os valores de exemplo abaixo.

odds_time_da_casa = 2.50  # Ex: Vasco
odds_empate = 3.40
odds_time_visitante = 2.80  # Ex: Botafogo

# 3. Execute o script e veja o resultado no terminal
# python prever_jogo.py
```

O script irá carregar os dados, treinar o modelo e imprimir uma análise detalhada da partida com as probabilidades calculadas.