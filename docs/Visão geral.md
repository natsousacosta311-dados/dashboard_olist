5. Visão Geral do Dashboard Olist

Este documento apresenta uma visão executiva das principais telas do dashboard do projeto Olist.
Aqui você encontrará:
KPIs principais
Insights estratégicos
Tendências importantes
Interpretações analíticas das telas
As imagens completas estão na pasta /images do repositório.
   
🏡 Tela Home — Visão Geral do Negócio

<p align="center"> <img width="900" src="https://github.com/user-attachments/assets/07e2bc41-e725-4c32-968d-45c81f26cb1b" /> </p>

A Home fornece um panorama consolidado da operação, com ênfase nos principais indicadores financeiros e operacionais da Olist.

🔎 Destaques da Página

💰 Indicadores Financeiros
Receita Total: R$ 1,8 Bi
Crescimento YoY: +20,9%
Ticket Médio: R$ 18,2k
Produtos: 134k (+21,9%)
Clientes: 99k (+7,8%)

🌍 Panorama Geográfico
SP responde por 37,4% da receita — concentração relevante e estratégica para campanhas e expansão regional. 

💳 Métodos de Pagamento

Cartão representa 76,5% dos pagamentos — padrão esperado para e-commerce e útil para análises de risco/chargeback.

📦 Categorias de produto
As categorias Beleza_saude, cama_mesa_banho e relogios_presentes lideram com maior faturamento.
 
📈 Principais Insights

A página destaca evolução temporal (receita, pedidos e clientes) e evidencia quais categorias e vendedores mais impulsionam o faturamento.

👥 Tela Clientes — CRM & RFV

<p align="center"> <img width="900" src="https://github.com/user-attachments/assets/27a8c6d0-8e53-4c5d-a725-f1dfbde8cbfc" /> </p>

A página de Clientes utiliza segmentação RFV para mapear comportamento e engajamento, permitindo direcionar estratégias de retenção.

🎯 Segmentação RFV

Campeões: 16.520
Em Risco: 15.488
Leais: 11.760
Hibernando: 8.490

📌 Insights Importantes

Linha “Em Risco” cruza com “Leais” ao longo dos meses, indicando potencial deterioração da base de clientes.
SP, RJ e MG lideram a base de clientes e concentram maior receita.
Top 10 Clientes por Faturamento ajudam a definir campanhas personalizadas de alto impacto.
Clientes por Status de Pedido:
97% entregues → excelente consistência logística.

🧑‍🏫 Tela Vendedores — Performance & NPS

<p align="center"> <img width="900" src="https://github.com/user-attachments/assets/d867f24e-2231-4017-b0e2-bcb0ed040197" /> </p>

Esta tela avalia o desempenho dos 3.095 vendedores na plataforma.

🏅 KPIs Principais

Vendedores: 3.095
Receita: R$1,8 Bi
NPS médio: 62,38 (Bom)
Promotores: 2.276 vendedores
Vendedores Críticos: 186
Detratores: 60

📌 Pontos relevantes:
A queda de vendas após setembro sugere sazonalidade crítica.
Ação recomendada: intensificar campanhas para Black Friday e Natal.
A tabela detalhada permite monitorar desempenho individual (receita, ticket médio, pedidos, NPS), facilitando coaching e detecção de casos extremos.

📦 Tela Produtos — Catálogo, Logística & Rentabilidade

<img width="959" height="540" alt="Produtos - Olist" src="https://github.com/user-attachments/assets/49bbe98e-6d6d-40c4-a609-34dfd26dbcf1" />

Focada na análise do catálogo, a página cruza dimensões físicas (peso, volume) com métricas financeiras (ticket, frete, giro)

🏅 KPIs Logísticos
Volume Médio: 4.045 cm³
Peso Médio: 2,28 kg
Itens/Pedido: 1,36
Frete Médio: R$ 1.669

📌 Insights de Produto

Pareto indica forte concentração em:
beleza_saude
cama_mesa_banho

Faixas de peso superiores têm:
Tickets mais altos
Frete muito elevado, impactando margem.

Produtos mais leves são:
Mais baratos para envio
Menos rentáveis individualmente, porém com maior giro

🌍 Desempenho por Estado
SP (R$890,69) e RJ (R$872,71) lideram em Ticket Médio.
SP também lidera em Giro de Estoque (1,74) — ótima eficiência

