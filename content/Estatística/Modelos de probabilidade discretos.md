---
tags:
  - estatística
---

Um modelo de probabilidade é uma função que possui como entrada o valor de uma variável aleatória e retorna a probabilidade.

# *Bernoulli*
O modelo mais fácil para entender modelos probabilísticos é o de *Bernoulli*, pois é um modelo que retorna a probabilidade em cenários em que há apenas um caso para o sucesso e outro para o fracasso. Ou seja, a nossa variável aleatória são os nossos casos de sucesso (1) ou fracasso (0). Temos então:
$$
P(X = x) = p^x \cdot (1-p)^{1-x}.
$$
Perceba que se nossa variável aleatória $X$ for 0 a função retornará a probabilidade de fracasso $1-p$, mas se nossa variável for 1 a função retornará a probabilidade de sucesso $p$.

# Binomial
É natural que o modelo binomial se segue na lista, pois esse modelo retorna a probabilidade em um cenário em que vários ensaios de *Bernoulli* aconteceram. Temos:
$$
P(X=k) = \binom{x}{k} \; \cdot \; p^k \; \cdot \; (1-p)^{x-k}.
$$
É um pouco mais difícil de entender, então é necessário uma abstração utilizando um exemplo sobre imunização: imagine que há uma vacina para imunizar pessoas com 80% de eficiência. Agora, pegamos 3 pessoas que tomaram essa vacina. Temos, portanto, para cada indivíduo 80% de chance deles estarem imunizados. Queremos estudar a variável aleatória $X$: **número de indivíduos imunizados nesse grupo**. Portanto, a nossa variável varia de 0 a 3, pois temos 3 pessoas no grupo que tomaram a vacina. Se calcularmos as probabilidades de cada indivíduo terem sido imunizados ou não, teremos a seguinte tabela:

![[tabela_exemplo_binomial.png]]

Sendo $I$ para imunizado e $I^c$ para não imunizado. Isso é basicamente *Bernoulli*, mas sendo feito repetidas vezes. Entretanto, observe que as variáveis 1 e 2 repetem os mesmos valores. É por isso que nós utilizamos *combinação* na nossa função para levar em conta esses valores repetidos. Por fim, $k$ é a quantidade de casos de sucesso que se deve levar em consideração.

Para fixar, se nosso $k=1$, estaríamos atrás da probabilidade de uma pessoa desse grupo de 3 pessoas estar imunizada. Para acharmos essa probabilidade teríamos:

$$
\begin{align} 
P(X=k) & = \binom{3}{1} \; \cdot \; p^1 \; \cdot \; (1-p)^{3-1} \\
& = 3 \; \cdot \; 0.8 \; \cdot \; 0.2^2,
\end{align}
$$

que é exatamente o que nós encontramos na tabela.