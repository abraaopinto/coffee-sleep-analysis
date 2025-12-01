# ☕ Análise: Consumo de Café e Qualidade do Sono

## 📌 Sobre o Projeto

Este projeto analisa como o consumo de café influencia a qualidade do sono dos clientes, utilizando técnicas de análise exploratória de dados, visualizações avançadas e modelos de Machine Learning.

**Empresa (fictícia):** Health&Life Analytics  
**Dataset:** synthetic_coffee_health_10000  
**Objetivo principal:** prever a **qualidade do sono** (`Sleep_Quality`) com base em hábitos e características dos clientes.

---

## 🎯 Objetivos

1. **Análise Exploratória (EDA):**  
   Entender o perfil dos clientes e padrões nos dados (distribuições, correlações, outliers, dados faltantes etc.).

2. **Insights de Negócio:**  
   Identificar relações entre:
   - consumo de café e qualidade do sono;
   - estresse, atividade física e sono;
   - perfis de clientes com maior risco de baixa qualidade de sono.

3. **Modelo Preditivo:**  
   Construir e avaliar modelos de classificação para prever `Sleep_Quality`, comparando diferentes algoritmos e selecionando o melhor.

---

## 📊 Dataset

O dataset contém **10.000 registros**, com as seguintes variáveis principais:

| Variável                   | Tipo        | Descrição                                         |
|---------------------------|------------|---------------------------------------------------|
| `ID`                      | Integer    | Identificador único                               |
| `Age`                     | Integer    | Idade (18–80 anos)                                |
| `Gender`                  | Categorical| Gênero (Male/Female/Other)                        |
| `Country`                 | Categorical| País de residência                                |
| `Coffee_Intake`           | Float      | Consumo diário em xícaras (0–10)                  |
| `Caffeine_mg`             | Float      | Cafeína diária em mg                              |
| `Sleep_Hours`             | Float      | Média de horas de sono (3–10h)                    |
| `Sleep_Quality`           | Categorical| **TARGET** – Poor/Fair/Good/Excellent             |
| `BMI`                     | Float      | Índice de Massa Corporal (15–40)                  |
| `Heart_Rate`              | Integer    | Frequência cardíaca (50–110 bpm)                  |
| `Stress_Level`            | Categorical| Nível de estresse (Low/Medium/High)              |
| `Physical_Activity_Hours` | Float      | Atividade física semanal (0–15h)                  |
| `Health_Issues`           | Categorical| Condições de saúde                                 |
| `Occupation`              | Categorical| Ocupação principal                                 |
| `Smoking`                 | Boolean    | Fumante (0/1)                                      |
| `Alcohol_Consumption`     | Boolean    | Consome álcool (0/1)                               |

**Fonte original do dataset:** Kaggle – *Coffee and Health Dataset*.

---

## 🛠️ Tecnologias Utilizadas

- **Python 3.8+**
- **Pandas** – Manipulação e limpeza de dados
- **NumPy** – Operações numéricas
- **Matplotlib & Seaborn** – Visualizações
- **Scikit-learn** – Modelagem de Machine Learning
- **Joblib** – Persistência de modelos e transformadores

---

## 📁 Estrutura do Projeto

```text
coffee-sleep-analysis/
├─ analise_cafe_sono.ipynb       # Notebook principal com EDA, modelos e conclusões
├─ requirements.txt              # Dependências do projeto
├─ README.md                     # Este arquivo
├─ data/
│  ├─ inputs/
│  │  └─ synthetic_coffee_health_10000(in).csv   # Dataset de entrada
│  └─ outputs/
│     ├─ figures/                # Gráficos gerados na análise
│     ├─ models/                 # Modelos treinados e encoders salvos (.pkl)
│     └─ reports/                # Textos de insights e recomendações (.txt)
└─ .gitignore                    # Configuração para ignorar arquivos locais (venv, outputs, etc.)
```

> Obs.: as pastas dentro de `data/outputs/` são criadas automaticamente pelo notebook, caso ainda não existam.

---

## ▶️ Como Executar o Projeto

### 1. Pré-requisitos

- Python **3.8 ou superior**
- `git` instalado (opcional, para clonar o repositório)
- Navegador + Jupyter Notebook **ou** VSCode com suporte a notebooks  
- (Opcional, mas recomendado) ambiente virtual (`venv`)

### 2. Clonar o repositório

```bash
git clone https://github.com/abraaopinto/coffee-sleep-analysis.git
cd coffee-sleep-analysis
```

Se preferir, também é possível baixar o `.zip` direto pelo GitHub e extrair a pasta.

### 3. Criar e ativar o ambiente virtual

**Windows (PowerShell / CMD):**

```bash
python -m venv venv
venv\Scripts\activate
```

**Linux / macOS:**

```bash
python3 -m venv venv
source venv/bin/activate
```

### 4. Instalar as dependências

Com o ambiente virtual ativado:

```bash
pip install -r requirements.txt
```

### 5. Garantir o dataset no local correto

