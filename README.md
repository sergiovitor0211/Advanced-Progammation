# Trabalho -- Programação Avançada: Classificação de Diabetes

## Sobre o projeto

Este repositório contém o trabalho de análise exploratória e aprendizado
de máquina para classificação de diabetes.

O projeto utiliza um conjunto de dados com **403 observações e 19
variáveis**. Como o conjunto original não apresentava uma variável-alvo
adequada para o problema proposto, a variável `diabetes` foi criada a
partir de `glyhb`.

Os registros sem informação de `glyhb` foram tratados separadamente para
evitar classificações incorretas.

## Arquivos

-   `Trabalho_Diabetes_Programacao_Avancada.ipynb` --- notebook
    principal com a análise exploratória, tratamento dos dados,
    treinamento dos modelos, avaliação dos resultados e conclusão.
-   `diabetes.csv` --- conjunto de dados utilizado no trabalho.
-   `melhor_modelo_diabetes.joblib` --- arquivo contendo o melhor modelo
    treinado e os objetos de pré-processamento necessários para
    utilizá-lo.

## Modelos utilizados

Foram avaliados dois métodos de aprendizado de máquina:

-   **K-Nearest Neighbors (KNN)**
-   **Random Forest**

A divisão dos dados foi realizada em:

-   **80%** para treinamento;
-   **20%** para teste;
-   utilizando **estratificação** para manter a proporção das classes.

### Pré-processamento

Para o KNN:

-   valores numéricos ausentes foram preenchidos pela mediana;
-   valores categóricos ausentes foram preenchidos pela categoria mais
    frequente;
-   as variáveis numéricas foram padronizadas;
-   as variáveis categóricas foram codificadas.

Para o Random Forest:

-   valores numéricos ausentes foram preenchidos pela mediana;
-   valores categóricos ausentes foram preenchidos pela categoria mais
    frequente;
-   as variáveis categóricas foram codificadas;
-   não foi realizada padronização, pois o algoritmo não depende da
    escala das variáveis.

A variável `glyhb` não é utilizada como entrada dos modelos, pois ela
foi usada para criar a variável-alvo `diabetes`, evitando vazamento de
dados.

## Avaliação

Os modelos foram comparados utilizando:

-   Acurácia
-   Precisão
-   Recall
-   F1-score
-   ROC-AUC
-   Matriz de confusão

Os dois modelos atingiram a acurácia mínima de **85%** estabelecida para
o trabalho.

O **Random Forest apresentou o melhor desempenho geral** e foi
selecionado como o melhor modelo.

## Análise exploratória

O notebook investiga questões como:

1.  As classes estão balanceadas?
2.  Existem dados ausentes ou valores que precisam de tratamento?
3.  Quais variáveis apresentam distribuições diferentes entre as
    classes?
4.  Existem relações fortes entre as variáveis numéricas?
5.  Qual modelo apresenta melhor desempenho em dados não vistos?

As respostas são apresentadas por meio de tabelas, estatísticas e
gráficos no notebook.

## Como executar

### 1. Instalar as bibliotecas

O projeto utiliza Python e bibliotecas como:

``` text
pandas
numpy
matplotlib
scikit-learn
joblib
```

Caso necessário, elas podem ser instaladas com:

``` bash
pip install pandas numpy matplotlib scikit-learn joblib
```

### 2. Manter os arquivos na mesma pasta

O notebook procura o dataset com:

``` python
ARQUIVO = Path("diabetes.csv")
```

Portanto, mantenha `diabetes.csv` na mesma pasta do notebook.

### 3. Executar o notebook

Abra:

`Trabalho_Diabetes_Programacao_Avancada.ipynb`

O notebook pode ser executado no Google Colab ou em um ambiente
Jupyter/Python compatível.

## Modelo salvo

O arquivo:

`melhor_modelo_diabetes.joblib`

contém o modelo selecionado como melhor resultado, juntamente com os
objetos de pré-processamento utilizados no treinamento.

O modelo selecionado no trabalho foi o **Random Forest**.

## Observação

Os resultados apresentados neste trabalho são experimentais e não devem
ser interpretados como uma ferramenta de diagnóstico médico. O conjunto
possui algumas centenas de observações, apresenta desequilíbrio entre as
classes e contém valores ausentes em algumas variáveis.

## Autor

**Sérgio Vitor**

Trabalho acadêmico -- Programação Avançada.
