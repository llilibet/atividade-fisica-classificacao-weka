# Etapa 02 — Geração do Dataset

## 1. Objetivo da Geração do Dataset

O dataset utilizado neste trabalho foi desenvolvido artificialmente com auxílio de modelos de linguagem (LLMs), conforme solicitado no enunciado da atividade.

O objetivo da construção do conjunto de dados foi criar um cenário coerente e semanticamente consistente para o problema de classificação do nível de atividade física, permitindo a aplicação de técnicas de aprendizado de máquina no Weka.

Diferente de uma geração aleatória simples, o dataset foi projetado considerando relações plausíveis entre os atributos e a variável alvo do problema.

---

# 2. Estratégia de Construção

A geração dos dados foi realizada utilizando prompts direcionados para criação de indivíduos com diferentes perfis comportamentais relacionados à atividade física.

Os dados foram construídos considerando:
- hábitos cotidianos;
- indicadores de saúde;
- comportamento sedentário;
- prática de exercícios físicos;
- padrões de sono;
- uso de telas;
- consumo de água.

As classes do problema foram definidas como:

- Sedentario
- Moderadamente_Ativo
- Ativo

Cada grupo foi gerado respeitando características coerentes com o perfil esperado.

---

# 3. Estrutura do Dataset

O dataset final foi composto por:

| Característica | Quantidade |
|---|---|
| Instâncias | 535 |
| Atributos | 10 |
| Classes | 3 |

---

# 4. Atributos Utilizados

Os atributos presentes no dataset foram:

| Atributo | Tipo | Descrição |
|---|---|---|
| idade | Numérico | idade do indivíduo |
| horas_sono | Numérico | média diária de horas de sono |
| passos_diarios | Numérico | quantidade média de passos diários |
| horas_sentado | Numérico | média diária de horas sentado |
| freq_exercicio_semana | Numérico | frequência semanal de exercícios |
| imc | Numérico | índice de massa corporal |
| horas_tela | Numérico | média diária de uso de telas |
| consumo_agua_litros | Numérico | consumo médio diário de água |
| cor_roupa_favorita | Nominal | atributo irrelevante |
| nivel_atividade | Nominal | classe alvo |

---

# 5. Construção das Classes

## 5.1 Sedentario

Os indivíduos sedentários foram gerados apresentando:
- baixa frequência de exercícios;
- poucos passos diários;
- maior tempo sentado;
- maior tempo de tela;
- menor equilíbrio nos hábitos físicos.

---

## 5.2 Moderadamente_Ativo

Os indivíduos moderadamente ativos foram construídos como uma classe intermediária, apresentando:
- frequência moderada de exercícios;
- quantidade intermediária de passos;
- equilíbrio parcial entre hábitos saudáveis e sedentários.

Essa classe foi propositalmente construída com maior sobreposição em relação às demais, tornando o problema mais realista.

---

## 5.3 Ativo

Os indivíduos ativos foram gerados apresentando:
- maior frequência de exercícios;
- elevada quantidade de passos diários;
- menor tempo sentado;
- menor tempo de tela;
- hábitos mais saudáveis de forma geral.

---

# 6. Inserção de Valores Faltantes

O dataset foi construído contendo valores ausentes em diferentes atributos, simulando problemas comuns encontrados em bases reais.

Os valores faltantes foram inseridos nos seguintes atributos:

- horas_sono
- passos_diarios
- freq_exercicio_semana
- imc
- horas_tela
- consumo_agua_litros

A presença desses valores permitiu aplicar técnicas de tratamento durante o pré-processamento.

---

# 7. Inserção de Outliers

Também foram inseridos propositalmente valores extremos em alguns atributos numéricos.

Exemplos:
- indivíduos com quantidade extremamente alta de passos diários;
- valores elevados de IMC;
- tempo excessivo de uso de telas.

Esses elementos foram adicionados para simular cenários reais e aumentar a complexidade do processo de classificação.

---

# 8. Inserção de Ruídos

O conjunto de dados também recebeu ruídos e inconsistências controladas.

Foram criadas algumas instâncias com comportamentos parcialmente contraditórios, como:
- indivíduos sedentários com quantidade elevada de passos;
- indivíduos moderadamente ativos com características próximas de ativos;
- combinações menos comuns entre atributos.

A inserção desses ruídos teve como objetivo tornar o problema menos trivial e mais próximo de aplicações reais de aprendizado de máquina.

---

# 9. Inserção de Atributo Irrelevante

O atributo:

```txt
cor_roupa_favorita
```

foi incluído propositalmente como variável irrelevante para o problema.

Esse atributo não possui relação lógica com o nível de atividade física e foi utilizado para permitir análise de relevância e aplicação de técnicas de pré-processamento.

---

# 10. Balanceamento das Classes

As classes do dataset foram mantidas relativamente equilibradas para evitar desbalanceamento severo durante o treinamento dos modelos.

Distribuição observada:

| Classe | Quantidade |
|---|---|
| Sedentario | 190 |
| Moderadamente_Ativo | 186 |
| Ativo | 159 |

Essa distribuição permitiu avaliação mais justa dos algoritmos de classificação.

---

# 11. Conversão para ARFF

Após a geração dos dados, o conjunto final foi estruturado no formato:

```txt
.arff
```

compatível com o Weka.

O arquivo final foi salvo como:

```txt
dataset_original.arff
```

e armazenado na pasta:

[dataset](../dataset/)

---

# 12. Considerações Finais

A construção do dataset foi realizada de forma planejada e semântica, buscando criar um conjunto de dados coerente com o problema proposto.

A inserção proposital de:
- valores faltantes;
- ruídos;
- outliers;
- atributos irrelevantes;

permitiu tornar o cenário mais próximo de aplicações reais de aprendizado de máquina, além de possibilitar análise crítica durante as etapas de pré-processamento e classificação.