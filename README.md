# MVP – Análise Exploratória e Pré-processamento de Dados
## Qualidade de Vinhos Tintos (*Red Wine Quality*)

Projeto desenvolvido como MVP da Pós-Graduação em Ciência de Dados e Analytics da PUC-Rio, contemplando as disciplinas de Análise Exploratória e Pré-processamento de Dados, Visualização da Informação e Engenharia de Software para Ciência de Dados.

---

## Objetivo

Explorar e preparar um dataset de vinhos tintos portugueses para um problema de **classificação binária**: prever se um vinho é *bom* (nota ≥ 7) ou *não bom* (nota < 7), com base em suas propriedades físico-químicas.

---

## Dataset

- **Nome:** Wine Quality – Red Wine
- **Fonte:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/wine+quality)
- **Arquivo:** `winequality-red.csv`
- **Instâncias:** 1.599
- **Atributos:** 12 (11 físico-químicos + 1 variável alvo: `quality`)
- **Referência:** Cortez, P. et al. (2009). *Modeling wine preferences by data mining from physicochemical properties.* Decision Support Systems, 47(4), 547-553.

---

## Estrutura do Repositório

```
├── mvp_qualidade_vinho.ipynb   # Notebook principal (análise + pré-processamento)
├── winequality-red.csv         # Dataset
└── README.md                   # Este arquivo
```

---

## Etapas Realizadas no Notebook

1. **Definição do Problema** — descrição, tipo de aprendizado, hipóteses, restrições e definição dos atributos
2. **Análise de Dados**
   - Visão geral (shape, tipos, primeiras linhas)
   - Verificação de valores faltantes e duplicatas
   - Resumo estatístico (mín, máx, média, mediana, moda, desvio-padrão)
   - Visualizações: histogramas, distribuição do alvo, mapa de correlação, boxplots, análise por classe
3. **Pré-processamento**
   - Remoção de duplicatas
   - Criação da variável alvo binária (`quality_bin`)
   - Tratamento de outliers (método IQR)
   - Normalização (Min-Max Scaling)
   - Padronização (Z-score)
4. **Análise Pós-processamento** — verificação do impacto das transformações
5. **Conclusão** — síntese dos achados e hipóteses validadas

---

## Como Executar

1. Acesse o notebook no Google Colab
2. Execute todas as células em ordem: **Runtime → Run all**
3. Nenhuma instalação adicional é necessária — todas as bibliotecas utilizadas estão disponíveis por padrão no Colab

---

## Bibliotecas Utilizadas

| Biblioteca | Versão recomendada | Uso |
|---|---|---|
| `pandas` | ≥ 1.5 | Manipulação de dados |
| `numpy` | ≥ 1.23 | Operações numéricas |
| `matplotlib` | ≥ 3.6 | Visualizações |
| `seaborn` | ≥ 0.12 | Visualizações estatísticas |
| `scikit-learn` | ≥ 1.1 | Pré-processamento (MinMaxScaler, StandardScaler) |

---

## Resultados Principais

- Ausência de valores faltantes; 240 duplicatas removidas
- Atributos com maior correlação com qualidade: `alcohol` (r = +0,48), `volatile acidity` (r = -0,39), `sulphates` (r = +0,25)
- Desbalanceamento de classes: ~86,5% não bom vs ~13,5% bom
- Três versões do dataset geradas: escala original, normalizado e padronizado
