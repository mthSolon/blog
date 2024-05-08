---
tags:
  - estatística
---
Um modelo de probabilidade é uma função que retorna a probabilidade de uma variável aleatória acontecer.

# Uniforme
Um modelo uniforme retorna a mesma probabilidade para todas as variáveis discretas. Por exemplo, você comprou cinco números numa loteria que permite escolher até 100, os números que você escolheu foram: 10, 11, 12, 13 e 14. O seu amigo comprou, também, cinco números: 7, 34, 43, 55 e 67. Pela nossa intuição, o seu amigo tem mais chances de ganhar porque ele escolheu números mais espaçados, mas, na verdade, você e ele tem a mesma chance porque os números possuem as mesmas probabilidades: $1/100$. 

Neste cenário, nós temos um modelo uniforme porque não importa qual número você escolha (variável aleatória), a função retornará a mesma probabilidade:

$P(X=x_j) = 1/k,$ para todo $j = 1, 2, ..., k$.
# *Bernoulli*
Assim como o modelo uniforme, *Bernoulli* é bem fácil de entender, pois é um modelo que retorna a probabilidade em cenários em que há apenas um caso para o sucesso e outro para o fracasso. Ou seja, a nossa variável aleatória são os nossos casos de sucesso (1) ou fracasso (0). Temos então:
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
P(X=k) & = \binom{3}{1} \cdot p^1 \cdot (1-p)^{3-1} \\
& = 3 \cdot 0.8 \cdot 0.2^2,
\end{align}
$$

que é exatamente o que nós encontramos na tabela.

Hmm, mas eu não poderia apenas dizer que há uma chance de 80% de uma pessoa desse grupo estar imunizada? No início pode ser que você se confunda com isso, mas essa probabilidade vale apenas para um cenário onde há **UM** indivíduo. Por isso você usa *Bernoulli*, ou ele está imunizado ou não. Entretanto, no caso acima em que temos um grupo é diferente, pois precisamos considerar a probabilidade de estar imunizado ou não de cada indivíduo para cada cenário diferente, ou seja... *Bernoulli* repetidas vezes.

# Geométrico
O modelo geométrico pode ser entendido como o número de ensaios de *Bernoulli* que acontecem antes do primeiro sucesso. Ou seja, podemos obter a probabilidade de uma variável aleatória $k$ acontecer **ANTES** do caso de sucesso $p$ acontecer.
$$
P(X=k) = p(1-p)^k,
$$
com $p$ sendo a probabilidade de sucesso e $k$ nossa variável aleatória.

> [!NOTE] Nota
> Por "**sucesso**", não significa, necessariamente, o caso em que algo positivo acontece, mas qualquer caso que seja visto como sucesso pela variável aleatória. Por exemplo, se nossa variável aleatória fosse "quantidade de peças boas antes da defeituosa", teríamos a "**peça defeituosa**" como o caso de sucesso.


Vamos ao exemplo: temos uma vacina que possui 1% de chance de falha. Qual a probabilidade de 20 pessoas serem imunizadas ao tomarem a vacina antes que ela apresente uma falha?

É necessário que cada vacinação não influencie na probabilidade de outra vacina, portanto, supondo independência entre as vacinas teríamos:
$$
\begin{align}
P(X=20) & = 0,01 \cdot 0,99^{20} \\
& = 0,0081.
\end{align}
$$
Portanto, a chance da vacina **imunizar** 20 pessoas **antes da vacina falhar** seria de 0,81%.

