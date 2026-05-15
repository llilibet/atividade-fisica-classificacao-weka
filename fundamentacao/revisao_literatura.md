# Revisão de Literatura
## Objetivo da Revisão

Esta revisão bibliográfica foi conduzida com o objetivo de analisar a aplicação de técnicas de aprendizado de máquina na classificação do nível de atividade física, com foco especial em algoritmos supervisionados, estratégias de pré-processamento, métricas de avaliação e utilização da ferramenta Weka em contextos relacionados à saúde e reconhecimento de atividades humanas.

Além disso, a revisão buscou identificar decisões metodológicas presentes na literatura científica que pudessem fundamentar o desenvolvimento deste projeto, especialmente em relação à escolha dos algoritmos de classificação, tratamento dos dados e utilização de validação cruzada.

---

## Ferramenta Utilizada

A pesquisa bibliográfica foi conduzida com auxílio da ferramenta NotebookLM, plataforma baseada em inteligência artificial desenvolvida pelo Google para análise e organização de documentos acadêmicos.

A ferramenta foi utilizada para:
- organizar os artigos selecionados;
- comparar metodologias utilizadas nos estudos;
- identificar algoritmos recorrentes;
- analisar técnicas de pré-processamento;
- auxiliar na síntese e comparação dos trabalhos relacionados.

Os artigos analisados foram obtidos por meio de bases acadêmicas como Google Scholar e Semantic Scholar, priorizando trabalhos relacionados à classificação de atividade física, reconhecimento de atividades humanas e aplicações de aprendizado de máquina na área da saúde.
## Introdução

O problema de classificação do nível de atividade física humana (Human Activity Recognition - HAR) consiste em identificar e categorizar automaticamente as ações e posturas diárias de um indivíduo, como caminhar, correr, sentar ou subir escadas, a partir de dados capturados por sensores ou registros de hábitos (Feng et al., 2014; Yang et al., 2010). Nos últimos anos, essa tarefa expandiu-se para englobar não apenas o movimento, mas também a predição de condições de saúde associadas ao sedentarismo, como a obesidade (Gandhi et al., 2026; Görmez et al., 2025).

O aprendizado de máquina (Machine Learning - ML) desempenha um papel fundamental nesta área, pois os dados brutos de sensores inerciais ou de questionários de hábitos são altamente dimensionais e complexos (Khan et al., [s.d.]). Modelos de ML são capazes de identificar padrões ocultos e relações não lineares nesses conjuntos de dados, substituindo abordagens tradicionais baseadas em limiares fixos.

As aplicações desses sistemas impactam diretamente áreas como:
- saúde pública;
- telemedicina;
- monitoramento de idosos;
- aplicativos fitness;
- prevenção de doenças relacionadas ao sedentarismo.

---

# Artigos Selecionados

## A Random Forest-Based Ensemble Method for Activity Recognition

O trabalho de Feng et al. (2014) propôs uma abordagem baseada em Random Forest utilizando múltiplos sensores para reconhecimento de atividades físicas.

O dataset utilizado foi o PAMAP, contendo dados de 17 participantes executando 19 tipos de atividades físicas. Foram extraídas 179 características relacionadas aos domínios do tempo e frequência.

As técnicas de pré-processamento envolveram:
- extração de atributos em janelas de tempo;
- divisão treino/teste;
- processamento de sinais dos sensores.

Os algoritmos avaliados incluíram:
- Random Forest;
- KNN;
- SVM;
- Bayes Net;
- J48.

O estudo utilizou explicitamente o software Weka 3.7.9 para os experimentos.

Os resultados mostraram que o Random Forest apresentou melhor desempenho geral, alcançando 93,44% de acurácia.

### Contribuição metodológica

O artigo fundamenta:
- o uso do Weka;
- a utilização do RandomForest;
- o uso de algoritmos baseados em árvores;
- a importância da extração de atributos estatísticos.

---

## Benchmarking Machine Learning Models for Obesity Classification with SHAP-Based Interpretability

O estudo de Gandhi et al. (2026) comparou diferentes algoritmos de aprendizado de máquina para classificação de obesidade utilizando hábitos alimentares e atividade física.

O dataset possuía 2111 registros e 17 atributos relacionados a:
- atividade física;
- tempo de uso de tecnologia;
- características antropométricas;
- hábitos alimentares.

O pré-processamento incluiu:
- imputação de valores faltantes;
- codificação one-hot;
- normalização Min-Max;
- balanceamento com SMOTE.

Os algoritmos utilizados foram:
- Random Forest;
- Decision Tree;
- KNN;
- SVM;
- Gradient Boosting.

As métricas utilizadas incluíram:
- acurácia;
- precisão;
- recall;
- F1-Score;
- matriz de confusão.

O melhor resultado foi obtido pelo Gradient Boosting com 95,93% de acurácia.

### Contribuição metodológica

O artigo fundamenta:
- uso de normalização;
- tratamento de valores faltantes;
- utilização de validação cruzada;
- importância do F1-Score;
- comparação entre múltiplos algoritmos.

---

## Classification and Analysis of Human Activities

O artigo de Priyadharshini et al. (2017) analisou o dataset PAMAP2 utilizando algoritmos de classificação supervisionada no Weka.

Os autores utilizaram:
- J48;
- Random Forest;
- Naive Bayes.

O pré-processamento incluiu tratamento de valores faltantes e divisão treino/teste.

Os resultados mostraram:
- Naive Bayes: 93,2%;
- Random Forest: 90,11%;
- J48 com forte overfitting.

O estudo evidenciou que o J48 apresentou:
- 100% de acurácia no treino;
- apenas 19,2% no teste.

