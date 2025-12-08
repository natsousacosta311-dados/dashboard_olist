📊 Dashboard Olist — BI/DS End-to-End

Projeto completo de Analytics utilizando o dataset público da Olist (Kaggle) para criação de um ecossistema integrado de Business Intelligence + Data Science, com foco em Receita, Clientes, Produtos, Vendedores e Qualidade (NPS + Análise de Sentimentos).

Dataset: Olist E-commerce (9 CSVs)
Modelos: Power BI, Python (NLP), Power Query, DAX
Arquitetura: ETL → Modelagem Dimensional → Métricas DAX → ML (SVM + Regras) → Dashboards Interativos

1. 🎨 Layout & Design

Layout criado no Figma, com ícones e paleta padronizada para consistência visual. Todos os elementos foram exportados em SVG/PNG e integrados ao Power BI.

2. 🧩 Modelagem & Tratamento de Dados

A modelagem segue o padrão estrela (star schema):

Fatos: Pedidos, Itens, Pagamentos, Avaliações
Dimensões: Clientes, Vendedores, Produtos, Datas, Geolocalização, Categorias
Tratamentos no Power Query: normalização de textos, conversão de tipos, tratamento de datas, criação de tabelas calendário e tabelas auxiliares (RFV, NPS, Faixas de Peso/Volume, Sentimentos).
Relacionamentos documentados abaixo:

## 🔗 Relacionamentos do Modelo (Power BI)

| Tabela Origem | Coluna Origem | Tabela Destino | Coluna Destino | Cardinalidade | Direção | Status |
|--------------|----------------|----------------|----------------|---------------|---------|--------|
| olist | Date accessed | LocalDateTable_bc25db41... | Date | Many → One | OneDirection | Ativo |
| olist | Date modified | LocalDateTable_d24415e6... | Date | Many → One | OneDirection | Ativo |
| olist | Date created | LocalDateTable_da781db8... | Date | Many → One | OneDirection | Ativo |
| olist_avaliações_dataset | data_resposta_avaliacao | LocalDateTable_a30b965a... | Date | Many → One | OneDirection | Ativo |
| olist_pedidos_dataset | Data_aprovação | LocalDateTable_06da45c7... | Date | Many → One | OneDirection | Ativo |
| olist_pedidos_dataset | data_entrega | LocalDateTable_9610681f... | Date | Many → One | OneDirection | Ativo |
| olist_pedidos_dataset | data_prevista_entrega | LocalDateTable_69f414a0... | Date | Many → One | OneDirection | Ativo |
| olist_pedidos_dataset | Cliente_ID | olist_clientes_dataset | Cliente_ID | One → One | BothDirections | Ativo |
| olist_produtos_pedidos_dataset | Pedido_ID | olist_pedidos_dataset | Pedido_ID | Many → Many | BothDirections | Ativo |
| olist_pagamentos_dataset | ID_Pedido | olist_pedidos_dataset | Pedido_ID | Many → Many | OneDirection | Ativo |
| olist_avaliações_dataset | ID_Pedido | olist_pedidos_dataset | Pedido_ID | Many → One | OneDirection | Ativo |
| olist_produtos_pedidos_dataset | Produto_ID | olist_produtos_dataset | ID_Produto | Many → One | OneDirection | Ativo |
| olist_produtos_pedidos_dataset | Vendedor_ID | olist_vendedores_dataset | Vendedor_ID | Many → One | OneDirection | Ativo |
| olist_produtos_pedidos_dataset | Data_Limite_envio | LocalDateTable_31e0bb4d... | Date | Many → One | OneDirection | Ativo |
| olist_clientes_dataset | Cliente_ID | Tabela RFV Clientes | Cliente_ID | One → One | BothDirections | Ativo |
| Base_com_Sentimento | ID_Pedido | olist_pedidos_dataset | Pedido_ID | Many → One | OneDirection | Ativo |
| olist_avaliações_dataset | ID_avaliaçao | Base_com_Sentimento | ID_avaliaçao | Many → Many | BothDirections | Ativo |
| Exemplos_Problemas | Tipo_Problema | Top_10_Reclamacoes | Tipo_Problema | Many → One | OneDirection | Ativo |
| Sentimento_por_Confianca | Faixa_Confianca | Distribuicao_Confianca | Faixa_Confianca | One → One | BothDirections | Ativo |
| dCalendario | Data | LocalDateTable_0f03f024... | Date | Many → One | OneDirection | Ativo |
| olist_pedidos_dataset | data_envio | dCalendario | Data | Many → One | OneDirection | **Inativo** |
| olist_avaliações_dataset | Data_criação | dCalendario | Data | Many → One | OneDirection | **Inativo** |
| olist_pedidos_dataset | Data_compra | dCalendario | Data | Many → One | OneDirection | Ativo |
| Base_com_Sentimento | Metodo_Classificacao | Confianca_por_Metodo | Metodo_Classificacao | Many → One | OneDirection | Ativo |
| olist_avaliações_dataset | ID_Pedido | olist_produtos_pedidos_dataset | Pedido_ID | Many → Many | BothDirections | **Inativo** |
| olist_clientes_dataset | Primeira Compra (Cliente) | LocalDateTable_f36dd289... | Date | Many → One | OneDirection | Ativo |

