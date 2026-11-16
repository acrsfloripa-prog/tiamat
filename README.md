<img width="2535" height="380" alt="image" src="https://github.com/user-attachments/assets/c69afcc9-ef14-4780-99a4-e74768a01db7" />


# Tiamat

**Autor**: Arthur Cunha Rangel de Sousa

**Disciplina**: Aprendizado de Máquina

**Instituição**: Ilum Escola de Ciência

**Professor**: Daniel Roberto Cassar - Doutor em Ciência e Engenharia de Materiais pela UFSCAR (2014)

**Linguagem**: Python

## Resumo

Este trabalho tem como objetivo prever a ocorrência de violência unilateral contra civis utilizando técnicas de aprendizado de máquina aplicadas ao conjunto de dados UCDP Country-Year Dataset. Inicialmente, foi realizada uma análise exploratória dos dados para compreender a distribuição das variáveis e suas relações com a variável alvo. Em seguida, foram avaliados diferentes algoritmos de classificação, incluindo Regressão Logística, k-Nearest Neighbors, Árvore de Decisão, Floresta Aleatória e HistGradientBoosting.

Os modelos foram submetidos a um processo de otimização de hiperparâmetros utilizando o Optuna e avaliados por meio de validação cruzada estratificada. O HistGradientBoosting apresentou o melhor desempenho entre os modelos analisados. Além da avaliação tradicional através de métricas de classificação, foi realizada uma análise da importância das variáveis utilizando Permutation Importance para compreender quais fatores exercem maior influência sobre as previsões do modelo, e uma avaliação da robustez do modelo com variação da semente aleatória.

## Sumário

- Introdução
- Conjunto de dados
- Instalação e instruções
- Estrutura do notebook
- Metodologia
- Resultados
- Descrição do uso de IA
- Referências

## Introdução

O Tiamat, trabalho final da disciplina de Aprendizado de Máquina da Ilum Escola de Ciência, propõe que o estudante desenvolva todas as etapas de um fluxo completo de análise de dados, incluindo obtenção e tratamento dos dados, análise exploratória, construção de modelos preditivos, avaliação de desempenho e interpretação dos resultados.

Neste trabalho, o objetivo consiste em prever a ocorrência de violência unilateral contra civis em um país durante um determinado ano. Para essa tarefa, foram utilizadas variáveis relacionadas à localização geográfica, ao período temporal e às características dos conflitos observados, como a existência de conflitos estatais e não estatais e o número de díades/organizações envolvidas em cada conflito.

## Conjunto de dados

Foi utilizado o conjunto de dados UCDP Country-Year Dataset, desenvolvido pelo Uppsala Conflict Data Program (UCDP) [1]. O conjunto reúne informações anuais sobre diferentes formas de violência organizada ao redor do mundo, incluindo conflitos estatais, conflitos não estatais e violência unilateral contra civis. Cada observação representa um país em um determinado ano, contendo informações sobre a ocorrência desses eventos e métricas relacionadas à intensidade dos conflitos.

## Instalação e instruções

Para executar o notebook, recomenda-se a utilização de um ambiente virtual Python com as dependências necessárias instaladas.

### Dependências
- Python 3.10+
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- optuna

As bibliotecas podem ser instaladas utilizando:

pip install pandas numpy matplotlib seaborn scikit-learn optuna

### Execução
- Clone o repositório.
- Instale as dependências.
- Abra o notebook em um ambiente Jupyter.
- Execute as células sequencialmente.

## Estrutura do notebook

O notebook foi organizado nas seguintes seções:

- Introdução
- Organização do conjunto de dados e análise exploratória
- Divisão dos dados em treino e teste
- Modelo baseline
- Pré-processamento dos dados
- Otimização de hiperparâmetros com optuna
- Comparação entre modelos
- O melhor modelo
- Importância de cada variável
- Estratégia oposta de interessante
- Conclusão e principais aprendizados
- Descrição do uso de IA
- Referências

## Metodologia

Inicialmente, foi realizada uma análise exploratória dos dados com o objetivo de compreender as distribuições das variáveis e identificar possíveis relações com a variável alvo.

Em seguida, os dados foram divididos em conjuntos de treino e teste. As variáveis categóricas foram transformadas utilizando One-Hot Encoding, enquanto as variáveis numéricas foram padronizadas por meio do StandardScaler.

Foi desenvolvido um modelo baseline utilizando a estratégia de previsão da classe majoritária, permitindo estabelecer uma referência mínima de desempenho.

Posteriormente, foram treinados cinco algoritmos de classificação:

Regressão Logística;
k-Nearest Neighbors (KNN);
Árvore de Decisão;
Floresta Aleatória;
HistGradientBoosting.
Os hiperparâmetros de cada modelo foram otimizados utilizando o framework Optuna. Cada configuração foi avaliada por meio de validação cruzada estratificada com cinco folds, utilizando o F1-score como métrica de otimização.

