---
tags:
  - estatística
---
O paradoxo de Simpson ocorre quando os dados agrupados possuem uma tendência, mas ao combiná-los essa tendência se inverte ou desaparece. O mesmo conjunto de dados pode mostrar tendências opostas dependendo da maneira como está combinado.

O melhor exemplo para entender esse paradoxo é o famoso _Viés de gênero da Universidade de Berkeley_. Os números de admissões em 1973 mostraram que os homens eram mais propensos do que as mulheres a serem admitidos. Contudo, ao analisar individualmente as taxas de admissão dos departamentos, quatro dos seis departamentos possuíam um viés a favor das mulheres e os dois restantes não possuíam viés de gênero significativo. Os dados agrupados mostraram um viés em favor das mulheres.

Para explicar esse fenômeno, concluíram que as mulheres tendiam a se inscreverem em departamentos muito competitivos em que as taxas de admissão eram baixas até mesmo para os candidatos qualificados, essa variável escondida influenciava os [valores marginais](https://en.wikipedia.org/wiki/Marginal_value) das porcentagens de admissão de tal modo que invertia a tendência que os dados apresentavam como um todo.

Esse fenômeno aparece com regularidade na vida real. O problema está no fato de que a correlação mede a relação entre duas variáveis [_ceteris paribus_](https://pt.wikipedia.org/wiki/Ceteris_paribus) (se não há nenhum outros fatores que influenciem a variável). Se suas classes de dados forem atribuídas aleatoriamente, como elas devem ser em um experimento bem realizado, _ceteris paribus_ pode não ser uma suposição ruim. Entretanto, quando há um padrão escondido nas atribuições das classes, supor _ceteris paribus_ torna-se uma decisão ruim.

A única maneira de evitar isso é conhecendo os seus dados e checar os possíveis fatores que podem confundir sua análise. Infelizmente, nem sempre isso é possível e você poderá acabar concluindo algo de errado sobre os dados.