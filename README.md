# dashboard_olist
Projeto de BI/DS End-to-End para E-commerce (Kaggle). Dashboard completo em Power BI com 6 telas: Home, Clientes, Vendedores, Produtos, Avaliações. Diferencial: Análise de Sentimento dos comentários (NLP/ML em Python) para extrair informações  acionáveis (Top Reclamações, Sentimento por Produto) e correlacionar NPS à qualidade do feedback.
Dataset disponível em: https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce/code?datasetId=55151&sortBy=voteCount
Enolve 9 arquivos CSV:
olist_customers_dataset; olist_geolocation_dataset;olist_order_items_dataset; olist_order_payments_dataset.;olist_order_reviews_dataset; olist_orders_dataset.;olist_products_dataset; olist_sellers_dataset; product_category_name_translation

1. Layout
   (explicação de que foi feito no figma, ícones utilizados e processo de exportação, etc, se necessário..)

1. Modelagem
   (aqui estarão a descrição dos relacionamentos e tratamentos de dados)

2. Medidas DAX utilizadas, colunas e tabelas calculadas
   (toda a documentação estará em um arquivo excel, com as seguintes colunas: nome da medida/tabela/coluna, sintaxe, descrição, tipo, tela associada...)

3. Script do Modelo de machine learning utilizado para análise de sentimentos
Disponível no repositório

4. Visualização e Telas

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

Esta tela oferece uma visão profunda sobre o desempenho dos 3.095 vendedores na plataforma. O foco principal é a performance financeira e a qualidade do serviço (NPS), permitindo a gestão ativa e a identificação de áreas que precisam de intervenção.

1. 🏅 Key Performance Indicators (KPIs)
Os KPIs de topo fornecem um resumo do volume e da qualidade dos parceiros de vendas:

Vendedores Totais: 3.095 vendedores ativos na plataforma.

Vendas (Receita Total): R$1.805 Bilhões, mostrando a contribuição massiva dos vendedores.

Pedidos: 98.666 pedidos processados.

NPS Médio: 62,38, indicando que a plataforma se encontra na faixa de "Bom" (Score acima de 50 é considerado Bom/Excelente em muitas métricas globais).

2. 📊 Análise da Qualidade de Serviço (NPS)
O NPS é o foco central para a gestão da experiência do cliente.

Vendedores por Faixa de NPS: O histograma mostra a distribuição da base de vendedores por grupos de NPS:

Promotores (Faixa 1): A maior parte dos vendedores (2.276) está no topo, o que é um excelente indicativo da satisfação geral do cliente.

Críticos e Detratores: Apesar da alta média (62,38), há um número significativo de vendedores nas faixas Crítico (186) e Detrator (60), que exigem programas de melhoria imediata.

Top 10 Vendedores: Permite reconhecer e analisar os vendedores de maior pontuação por um Score de Performance Consolidado (10,0 a 6,8), que serve como benchmark para o restante da base.

3. 📈 Evolução de Vendas e Pedidos (Série Temporal)
O gráfico de linha e coluna mostra a saúde financeira ao longo do tempo:

Tendência Sazonal: Há um claro padrão de alta nas Vendas (R$) e Pedidos no primeiro semestre do ano (até agosto), seguido por uma queda nos meses finais (Setembro a Dezembro).

Ação Sugerida: Essa queda de volume no final do ano é um ponto de atenção que pode indicar a necessidade de campanhas promocionais ou ajustes de estoque para maximizar a receita no período de maior movimento comercial (geralmente Black Friday e Natal, que caem nos últimos meses).

4. Tabela de Desempenho Individual
A tabela de detalhe lista as principais métricas por Vendedor_ID, incluindo Receita (Vendas R$), Ticket Médio, Pedidos e NPS individual. Isto permite ações de coaching e a investigação pontual de vendedores com baixo desempenho ou alto faturamento (como o líder de vendas R$137.530.931).

Tela de Produtos

<img width="959" height="540" alt="Produtos - Olist" src="https://github.com/user-attachments/assets/49bbe98e-6d6d-40c4-a609-34dfd26dbcf1" />

Esta tela se concentra em otimizar o catálogo de produtos e a logística, cruzando dimensões físicas (volume e peso) com métricas financeiras (ticket médio e frete). O objetivo é identificar quais produtos e categorias são mais rentáveis e quais impactam mais os custos de envio.