## 🧩 Resumo dos Relacionamentos

O modelo utiliza relacionamentos entre diversas tabelas do Olist, integrando pedidos, produtos, clientes, vendedores, avaliações, pagamentos e análises de sentimento.

Principais características:
- A maioria dos relacionamentos segue cardinalidade **Many → One**, típica de modelos estrela.
- Há relacionamentos **One → One** para dimensões especializadas (ex.: RFV).
- Alguns relacionamentos são **Many → Many**, preservados por necessidade do negócio.
- Relacionamentos envolvendo datas utilizam tabelas de calendário automáticas.

Relacionamentos inativos foram mantidos para análises alternativas de data:
- `olist_pedidos_dataset[data_envio]` → `dCalendario[Data]`
- `olist_avaliações_dataset[Data_criação]` → `dCalendario[Data]`
- `olist_avaliações_dataset[ID_Pedido]` → `olist_produtos_pedidos_dataset[Pedido_ID]`
- 
3. 📐 Medidas, Colunas e Tabelas Calculadas

Toda a documentação DAX (medidas, táticas e explicação) está disponível em um arquivo Excel incluído no repositório, com:

Nome
Sintaxe
Descrição
Tipo
Tela associada

Inclui RFV, NPS, Análises de Receita, Faixas de Peso/Volume, Tabelas Virtuais, Séries Temporais, etc.

4. 🤖 Análise de Sentimentos (Python — Modelo Híbrido ML + Regras)

Notebook completo disponível no repositório.
Modelo: SVM + TF-IDF
Acurácia ML: 80,3%
Regras de negócio corrigiram 14,2k classificações (ex.: atraso, defeito, “não gostei”)
Confiança final do pipeline híbrido: 81,3%
Output integrado ao Power BI para dashboards de CX

5. 📺 Telas do Dashboard
   
Tela Home:

<img width="911" height="504" alt="Home-Olist" src="https://github.com/user-attachments/assets/07e2bc41-e725-4c32-968d-45c81f26cb1b" />

🏡 Visão Geral do Dashboard (Página Home):
Este painel é a porta de entrada para a análise de desempenho do negócio Olist, fornecendo uma visão consolidada e em tempo real das métricas mais críticas. O design foca na clareza e na identificação imediata de tendências e áreas de atenção.

Resumo financeiro e operacional:

Receita Total: R$ 1,8 Bi (+20,9% YoY)
Produtos: 134k (+21,9%)
Clientes: 99k (+7,8%)
Ticket Médio: R$ 18,2k
SP é responsável por 37,4% da receita
Cartão representa 76,5% dos pagamentos
Inclui séries temporais e destaque para categorias e vendedores Top.

