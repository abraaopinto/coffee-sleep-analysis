# ☕ Análise: Consumo de Café e Qualidade do Sono

## 📌 Sobre o Projeto

Este projeto analisa como o consumo de café influencia a qualidade do sono dos clientes, utilizando técnicas de análise exploratória de dados, visualizações avançadas e modelos de Machine Learning.

**Empresa:** Health&Life Analytics  
**Dataset:** synthetic_coffee_health_10000  
**Objetivo:** Prever a qualidade do sono baseado em hábitos e características dos clientes

---

## 🎯 Objetivos

1. **Análise Exploratória:** Entender o perfil dos clientes e padrões nos dados
2. **Insights de Negócio:** Identificar relações entre café, estresse e sono
3. **Modelo Preditivo:** Prever qualidade do sono com alta acurácia

---

## 📊 Dataset

O dataset contém **10.000 registros** com as seguintes variáveis:

| Variável | Tipo | Descrição |
|----------|------|-----------|
| ID | Integer | Identificador único |
| Age | Integer | Idade (18-80 anos) |
| Gender | Categorical | Gênero (Male/Female/Other) |
| Country | Categorical | País de residência |
| Coffee_Intake | Float | Consumo diário em xícaras (0-10) |
| Caffeine_mg | Float | Cafeína diária em mg |
| Sleep_Hours | Float | Média de horas de sono (3-10h) |
| Sleep_Quality | Categorical | **TARGET** - Poor/Fair/Good/Excellent |
| BMI | Float | Índice de Massa Corporal (15-40) |
| Heart_Rate | Integer | Frequência cardíaca (50-110 bpm) |
| Stress_Level | Categorical | Nível de estresse (Low/Medium/High) |
| Physical_Activity_Hours | Float | Atividade física semanal (0-15h) |
| Health_Issues | Categorical | Condições de saúde |
| Occupation | Categorical | Ocupação principal |
| Smoking | Boolean | Fumante (0/1) |
| Alcohol_Consumption | Boolean | Consome álcool (0/1) |

**Fonte:** [Kaggle - Coffee and Health Dataset](https://www.kaggle.com/)

---

## 🛠️ Tecnologias Utilizadas

- **Python 3.8+**
- **Pandas** - Manipulação de dados
- **NumPy** - Operações numéricas
- **Matplotlib & Seaborn** - Visualizações
- **Scikit-learn** - Machine Learning
- **Joblib** - Persistência de modelos