1. 🏅 Key Performance Indicators (KPIs) - Logística
Os KPIs de topo destacam o volume do catálogo e as dimensões físicas médias:

| **Métrica**      | **Valor**         | **Significado**                                                         |
|------------------|-------------------|-------------------------------------------------------------------------|
| **Produtos**     | 134.936           | Tamanho do catálogo de produtos.                                       |
| **Categorias**   | 74                | Diversidade do mix de produtos.                                        |
| **Volume Médio** | 4.045 cm³         | Volume médio dos produtos vendidos.                                    |
| **Peso Médio**   | 2,28 Kg           | Peso médio dos produtos vendidos.                                      |
| **Itens/Pedido** | 1,36              | Baixo índice, indicando que a maioria dos pedidos é de item único.     |
| **Frete Médio**  | R$ 1.669          | Custo médio de frete por transação (valor alto indica impacto crítico). |

2. 💲 Análise de Categoria (Pareto de Receita)
Pareto de Categoria de Produtos: O gráfico de Pareto mostra que o princípio de 80/20 se aplica: poucas categorias geram a maior parte da receita.

As primeiras categorias como beleza_saude, cama_mesa_banho, relogios_presentes e informatica_acessorios são as mais importantes e devem ser priorizadas em estoque e promoções.

3. ⚖️ Peso vs. Rentabilidade e Custo
Ticket Médio por Faixa de Peso: Cruza a receita média com o peso do produto.

A faixa "Carga Expresso" e "Carga Grande" (acima de 10 Kg e 5-10 Kg) possui os Tickets Médios mais altos (R$4.918 e R$1.367), mas são produtos mais caros para transportar.

Produtos de Peso Pequeno (0.2-0.5 Kg) e Médio (1-3 Kg) têm tickets mais baixos, mas são mais fáceis de expedir.

Média de Frete e Ticket Médio por Faixa de Peso:

Confirma que a Carga Expresso tem o Frete Médio mais alto (e, consequentemente, o maior Ticket Médio), validando que produtos grandes/pesados tendem a ter fretes mais caros, impactando a rentabilidade bruta.

4. 🧭 Top 10 Estados e Categorias por Performance
Top 10 Estados por Ticket Médio:

SP (R$890,69) e RJ (R$872,71) lideram o Ticket Médio, o que é um fator positivo. No entanto, é importante notar o Giro Estoque (giro de inventário) em SP (1,74), que é o mais alto, indicando que o inventário em SP está se movendo mais rapidamente.

Categorias e Produtos por Faixa de Peso:

Esta tabela fornece a granularidade, mostrando que categorias como cama_mesa_banho e esporte_lazer lideram o Ticket Médio e o Giro Estoque dentro das faixas de peso, sendo as mais eficientes e rentáveis.

Tela de Avaliações
<img width="964" height="505" alt="Avaliações" src="https://github.com/user-attachments/assets/d2bd231d-33f8-478f-aa9c-23124da8ecb0" />

Esta tela é dedicada a medir a Qualidade da Experiência do Cliente (CX), usando o feedback direto para identificar pontos fortes e problemas de forma rápida e quantificada. O grande destaque é o uso de um modelo de Machine Learning para análise de sentimentos.

1. 🤖 Inovação: Análise de Sentimentos Híbrida (ML + Regras)
O gráfico de rosca "Distribuição de Sentimentos (Comentário)" é gerado a partir de um modelo de Machine Learning (SVM com TF-IDF) treinado em Python (Jupyter Notebook), que foi aprimorado com Regras de Negócio (modelo híbrido).

Acurácia: O modelo foi testado em uma base de validação, atingindo uma acurácia de 80.3%.

Distribuição:

NEGATIVO (45.9%): Alto volume de comentários negativos (18.778), indicando que a insatisfação precisa ser endereçada.

POSITIVO (43.6%): Um volume ligeiramente menor que o negativo, mas ainda robusto (17.863).

NEUTRO (10.5%): Comentários factuais que não expressam emoção forte (4.309).