👥 Clientes — RFV e CRM

<img width="865" height="486" alt="Clientes-Olist" src="https://github.com/user-attachments/assets/27a8c6d0-8e53-4c5d-a725-f1dfbde8cbfc" />

Esta tela é dedicada à Gestão de Relacionamento com o Cliente (CRM), utilizando a  metodologia RFV (Recência, Frequência, Valor) para segmentar a base de clientes.
O objetivo é entender o comportamento do consumidor e direcionar campanhas de retenção e crescimento

Segmentação RFV:

Campeões: 16.520
Em Risco: 15.488
Leais: 11.760
Hibernando: 8.490

Insights-chave:

Evolução Mensal de Clientes: O gráfico de linha demonstra a variação dos segmentos mais sensíveis ao longo dos meses. Observa-se que a linha de clientes Em Risco (vermelha) e Leais (verde) está se cruzando, o que é um sinal de alerta: é preciso garantir que os clientes leais não migrem para a categoria de risco.
SP, RJ e MG lideram a base de clientes.
Top 10 Clientes por Faturamento: Permite a identificação dos clientes de maior valor para ações de relacionamento personalizadas.
Clientes por Status de Pedido: Fornece um panorama sobre a experiência pós-venda, mostrando que 97.0% dos pedidos estão classificados como Entregue, refletindo uma alta taxa de sucesso na logística.

🧑‍🏫 Vendedores

<img width="881" height="496" alt="Vendedores-Olist" src="https://github.com/user-attachments/assets/d867f24e-2231-4017-b0e2-bcb0ed040197" />

Esta tela oferece uma visão profunda sobre o desempenho dos 3.095 vendedores na plataforma. O foco principal é a performance financeira e a qualidade do serviço (NPS), permitindo a gestão ativa e a identificação de áreas que precisam de intervenção.

🏅 Key Performance Indicators (KPIs)
Os KPIs de topo fornecem um resumo do volume e da qualidade dos parceiros de vendas:

Vendedores: 3.095
Receita: R$1,8 Bi
NPS médio: 62,38 (Bom)

Destaques:

2.276 vendedores são Promotores
Há 186 Críticos e 60 Detratores — necessidade de intervenção
Tendência de queda de vendas após setembro alerta para sazonalidade
Ação Sugerida: Essa queda de volume no final do ano é um ponto de atenção que pode indicar a necessidade de campanhas promocionais ou ajustes de estoque para maximizar a receita no período de maior movimento comercial (geralmente Black Friday e Natal, que caem nos últimos meses).

Tabela de Desempenho Individual
A tabela de detalhe lista as principais métricas por Vendedor_ID, incluindo Receita (Vendas R$), Ticket Médio, Pedidos e NPS individual. Isto permite ações de coaching e a investigação pontual de vendedores com baixo desempenho ou alto faturamento (como o líder de vendas R$137.530.931).

Tela de Produtos

<img width="959" height="540" alt="Produtos - Olist" src="https://github.com/user-attachments/assets/49bbe98e-6d6d-40c4-a609-34dfd26dbcf1" />

Esta tela se concentra em otimizar o catálogo de produtos e a logística, cruzando dimensões físicas (volume e peso) com métricas financeiras (ticket médio e frete). O objetivo é identificar quais produtos e categorias são mais rentáveis e quais impactam mais os custos de envio.

🏅 Key Performance Indicators (KPIs) - Logística
Os KPIs de topo destacam o volume do catálogo e as dimensões físicas médias:

Volume Médio: 4.045 cm³
Peso Médio: 2,28 kg
Itens/Pedido: 1,36
Frete Médio: R$ 1.669