Após a seleção do melhor modelo, este foi treinado utilizando todo o conjunto de treino e posteriormente avaliado no conjunto de teste através das métricas Accuracy, Precision, Recall, F1-score e ROC-AUC.

## Resultados

O HistGradientBoosting apresentou o melhor desempenho médio durante a validação cruzada, sendo escolhido como modelo final.

As métricas obtidas no conjunto de teste foram:

- Accuracy:	92,99%
- Precision: 87,07%
- Recall:	80,50%
- F1-score:	83,66%
- ROC-AUC:	96,58%

A análise de importância das variáveis por meio de Permutation Importance indicou que os atributos mais relevantes para as previsões foram country, sb_dyad_count, ns_dyad_count, sb_intrastate_dyad_count, region e year.

Os resultados demonstraram desempenho significativamente superior ao baseline e evidenciaram a capacidade do modelo de identificar padrões associados à ocorrência de violência unilateral contra civis.

## Descrição do uso de IA

Ao longo do trabalho, foi utilizada a IA genertiva Microsoft 365 Copilot, para alguns fins específicos:

- Auxílio na escolha do conjunto de dados;
- Indicação da documentação adequada para os modelos escolhidos;
- Explicações didáticas sobre o código de documentações confusas;
- Aconselhamento na definição do espaço de busca do optuna (hiperparâmetros escolhidos e limite deles);
- Conferência da ordem lógica correta a fim de evitar vazamento de dados (montei um fluxograma da ordem a ser seguida, e requisitei ajustes, se necessário);
- Referenciamento correto das fontes.

## Referências

1. UCDP. UCDP Country-Year Dataset on Organized Violence within Country Borders. Uppsala: Uppsala Conflict Data Program. Disponível em: https://ucdp.uu.se/downloads/. Acesso em: 16 nov. 2026.

2. UCDP. UCDP Organized Violence Country-Year Dataset Codebook. Disponível em: https://ucdp.uu.se/downloads/organizedviolencecy/UCDP_OrganizedViolenceCY_Codebook_261.pdf. Acesso em: 16 nov. 2026.

3. GEORGE, James; WITTEN, Daniela; HASTIE, Trevor; TIBSHIRANI, Robert. An Introduction to Statistical Learning. 2. ed. Cham: Springer, 2021.

4. RASCHKA, Sebastian. Model Evaluation, Model Selection, and Algorithm Selection in Machine Learning. 2020. Disponível em: http://arxiv.org/abs/1811.12808. Acesso em: 16 nov. 2026.

5. SCIKIT-LEARN. Model evaluation: quantifying the quality of predictions. Disponível em: https://scikit-learn.org/stable/modules/model_evaluation.html. Acesso em: 16 nov. 2026.

6. SCIKIT-LEARN. LogisticRegression. Disponível em: https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html. Acesso em: 16 nov. 2026.

7. SCIKIT-LEARN. KNeighborsClassifier. Disponível em: https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html. Acesso em: 16 nov. 2026.

8. SCIKIT-LEARN. DecisionTreeClassifier. Disponível em: https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html. Acesso em: 16 nov. 2026.

9. SCIKIT-LEARN. RandomForestClassifier. Disponível em: https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html. Acesso em: 16 nov. 2026.

10. SCIKIT-LEARN. HistGradientBoostingClassifier. Disponível em: https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.HistGradientBoostingClassifier.html. Acesso em: 16 nov. 2026.

11. SCIKIT-LEARN. Permutation Feature Importance. Disponível em: https://scikit-learn.org/stable/modules/permutation_importance.html. Acesso em: 16 nov. 2026.

12. SEABORN. seaborn.heatmap. Disponível em: https://seaborn.pydata.org/archive/0.11/generated/seaborn.heatmap.html. Acesso em: 16 nov. 2026.

13. SPERAT, Walter. Using Optuna with Scikit-Learn the Right Way - Part 1. Disponível em: https://medium.com/@walter_sperat/using-optuna-with-sklearn-the-right-way-part-1-6b4ad0ab2451. Acesso em: 16 nov. 2026.

14. GEEKSFORGEEKS. HistGradientBoostingClassifier in Scikit-Learn. Disponível em: https://www.geeksforgeeks.org/machine-learning/histgradientboostingclassifier-in-sklearn/. Acesso em: 16 nov. 2026.

15. CASSAR, D. R. Notebooks de aula da disciplina ATP-203 (Aprendizado de Máquina): k-NN e métricas; divisão de dados em treino e teste; modelo linear e baseline; árvore de decisão e floresta aleatória; classificação binária; validação cruzada e otimização de hiperparâmetros; vazamento de dados; dados sintéticos e pipeline; otimização de hiperparâmetros com optuna. Ilum Escola de Ciência, 2026.
