---
description: Como a alta dimensionalidade afeta sua análise de dados
tags:
  - estatística
---
"The curse of dimensionality" de Altman e Krzywinski é um artigo que discorre sobre a maldição que uma grande quantidade de dados podem trazer para sua análise estatística. Vou elencar alguns pontos importantes que o artigo traz pra você ter em mente quando estiver trabalhando com muitos dados.  
  
- Se você tiver poucas amostras, quanto maior o número de variáveis (p) mais esparsa elas serão, pois o número de dimensões aumenta. Em uma distribuição normal com uma única dimensão com valor 1.5, 32% dos pontos caem em 1 desvio padrão da média. Se você aumentar o número de variáveis para p > 2, essa porcentagem cai drasticamente para aproximadamente 1,2% e sucessivamente para mais variáveis. Essa esparsidade pode te atrapalhar na hora de coletar dados representativos.

  ![[Pasted image 20240510200602.png]]

- Avaliar se um dado é um outlier se torna penoso quando se há muitas variáveis. 68% dos pontos em uma distribuição normal caem dentro do desvio padrão da média se você tiver apenas uma variável, mas se você tiver 10 variáveis, essa porcentagem cai para 0.017%. A correlação também é afetada, com 100 variáveis e 10,000 pares de pontos nós não conseguimos observar correlações maiores que 0.5.

  ![[Pasted image 20240510200634.png]]

- Com dados em que o número de amostras é menor que o número de variáveis surge um outro problema que afeta nossa análise: multicolinearidade perfeita. Multicolinearidade pode atrapalhar especialmente se você estiver tentando prever algo e quiser interpretar a predição, pois se uma variável pode ser expressa pela combinação linear das outras, não há como saber qual o verdadeiro impacto que as variáveis causam individualmente em nossa previsão.  

- Em cenários de testes para saber se uma variável possui um efeito significativo na resposta/alvo, os valores padrões de p-values geram muitos falsos positivos com uma grande quantidade de variáveis. Pra mitigar isso, é possível controlar a taxa de falsa descoberta, o que por sua vez pode aumentar as taxas de falsos negativos.

  ![[Pasted image 20240510200649.png]]
  
- Overfitting talvez seja um dos problemas mais conhecidos causados pela alta dimensionalidade. A flexibilidade de algumas equações pertencentes a alguns algoritmos de ML é, em parte, determinada pela quantidade de variáveis. Se você tiver um modelo muito flexível, ele se adaptará bastante aos dados de treino, pois identificará padrões inúteis ou aleatórios, levando a um overfitting.  

# Solução?

Redução do número de variáveis e PCA são métodos famosos para tentar mitigar os efeitos da alta dimensionalidade, mas as vezes não são suficientes. É necessário, além de métodos de redução de dimensionalidade, domínio sobre os dados para identificar uma análise que leve em conta todas as possíveis variáveis que contribuem para o processo que está sendo analisado e que decida sobre o impacto da utilização de um conjunto específico e reduzido das variáveis.