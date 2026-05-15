# Análise Exploratória Inicial

## Visão Geral do Dataset

O dataset utilizado neste trabalho possui 535 instâncias e atributos relacionados ao estilo de vida, hábitos físicos e indicadores de saúde dos indivíduos. A variável alvo do problema é `nivel_atividade`, composta pelas classes:

- Sedentario
- Moderadamente_Ativo
- Ativo

A análise exploratória inicial foi realizada no Weka antes da aplicação de qualquer técnica de pré-processamento. Essa etapa teve como objetivo investigar o comportamento geral dos dados, identificar possíveis inconsistências, analisar distribuições estatísticas e detectar problemas que poderiam impactar o treinamento dos modelos de aprendizado de máquina.

Durante essa fase, foram analisados:
- valores mínimos e máximos;
- médias e desvios padrão;
- presença de valores faltantes;
- possíveis outliers;
- distribuição das classes;
- atributos irrelevantes;
- possíveis ruídos e inconsistências.

| Característica | Valor |
|---|---|
| Total de instâncias | 535 |
| Total de atributos | 10 |
| Atributos numéricos | 8 |
| Atributos nominais | 2 |
| Atributo irrelevante | cor_roupa_favorita |
| Classe alvo | nivel_atividade |

---

# Análise dos Atributos

Os atributos numéricos analisados foram:

- idade
- horas_sono
- passos_diarios
- horas_sentado
- freq_exercicio_semana
- imc
- horas_tela
- consumo_agua_litros

Além disso, o dataset apresentou os atributos nominais:

- cor_roupa_favorita
- nivel_atividade

Os atributos apresentaram distribuições variadas e amplitudes diferentes de valores, indicando diversidade entre os perfis simulados no conjunto de dados. Também foi possível observar relações iniciais entre alguns atributos e a variável alvo, principalmente em variáveis associadas ao comportamento sedentário e prática de exercícios físicos.

---

# Valores Faltantes

Foram identificados valores ausentes nos seguintes atributos:

- horas_sono
- passos_diarios
- freq_exercicio_semana
- imc
- horas_tela
- consumo_agua_litros

Cada um desses atributos apresentou aproximadamente:

```txt
22 valores faltantes (~4%)
```

A presença desses valores simulou cenários realistas de incompletude dos dados, situação bastante comum em aplicações reais de mineração de dados e aprendizado de máquina.

A identificação desses elementos foi importante para definir posteriormente a estratégia de tratamento dos valores ausentes durante o pré-processamento.

---

# Presença de Outliers

Durante a análise estatística inicial foram identificados possíveis outliers em alguns atributos numéricos.

## passos_diarios

O atributo `passos_diarios` apresentou:
- valor mínimo igual a 0;
- valor máximo igual a 30000;
- média aproximada de 6949 passos.

Esses valores indicaram presença de instâncias significativamente distantes da distribuição principal dos dados.

---

## imc

O atributo `imc` apresentou valores máximos elevados, chegando a:

```txt
47.9
```

caracterizando possíveis comportamentos extremos relacionados ao índice de massa corporal.

---

## horas_tela

O atributo `horas_tela` apresentou valores de até:

```txt
14.2 horas diárias
```

indicando indivíduos com comportamento sedentário extremo relacionado ao uso excessivo de telas.

A presença desses outliers foi considerada importante para tornar o dataset mais próximo de situações reais.

---

# Atributo Irrelevante

O atributo:

```txt
cor_roupa_favorita
```

foi identificado como irrelevante para o problema de classificação do nível de atividade física.

Esse atributo não possui relação lógica direta com:
- saúde;
- prática de exercícios;
- hábitos sedentários;
- comportamento físico.

Sua presença foi inserida intencionalmente para simular cenários reais em que bases de dados podem conter atributos sem relevância preditiva.

---

# Distribuição das Classes

A variável alvo apresentou distribuição relativamente equilibrada entre as classes:

| Classe | Quantidade | Percentual |
|---|---|---|
| Sedentario | 190 | 35,5% |
| Moderadamente_Ativo | 186 | 34,8% |
| Ativo | 159 | 29,7% |

Essa distribuição reduziu problemas relacionados ao desbalanceamento severo de classes durante o treinamento dos modelos.

Entretanto, observou-se leve redução na quantidade de instâncias da classe `Ativo`, representando aproximadamente 6% menos exemplos em relação às demais categorias.

Apesar disso, o desbalanceamento foi considerado pequeno e não comprometeu significativamente o processo de classificação.

---

# Presença de Ruído

Durante a análise exploratória também foram observadas possíveis inconsistências e ruídos no conjunto de dados.

Algumas instâncias apresentaram:
- comportamentos parcialmente contraditórios;
- sobreposição entre perfis;
- características intermediárias entre classes.

Exemplos observados:
- indivíduos sedentários com quantidade relativamente elevada de passos;
- indivíduos moderadamente ativos próximos do perfil de ativos;
- combinações incomuns entre atributos.

Esses ruídos foram inseridos propositalmente para aumentar a complexidade do problema e tornar o cenário mais próximo de aplicações reais de aprendizado de máquina.

---

# Considerações da Análise Inicial

A análise exploratória mostrou que o dataset apresentava:
- boa diversidade entre atributos;
- separação parcial entre classes;
- presença controlada de problemas reais de dados;
- atributos relevantes para classificação.

Os principais desafios identificados foram:
- valores faltantes;
- presença de outliers;
- ruídos;
- atributo irrelevante;
- sobreposição parcial entre classes.

As informações obtidas nessa etapa foram fundamentais para orientar as decisões tomadas posteriormente durante o pré-processamento e treinamento dos modelos de classificação.