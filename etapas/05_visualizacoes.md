# Etapa 05 — Visualização dos Dados

## 1. Objetivo das Visualizações

Após a etapa de pré-processamento, foram realizadas diferentes visualizações no Weka com o objetivo de analisar:
- separação entre classes;
- comportamento dos atributos;
- relações entre variáveis;
- presença de sobreposição entre grupos;
- padrões relevantes para classificação.

As visualizações foram utilizadas como ferramenta analítica para apoiar a interpretação dos dados e compreender como os atributos se relacionam com a variável alvo `nivel_atividade`.

Todos os gráficos foram gerados utilizando os recursos de visualização do Weka após o pré-processamento do dataset.

---

# 2. Estratégia de Visualização

Os gráficos foram construídos utilizando:
- atributos numéricos no eixo X;
- atributos numéricos no eixo Y;
- coloração baseada na classe `nivel_atividade`.

As cores utilizadas pelo Weka permitiram identificar visualmente:
- indivíduos sedentários;
- indivíduos moderadamente ativos;
- indivíduos ativos.

As imagens geradas foram armazenadas na pasta: ([imagens](../imagens/visualizacao_weka))

```txt
/imagens/visualizacao_weka
```

---

## 3. Primeira Visualização

A primeira visualização foi entre:

| Eixo | Atributo |
|---|---|
| X | passos_diarios |
| Y | freq_exercicio_semana |

Imagem:

![Alt text](../imagens/visualizacao_weka/dispersao_passos_exercicio.png)

A visualização de dispersão entre os atributos `passos_diarios` e `freq_exercicio_semana` demonstrou uma separação parcial entre as classes do problema. Observamos que indivíduos classificados como `sedentários` concentram em regiões com menor frequência de exercícios e menor quantidade de passos diários, enquanto indivíduos `ativos` aparecem majoritariamente em regiões de valores mais elevados.

Os indivíduos `moderadamente ativos` ocuparam regiões intermediárias, indicando uma transição gradual entre os perfis comportamentais. Esses padrões sugerem que os atributos analisados possuem relevância para o processo de classificação.

---

## 4. Segunda Visualização

A segunda visualização foi entre:

| Eixo | Atributo |
|---|---|
| X | horas_sentado |
| Y | horas_tela |

Imagem:

![Alt text](../imagens/visualizacao_weka/dispersao_sedentarismo.png)

A visualização entre os atributos `horas_sentado` e `horas_tela` apresentou uma separação mais evidente entre as classes do problema. Os indivíduos sedentários concentraram-se majoritariamente em regiões com maiores valores de tempo sentado e maior exposição a telas, enquanto indivíduos ativos apareceram em regiões com menores valores para ambos os atributos.

Os indivíduos moderadamente ativos permaneceram distribuídos em regiões intermediárias, indicando uma transição gradual entre os perfis. A distribuição observada sugere forte relação entre comportamento sedentário e nível de atividade física, reforçando a relevância desses atributos para a tarefa de classificação.

---

## 5. Terceira Visualização

A terceira visualização foi entre:

| Eixo | Atributo |
|---|---|
| X | imc |
| Y | passos_diarios |

Imagem:

![Alt text](../imagens/visualizacao_weka/dispersao_imc_passos.png)

A visualização entre os atributos `imc` e `passos_diarios` apresentou maior sobreposição entre as classes quando comparada às demais visualizações analisadas. Embora exista tendência de indivíduos ativos apresentarem maior quantidade de passos diários e sedentários concentrarem-se em regiões inferiores, observou-se dispersão significativa entre os grupos.

Essa sobreposição indica que o problema de classificação não é perfeitamente separável apenas com esses atributos, tornando o cenário mais próximo de aplicações reais de aprendizado de máquina. Além disso, o gráfico evidenciou a presença de possíveis outliers e comportamentos discrepantes, especialmente em regiões extremas da distribuição.

---

## 6. Quarta Visualização

A quarta visualização foi entre:

| Eixo | Atributo |
|---|---|
| X | horas_sono |
| Y | horas_tela |

Imagem:

![Alt text](../imagens/visualizacao_weka/dispersao_sono_tela.png)

A visualização entre os atributos `horas_sono` e `horas_tela` evidenciou padrões distintos entre as classes do problema. Observou-se que indivíduos sedentários concentraram-se em regiões associadas a maior tempo de exposição a telas e menores valores de horas de sono, enquanto indivíduos ativos apresentaram comportamento oposto.

Os indivíduos moderadamente ativos permaneceram distribuídos em regiões intermediárias, reforçando a ideia de transição gradual entre os perfis de atividade física. O gráfico sugere relação inversa parcial entre tempo de tela e horas de sono no conjunto de dados analisado.

---

## 7. Quinta Visualização

A quinta visualização foi entre:

| Eixo | Atributo |
|---|---|
| X | idade |
| Y | freq_exercicio_semana |

Imagem:

![Alt text](../imagens/visualizacao_weka/dispersao_idade_exercicio.png)

A visualização entre os atributos `idade` e `freq_exercicio_semana` mostrou que a frequência de exercícios possui relação mais evidente com o nível de atividade física, enquanto a idade apresentou maior dispersão entre as classes.

Indivíduos sedentários concentraram-se principalmente em baixas frequências de exercício, enquanto indivíduos ativos apareceram em frequências mais elevadas. Entretanto, a distribuição da idade ocorreu de forma espalhada entre todas as classes, indicando que esse atributo isoladamente não é suficiente para separar os grupos de forma clara.

Esse comportamento reforça a necessidade de utilização conjunta de múltiplos atributos durante o processo de classificação.

---

# 8. Considerações Gerais das Visualizações

As visualizações permitiram identificar:
- padrões coerentes entre atributos e classes;
- separação parcial entre grupos;
- regiões de sobreposição;
- presença de comportamento intermediário;
- possíveis outliers.

Os gráficos também mostraram que:
- atributos relacionados à frequência de exercícios, passos diários e comportamento sedentário possuem forte relação com a variável alvo;
- algumas classes apresentam regiões parcialmente misturadas;
- o problema não é perfeitamente separável, tornando o cenário mais próximo de aplicações reais de aprendizado de máquina.

Além disso, as visualizações auxiliaram na compreensão do comportamento do dataset antes da etapa de classificação, contribuindo para interpretação posterior dos resultados obtidos pelos algoritmos.