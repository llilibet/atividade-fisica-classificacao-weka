# Relatório Final — Aprendizado de Máquina com Weka

## Integrantes

- Alicia de Souza Miranda
- Carlos Victor de Araujo Llima
- Elizabeth Brasil Carneiro
- João Gabriel da Silva Maciel
- Margarida Nayandra Pessoa dos Santos
- Verissímo Casas

---

# 1. Introdução

O avanço das técnicas de aprendizado de máquina tem permitido o desenvolvimento de modelos capazes de identificar padrões comportamentais e auxiliar na tomada de decisões em diferentes áreas, incluindo saúde e qualidade de vida.

Neste trabalho foi desenvolvido um problema de classificação supervisionada relacionado ao nível de atividade física de indivíduos. O objetivo foi utilizar algoritmos de aprendizado de máquina no Weka para classificar pessoas em diferentes categorias de atividade física com base em atributos associados ao estilo de vida, hábitos diários e indicadores de saúde.

O projeto envolveu todas as etapas do processo de mineração de dados, incluindo geração de dataset sintético utilizando modelos de linguagem (LLMs), análise exploratória, pré-processamento, visualização dos dados, treinamento dos modelos e análise comparativa dos resultados obtidos.

---

# 2. Definição do Problema

O problema abordado neste trabalho consiste na classificação do nível de atividade física de indivíduos em três categorias:

- Sedentario
- Moderadamente_Ativo
- Ativo

A tarefa foi modelada como um problema de classificação supervisionada, utilizando atributos relacionados ao comportamento físico e hábitos cotidianos dos indivíduos.

Os atributos utilizados foram:

- idade
- horas_sono
- passos_diarios
- horas_sentado
- freq_exercicio_semana
- imc
- horas_tela
- consumo_agua_litros

Além disso, foi incluído propositalmente o atributo irrelevante:

- cor_roupa_favorita

O conjunto de dados também foi construído contendo:
- valores faltantes;
- ruídos;
- outliers;
- atributos irrelevantes.

Esses elementos foram inseridos intencionalmente para tornar o cenário mais próximo de aplicações reais de aprendizado de máquina.

Para mais detalhes desta etapa:

[Etapa 01 — Definição do Problema](../etapas/01_definicao_problema.md)

---

# 3. Geração do Dataset

O dataset utilizado no trabalho foi gerado artificialmente com auxílio de modelos de linguagem (LLMs), conforme solicitado no enunciado da atividade.

A construção dos dados foi realizada de forma semântica e controlada, buscando manter coerência entre os atributos e a variável alvo do problema.

O dataset final apresentou:
- 535 instâncias;
- 10 atributos;
- classes relativamente balanceadas;
- presença de ruídos, valores faltantes e outliers.

Todos os prompts utilizados durante a geração foram documentados e armazenados no repositório.

Mais detalhes:

[Etapa 02 — Geração do Dataset](../etapas/02_geracao_dataset.md)

---

# 4. Análise Exploratória Inicial

Antes da aplicação de qualquer técnica de pré-processamento, foi realizada uma análise exploratória inicial no Weka com o objetivo de investigar:
- distribuições dos atributos;
- presença de valores faltantes;
- possíveis outliers;
- atributos irrelevantes;
- comportamento geral das classes.

Durante essa etapa foram identificados:
- valores ausentes em diferentes atributos;
- presença de outliers em atributos como `passos_diarios` e `imc`;
- o atributo irrelevante `cor_roupa_favorita`.

A análise inicial foi fundamental para orientar as decisões posteriores de pré-processamento.

Mais detalhes:

[Etapa 03 — Análise Exploratória](../etapas/03_analise_exploratoria.md)

---

# 5. Pré-processamento

O pré-processamento foi realizado com o objetivo de preparar o conjunto de dados para a etapa de modelagem no Weka.

As principais etapas executadas foram:
- substituição de valores faltantes;
- remoção de atributo irrelevante;
- normalização dos atributos numéricos;
- aplicação de filtro adicional do Weka.

Os filtros utilizados foram:
- ReplaceMissingValues
- Normalize
- RemoveUseless

Além disso, optou-se por manter os outliers identificados no dataset, visando preservar características realistas dos dados e avaliar a robustez dos algoritmos de classificação.

Mais detalhes:

[Etapa 04 — Pré-processamento](../etapas/04_preprocessamento.md)

---

# 6. Visualização dos Dados

Foram realizadas diferentes visualizações no Weka após o pré-processamento, utilizando gráficos de dispersão entre atributos relevantes do problema.

