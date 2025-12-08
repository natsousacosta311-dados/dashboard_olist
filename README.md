📊 Dashboard Olist — BI/DS End-to-End
--

Projeto completo de Business Intelligence + Data Analytics + NLP (Análise de Sentimentos) desenvolvido com Power BI, Python e Power Query.
Dataset oficial da Olist (Kaggle).
Modelos: Power BI, Python (NLP), Power Query, DAX
Arquitetura: ETL → Modelagem Dimensional → Métricas DAX → ML (SVM + Regras) → Dashboards Interativos

📝 Resumo Executivo 
--

Este projeto entrega uma visão completa da operação de e-commerce da Olist, consolidando vendas, comportamento do cliente, desempenho de vendedores e percepção de qualidade. O dashboard transforma dados brutos em insights acionáveis, incluindo análise de sentimento baseada em NLP. A solução demonstra domínio em modelagem de dados, DAX, storytelling e machine learning aplicado ao negócio.

🧩 1. Objetivo do Projeto
--

Construir um dashboard profissional que responda perguntas-chave de negócio:

Como está o desempenho comercial (faturamento, pedidos, ticket médio)?
Quais clientes geram mais valor e como segmentá-los (RFV)?
Quais produtos têm melhor performance e margem?
Como os vendedores se comportam (prazo de envio, pedidos, reclamações)?
O que os clientes relatam em suas avaliações? Quais problemas são mais frequentes?

🛠️ 2. Tecnologias e Arquitetura
--
| Categoria               | Ferramentas / Tecnologias                                       |
|-------------------------|------------------------------------------------------------------|
| Arquitetura             | Modelagem Dimensional (Star Schema)                              |
| Modelagem/Visualização  | Power BI Desktop, DAX                                            |
| Transformação de Dados  | Power Query (M Language), ETL (Extract, Transform, Load)         |
| Data Science / ML       | Python, Jupyter Notebook, NLP (Pré-processamento, Classificação de Sentimento) |
| Datasets                | Olist (Kaggle), Integração dos dados tratados via Python (Sentimento) |


📖 3. Documentação Técnica
--
A documentação detalhada do projeto está organizada na pasta `docs/`.

| Tema                   | Conteúdo                                                         | Acesso Rápido                                            |
|------------------------|------------------------------------------------------------------|----------------------------------------------------------|
| Visão Geral            | Escopo, objetivos e principais resultados                        | [docs/01_visao_geral.md](docs/Visão_geral.md)         |
| Modelagem de Dados     | Diagrama de relacionamentos, cardinalidades e direção dos filtros | [docs/02_modelagem_de_relacionamentos.md](docs/02_modelagem_de_relacionamentos.md) |
| Transformações ETL     | Guia completo das etapas de transformação e limpeza (Power Query) | [docs/03_transformacoes_power_query.md](docs/transformacoes_powerquery.md)     |
| Dicionário de Medidas  | Definições e lógica de todas as métricas e KPIs em DAX           | [docs/04_dicionario_medidas.md](docs/medidas_descrição.md)                     |


🤖 4. Análise de Sentimento (NLP)
--
O coração do componente de Data Science é a análise de sentimento, que transforma o texto livre dos comentários dos clientes em dados estruturados.
Processo: Toda a lógica de pré-processamento, classificação de sentimento (via SVM + regras linguísticas) e geração de métricas de confiança foi executada em Python.
Output: Os resultados (tabelas de sentimento e confiança) são integrados ao modelo Power BI.
Notebook: notebook/analise_sentimentos.ipynb

📁 5. Estrutura de Pastas do Repositório 
---
O repositório está organizado para facilitar a exploração do código e da documentação:

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
├── imagens/                                     ← prints das páginas do BI
│
├── notebook/
│   └── analise_sentimentos.ipynb               ← NLP (Python)


📄 Licença

Este projeto está sob licença MIT. Sinta-se à vontade para estudar, evoluir e adaptar.


