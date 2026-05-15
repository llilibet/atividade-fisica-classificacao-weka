# Etapa 01 — Definição do Problema

## 1. Contextualização

O sedentarismo e os baixos níveis de atividade física representam problemas relevantes e crescentes para a saúde pública na sociedade contemporânea [1]. Esses comportamentos estão diretamente associados ao aumento do risco de doenças crônicas não transmissíveis, como doenças cardiovasculares, obesidade, diabetes tipo 2 e outras condições que impactam negativamente a qualidade de vida e elevam os índices de mortalidade global [2].

Com o avanço das tecnologias de monitoramento pessoal, como acelerômetros, smartphones e dispositivos vestíveis (*wearables*), tornou-se possível coletar dados objetivos sobre os hábitos cotidianos e o comportamento físico dos indivíduos [3]. Esse grande volume de dados multimodais possibilita o desenvolvimento de sistemas inteligentes capazes de identificar padrões comportamentais e auxiliar na análise automatizada do nível de atividade física diária [4].

Nesse contexto, técnicas de aprendizado de máquina (*machine learning*) têm sido amplamente aplicadas na classificação de indivíduos em diferentes categorias de atividade física [5]. A partir de atributos relacionados ao estilo de vida, fatores biopsicossociais e dados comportamentais, modelos computacionais conseguem identificar padrões complexos, permitindo classificar perfis de atividade física e até mesmo prever a adesão de indivíduos à prática de exercícios físicos.

---

# 2. Problema Proposto

O problema definido neste trabalho consiste em classificar indivíduos de acordo com seu nível de atividade física.

A tarefa escolhida foi:

```txt
Classificação supervisionada
```

A variável alvo do problema é:

```txt
nivel_atividade
```

As classes definidas foram:

- Sedentario
- Moderadamente_Ativo
- Ativo

O objetivo do modelo é prever corretamente a categoria de atividade física de um indivíduo com base em diferentes atributos relacionados à rotina, saúde e comportamento físico.

---

# 3. Entradas e Saída Esperada

## Entradas do Modelo

Os atributos utilizados para representar os indivíduos foram:

| Atributo | Descrição |
|---|---|
| idade | idade do indivíduo |
| horas_sono | média diária de horas de sono |
| passos_diarios | quantidade média de passos por dia |
| horas_sentado | tempo médio diário sentado |
| freq_exercicio_semana | frequência semanal de exercícios físicos |
| imc | índice de massa corporal |
| horas_tela | tempo médio diário de uso de telas |
| consumo_agua_litros | consumo médio diário de água |
| cor_roupa_favorita | atributo irrelevante inserido propositalmente |

---

## Saída Esperada

A saída esperada do modelo corresponde à classificação do indivíduo em uma das seguintes categorias:

- Sedentario
- Moderadamente_Ativo
- Ativo

---

# 4. Justificativa da Escolha do Problema

O problema foi escolhido por possuir relação direta com saúde, qualidade de vida e hábitos comportamentais da população.

Além disso, trata de um cenário adequado para aplicação de técnicas de aprendizado de máquina, pois:
- existem atributos numéricos e comportamentais relevantes;
- é possível identificar padrões entre indivíduos;
- diferentes algoritmos podem ser comparados;
- o problema apresenta separação parcial entre classes.

O tema também permite explorar situações realistas envolvendo:
- ruídos;
- valores faltantes;
- atributos irrelevantes;
- outliers.

Esses fatores tornam o problema mais próximo de aplicações reais de mineração de dados e aprendizado de máquina.

---

# 5. Tipo de Aprendizado

O trabalho utiliza:

```txt
Aprendizado supervisionado
```

Isso ocorre porque:
- o conjunto de dados possui classes previamente definidas;
- o modelo é treinado utilizando exemplos rotulados;
- o objetivo é prever corretamente a classe de novas instâncias.

A tarefa específica utilizada foi:

```txt
Classificação
```

pois a variável alvo representa categorias discretas e não valores contínuos.

---

# 6. Principais Desafios do Problema

Durante a definição do problema, foram identificados alguns desafios importantes relacionados ao processo de classificação:

## 6.1 Sobreposição entre Classes

Indivíduos moderadamente ativos podem apresentar características semelhantes tanto a indivíduos sedentários quanto ativos, dificultando a separação perfeita entre as categorias.

---

## 6.2 Presença de Ruídos

Foram inseridas propositalmente algumas inconsistências no conjunto de dados, simulando cenários reais nos quais indivíduos podem apresentar comportamentos atípicos.

---

## 6.3 Valores Faltantes

O dataset foi construído contendo valores ausentes em diferentes atributos, exigindo aplicação de técnicas de tratamento durante o pré-processamento.

---

## 6.4 Outliers

Também foram inseridos valores extremos em atributos como:
- passos_diarios;
- imc;
- horas_tela.

Esses outliers simulam situações reais e aumentam a complexidade da modelagem.

---

## 6.5 Atributos Irrelevantes

O atributo:

```txt
cor_roupa_favorita
```

foi incluído propositalmente para representar variáveis sem relevância preditiva para o problema.

Esse elemento permitiu avaliar a capacidade de análise e pré-processamento do conjunto de dados.

---

# 7. Objetivo do Trabalho

O principal objetivo deste trabalho é aplicar técnicas de aprendizado de máquina utilizando o Weka para construir modelos capazes de classificar corretamente o nível de atividade física dos indivíduos.

Além disso, busca:
- analisar o impacto do pré-processamento nos dados;
- comparar diferentes algoritmos de classificação;
- avaliar métricas de desempenho;
- interpretar os resultados obtidos;
- compreender o comportamento dos modelos diante de dados realistas.

# 10. Referências
- [1] GONÇALVES, I. B. et al. O impacto do sedentarismo na saúde pública do Brasil: desafios e estratégias de intervenção. In: I CONGRESSO NACIONAL SOBRE O SUS ON-LINE: DESAFIOS E PERSPECTIVAS. Anais... IME Events, [s.d.].

- [2] MAHENDRA, D. R. P. et al. A Machine Learning Approach to Predicting Physical Activity Levels in Adolescents. Indonesian Journal of Sport Management, v. 3, n. 2, p. 261-272, 2023. DOI: https://doi.org/10.31949/ijsm.v3i1.7145.

- [3] THE COPENHAGEN INSTITUTE FOR FUTURES STUDIES. The next era in global health. Editado por Klaus Æ. Mogensen. Copenhague: Copenhagen Institute for Futures Studies / Novo Nordisk Business Innovation Garage, [s.d.].

- [4] ESTRELLA, T. et al. Machine Learning for the Analysis of Healthy Lifestyle Data: Scoping Review and Guidelines. JMIR Human Factors, v. 13, e78648, 2026. DOI: 10.2196/78648.

- [5] MAHENDRA, D. R. P. et al. A Machine Learning Approach to Predicting Physical Activity Levels in Adolescents. Indonesian Journal of Sport Management, v. 3, n. 2, p. 261-272, 2023. DOI: https://doi.org/10.31949/ijsm.v3i1.7145.