Valor: A implementação de regras de negócio corrigiu mais de 14.280 classificações do ML puro, garantindo que frases críticas como "veio com defeito" ou "mas não gostei" fossem categorizadas corretamente como NEGATIVO, aumentando a Confiança Média Final para 81.3%.

2. 🏅 Key Performance Indicators (KPIs) - Qualidade
   
| Métrica                     | Valor     | Significado                                                           |
|-----------------------------|-----------|------------------------------------------------------------------------|
| NPS                         | 62,38     | Classificação "Bom/Excelente" na média geral da plataforma.           |
| Promotores                  | 76.470    | Alto volume de promotores na base de notas (Notas 4 e 5).             |
| Detratores                  | 14,7%     | Baixa taxa de detratores na base de notas (Notas 1 e 2).              |
| TMR (Tempo Médio de Resposta) | 2,58    | Tempo médio de 2 dias e meio para responder a uma avaliação.          |
| Comentários                 | 40.950    | Volume de feedback não estruturado capturado pelo modelo de ML.       |
| Média de Notas              | 4,09      | Nota média geral alta, reforçando a qualidade do serviço.             |


3. 📈 Análise de Tendências e Notas
NPS e % Promotores por Mês: O gráfico de linha e coluna mostra que a performance do NPS e do percentual de promotores caiu drasticamente a partir de Setembro, com o NPS entrando em território NEGATIVO (abaixo de zero).

Ação Sugerida: Essa queda sazonal/temporal é um alerta máximo que exige investigação imediata na logística ou qualidade dos produtos vendidos a partir de setembro.

Distribuição de Nota e Total Avaliações:

O volume de notas 5 é dominante, o que mantém a Média de Notas em 4,09.

A alta taxa de promotores (77,6%) e a baixa taxa de detratores (14,7%) (no gráfico de rosca superior) confirmam que a maioria dos clientes fica satisfeita.

4. ⏱️ Tempo de Resposta e Detalhamento
Tempo Médio de Resposta por Semana: O gráfico de barras mostra a consistência no tempo de resposta, flutuando entre a Semana 10 e 12. A gestão precisa monitorar este KPI para garantir que não ultrapasse o TMR de 2,58 dias.

Avaliações (Detalhe): A tabela fornece o drill-down nos comentários brutos, permitindo investigar individualmente avaliações críticas (como notas 1 ou 2) e o tempo de resposta associado.

🤖 Análise de Sentimentos (Modelo Híbrido ML)

<img width="964" height="508" alt="Sentimentos - Olist" src="https://github.com/user-attachments/assets/7b46ef47-8bf3-4ed9-afcc-851ade0ee3d9" />

Esta tela é o resultado da aplicação de um modelo de Análise de Sentimentos (NLP - Processamento de Linguagem Natural) desenvolvido em Python, que classifica automaticamente os comentários dos clientes.

Fonte de Dados: As informações aqui exibidas são geradas a partir do modelo treinado sobre o dataset de avaliações da Olist. Os scripts para treinamento e aplicação, incluindo o modelo híbrido de ML + Regras de Negócio, podem ser encontrados no repositório com o nome Análise de sentimentos.ipynb.

1. 📊 Distribuição e Volume do Sentimento
Os KPIs e o gráfico de rosca "Distribuição de Sentimentos (Comentário)" fornecem uma visão quantificada do humor do cliente:

Comentários Totais: 40.950 avaliações foram processadas pelo modelo.

Sentimento Negativo (🔴): 17.587 (42,95%) dos comentários são negativos.

Sentimento Positivo (🟢): 16.314 (39,84%) são positivos.

Conclusão: Há uma leve prevalência de sentimentos negativos sobre os positivos na base de comentários, o que é um ponto de atenção crítica para o CX (Customer Experience).

2. 📈 Evolução e Tendência
Evolução e Tendência de Sentimento: O gráfico de série temporal (canto inferior esquerdo) revela a dinâmica emocional ao longo do tempo.

O volume de NEGATIVO (linha vermelha) tem uma tendência clara de crescimento ao longo do ano.

O volume de POSITIVO (linha verde) também cresce, mas em um ritmo menor ou mais volátil.

Ponto de Alerta: A partir de outubro/novembro, há um pico significativo no sentimento negativo, exigindo investigação imediata para identificar falhas operacionais ou sazonais.

