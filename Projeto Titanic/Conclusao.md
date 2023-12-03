<h1 style="text-align:center">
    <b>Pré-Processamento</b>
</h1>

#### O Pré-Processamento é o agrupamento de atividades que envolvem converter dados brutos em dados preparados, consequentemente, é o tratamento dos dados de tudo aquilo que entra no modelo, desse modo o Pré-Processamento é feito para entrada de formas úteis e eficientes, estando devidamente preparado, organizado e estruturado; indentificando quais dados serão utlizados anteriormente na utilização do treinamento de modelos.

<br/>

<h1 style="text-align:center">
    <b>Análise de dados</b>
</h1>

#### É feita análise de dados em acordo com gráficos, sendo eles de pizza, barras, linhas e etc. O objetivo principal é extrair informações úteis para observação dos dados, pelos gráficos criados de acordo com os atributos requisitados, como: Quantos sobreviveram e morreram de cada classe da Pclass realizados por um gráfico de linha, a observação nesse gráfico em si foi que a classe 3 representada pelas pessoas de classe alta sobreviveram mais do que as pessoas de classe baixa, diferencialmente na quantidade de pessoas que morreram, a classe baixa teve mais indícios de mortos do que a classe alta. Outrossim, na análise de dados é reconhecido o padrão dos dados anteriormente ao tratamento de dados.

<br/>

<h1 style="text-align:center">
    <b>Tratamento de dados</b>
</h1>

## Tópicos do tratamento de dados:

- ### **Remoção das colunas irrelevantes**
#### Remove-se as colunas que tem dados irreleventes para o treinamento de modelos, em outros termos as colunas que foram removidas tendem a ser dados str que não há a possibilidade de tratamento para int, portanto para remoção é utilizado a função .drop().

<br/>

- ### **Dados Faltantes**
#### Nos dados faltantes é tratado fazendo a média dos dados e/ou colocando "0" para representação que não há existência desse dado, aplicando a função .fillna() que gerencia e permite que substitua os valores; para a média .mean(). No tratamento utilizando a média é feita por causa dos dados númericos faltantes, em síntese se faz a média, então como os valores são idades e equivalentes a quantidades pequenas de dados faltantes é adequado que os dados inexistentes passem a ser o valor calculado da média dos valores existentes. Já o tratamento com o posicionamento do "0" na demonstração de dados inexistentes consiste quando é dado uma string ou seja não há a possibilidade de fazer uma média dos dados, efetuando com que os dados inexistentes passem a ser colocado como um dado "0". Porventura, os dados faltantes terem uma quantidade maior do que os dados existentes é utlizado a função .drop() para remoção da coluna, no sentido de ser inviavel a execução de uma das técnicas em razão da problemática de criar novos dados que não existem, procedendo a uma coluna totalmente criada por dados "falsos".

<br/>

- ### **Dados Categóricos**
#### Os dados categóricos são tratados de str para int, alterando suas classes por dados númericos, empregando a função .replace() que é utilizada para manipulação de variáveis do tipo categórico.

<br/>

- ### **Dados Duplicados**
#### Para os dados duplicados é necessário a remoção delas, usando a função .drop_duplicates(inplace=True) remove todos os dados duplicados de forma automática. Consistindo na importância de não houver números pares de atributos originais, devido que o número repetido pode ser alto tornando uma tarefa computacionalmente custosa, além de produzir uma quantidade de dados desbalanceada.

<br/>

- ### **Normalização dos dados númericos**
#### É utilizada para redução do problma de enviesamento no treinamento de modelos, ao qual pode-se achar que o atributo com a escala maior é mais importante que a menor. Dessa maneira, quando se há intervalos abrangentes entre as variáveis númericas, representados na distribuição de cada atributo necessita fazer a normalização para que os dados estejam no mesmo intervalo, mantendo sua originalidade. Uma das formas para a normalização ser tratada é utilizando o Zscore, uma fórmula estastística que aproxima todos os dados sendo a média em zero e o desvio padrão em 1.

<br/>

- ### **Balanceamento dos dados categóricos**
#### O balanceamento de dados refere-se ao processo de equiparar um determinado conjunto de dados, referindo a quantidade de amostras de cada classe disponível para análise, tornando-se igualmente representadas. Dado que, se houver uma diferença alta dos valores numa amostragem entre os valores positivos e negativos os dados estarão desbalanceados tornando um problema na construção de modelos e na geração de previsões dos mesmos. 


<br/>

##### **Oversampling**: Realiza o aumento de uma amostragem que está com a frequência mínimas da amostragem, dessa forma aplicado o SMOTE sendo uma das técnicas utlizadas para resolução do problema, importado pela função from imblearn.over_sampling import SMOTE.

