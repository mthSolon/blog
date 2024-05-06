---
tags:
  - estatística
---

>[!summary] Resumo
>R² é uma medida-resumo, também utilizada como métrica em análise de regressões, que quantifica o grau de associação entre uma variável qualitativa e uma variável quantitativa.

>[!missing] MELHORAR
>O que está sendo descrito aqui é o mesmo que o R² comumente utilizado na avaliação de modelos de ML?

No estudo da associação entre variáveis qualitativas e quantitativas convém utilizar a variância para construir uma medida. A variância calculada para a variável quantitativa para todos os dados mede a dispersão dos dados globalmente. Se a variância dentro de cada categoria for pequena e menor do que a global, significa que a variável qualitativa melhora a capacidade de previsão da quantitativa e portanto existe uma relação entre as duas variáveis.

Necessita-se, então, de uma medida-resumo da variância entre as categorias da variável qualitativa. Vamos usar a média das variâncias, porém ponderada pelo número de observações em cada categoria, ou seja:
$$\overline{var(X)} = \frac{\sum_{i=1}^k n_i var_i(X)}{\sum_{i=1}^k n_i}$$
no qual $k$ é o número de categorias da variável qualitativa e $var_i(X)$ denota a variância de X dentro da categoria $i$, $i = 1, 2, \dots, k$.

Podemos mostrar que $\overline{var(X)} \le var(X)$, de modo que podemos definir o grau de associação entre as duas variáveis como o ganho relativo na variância, obtido pela introdução da variável qualitativa. Ou seja,
$$R^2 = \frac{var(X) - \overline{var(X)}}{var(X)} = 1 - \frac{\overline{var(X)}}{var(X)}.$$
Note que $0 \le R^2 \le 1$. O símbolo $R^2$ é usual em análise de variância e regressão, sendo uma métrica bastante conhecida.