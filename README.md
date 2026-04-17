# 🛒 Marketplace Olist — Dashboard Analítico & NLP

[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org)
[![Figma](https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white)](https://figma.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)

> Análise completa do marketplace Olist com **segmentação de clientes por RFV**, **análise de sentimentos com Machine Learning** e dashboard analítico desenvolvido no Figma.

---

## 🎯 Objetivo

Extrair insights estratégicos do dataset público do Olist, identificando perfis de clientes por valor, frequência e recência de compras — e compreendendo a satisfação dos clientes por meio de análise de sentimentos nas avaliações textuais.

---

## ✨ Funcionalidades

### 👥 Segmentação RFV

| Métrica | Descrição |
|---|---|
| **R** — Recência | Há quantos dias o cliente fez sua última compra |
| **F** — Frequência | Quantas vezes o cliente comprou no período |
| **V** — Valor | Valor total gasto pelo cliente |

- Clusterização dos clientes em segmentos estratégicos *(Champions, Leais, Em risco, etc.)*
- Identificação dos clientes mais valiosos para ações de retenção e fidelização

### 💬 Análise de Sentimentos com NLP

- Pré-processamento e limpeza dos textos de avaliação
- Classificação de sentimentos usando **Machine Learning**
- Correlação entre nota de avaliação e sentimento do texto

### 🎨 Dashboard Analítico

- Interface projetada no **Figma** com foco em clareza e UX analítica
- Visualizações de KPIs por segmento de cliente
- Mapa de satisfação e distribuição geográfica

---

## 🛠️ Tecnologias

| Tecnologia | Uso |
|---|---|
| **Python** | Linguagem base da análise |
| **Pandas / NumPy** | Manipulação e preparação dos dados |
| **Scikit-learn** | Modelos de ML para análise de sentimentos |
| **NLTK / spaCy** | Processamento de linguagem natural |
| **Matplotlib / Seaborn** | Visualizações exploratórias |
| **Figma** | Design do dashboard analítico |

---

## 📊 Dataset

Dataset público disponível no [Kaggle — Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).

```
olist_orders_dataset.csv
olist_customers_dataset.csv
olist_order_reviews_dataset.csv
olist_order_items_dataset.csv
olist_products_dataset.csv
```

---

## 📂 Estrutura do Projeto

```
dashboard_olist/
│
├── notebooks/
│   ├── 01_eda_exploração.ipynb         # Análise exploratória
│   ├── 02_segmentacao_rfv.ipynb        # Clusterização RFV
│   └── 03_analise_sentimentos.ipynb    # NLP e ML
│
├── data/                               # Datasets Olist
├── dashboard/                          # Arquivos do design Figma
├── requirements.txt
└── README.md
```

---

## 🚀 Como Executar

```bash
git clone https://github.com/natsousacosta311-dados/dashboard_olist.git
cd dashboard_olist
pip install -r requirements.txt
jupyter notebook
```

Execute os notebooks em sequência (01 → 03).

---

## 📌 Aprendizados e Próximos Passos

- [x] Segmentação RFV funcional
- [x] Modelo NLP para análise de sentimentos
- [x] Design do dashboard no Figma
- [ ] Deploy do dashboard como webapp (Streamlit)
- [ ] Análise preditiva de churn por segmento

---

## 👩‍💻 Autora

**Natasha de Sousa Costa** — AI Engineer | Data Scientist

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/seu-perfil)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/natsousacosta311-dados)

📄 Licença

Este projeto está sob licença MIT. Sinta-se à vontade para estudar, evoluir e adaptar.


