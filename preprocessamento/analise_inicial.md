# Análise Exploratória Inicial

## Visão Geral do Dataset

O dataset possui 535 instâncias e 10 atributos relacionados ao estilo de vida, hábitos físicos e indicadores de saúde dos indivíduos. A variável alvo do problema é `nivel_atividade`, composta pelas classes:

- Sedentario
- Moderadamente_Ativo
- Ativo

A análise exploratória inicial foi realizada no Weka antes da aplicação de qualquer técnica de pré-processamento, permitindo identificar características estatísticas, possíveis inconsistências e problemas presentes no conjunto de dados.

| Característica           | Valor                          |
|--------------------------|--------------------------------|
| Total de instâncias      | 535                            |
| Total de atributos       | 9 (8 preditores + 1 classe)   |
| Atributos numéricos      | 8                              |
| Atributos nominais       | 1 (cor_roupa_favorita)        |
| Atributo irrelevante     | cor_roupa_favorita             |
| Classe                   | nivel_atividade (3 valores)   |

## Análise dos Atributos

Os atributos numéricos analisados foram:

- idade
- horas_sono
- passos_diarios
- horas_sentado
- freq_exercicio_semana
- imc
- horas_tela
- consumo_agua_litros

Além disso, o dataset possui os atributos nominais:

- cor_roupa_favorita
- nivel_atividade

Os atributos apresentaram distribuições variadas, médias coerentes e diferentes amplitudes de valores, indicando diversidade entre os perfis simulados no conjunto de dados.

## Valores Faltantes

Foram identificados valores ausentes nos seguintes atributos:

- horas_sono
- passos_diarios
- freq_exercicio_semana
- imc
- horas_tela
- consumo_agua_litros

Cada um desses atributos apresentou aproximadamente 4% de valores faltantes, representando um cenário realista de inconsistência e incompletude dos dados.

## Presença de Outliers

Durante a análise estatística, foram identificados possíveis outliers em alguns atributos.

O atributo `passos_diarios` apresentou valores extremos, variando entre 0 e 30000 passos por dia, enquanto sua média foi de aproximadamente 6949 passos. Esses valores discrepantes indicam instâncias distantes da distribuição principal dos dados.

O atributo `imc` apresentou valores máximos elevados, chegando a 47.9, enquanto `horas_tela` atingiu valores de até 14.2 horas diárias, também caracterizando possíveis comportamentos extremos.

## Atributo Irrelevante

O atributo `cor_roupa_favorita` foi identificado como irrelevante para o problema de classificação, pois não possui relação lógica direta com o nível de atividade física dos indivíduos.

Sua presença foi intencional, visando simular cenários reais em que bases de dados podem conter atributos sem relevância preditiva.

## Distribuição das Classes

A variável alvo apresentou distribuição relativamente equilibrada entre as classes:

| Classe               | N   | %    |
|----------------------|-----|------|
| Sedentario           | 190 | 35,5 |
| Moderadamente_Ativo  | 186 | 34,8 |
| Ativo                | 159 | 29,7 |

Isso reduz problemas relacionados ao desbalanceamento severo de classes durante o treinamento dos modelos.


**Observação:** O dataset é levemente desbalanceado, com a classe
`Ativo` tendo ~6% menos instâncias. Isso deve ser considerado
na escolha da métrica de avaliação (preferir F1-macro a acurácia simples).

## Presença de Ruído

Também foram observadas possíveis inconsistências e ruídos no conjunto de dados, como indivíduos classificados em categorias incompatíveis com alguns padrões esperados de comportamento físico.

A presença desses elementos foi inserida de forma intencional para tornar o dataset mais próximo de situações reais e aumentar a complexidade do processo de modelagem.