Pareto mostra que poucas categorias concentram a receita (beleza_saude, cama_mesa_banho) e devem ser priorizadas em estoque e promoções.
Ticket Médio por Faixa de Peso: Cruza Faixa de Peso × Ticket × Frete para identificar produtos rentáveis vs. caros de transportar.
A faixa "Carga Expresso" e "Carga Grande" (acima de 10 Kg e 5-10 Kg) possui os Tickets Médios mais altos (R$4.918 e R$1.367), mas são produtos mais caros para transportar.
Produtos de Peso Pequeno (0.2-0.5 Kg) e Médio (1-3 Kg) têm tickets mais baixos, mas são mais fáceis de expedir.

Média de Frete e Ticket Médio por Faixa de Peso:
Confirma que a Carga Expresso tem o Frete Médio mais alto (e, consequentemente, o maior Ticket Médio), validando que produtos grandes/pesados tendem a ter fretes mais caros, impactando a rentabilidade bruta.

🧭 Top 10 Estados e Categorias por Performance
Top 10 Estados por Ticket Médio:

SP (R$890,69) e RJ (R$872,71) lideram o Ticket Médio, o que é um fator positivo. No entanto, é importante notar o Giro Estoque (giro de inventário) em SP (1,74), que é o mais alto, indicando que o inventário em SP está se movendo mais rapidamente.


Tela de Avaliações
<img width="964" height="505" alt="Avaliações" src="https://github.com/user-attachments/assets/d2bd231d-33f8-478f-aa9c-23124da8ecb0" />

Esta tela é dedicada a medir a Qualidade da Experiência do Cliente (CX), usando o feedback direto para identificar pontos fortes e problemas de forma rápida e quantificada. O grande destaque é o uso de um modelo de Machine Learning para análise de sentimentos.

1. 🤖 Inovação: Análise de Sentimentos Híbrida (ML + Regras)
O gráfico de rosca "Distribuição de Sentimentos (Comentário)" é gerado a partir de um modelo de Machine Learning (SVM com TF-IDF) treinado em Python (Jupyter Notebook), que foi aprimorado com Regras de Negócio (modelo híbrido).


Distribuição:

NEGATIVO (45.9%): Alto volume de comentários negativos (18.778), indicando que a insatisfação precisa ser endereçada.
POSITIVO (43.6%): Um volume ligeiramente menor que o negativo, mas ainda significativo  (17.863).
NEUTRO (10.5%): Comentários factuais que não expressam emoção forte (4.309).

🏅 Key Performance Indicators (KPIs) - Qualidade
   
| Métrica                     | Valor     | Significado                                                           |
|-----------------------------|-----------|------------------------------------------------------------------------|
| NPS                         | 62,38     | Classificação "Bom/Excelente" na média geral da plataforma.           |
| Promotores                  | 76.470    | Alto volume de promotores na base de notas (Notas 4 e 5).             |
| Detratores                  | 14,7%     | Baixa taxa de detratores na base de notas (Notas 1 e 2).              |
| TMR (Tempo Médio de Resposta) | 2,58    | Tempo médio de 2 dias e meio para responder a uma avaliação.          |
| Comentários                 | 40.950    | Volume de feedback não estruturado capturado pelo modelo de ML.       |
| Média de Notas              | 4,09      | Nota média geral alta, reforçando a qualidade do serviço.             |


📈 Análise de Tendências e Notas
NPS e % Promotores por Mês: O gráfico de linha e coluna mostra que a performance do NPS e do percentual de promotores caiu drasticamente a partir de Setembro, com o NPS entrando em território NEGATIVO (abaixo de zero).

Ação Sugerida: Essa queda sazonal/temporal é um alerta máximo que exige investigação imediata na logística ou qualidade dos produtos vendidos a partir de setembro.

Distribuição de Nota e Total Avaliações:

O volume de notas 5 é dominante, o que mantém a Média de Notas em 4,09.
A alta taxa de promotores (77,6%) e a baixa taxa de detratores (14,7%) (no gráfico de rosca superior) confirmam que a maioria dos clientes fica satisfeita.

 ⏱️ Tempo de Resposta e Detalhamento