Verifique se o arquivo:

```text
data/inputs/synthetic_coffee_health_10000(in).csv
```

existe.  
Se não existir:

1. Crie as pastas `data/inputs/` (se necessário).
2. Coloque o arquivo `synthetic_coffee_health_10000(in).csv` dentro de `data/inputs/`.

### 6. Abrir e executar o notebook

Se estiver usando Jupyter:

```bash
jupyter notebook
```

Depois:

1. Abra o arquivo `analise_cafe_sono.ipynb`.
2. Execute as células em ordem (`Run All`), ou seção por seção:
   - Carregamento de dados
   - Análise Exploratória
   - Visualizações comparativas
   - Preparação dos dados e modelagem
   - Avaliação dos modelos
   - Geração de relatórios e recomendações

> Dica: o próprio notebook contém uma célula inicial com:
> ```python
> !pip install -qq -r "./requirements.txt"
> ```
> Isso ajuda principalmente em ambientes como Google Colab.

---

## 🔍 Fluxo da Análise no Notebook

De forma resumida, o notebook segue o fluxo abaixo:

1. **Carregamento e inspeção inicial**
   - Leitura do CSV a partir de `data/inputs/`.
   - Visualização de dimensões, amostras, tipos de dados, valores nulos e duplicados.

2. **Análise Exploratória (EDA)**
   - Estatísticas descritivas de colunas numéricas e categóricas.
   - Distribuições (histogramas, boxplots).
   - Frequência de categorias.
   - Matriz de correlação entre variáveis numéricas.

3. **Visualizações e comparações**
   - Relação entre consumo de café (`Coffee_Intake`, `Caffeine_mg`) e:
     - horas de sono (`Sleep_Hours`);
     - qualidade do sono (`Sleep_Quality`);
     - níveis de estresse.
   - Segmentações por:
     - gênero (`Gender`);
     - faixa etária;
     - nível de atividade física;
     - nível de estresse.

4. **Engenharia de Atributos**
   - Criação de novas features (ex.: razões envolvendo cafeína e BMI, indicadores de sono adequado, índices combinados de saúde etc.).
   - Transformação de variáveis categóricas (codificação) para uso em modelos.

5. **Modelagem Preditiva**
   - Separação em treino e teste.
   - Treinamento de diferentes modelos de classificação (por exemplo: Random Forest, Gradient Boosting, Regressão Logística).
   - Cálculo de métricas como acurácia, matriz de confusão e relatório de classificação.

6. **Seleção do Melhor Modelo**
   - Comparação das métricas entre modelos.
   - Escolha do modelo com melhor desempenho no conjunto de teste.
   - Análise de importância de features (quando aplicável).

7. **Geração de Relatórios e Artefatos**
   - Salvamento de:
     - gráficos em `data/outputs/figures/`;
     - dataset processado em `data/outputs/models/` (arquivo `.csv`);
     - modelo vencedor e encoders em `data/outputs/models/` (`.pkl`);
     - arquivos `.txt` com:
       - principais descobertas;
       - recomendações de negócio.

---

## 📂 Saídas Geradas

Após executar todo o notebook, você deverá encontrar:

- **Gráficos** (PNG) em:
  - `data/outputs/figures/`

- **Modelo treinado** (pickle, melhor modelo):
  - `data/outputs/models/modelo_melhor_<timestamp>.pkl`

- **Dataset processado**:
  - `data/outputs/models/dataset_processado_<timestamp>.csv`

- **Outros artefatos**:
  - Encoders de variáveis categóricas (`label_encoders_<timestamp>.pkl`)
  - Encoder do alvo (`target_encoder_<timestamp>.pkl`)
  - Scaler (`scaler_<timestamp>.pkl`), quando aplicável

- **Relatórios em texto**:
  - `data/outputs/reports/principais_descobertas_<timestamp>.txt`
  - `data/outputs/reports/recomendacoes_negocio_<timestamp>.txt`

---

## 💡 Principais Perguntas Respondidas pelo Projeto

- Há relação clara entre **níveis mais altos de cafeína** e **pior qualidade de sono**?
- Como o **nível de estresse** afeta tanto as **horas de sono** quanto a **qualidade** percebida?
- Grupos com **maior atividade física** tendem a relatar melhor qualidade de sono?
- Quais variáveis mais contribuem para a previsão de `Sleep_Quality` segundo o modelo treinado?

---

## 🚀 Possíveis Extensões Futuras

Algumas ideias de continuidade para o projeto:

- Testar outros algoritmos (XGBoost, LightGBM, redes neurais).
- Implementar validação cruzada e busca de hiperparâmetros (GridSearchCV/RandomizedSearchCV).
- Criar uma API ou aplicação (por exemplo, Streamlit) para que usuários possam simular cenários.
- Explorar explicabilidade de modelos (SHAP, LIME) para aprofundar os insights.

---

## 👨‍💻 Autor

Projeto desenvolvido por **Abraão Pinto** como parte de um desafio de análise de dados e Machine Learning.
