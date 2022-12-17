# Análise de Cluster I - Métodos Hierárquicos
Projeto em Análise de Cluster utilizando Método Hierárquico, desenvolvido durante meu MBA em Data Science & Analytics, pela ESALQ/USP.

Para estudarmos como realizar uma análise de clusters, vamos carregar um pequeno banco de dados com notas de vestibular de 3 disciplinas (variáveis), de 5 alunos diferentes (observações). O objetivo é agrupar alunos com desempenho semelhante.

Vamos carregar e visualizar a base de dados Vestibular:

![Rplot_clustering_1_2](https://user-images.githubusercontent.com/96158594/208254712-783da66c-429f-4e02-9b9a-5a035a74c2d2.png)

Vamos plotar, para melhor visualização, um gráfico 3D com scatter, para identificarmos a posição de cada estudante em relação às disciplinas:

![Rplot_clustering_I](https://user-images.githubusercontent.com/96158594/208254335-7d2f388e-020e-4844-8bd9-4917018a071d.png)

Vamos plotar as estatísticas descritivas em um gráfico interativo, com ggplotly:

![Rplot_clustering_I_3](https://user-images.githubusercontent.com/96158594/208254417-d4d8344e-d462-4848-9546-9d3b8363b7ba.png)

ESQUEMA DE AGLOMERAÇÃO HIERÁRQUICO

Vamos iniciar agora o esquema de aglomeração hieráriquico, de fato. 

Devemos escolher qual será a MEDIDA DE DISSIMILARIDADE que utilizaremos. A medida de dissimilaridade refere-se à distância entre as observações, com base nas variáveis escolhidas. Portanto, indica o quanto as observações são diferentes entre si.

Neste projeto, vamos utilizar a Medida Euclidiana.

Para a elaboração da clusterização hieráriquica, iremos utilizar o método de encadeamento o Single Linkage ou Nearest Neighboor.

Vamos extrair algumas informações do nosso interesse:

1. COEFICIENTES: os valores das distâncias em que ocorreram as junções no esquema de clusterização:

![Rplot_clustering_I_5](https://user-images.githubusercontent.com/96158594/208254537-c2aba54b-b0da-4986-924c-a7d4edb827ca.png)

Quando os valores em Cluster 1 e 2 forem negativos, significa junções de observações;
Quando forem positivos, significa o cluster formado naquele estágio.

(-) O sinal negativo significa a observação por si só.
(+) O sinal positivo significa o cluster ao qual ele se refere.

-1: OBSERVAÇÃO 1
1: CLUSTER 1

Vamos construir o dendrograma para visualização das etapas de formação dos clusters:

![Rplot_clustering_I_7](https://user-images.githubusercontent.com/96158594/208254564-9eb85988-7b6d-47e1-980c-67d97a6d75f3.png)

ESQUEMA DE AGLOMERAÇÃO NÃO-HIERÁRQUICO

1. Neste esquema, a primeira parte também deverá ser a padronização das unidades de medida das variáveis em ZScore.

2. Em seguida, vamos elaborar os clusters definindo quantos clusters queremos.

Aplicamos o número 3 como input no método não-hierárquico, pois foi o nosso output no método hierárquico. Mas se não houvéssemos feito o primeiro método antes, como saber qual o k ótimo para aplicar?

Podemos, neste caso, utilizar o método Elbow, onde a dobra do gráfico permite identificar o número ótimo de clusters.

![Rplot_clustering_I_8](https://user-images.githubusercontent.com/96158594/208254681-f6cdf21d-f303-4d6e-a949-b49ed268ed8a.png)

Agora vamos criar mais uma variável categórica para indicação do cluster no banco de dados originial e comprar a atuação dos dois métodos:

![Rplot_clustering_I_9](https://user-images.githubusercontent.com/96158594/208254691-3aea031a-6cf0-41cb-817e-fcd372e29c30.png)

Aqui podemos notar que os resultados foram os mesmos, pois as observações foram alocadas nos mesmos clusters.

Ao analisar a variância de um fator para o método não-hierárquico, também vemos que os resultados são os mesmos.

Deixo o script completo, com explicações e códigos.
