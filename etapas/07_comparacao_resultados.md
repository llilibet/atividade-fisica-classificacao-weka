# Etapa 07 — Comparação dos Resultados

## 1. Objetivo da Comparação

Após a execução dos algoritmos de classificação no Weka, foi realizada uma análise comparativa dos resultados obtidos.

O objetivo dessa etapa foi:
- comparar desempenho dos modelos;
- analisar diferenças entre algoritmos;
- identificar vantagens e limitações;
- interpretar comportamento dos classificadores;
- avaliar capacidade de generalização dos modelos.

Os algoritmos comparados foram:
- J48;
- RandomForest;
- NaiveBayes;
- IBk;
- OneR.

Todos os modelos foram avaliados utilizando:
```txt
10-fold Cross-validation
```

sobre o dataset previamente pré-processado.

---

# 2. Comparação Geral das Métricas

## 2.1 Tabela Comparativa

| Algoritmo | Acurácia | Instâncias Corretas | Instâncias Incorretas | Kappa |
|---|---|---|---|---|
| RandomForest | 99,63% | 533 | 2 | 0,9944 |
| NaiveBayes | 99,07% | 530 | 5 | 0,9859 |
| IBk | 98,69% | 528 | 7 | 0,9803 |
| J48 | 97,76% | 523 | 12 | 0,9663 |
| OneR | 94,39% | 505 | 30 | 0,9158 |

---

# 3. Análise dos Resultados

## 3.1 RandomForest

O algoritmo RandomForest apresentou o melhor desempenho geral entre todos os classificadores avaliados.

Principais características observadas:
- maior acurácia;
- menor quantidade de erros;
- excelente capacidade de generalização;
- robustez frente a ruídos e outliers.

A utilização de múltiplas árvores de decisão permitiu reduzir erros de classificação e minimizar problemas de overfitting.

Além disso, o modelo apresentou desempenho praticamente perfeito para as classes:
- `Sedentario`;
- `Ativo`.

Os únicos erros ocorreram entre:
- `Moderadamente_Ativo`
- `Ativo`.

---

## 3.2 NaiveBayes

O NaiveBayes apresentou desempenho extremamente elevado mesmo utilizando um modelo probabilístico relativamente simples.

Os resultados mostraram que:
- os atributos apresentaram forte separação estatística;
- as distribuições das classes estavam bem definidas;
- o dataset possuía padrões coerentes.

O algoritmo destacou-se por:
- simplicidade matemática;
- rapidez;
- alta eficiência computacional.

Apesar da hipótese de independência entre atributos não ser totalmente verdadeira no problema analisado, o modelo conseguiu excelente desempenho.

---

## 3.3 IBk

O algoritmo IBk apresentou desempenho muito elevado utilizando classificação baseada em similaridade entre instâncias.

O resultado obtido mostrou que:
- indivíduos da mesma classe apresentaram proximidade no espaço dos atributos;
- a etapa de normalização foi fundamental para o algoritmo;
- os grupos estavam relativamente bem organizados no dataset.

O uso de:

```txt
K = 1
```

permitiu ao modelo utilizar o vizinho mais próximo como critério de classificação.

Os principais erros ocorreram entre:
- `Moderadamente_Ativo`
- `Ativo`.

---

## 3.4 J48

O algoritmo J48 apresentou excelente desempenho e destacou-se principalmente pela interpretabilidade do modelo gerado.

A árvore produzida permitiu identificar:
- atributos mais importantes;
- regras de separação;
- decisões tomadas pelo modelo.

O atributo:
```txt
freq_exercicio_semana
```

foi identificado como principal critério de divisão da árvore.

Embora tenha apresentado desempenho inferior ao RandomForest, o J48 possui como principal vantagem a facilidade de interpretação das regras produzidas.

---

## 3.5 OneR

O algoritmo OneR apresentou o menor desempenho entre os modelos avaliados, porém ainda obteve resultados bastante elevados considerando sua simplicidade.

O modelo utilizou exclusivamente o atributo:
```txt
freq_exercicio_semana
```

para gerar regras de classificação.

Mesmo utilizando apenas uma variável, o algoritmo alcançou:
```txt
94,39% de acurácia
```

Esse resultado mostrou que:
- a frequência semanal de exercícios possui forte capacidade discriminativa;
- o dataset apresenta padrões bem definidos;
- existe relação significativa entre o atributo e a variável alvo.

---

# 4. Comparação entre Complexidade e Interpretabilidade

Os algoritmos apresentaram diferenças importantes relacionadas à:
- complexidade;
- interpretabilidade;
- forma de funcionamento.

| Algoritmo | Interpretabilidade | Complexidade |
|---|---|---|
| OneR | Muito alta | Muito baixa |
| J48 | Alta | Média |
| NaiveBayes | Média | Baixa |
| IBk | Média | Média |
| RandomForest | Baixa | Alta |

---

# 5. Comparação dos Principais Erros

Em praticamente todos os algoritmos, os principais erros ocorreram entre as classes:

- `Moderadamente_Ativo`
- `Ativo`

Esse comportamento era esperado porque:
- as classes possuem características parcialmente semelhantes;
- existe região intermediária entre os perfis;
- o problema não apresenta separação perfeitamente linear.

A classe:
```txt
Sedentario
```

foi a que apresentou melhor separação na maioria dos modelos.

---

# 6. Influência do Pré-processamento

Os resultados obtidos mostraram que o pré-processamento teve impacto significativo na qualidade da classificação.

As etapas mais importantes foram:
- tratamento de valores faltantes;
- remoção de atributo irrelevante;
- normalização dos dados.

A normalização mostrou-se especialmente importante para:
- IBk;
- algoritmos baseados em distância.

Além disso, a manutenção dos outliers permitiu avaliar a robustez dos modelos diante de dados mais realistas.

---

# 7. Discussão Geral

Os resultados demonstraram que o dataset foi construído de forma consistente e coerente com o problema proposto.

Os algoritmos conseguiram identificar padrões relevantes utilizando principalmente atributos relacionados a:
- frequência de exercícios;
- quantidade de passos;
- comportamento sedentário;
- tempo de exposição a telas.

O excelente desempenho dos modelos sugere que:
- as classes apresentaram separação significativa;
- os atributos escolhidos foram adequados;
- o processo de pré-processamento contribuiu positivamente para a modelagem.

---

# 8. Conclusão da Comparação

Entre os modelos avaliados:
- o RandomForest apresentou o melhor desempenho geral;
- o J48 destacou-se pela interpretabilidade;
- o NaiveBayes apresentou excelente equilíbrio entre simplicidade e desempenho;
- o IBk demonstrou forte eficiência baseada em similaridade;
- o OneR mostrou que um único atributo já possuía grande poder preditivo.

A comparação entre algoritmos permitiu compreender diferenças importantes entre:
- modelos baseados em regras;
- modelos probabilísticos;
- modelos baseados em distância;
- métodos ensemble.

Além disso, os experimentos mostraram a importância da escolha adequada dos algoritmos e da preparação dos dados em tarefas de aprendizado de máquina.

---

# 9. Evidências e Prints

Os resultados comparativos foram registrados utilizando:
- tabelas;
- matrizes de confusão;
- métricas de desempenho;
- árvores de decisão;
- regras produzidas pelos algoritmos.

Os prints utilizados foram armazenados em:

```txt
/imagens/algotitmos
```