⭐ Tela Avaliações — Qualidade & Voz do Cliente
<p align="center"> <img width="900" src="https://github.com/user-attachments/assets/d2bd231d-33f8-478f-aa9c-23124da8ecb0" /> </p>
Esta tela foca no CX (Customer Experience) usando notas, tempo de resposta e comentários.

🏅 KPIs Gerais de Qualidade
   
| Métrica                     | Valor     | Significado                                                           |
|-----------------------------|-----------|------------------------------------------------------------------------|
| NPS                         | 62,38     | Classificação "Bom/Excelente" na média geral da plataforma.           |
| Promotores                  | 76.470    | Alto volume de promotores na base de notas (Notas 4 e 5).             |
| Detratores                  | 14,7%     | Baixa taxa de detratores na base de notas (Notas 1 e 2).              |
| TMR (Tempo Médio de Resposta) | 2,58    | Tempo médio de 2 dias e meio para responder a uma avaliação.          |
| Comentários                 | 40.950    | Volume de feedback não estruturado capturado pelo modelo de ML.       |
| Média de Notas              | 4,09      | Nota média geral alta, reforçando a qualidade do serviço.             |

📌 Tendências Relevantes

NPS cai drasticamente a partir de setembro, chegando a zona negativa → alerta crítico.
Notas 5 dominam, mas a queda recente sugere falhas pontuais em logística ou qualidade.
Ação Sugerida: Essa queda sazonal/temporal é um alerta máximo que exige investigação imediata na logística ou qualidade dos produtos vendidos a partir de setembro.


🤖 Tela Análise de Sentimentos — NLP Híbrido (ML + Regras)
<p align="center"> <img width="900" src="https://github.com/user-attachments/assets/7b46ef47-8bf3-4ed9-afcc-851ade0ee3d9" /> </p>
O diferencial técnico do projeto: um modelo SVM + TF-IDF, ajustado com Regras de Negócio.
Scripts disponíveis em:
👉 /notebook/analise_sentimentos.ipynb

📊 Distribuição de Sentimentos (40.950 comentários)

Negativo: 42,95%
Positivo: 39,84%
Neutro: restante

📌 Há predominância leve de sentimento negativo — demanda atenção imediata.

📉 Tendências
Pico negativo após outubro → indica problema sazonal/operacional real.
NPS Negativo para Sentimento Negativo (-18,13) comprova convergência ML + realidade.
NPS Positivo extremamente alto (91,79) para Sentimento Positivo → excelente validação do modelo.

🛑 Top Reclamações

Atraso de Entrega — 15,32%
Embalagem Violada/Dano — 6,49%

✔ Ação Estratégica

Priorizar melhorias logísticas imediatamente para reduzir o volume de atrasos.
Conclusão: Há uma leve prevalência de sentimentos negativos sobre os positivos na base de comentários, o que é um ponto de atenção crítica para o CX (Customer Experience).


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


🎯 Conclusão e Resultados Estratégicos do Projeto Olist
Este conjunto de dashboards fornece uma visão 360º do ecossistema Olist, transformando dados brutos em inteligência de negócio acionável em quatro pilares fundamentais: Receita, Clientes, Vendedores e Qualidade (CX).

💰 1. Performance Financeira

Crescimento forte da receita e do volume de produtos (+20% YoY)
SP domina o faturamento

🧑‍🤝‍🧑 2. Gestão de Clientes e Vendedores

Matriz RFV identifica risco real na base (aumento de clientes em risco)
NPS geral bom, mas vendedores críticos precisam de ação imediata


🤖 Diferencial Técnico: A Voz do Cliente (Análise de Sentimentos)
Modelo híbrido aumenta precisão e interpretabilidade
Insights acionáveis identificam principais dores do cliente

🔧 4. Prioridades Estratégicas

Resolver atrasos de entrega
Investigar queda após setembro
Focar em segmentos de alto valor (Campeões, Leais, SP)

Prioridade de CX: O modelo identifica claramente que Atraso de Entrega é a principal reclamação (15,32%) e o sentimento NEGATIVO (45,9%) está em tendência de crescimento, confirmando a necessidade de otimizar a logística para manter a satisfação do cliente.