NPS por Sentimento: O NPS do grupo NEGATIVO é -18,13, confirmando que a insatisfação nos comentários se traduz em notas baixas. O NPS do grupo POSITIVO é 91,79, validando a acurácia do modelo em identificar clientes satisfeitos.

3. 🔍 Termos e Reclamações Mais Frequentes
Palavras Mais Frequentes: O painel lista termos genéricos como compras, bem, bom, recebi, chegou, entrega, que são usados por clientes Neutros ou Fatuais.

Top 10 Reclamações: Esta é a seção mais acionável, pois identifica os maiores problemas:

Atraso de Entrega (15,32%)

Embalagem Violada/Dano (6,49%)

Qualidade (5,59%)

Ação de Gestão: A prioridade deve ser resolver Atrasos de Entrega, que é a maior fonte de insatisfação.

4. 📦 Contagem de Sentimento por Categoria de Produto
Este gráfico cruza o resultado do ML com o catálogo, mostrando o impacto do sentimento em categorias específicas:

Cama, Mesa e Banho: Lidera o volume de comentários NEGATIVOS (1.662) e POSITIVOS (1.764), indicando que é a categoria de maior interação emocional.

Beleza e Saúde: Também possui um alto volume de negativos (1.287), que deve ser monitorado de perto.

5. ⚙️ Auditoria do Modelo de Classificação
O painel de auditoria demonstra a robustez do modelo Híbrido (ML + Regras):

Correção por Regras: As regras de negócio implementadas (ex: REGRA_ATRASO, REGRA_DEFEITO, REGRA_NAO_GOSTEI) foram responsáveis por corrigir milhares de classificações que o ML puro poderia ter classificado com baixa confiança ou de forma errada, elevando a confiabilidade dos dados apresentados.

Confiança: Mostra a confiança média das classificações, diferenciando onde o ML ALTA CONF (alta confiança) atuou sozinho e onde as regras de override (como REGRA_CRITICA) garantiram a classificação correta.

🎯 Conclusão e Resultados Estratégicos do Projeto Olist
Este conjunto de dashboards fornece uma visão 360º do ecossistema Olist, transformando dados brutos em inteligência de negócio acionável em quatro pilares fundamentais: Receita, Clientes, Vendedores e Qualidade (CX).

💰 Performance Financeira e Crescimento
O projeto valida um crescimento robusto na plataforma, com a Receita Total e o volume de Produtos apresentando alta variação anual (acima de +20.9% e +21.9%, respectivamente).

Foco Regional: São Paulo é o motor financeiro, responsável por 37,4% da Receita e o maior volume de clientes.

Alerta de Sazonalidade: Observa-se uma queda clara e preocupante nas vendas e pedidos a partir de Setembro, o que exige uma estratégia imediata de campanha para os meses finais do ano.

🧑‍🤝‍🧑 Gestão de Clientes e Parceiros
A plataforma permite a gestão ativa da base de clientes e vendedores:

Retenção de Clientes: A Matriz RFV (Recência, Frequência, Valor) identifica os Clientes Em Risco (15.488) como um grupo de alto valor que precisa de atenção, pois contribuem significativamente para a receita.

Qualidade dos Vendedores: O NPS médio geral é bom (62,38), mas a segmentação revela 186 vendedores no grupo "Crítico" (NPS < -50) e 60 na faixa "Detrator", exigindo intervenção urgente para mitigar o risco de reputação.

🤖 Diferencial Técnico: A Voz do Cliente (Análise de Sentimentos)
O dashboard de Avaliações é a prova de conceito do seu skill em Data Science, onde o modelo de NLP transformou feedback não estruturado em métricas de qualidade:

Metodologia Híbrida: O gráfico de sentimentos é o resultado de um modelo de Machine Learning (SVM), aprimorado com Regras de Negócio para garantir a precisão de frases críticas.

Confiança Comprovada: A aplicação dessas regras corrigiu milhares de classificações e elevou a Confiança Média Final para 81,3%, fornecendo dados de alta fidelidade para o BI.

Prioridade de CX: O modelo identifica claramente que Atraso de Entrega é a principal reclamação (15,32%) e o sentimento NEGATIVO (45,9%) está em tendência de crescimento, confirmando a necessidade de otimizar a logística para manter a satisfação do cliente.