Tempo Médio de Resposta por Semana: O gráfico de barras mostra a consistência no tempo de resposta, flutuando entre a Semana 10 e 12. A gestão precisa monitorar este KPI para garantir que não ultrapasse o TMR de 2,58 dias.
Avaliações (Detalhe): A tabela fornece o drill-down nos comentários brutos, permitindo investigar individualmente avaliações críticas (como notas 1 ou 2) e o tempo de resposta associado.

🤖 Análise de Sentimentos (Modelo Híbrido ML)

<img width="964" height="508" alt="Sentimentos - Olist" src="https://github.com/user-attachments/assets/7b46ef47-8bf3-4ed9-afcc-851ade0ee3d9" />

Esta tela é o resultado da aplicação de um modelo de Análise de Sentimentos (NLP - Processamento de Linguagem Natural) desenvolvido em Python, que classifica automaticamente os comentários dos clientes.

Fonte de Dados: As informações aqui exibidas são geradas a partir do modelo treinado sobre o dataset de avaliações da Olist. Os scripts para treinamento e aplicação, incluindo o modelo híbrido de ML + Regras de Negócio, podem ser encontrados no repositório com o nome Análise de sentimentos.ipynb.

📊 Distribuição e Volume do Sentimento
Os KPIs e o gráfico de rosca "Distribuição de Sentimentos (Comentário)" fornecem uma visão quantificada do humor do cliente:

Comentários Totais: 40.950 avaliações foram processadas pelo modelo.
Sentimento Negativo (🔴): 17.587 (42,95%) dos comentários são negativos.
Sentimento Positivo (🟢): 16.314 (39,84%) são positivos.

Conclusão: Há uma leve prevalência de sentimentos negativos sobre os positivos na base de comentários, o que é um ponto de atenção crítica para o CX (Customer Experience).

📈 Evolução e Tendência
   
Evolução e Tendência de Sentimento: O gráfico de série temporal (canto inferior esquerdo) revela a dinâmica emocional ao longo do tempo.
Ponto de Alerta: A partir de outubro/novembro, há um pico significativo no sentimento negativo, exigindo investigação imediata para identificar falhas operacionais ou sazonais.

NPS por Sentimento: O NPS do grupo NEGATIVO é -18,13, confirmando que a insatisfação nos comentários se traduz em notas baixas. O NPS do grupo POSITIVO é 91,79, validando a acurácia do modelo em identificar clientes satisfeitos.

🔍 Termos e Reclamações Mais Frequentes
Palavras Mais Frequentes: O painel lista termos genéricos como compras, bem, bom, recebi, chegou, entrega, que são usados por clientes Neutros ou Fatuais.
Top 10 Reclamações: Esta é a seção mais acionável, pois identifica os maiores problemas:

Atraso de Entrega (15,32%)
Embalagem Violada/Dano (6,49%)
Qualidade (5,59%)

Ação de Gestão: A prioridade deve ser resolver Atrasos de Entrega, que é a maior fonte de insatisfação.

📦 Contagem de Sentimento por Categoria de Produto
Este gráfico cruza o resultado do ML com o catálogo, mostrando o impacto do sentimento em categorias específicas:

Cama, Mesa e Banho: Lidera o volume de comentários NEGATIVOS (1.662) e POSITIVOS (1.764), indicando que é a categoria de maior interação emocional.
Beleza e Saúde: Também possui um alto volume de negativos (1.287), que deve ser monitorado de perto.

⚙️ Auditoria do Modelo de Classificação
O painel de auditoria demonstra a eficácia do modelo Híbrido (ML + Regras):

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

Confiança Comprovada: A aplicação dessas regras corrigiu milhares de classificações e elevou a Confiança Média Final para 81,3%.

Prioridade de CX: O modelo identifica claramente que Atraso de Entrega é a principal reclamação (15,32%) e o sentimento NEGATIVO (45,9%) está em tendência de crescimento, confirmando a necessidade de otimizar a logística para manter a satisfação do cliente.

