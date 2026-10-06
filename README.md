# Projeto de Machine Learning - Classificação de Faixas Salariais

## Descrição

Projeto completo de Machine Learning para classificação de faixas salariais de profissionais baseado em características como cargo, experiência, educação e localização.

## Estrutura do Projeto

```
testesC318/
├── data/
│   ├── raw/           # Dados brutos
│   └── processed/     # Dados processados
├── notebooks/
│   └── main_analysis.ipynb  # Notebook principal
├── models/            # Modelos treinados
├── artifacts/         # Preprocessadores e transformers
├── reports/
│   └── figures/       # Visualizações
└── src/               # Código fonte
```

## Metodologia

### Split dos Dados

- **Treino**: 60% dos dados - usado para treinar modelos
- **Validação**: 20% dos dados - usado para seleção de modelo e tuning
- **Teste**: 20% dos dados - usado **APENAS UMA VEZ** para avaliação final

### Pipeline de ML

1. **Pré-processamento** integrado ao pipeline (evita data leakage)
2. **Validação cruzada** no conjunto de treino para seleção
3. **Otimização** via GridSearchCV e Optuna
4. **Avaliação final** única no conjunto de teste

## Modelos Implementados

- Logistic Regression
- Random Forest (com otimização)
- XGBoost
- SVM (RBF)

## Seções do Notebook

| Seção                       | Status | Descrição                 |
| --------------------------- | ------ | ------------------------- |
| 1. Configuração             | ✅     | Imports e seed            |
| 2. Carregamento             | ✅     | Leitura dos dados         |
| 3. EDA                      | ✅     | Exploração, VIF, outliers |
| 4. Pré-processamento        | ✅     | Pipeline sklearn          |
| 5. Modelagem Supervisionada | ✅     | Treino e validação        |
| 6. Otimização               | ✅     | GridSearch e Optuna       |
| 7. Não Supervisionado       | ✅     | K-Means, PCA              |
| 8. Avaliação Final          | ✅     | Teste (única vez)         |
| 9. Conclusões               | ✅     | Resumo e limitações       |

## Como Executar

```bash
# Instalar dependências
pip install -r requirements.txt

# Executar notebook
jupyter notebook notebooks/main_analysis.ipynb
```

## Dependências

- scikit-learn
- xgboost
- optuna
- pandas, numpy
- matplotlib, seaborn
- statsmodels (VIF)
