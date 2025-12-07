# dashboard_olist
Projeto de BI/DS End-to-End para E-commerce (Kaggle). Dashboard completo em Power BI com 6 telas: Home, Clientes, Vendedores, Produtos, Avaliações. Diferencial: Análise de Sentimento dos comentários (NLP/ML em Python) para extrair informações  acionáveis (Top Reclamações, Sentimento por Produto) e correlacionar NPS à qualidade do feedback.

Tela Home:

<img width="911" height="504" alt="Home-Olist" src="https://github.com/user-attachments/assets/07e2bc41-e725-4c32-968d-45c81f26cb1b" />

🏡 Visão Geral do Dashboard (Página Home):
Este painel é a porta de entrada para a análise de desempenho do negócio Olist, fornecendo uma visão consolidada e em tempo real das métricas mais críticas. O design foca na clareza e na identificação imediata de tendências e áreas de atenção.
1. 🏅 Key Performance Indicators (KPIs)
Os cartões de topo fornecem uma visão de alto nível da saúde financeira e operacional, com destaque para a variação em relação ao ano anterior:

| **Métrica**       | **Valor Absoluto**   | **Variação Anual** | **Significado**                                   |
|-------------------|-----------------------|----------------------|---------------------------------------------------|
| **Receita Total** | R$ 1.805 Bilhões      | +20,9%               | Forte crescimento da plataforma.                  |
| **Produtos**      | 134.936               | +21,9%               | Aumento no volume de itens disponíveis.           |
| **Clientes**      | 99.441                | +7,8%                | Crescimento da base de consumidores.              |
| **Ticket Médio**  | R$ 18.238             | +0,9%                | Estabilidade no valor médio das transações.       |

2. 💰 Análise de Faturamento e Vendas
📈 Receita Digital por Mês: O gráfico de série temporal (canto inferior direito) é crucial, mostrando uma tendência de crescimento ascendente e consistente da receita ao longo do ano, validando o sucesso das estratégias implementadas.
💳 Pedidos por Forma de Pagamento: O Cartão de Crédito é o meio dominante, respondendo por 76.5% dos pedidos, seguido por Boleto (16.9%).
📍 Receita por Estado: O estado de São Paulo (SP) é o principal polo de faturamento (37.4% da Receita), seguido por Rio de Janeiro (RJ) e Minas Gerais (MG), permitindo focar esforços logísticos e de marketing nessas regiões.
3. 🛍️ Performance de Produtos e Vendedores
🏆 Top Vendedores por Receita: Este painel permite identificar e recompensar os vendedores de melhor desempenho, essencial para a gestão de parceiros.
🛒 Top Categorias: As categorias de beleza_saude e cama_mesa_banho lideram o faturamento, indicando onde está o maior valor transacionado na plataforma.

Tela de clientes:

<img width="865" height="486" alt="Clientes-Olist" src="https://github.com/user-attachments/assets/27a8c6d0-8e53-4c5d-a725-f1dfbde8cbfc" />

Esta tela é dedicada à Gestão de Relacionamento com o Cliente (CRM), utilizando a poderosa metodologia RFV (Recência, Frequência, Valor) para segmentar a base de clientes.
O objetivo é entender o comportamento do consumidor e direcionar campanhas de retenção e crescimento
.1. 🏅 Key Performance Indicators (KPIs) - Clientes
Os cartões de topo fornecem métricas cruciais sobre a base de clientes:
| **Métrica**               | **Valor**            | **Significado**                                               |
|---------------------------|-----------------------|---------------------------------------------------------------|
| **Clientes Novos**        | 54.011                | Volume de novos clientes na plataforma.                      |
| **Receita Total**         | R$ 1.805 Bilhões      | Receita total gerada pela base de clientes.                  |
| **Ticket Médio**          | R$ 18.238             | Valor médio das transações.                                  |
| **Recência Média (dias)** | 290,27                | Tempo médio desde a última compra — indica saúde da base.    |


2. 🧩 Matriz RFV de Clientes (Recência, Frequência, Valor)
O coração desta tela é a Matriz RFV, que segmenta a base em 6 grupos com base no comportamento de compra:


| **Segmento RFV**   | **Quantidade** | **Ação Sugerida**                                                     |
|--------------------|----------------|------------------------------------------------------------------------|
| **Campeões**       | 16.520         | Clientes de maior valor — focar na retenção e fidelização.            |
| **Em Risco**       | 15.488         | Clientes que compraram bem, mas estão sumidos — focar em reativação.  |
| **Clientes Leais** | 11.760         | Compram com frequência — focar em programas de fidelidade.            |
| **Potenciais**     | 8.169          | Recentes, mas com baixo valor — incentivar a segunda compra.          |
| **Hibernando**     | 8.490          | Não compram há muito tempo — usar promoções fortes para reativar.     |

💰 Receita por Segmento RFV: Este gráfico mostra que os clientes Em Risco e Campeões são os que mais contribuem para a receita total. Isto sublinha a urgência de reativar os clientes "Em Risco", pois eles representam um alto potencial de receita perdida.

3. 🗺️ Distribuição e Evolução da Base
Clientes por Estado: O painel indica a concentração da base, com SP (41.746), RJ (12.652) e MG (11.633) liderando o número de clientes.

Evolução Mensal de Clientes: O gráfico de linha demonstra a variação dos segmentos mais sensíveis ao longo dos meses. Observa-se que a linha de clientes Em Risco (vermelha) e Leais (verde) está se cruzando, o que é um sinal de alerta: é preciso garantir que os clientes leais não migrem para a categoria de risco.

Top 10 Clientes por Faturamento: Permite a identificação dos clientes de maior valor para ações de relacionamento personalizadas.

4. 🛒 Status de Pedido
Clientes por Status de Pedido: Fornece um panorama sobre a experiência pós-venda, mostrando que 97.0% dos pedidos estão classificados como Entregue, refletindo uma alta taxa de sucesso na logística.

Tela de Vendedores


<img width="881" height="496" alt="Vendedores-Olist" src="https://github.com/user-attachments/assets/d867f24e-2231-4017-b0e2-bcb0ed040197" />