##### **Undersampling**: Consiste em manter os dados de classe com menor frequência e na diminuição na quantidade dos dados que estão na classe de maior frequência.

<br/>

- ### **One Hot Enconding**
#### Trata os dados categóricos em dados binários, cada dado categórico é criado uma nova coluna, atribuindo no valor de cada linha respectiva como "1" ou "0", sendo classificado os 1 para a presença da característica e do contrário 0, conseguinte melhora o desempenho do modelo, devido a que oferece mais informações da variável categórica. Ademais, com os dados categóricos o modelo tende a classificar os valores pelo seu peso, exemplo: Dentre 0 e 5, o valor 5 tem mais "prioridade" do que o 0, visto que ele qualificará o valor mais alto como peso maior, porém tratando de uma decisão é fundamental que os dados sejam de certa forma classificadas como "sim" ou "não".

<br/>

- ### **CSV tratado**
#### Após todos os tópicos anteriores é situado todos os dados tratados num novo DataSet destinado a ser utilizado no treinamento de modelos.

<br/>

<h1 style="text-align:center">
    <b>Treinamento de Modelos</b>
</h1>

#### Treinamento de modelos é o processo de alimentar um algoritmo com os dados do DataSet atualizado para ajudar a identificar e aprender bons valores para todos os atributos envolvidos. Existindo vários tipos de modelos para treinamento. Com base nisso, os modelos utilizados foram: Ordinary Least Squares (Linear Models); Support Vector Machines (Classification); Nearest Neighbors (Classification); Naive Bayes (Gaussian Naive Bayes); Decision Trees (Classification); Forests of randomized trees (Ensamble methods). 

<br/>

#### Para a elaboração dos modelos é primordial as sepações dos dados, adquirindo os dados X e y, referindo o X como os dados do DataSet sem a coluna alvo, e o y apenas com a coluna alvo. Conseguinte, para cada modelo adquire sua função colocada em uma variável, como por exemplo o modelo MMQ mmq = LinearRegression(), para que o processo do modelo seja executado empregando a função .fit(=X_train, y=y_train), ela ajusta o modelo aos dados que está sendo executado, assim dizendo, ele faz o cálculo do modelo com os dados de treino, em diante a função .predict() permite prever os rótulos dos valores de dados com base no modelo treinado. 

<br/>

<h1 style="text-align:center">
    <b>Validação de Modelos</b>
</h1>

#### Em continuidade para que os dados sejam mostrados como Matriz de confusão, a função confusion_matrix(y_true=y_test, y_pred=y_pred) é executada; as métricas são calculadas usando verdadeiros e falsos positivos, verdadeiros e falsos negativos, assim rotula a verificação de previsões caso estejam certas ou erradas, como: 


##### **TN** (Verdadeiro Negativo): Quando um caso for dado como negativo e ele realmente ser negativo
##### **TP** (Verdadeiro Positivo): Quando um caso for dado como positivo e ele realmente ser positivo
##### **FN**(Falso Negativo): Quando um caso for dado como positivo e ele dar como negativo
##### **FP** (Falso Positivo): Quando um caso for dado como negativo e ele dar como positivo

<br/>

#### Com o englobamento dos quatros valores é calculado a Acurácia, Precisão, Revocação e o F1 Score. 

#### **Acurácia** tem a fórmula de Acurácia = TN+TP/TN+FP+TP+FN, representando o números de instâncias de dados classificados como corretos dividido pelo número total de instâncias de dados, indentificando a performace geral do modelo.
#### No qual a **Precisão** é de todos os positivos previstos, mostrando qual a porcentagem é verdadeiramente positiva, utilizando a formúla Precisão = TP/TP+FP.
#### A **Revocação** é o cálculo do total positivo como valor esperado, dado pela formúla Recall = TP/TP+FN.
#### **F1 Score** é a media harmônica de precisão e revocação fórmula F1 Score = 2*(Precisão*Revocação/Precisão+Revocação)

<br/>

#### Diante dos fatos citados, nos dados adquiridos após a função classification_report, é visto que a precisão dos dados da classe 0 é menor do que os dados da classe 1, inversamente na revocação a classe 0 tem mais porcentagem do que a classe 1, nesse fator concluisse que, pelos dados positivos mais abrangentes na classe 0 a sua porcentagem será menor na precisão do que a revocação devido ao cálculo. Logo a classe 1 é a mais difícil de ser prevista, já que tem menos dados positivos e mais dados negativos dificultando o modelo.

 <br/>

#### Em suma, posteriormente aos processos e o treinamento do modelo foi observado qual modelo alcançou melhor resultado, consistindo no orests of randomized trees (Ensamble methods), por causa de atingir as porcentagens maiores e principalmente pela acurácia elevada em comparação aos outros modelos.