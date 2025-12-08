🧭 GUIA COMPLETO DE TRANSFORMAÇÕES – POWER QUERY (Olist BI)

Documento oficial de documentação das etapas de Power Query utilizadas no projeto.

📌 Objetivo

Este guia descreve cada etapa de transformação realizada em todas as tabelas usadas no projeto Olist.
Inclui:

Origem dos dados
Tratamentos aplicados
Conversões de tipos
Renomeação de colunas
Limpeza
Filtragem

Observações importantes para manutenção

📂 Sumário

Clientes – olist_customers_dataset
Geolocalização – olist_geolocation_dataset
Itens do Pedido – olist_order_items_dataset
Pagamentos – olist_order_payments_dataset
Avaliações – olist_order_reviews_dataset
Pedidos – olist_orders_dataset
Produtos – olist_products_dataset
Vendedores – olist_sellers_dataset
Top 75 Palavras – top_75_palavras.xlsx
Base com Sentimento – analises_bi_completas.xlsx
Confiança por Método – analises_bi_completas.xlsx
Top 10 Reclamações – analises_bi_completas.xlsx
Top 20 Geral – analises_bi_completas.xlsx

🟦 Clientes – olist_customers_dataset

Transformações aplicadas:

Etapa	Descrição

Leitura do CSV	Importa arquivo com delimitador “,” e 5 colunas.
Promover Cabeçalhos	Converte primeira linha em cabeçalho.
Alteração de Tipo	Define tipos adequados para cada coluna (texto e inteiro).
Renomeação de Colunas	Padroniza nomes para português e formato BI.

Código Utilizado

Fonte = Csv.Document(File.Contents("...olist_customers_dataset.csv"),[Delimiter=",", Columns=5, Encoding=1252]),
Cabeçalhos Promovidos = Table.PromoteHeaders(Fonte),
Tipo Alterado = Table.TransformColumnTypes(...),
Colunas Renomeadas = Table.RenameColumns(...)

Por que foi feito?

Padronizar nomes internos
Evitar erros de tipo (ZIP como número, datas como texto etc.)
Facilitar relacionamentos no modelo

🟦 Geolocalização – olist_geolocation_dataset

Transformações?

Importação CSV UTF-8
Conversão de tipos (lat/lng como inteiro — igual arquivo original)
Nenhuma renomeação adicional (mantém padrão de referência Olist)

🟦 Itens do Pedido – olist_order_items_dataset
Principais transformações

Conversão de tipos (Preço e Frete como Int64)

Renomeações importantes:

order_id → Pedido_ID
order_item_id → Qtd.
product_id → Produto_ID
seller_id → Vendedor_ID
shipping_limit_date → Data_Limite_envio

🟦 Pagamentos – olist_order_payments_dataset
Transformações

Conversões de tipo

Renomeação:

payment_value → Valor_pgto

payment_type → forma_pgto

Facilita análises de formas de pagamento e parcelamento

🟦 Avaliações – olist_order_reviews_dataset
Transformações Aplicadas
Coluna	Ajuste
Datas	Convertidas para datetime
Nomes	Renomeados para português
Comentários	Mantidos como texto

Destaques:

review_comment_message → Msg_comentário
review_score → Nota

Datas foram convertidas novamente para garantir consistência.

🟦 Pedidos – olist_orders_dataset
Transformações

Importação do CSV (8 colunas)

Conversões corretas para datas

Renomeações:

order_id → Pedido_ID
order_status → Status_Pedido
order_purchase_timestamp → Data_compra

Conversão adicional para type date em:

Data_compra
data_envio

🟦 Produtos – olist_products_dataset
Transformações Importantes

Conversões de tipos inteiros

Renomeações para facilitar entendimento:

product_category_name → Categoria
product_photos_qty → qtd_fotos_produto
product_height_cm → altura_cm

🟦 Vendedores – olist_sellers_dataset
Transformações

Conversão de tipos

Renomeações:

seller_id → Vendedor_ID
seller_city → Cidade

🟩 Top 75 Palavras – top_75_palavras.xlsx

Transformações:

Importação Excel
Conversões
Remoção das últimas 50 linhas → limpeza para manter apenas top palavras relevantes

🟩 Base com Sentimento – analises_bi_completas.xlsx

Transformações?

Tipagem de colunas (numéricas, texto e inteiro)
Remoção de comentários vazios ("" ou null)

Fonte para dashboards de:
Sentimento Geral
Wordcloud
Reclamações categorizadas
NPS por sentimento

🟩 Confiança por Método

Apenas tipos ajustados (número, inteiro, texto)
Utilizado para análise de acurácia dos métodos NLP aplicados

🟩 Top 10 Reclamações

Tipos ajustados

Mantém percentual e quantidade
Usado para telas de reclamações no dashboard

🟩 Top 20 Geral de Comentários

Leitura da aba

Conversão:

Confianca convertido para Percentual
Base para insights qualitativos
