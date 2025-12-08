📊 Dashboard Olist — BI/DS End-to-End

Projeto completo de Business Intelligence + Data Analytics + NLP (Análise de Sentimentos) desenvolvido com Power BI, Python e Power Query.
Dataset oficial da Olist (Kaggle).
Modelos: Power BI, Python (NLP), Power Query, DAX
Arquitetura: ETL → Modelagem Dimensional → Métricas DAX → ML (SVM + Regras) → Dashboards Interativos

📝 Resumo Executivo 

Este projeto entrega uma visão completa da operação de e-commerce da Olist, consolidando vendas, comportamento do cliente, desempenho de vendedores e percepção de qualidade. O dashboard transforma dados brutos em insights acionáveis, incluindo análise de sentimento baseada em NLP. A solução demonstra domínio em modelagem de dados, DAX, storytelling e machine learning aplicado ao negócio.

🧩 1. Objetivo do Projeto

Construir um dashboard profissional que responda perguntas-chave de negócio:

Como está o desempenho comercial (faturamento, pedidos, ticket médio)?
Quais clientes geram mais valor e como segmentá-los (RFV)?
Quais produtos têm melhor performance e margem?
Como os vendedores se comportam (prazo de envio, pedidos, reclamações)?
O que os clientes relatam em suas avaliações? Quais problemas são mais frequentes?

🧩 Guia de Instalação / Reprodutibilidade 
1. Baixar os dados originais da Olist
O dataset pode ser baixado diretamente do Kaggle, no link (https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

2. Abrir o Power BI Desktop
   
3. Importar as tabelas

olist_costumers_dataset.csv
olist_geolocation_datasset.csv
olist_order_items_dataset.csv
olist_order_payments_dataset.csv
olist_order_reviews_dataset.csv
olist_orders_dataset.csv
olist_products_dataset.csv 
olist_sellers_dataset.csv

## 📖 Documentação (docs)

A documentação principal do projeto está separada em arquivos Markdown na pasta `docs/`. Acesse:

🔎 1. Visão Geral do Projeto
- [Visão Geral do Projeto](docs/Visão_geral.md)

🧠 2. Modelagem de Dados (Power BI)
docs/02_modelagem_de_relacionamentos.md

🔄 3. Transformações (Power Query – ETL)
docs/transformacoes_powerquery.md

🧮 4. Dicionário de Medidas (DAX)
docs/medidas_descrição.md  

📊 Dashboard Power BI

As telas e visuais do BI estão disponíveis em:

➡️ /imagens
(com prints completos das páginas do dashboard)

## 🛠️ Como usar este projeto

1. Clone o repositório  
2. Explore a documentação em `docs/` — você encontra a visão geral, estrutura de dados, transformações e dicionário de medidas  
3. Veja os notebooks no diretório `notebook/`, especialmente a análise de sentimentos  
4. Revise os dashboards e imagens na pasta `images/`  
   
🤖 Análise de Sentimento (NLP)

Toda a lógica de processamento dos comentários de clientes foi feita em Python:

➡️ /notebook/analise_sentimentos.ipynb

Inclui:
pré-processamento dos textos
classificação de sentimento
geração de tabelas de confiança e métricas
integração das saídas ao Power BI


📁 2. Estrutura de Pastas do Repositório 

dashboard_olist/
│
├── README.md
│
├── docs/
│   ├── 01_visao_geral.md
│   ├── modelagem_de__relacionamentos.md       ← imagem exportada do Power BI
│   ├── transformacoes_power_query.md        ← guia detalhado
│   ├── medidas_descrição.md                ← tabela com DAX + descrição
│
├── imagnes/                                     ← prints das páginas do BI
│
├── notebook/
│   └── analise_sentimentos.ipynb               ← NLP (Python)

🎯 Objetivo do Projeto

Este projeto demonstra:

Construção de um modelo de dados 
Documentação técnica completa e organizada
Uso de Power Query, DAX e Modelagem Estrela
Técnicas de NLP aplicadas a avaliações reais
Criação de dashboard para insights acionáveis

📄 Licença

Este projeto está sob licença MIT.
Sinta-se livre para estudar, evoluir e adaptar.

