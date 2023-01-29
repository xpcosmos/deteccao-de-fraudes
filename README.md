# Detecção de Fraudes
## Introdução

O presente projeto tem o objetivo de explorar técnicas de classificação aplicadas na detecção de fraudes bancárias. Foi utilizado um conjunto de dados com poucos registros e que apresentava um comum problema do mundo real, o desbalanceamento de dados. Foi utilizado técnicas de pré-processamento do SKlearn como o OneHotEncoder e algoritmos de aprendizado pouco complexos com regressão logística, árvore de decisão e floresta aleatória.

## Resultados

Os dados foram submetidos a pré-processamento para ajuste de dados alfabéticos em numéricos assim como a remoção de atributos irrelevantes para a análise. Os atributos removidos eram informações dos clientes que não agregariam na criação do modelo. Após o pré-processamento, os dados foram dividos em conjuntos de treino e teste e durante a construção do baseline foi notado que o conjunto apresentava um desbalanceamento de classes. Para a resolução do problema foi utilizado um algoritmo de oversample chamado de SMOTE para criação de dados sintéticos. Após o ajuste, a acurácia do modelo foi reduzida, no entanto, também apresentou um aumento substancial nas métricas de Recall e precisão. Os resultados podem ser visualizados abaixo:

Métrica|DecisionTreeClassifier|LogisticRegression|RandomFlorest
-------|----------------------|------------------|-------------
**Acurácia**	| 0.9595 |0.9417|0.9695
**Precisão**	| 0.9379|0.9241|0.9805
**Recall**	| 0.9839|0.9623|0.9579
**F1**		| 0.96042|0.94287|0.9691

## Conclusão

Visando que a finalidade do modelo foi de evitar fraudes, podemos definir que o modelo que seria escolhido em nosso cenário hipotético seria o DecisionTreeClassifier, já que apresenta o menor valor de Recall, considerando que, é preferível para uma instituição financeira que seja classificado erroneamente transações financeiras não fraudulentas do que haver fraudes que não foram detectas, já que seria um maior prejuízo financeiro tanto para a instituição quanto para o cliente.