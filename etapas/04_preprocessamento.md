# Etapa 04 — Pré-processamento
## 1. Objetivo do Pré-processamento
O pré-processamento foi realizado com o objetivo de preparar o dataset para a etapa de modelagem no Weka, corrigindo problemas identificados durante a análise exploratória inicial e tornando os dados mais adequados para os algoritmos de aprendizado de máquina.

As decisões tomadas nesta etapa foram guiadas pelas evidências observadas na análise inicial, especialmente a presença de valores faltantes, diferenças de escala entre atributos numéricos, existência de atributo irrelevante e presença de possíveis outliers.

---
# 2. Dataset Utilizado
O pré-processamento foi aplicado sobre o arquivo: 

```ruby
dataset_original.arff
```

O dataset original possuía:
- 535 instâncias;
- 10 atributos;
- 8 atributos numéricos;
- 2 atributos nominais;
- variável alvo: `nivel_atividade`.

Após o pré-processamento, o dataset foi salvo como:

```ruby
dataset_preprocessado.arff
```
---

# 3. Tratamento de Valores Faltantes
Durante a análise inicial no Weka, foram identificados valores faltantes em diferentes atributos numéricos do dataset.
Os atributos com valores ausentes foram:
- `horas_sono`
- `passos_diarios`
- `freq_exercicio_semana`
- `mc`
- `horas_tela`
- `consumo_agua_litros`

Cada um desses atributos apresentou aproximadamente 22 valores faltantes, correspondendo a cerca de 4% do total de instâncias.

---
## 3.1 Filtro Utilizado

Para tratar esses valores, foi aplicado o filtro:

```ruby
filters → unsupervised → attribute → ReplaceMissingValues
```
Esse filtro substitui valores faltantes em atributos numéricos pela média dos valores observados no respectivo atributo. A escolha por essa abordagem foi feita para preservar o número total de instâncias do dataset, evitando a remoção de registros e reduzindo a perda de informação.

Após a aplicação do filtro, os atributos passaram a apresentar 0% de valores faltantes.

---

## 3.2 Justificativa

A utilização desse filtro foi escolhida para:
- preservar todas as instâncias do dataset;
- evitar perda de informação;
- manter equilíbrio entre as classes;
- melhorar compatibilidade com algoritmos de classificação.

Após a aplicação do filtro, o dataset passou a apresentar:

```txt
0% de valores faltantes
```

---

# 4. Remoção de Atributo Irrelevante

O atributo `cor_roupa_favorita` foi identificado como irrelevante para o problema de classificação do nível de atividade física.

Esse atributo não possui relação lógica direta com hábitos físicos, estilo de vida, saúde ou comportamento sedentário. Por isso, sua permanência poderia introduzir ruído no processo de aprendizagem dos algoritmos.

A remoção foi feita manualmente no Weka, selecionando o atributo e utilizando a opção:

```ruby
Remove
```

Após essa etapa, o dataset passou de 10 para 9 atributos.

---

# 5. Tratamento de Outliers
Durante a análise exploratória inicial foram identificados possíveis outliers em atributos como:
- passos_diarios;
- imc;
- horas_tela.

Exemplos observados:
- indivíduos com até 30000 passos diários;
- valores elevados de IMC;
- tempo excessivo de exposição a telas.

---

## 5.1 Decisão Adotada

Optou-se por:

```txt
manter os outliers no dataset
```

---

## 5.2 Justificativa

Essa decisão foi tomada porque:
- o conjunto de dados foi construído para simular cenários reais;
- aplicações reais frequentemente apresentam valores extremos;
- a manutenção dos outliers permite avaliar robustez dos algoritmos;
- a remoção completa poderia tornar o problema artificialmente simples.

Portanto, os outliers foram analisados e documentados, mas não removidos.

---

# 6. Normalização dos Dados

Os atributos numéricos apresentavam escalas muito diferentes.

Exemplos:
- `consumo_agua_litros`: aproximadamente entre 0.3 e 5;
- `passos_diarios`: entre 0 e 30000.

Essa diferença poderia prejudicar algoritmos baseados em distância e magnitude dos atributos.

---

## 6.1 Filtro Utilizado

Foi aplicado o filtro:

```txt
filters → unsupervised → attribute → Normalize
```

---

## 6.2 Configuração Utilizada

As configurações padrão do Weka foram mantidas:

```txt
scale = 1.0
translation = 0.0
```

---

## 6.3 Resultado

Após a normalização:
- os atributos numéricos passaram para escala entre 0 e 1;
- as diferenças de magnitude foram reduzidas;
- o dataset tornou-se mais adequado para algoritmos como IBk.

A variável alvo:

```txt
nivel_atividade
```

não foi alterada por ser um atributo nominal.

---

# 7. Aplicação de Filtro Adicional

Para atender ao requisito de utilização de um filtro adicional do Weka não explorado em sala, foi aplicado o filtro:

```txt
filters → unsupervised → attribute → RemoveUseless
```

---

## 7.1 Objetivo do Filtro

Esse filtro possui como objetivo:
- identificar atributos inúteis;
- remover atributos com pouca ou nenhuma variabilidade.

---

## 7.2 Resultado Obtido

Após sua execução:
- nenhum atributo adicional foi removido;
- os atributos restantes apresentaram variabilidade suficiente para permanecer no dataset.

Esse resultado indicou que, após a remoção do atributo irrelevante, os demais atributos ainda possuíam utilidade para o processo de classificação.

---

# 8. Pipeline Final de Pré-processamento

O pipeline final aplicado no dataset foi:

```txt
1. ReplaceMissingValues
2. Remove do atributo cor_roupa_favorita
3. Normalize
4. RemoveUseless
```

---

# 9. Resultado Final do Pré-processamento

Ao final do processo, o dataset passou a apresentar:

| Característica | Resultado |
|---|---|
| Instâncias | 535 |
| Atributos | 9 |
| Valores faltantes | 0 |
| Dados normalizados | Sim |
| Classe preservada | Sim |

O arquivo final foi salvo como:

```txt
dataset_preprocessado.arff
```

na pasta:

```txt
/dataset
```

---

# 10. Considerações Finais

O pré-processamento foi conduzido de forma planejada e fundamentada, utilizando informações obtidas na análise exploratória inicial.

As etapas realizadas permitiram:
- melhorar a qualidade do dataset;
- reduzir problemas de inconsistência;
- preparar os dados para classificação;
- manter características realistas do conjunto de dados.

Além disso, a utilização dos filtros do Weka possibilitou maior padronização dos dados e melhor adequação para os algoritmos de aprendizado de máquina utilizados posteriormente.

---

# 11. Evidências e Prints

Os prints gerados durante o pré-processamento foram armazenados em: ([imagens](../imagens/prints_weka))

```txt
/imagens/prints_weka
```

incluindo:
- aplicação dos filtros;
- remoção do atributo irrelevante;
- normalização dos dados;
- verificação dos valores faltantes;
- estrutura final do dataset preprocessado.