### Contribuição metodológica

Esse resultado fundamenta:
- uso obrigatório de validação cruzada;
- preocupação com overfitting;
- inclusão do Naive Bayes;
- uso do Weka como ambiente experimental.

---

## Evaluating Machine Learning Techniques on Human Activity Recognition Using Accelerometer Data

O estudo de Khan et al. ([s.d.]) avaliou técnicas de aprendizado de máquina utilizando dados de acelerômetros de smartphones.

O dataset utilizado foi o WISDM.

As técnicas de pré-processamento envolveram:
- normalização;
- conversão de atributos;
- filtros do Weka.

Os algoritmos utilizados incluíram:
- KNN;
- SVM;
- Redes Neurais;
- Bagged Trees.

Os melhores resultados foram:
- Bagged Trees: 96,2%;
- KNN: 95,1%.

### Contribuição metodológica

O trabalho fundamenta:
- uso da normalização;
- utilização do IBk/KNN;
- importância de algoritmos baseados em distância.

---

## Implementation of a Wearable Real-Time System for Physical Activity Recognition based on Naive Bayes Classifier

Yang et al. (2010) desenvolveram um sistema embarcado de reconhecimento de atividade física utilizando sensores vestíveis.

Os algoritmos analisados foram:
- Naive Bayes;
- SVM;
- OneR;
- C4.5 (J48);
- Redes Neurais.

O Naive Bayes apresentou:
- 88,06% de acurácia;
- tempo computacional extremamente baixo.

### Contribuição metodológica

O artigo fundamenta:
- uso do Naive Bayes;
- uso do OneR;
- utilização do J48;
- importância do baixo custo computacional.

---

## Prediction of Obesity Levels Based on Physical Activity and Eating Habits with Explainable Artificial Intelligence

O estudo de Görmez et al. (2025) aplicou modelos de aprendizado de máquina com IA explicável para prever níveis de obesidade.

Os algoritmos utilizados incluíram:
- CatBoost;
- Decision Tree;
- SVM;
- Naive Bayes.

As métricas utilizadas incluíram:
- acurácia;
- F1-Score;
- AUC;
- matriz de confusão.

O CatBoost apresentou melhor desempenho com 93,67%.

### Contribuição metodológica

O artigo fundamenta:
- uso de métricas além da acurácia;
- importância da validação robusta;
- uso de modelos baseados em árvores;
- análise de atributos relacionados à atividade física.

---

# Comparação Metodológica

| Artigo | Algoritmos | Métricas | Melhor Resultado |
|---|---|---|---|
| Feng et al. (2014) | RF, J48, KNN, SVM | Acurácia | RF: 93,44% |
| Gandhi et al. (2026) | RF, KNN, DT, GB | Accuracy, F1 | GB: 95,93% |
| Priyadharshini et al. (2017) | NB, RF, J48 | Accuracy | NB: 93,2% |
| Khan et al. ([s.d.]) | KNN, Bagged Trees | MAE, RMSE | Bagged: 96,2% |
| Yang et al. (2010) | NB, J48, OneR | Accuracy | NB: 88,06% |
| Görmez et al. (2025) | CatBoost, DT | F1, AUC | CatBoost: 93,67% |

---

# Fundamentação do Projeto

Os trabalhos analisados fundamentaram diretamente as decisões metodológicas adotadas neste projeto.

A literatura justificou:
- uso do Weka;
- aplicação de validação cruzada;
- uso de RandomForest;
- utilização de J48;
- inclusão do NaiveBayes;
- utilização do IBk/KNN;
- tratamento de valores faltantes;
- normalização dos dados;
- uso de matriz de confusão e F1-Score.

Além disso, os artigos mostraram que atributos relacionados à:
- frequência de exercício;
- comportamento sedentário;
- uso de tecnologia;
- atividade física;

possuem forte capacidade preditiva em problemas relacionados à saúde.

---

# Conclusão

A literatura analisada demonstrou que técnicas de aprendizado de máquina são altamente eficazes para classificação de atividade física e problemas relacionados ao sedentarismo.

Os estudos mostraram que algoritmos ensemble, especialmente o RandomForest, frequentemente apresentam os melhores desempenhos, enquanto modelos probabilísticos e baseados em distância continuam relevantes devido à simplicidade e eficiência computacional.

Os artigos também reforçaram a importância de:
- pré-processamento adequado;
- validação robusta;
- normalização;
- análise de métricas além da acurácia.

Dessa forma, as decisões metodológicas adotadas neste projeto encontram forte respaldo na literatura científica, demonstrando que a utilização do Weka e dos algoritmos escolhidos é coerente com práticas amplamente utilizadas em pesquisas acadêmicas da área.

---

# Referências

- FENG, Z.; MO, L.; LI, M. *A Random Forest-Based Ensemble Method for Activity Recognition*. IEEE International Conference, 2014.
- GANDHI, V. et al. *Benchmarking Machine Learning Models for Obesity Classification with SHAP-Based Interpretability*. International Journal of Computational Intelligence Systems, 2026.
- GÖRMEZ, Y. et al. *Prediction of obesity levels based on physical activity and eating habits with explainable artificial intelligence*. Frontiers in Physiology, 2025.
- KHAN, R. et al. *Evaluating Machine Learning Techniques on Human Activity Recognition Using Accelerometer Data*.
- PRIYADHARSHINI, J. M. H. et al. *Classification and analysis of human activities*. IEEE, 2017.
- YANG, X.; DINH, A.; CHEN, L. *Implementation of a wearable real-time system for physical activity recognition based on Naive Bayes classifier*. IEEE, 2010.