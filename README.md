# C318 - Projeto de Machine Learning

## Previsão de Salários no Mercado de IA/Dados

**Disciplina**: C318 - Aprendizado de Máquina  
**Objetivo**: Desenvolver um modelo preditivo para estimar salários de vagas na área de IA/dados

---

## Estrutura do Repositório

```
C318/
├── README.md                 # Este arquivo
├── requirements.txt          # Dependências com versões exatas
├── data/
│   └── AI Job Market Dataset.csv   # Dataset original
├── notebooks/
│   └── main_analysis.ipynb   # Notebook principal com toda a análise
├── models/
│   ├── best_random_forest.joblib   # Melhor modelo treinado
│   └── kmeans_model.joblib         # Modelo de clustering
├── artifacts/
│   ├── preprocessor.joblib   # Pipeline de pré-processamento
│   └── pca_2d.joblib         # PCA para visualização
└── reports/
    └── *.png                 # Gráficos e visualizações
```

---

## Instalação e Execução

### Pré-requisitos

- Python 3.10+
- pip

### Passos

1. **Clonar o repositório**

```bash
git clone <url-do-repositorio>
cd C318
```

2. **Criar ambiente virtual (recomendado)**

```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
# ou
venv\Scripts\activate     # Windows
```

3. **Instalar dependências**

```bash
pip install -r requirements.txt
```

4. **Executar o notebook**

```bash
jupyter notebook notebooks/main_analysis.ipynb
```

5. **Executar todas as células**

- No Jupyter: `Kernel > Restart & Run All`

---

## Dataset

| Característica | Valor                       |
| -------------- | --------------------------- |
| **Nome**       | AI Job Market Dataset       |
| **Registros**  | 10.345                      |
| **Features**   | 19                          |
| **Fonte**      | [Especificar fonte/licença] |

### Variáveis

| Variável            | Tipo       | Descrição                                 |
| ------------------- | ---------- | ----------------------------------------- |
| `job_id`            | ID         | Identificador único                       |
| `job_title`         | Categórica | Cargo (AI Engineer, Data Scientist, etc.) |
| `company_size`      | Categórica | Porte (Startup, Medium, MNC, Enterprise)  |
| `company_industry`  | Categórica | Setor (Technology, Finance, etc.)         |
| `country`           | Categórica | País                                      |
| `remote_type`       | Categórica | Modalidade (Remote, Hybrid, Onsite)       |
| `experience_level`  | Ordinal    | Nível (Entry, Mid, Senior)                |
| `years_experience`  | Numérica   | Anos de experiência                       |
| `education_level`   | Ordinal    | Escolaridade (Bachelor, Master, PhD)      |
| `skills_*`          | Binária    | Skills requeridas (Python, SQL, ML, etc.) |
| `salary`            | Numérica   | **Variável alvo** - Salário anual (USD)   |
| `job_posting_month` | Numérica   | Mês da publicação                         |
| `job_posting_year`  | Numérica   | Ano da publicação                         |
| `hiring_urgency`    | Ordinal    | Urgência (Low, Medium, High)              |
| `job_openings`      | Numérica   | Número de vagas                           |

---

## Metodologia

### 1. Análise Exploratória (EDA)

- Estatísticas descritivas
- Distribuições de variáveis
- Matriz de correlação
- Análise de valores faltantes

### 2. Pré-processamento

- **One-Hot Encoding**: variáveis nominais (job_title, country, etc.)
- **Ordinal Encoding**: variáveis ordinais (experience_level, education_level)
- **StandardScaler**: variáveis numéricas
- Divisão treino/teste: 80/20

### 3. Modelagem Supervisionada

| Modelo            | Tipo      |
| ----------------- | --------- |
| Linear Regression | Baseline  |
| Random Forest     | Principal |
| XGBoost           | Avançado  |

### 4. Otimização

- GridSearchCV no Random Forest
- 5-fold Cross-Validation

### 5. Modelagem Não Supervisionada

- **PCA**: Redução de dimensionalidade
- **K-Means**: Clustering de vagas

---

## Métricas de Avaliação

| Métrica  | Descrição                   |
| -------- | --------------------------- |
| **RMSE** | Root Mean Squared Error     |
| **MAE**  | Mean Absolute Error         |
| **R²**   | Coeficiente de Determinação |

---

## Reprodutibilidade

- **Seed global**: 42
- Aplicada em: `random.seed()`, `numpy.random.seed()`, `random_state` do sklearn
- Executar `Restart Kernel and Run All` produz resultados idênticos

---

## Hardware Utilizado

| Componente | Especificação |
| ---------- | ------------- |
| **SO**     | Linux         |
| **CPU**    | [Especificar] |
| **RAM**    | [Especificar] |
| **Python** | 3.10+         |

---

## Licença dos Dados

[Especificar a licença do dataset utilizado]

---

## Autores

- [Nome do integrante 1]
- [Nome do integrante 2]
- [Nome do integrante 3]

---

## Referências

- Scikit-learn Documentation: https://scikit-learn.org/
- XGBoost Documentation: https://xgboost.readthedocs.io/