As visualizações permitiram:
- observar separação entre classes;
- identificar regiões de sobreposição;
- analisar padrões comportamentais;
- investigar possíveis relações entre atributos.

Entre os gráficos gerados destacam-se:
- passos_diarios × freq_exercicio_semana;
- horas_sentado × horas_tela;
- imc × passos_diarios;
- horas_sono × horas_tela;
- idade × freq_exercicio_semana.

As visualizações mostraram que alguns atributos apresentaram forte capacidade de separação entre as classes, enquanto outros demonstraram maior sobreposição entre grupos.

Mais detalhes:

[Etapa 05 — Visualizações](../etapas/05_visualizacoes.md)

---

# 7. Classificação dos Dados

A etapa de modelagem foi realizada utilizando algoritmos de classificação supervisionada disponíveis no Weka.

Todos os modelos foram avaliados utilizando validação cruzada estratificada com 10 folds.

Os algoritmos testados foram:
- J48
- RandomForest
- NaiveBayes
- IBk
- OneR

Cada algoritmo foi analisado individualmente considerando:
- funcionamento;
- desempenho;
- matriz de confusão;
- acurácia;
- interpretabilidade.

Mais detalhes:

[Etapa 06 — Classificação](../etapas/06_classificacao.md)

---

# 8. Comparação dos Resultados

Os algoritmos apresentaram desempenho elevado no conjunto de dados analisado.

| Algoritmo | Acurácia |
|---|---|
| RandomForest | 99,63% |
| NaiveBayes | 99,07% |
| IBk | 98,69% |
| J48 | 97,76% |
| OneR | 94,39% |

O algoritmo RandomForest apresentou o melhor desempenho geral, alcançando praticamente classificação perfeita.

O NaiveBayes também apresentou resultados extremamente elevados, demonstrando forte separação estatística entre as classes do problema.

O J48 destacou-se principalmente pela interpretabilidade, permitindo visualização clara das regras utilizadas pelo modelo.

O OneR, apesar de extremamente simples, obteve desempenho significativo utilizando apenas o atributo `freq_exercicio_semana`, evidenciando a relevância dessa variável para o problema.

Mais detalhes:

[Etapa 07 — Comparação dos Resultados](../etapas/07_comparacao_resultados.md)

---

# 9. Conclusão

Os resultados obtidos demonstraram que os algoritmos de aprendizado de máquina avaliados foram capazes de classificar corretamente o nível de atividade física dos indivíduos com elevada taxa de acerto.

O trabalho permitiu aplicar na prática conceitos de:
- classificação supervisionada;
- pré-processamento;
- análise exploratória;
- visualização de dados;
- avaliação de modelos.

Além disso, o projeto mostrou a importância da qualidade do dataset e da preparação adequada dos dados para obtenção de bons resultados em aprendizado de máquina.

Entre os algoritmos avaliados, o RandomForest apresentou o melhor desempenho geral, enquanto o J48 destacou-se pela facilidade de interpretação das decisões do modelo.

Os resultados também mostraram que atributos como `freq_exercicio_semana`, `passos_diarios` e `horas_sentado` possuem forte relação com o nível de atividade física dos indivíduos.

---

# 10. Referências
- [1] GONÇALVES, I. B. et al. O impacto do sedentarismo na saúde pública do Brasil: desafios e estratégias de intervenção. In: I CONGRESSO NACIONAL SOBRE O SUS ON-LINE: DESAFIOS E PERSPECTIVAS. Anais... IME Events, [s.d.].

- [2] MAHENDRA, D. R. P. et al. A Machine Learning Approach to Predicting Physical Activity Levels in Adolescents. Indonesian Journal of Sport Management, v. 3, n. 2, p. 261-272, 2023. DOI: https://doi.org/10.31949/ijsm.v3i1.7145.

- [3] THE COPENHAGEN INSTITUTE FOR FUTURES STUDIES. The next era in global health. Editado por Klaus Æ. Mogensen. Copenhague: Copenhagen Institute for Futures Studies / Novo Nordisk Business Innovation Garage, [s.d.].

- [4] ESTRELLA, T. et al. Machine Learning for the Analysis of Healthy Lifestyle Data: Scoping Review and Guidelines. JMIR Human Factors, v. 13, e78648, 2026. DOI: 10.2196/78648.

- [5] MAHENDRA, D. R. P. et al. A Machine Learning Approach to Predicting Physical Activity Levels in Adolescents. Indonesian Journal of Sport Management, v. 3, n. 2, p. 261-272, 2023. DOI: https://doi.org/10.31949/ijsm.v3i1.7145.
