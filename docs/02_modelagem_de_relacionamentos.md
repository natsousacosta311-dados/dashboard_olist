# 02. Modelagem de Relacionamentos do Power BI

Este documento detalha a arquitetura do modelo de dados do dashboard, incluindo as **cardinalidades**, **direção de filtro** e **status de ativação** de cada relacionamento.

A modelagem segue, em essência, um **Star Schema (Modelo Estrela)**, utilizando:

- **olist_pedidos_dataset**  
- **olist_produtos_pedidos_dataset**

como tabelas **Fato** centrais.

---

## 🖼️ Diagrama de Relacionamentos

A imagem abaixo apresenta a visão completa do schema do modelo, exportada diretamente do Power BI.

> <img width="1177" height="560" alt="Relacionamentos" src="https://github.com/user-attachments/assets/36a7f0eb-f586-4461-ad4b-418c9427ba1b" />

> `docs/modelagem_relacionamentos.png`

---

## 🔗 Relacionamentos Detalhados

---

# A. Core Facts e Dimensões Principais

Estes são os relacionamentos que conectam as tabelas de transação (**Fato**) com as dimensões (**Lookup**) de Cliente, Produto e Vendedor.

| Tabela de Origem                  | Coluna de Origem     | Tabela de Destino         | Coluna de Destino  | Cardinalidade   | Direção | Status |
|----------------------------------|------------------------|-----------------------------|----------------------|------------------|---------|--------|
| olist_pedidos_dataset            | Cliente_ID            | olist_clientes_dataset      | Cliente_ID          | Um → Um          | Ambas   | Ativo  |
| olist_produtos_pedidos_dataset   | Produto_ID            | olist_produtos_dataset      | ID_Produto          | Muitos → Um      | Única   | Ativo  |
| olist_produtos_pedidos_dataset   | Vendedor_ID           | olist_vendedores_dataset    | Vendedor_ID         | Muitos → Um      | Única   | Ativo  |

---

# B. Relacionamentos entre Tabelas Fato

Relacionamentos que cruzam tabelas de transação ou auxiliares, normalmente no lado **Muitos** do modelo.

| Tabela de Origem                  | Coluna de Origem | Tabela de Destino         | Coluna de Destino | Cardinalidade   | Direção | Status |
|----------------------------------|-------------------|-----------------------------|---------------------|------------------|---------|--------|
| olist_produtos_pedidos_dataset   | Pedido_ID         | olist_pedidos_dataset       | Pedido_ID           | Muitos → Muitos  | Ambas   | Ativo  |
| olist_pagamentos_dataset         | ID_Pedido         | olist_pedidos_dataset       | Pedido_ID           | Muitos → Muitos  | Única   | Ativo  |
| olist_avaliações_dataset         | ID_Pedido         | olist_pedidos_dataset       | Pedido_ID           | Muitos → Um      | Única   | Ativo  |
| Base_com_Sentimento              | ID_Pedido         | olist_pedidos_dataset       | Pedido_ID           | Muitos → Um      | Única   | Ativo  |
| olist_clientes_dataset           | Cliente_ID        | Tabela RFV Clientes         | Cliente_ID          | Um → Um          | Ambas   | Ativo  |

---

# C. Relacionamentos de Data (dCalendario)

O modelo utiliza a tabela **dCalendario** para análises temporais.  
Diversos relacionamentos ficam **Inativos**, permitindo ativação via `USERELATIONSHIP` quando necessário.

| Tabela de Origem              | Coluna de Origem     | Tabela de Destino | Chave de Destino | Direção | Status  |
|-------------------------------|------------------------|--------------------|--------------------|---------|---------|
| olist_pedidos_dataset         | Data_compra           | dCalendario        | Data               | Única   | Ativo   |
| olist_pedidos_dataset         | data_envio            | dCalendario        | Data               | Única   | Inativo |
| olist_avaliações_dataset      | Data_criação          | dCalendario        | Data               | Única   | Inativo |
| (Diversas tabelas)            | (Diversas colunas)    | LocalDateTable...  | Date               | Única   | Ativo   |

---

# D. Relacionamentos Auxiliares e Análise de Sentimento

Relacionamentos usados para análises específicas, como sentimento e classificação.

| Tabela de Origem               | Coluna de Origem       | Tabela de Destino        | Coluna de Destino      | Cardinalidade   | Direção | Status |
|--------------------------------|--------------------------|----------------------------|--------------------------|------------------|---------|--------|
| olist_avaliações_dataset       | ID_avaliaçao            | Base_com_Sentimento        | ID_avaliaçao            | Muitos → Muitos  | Ambas   | Ativo  |
| Exemplos_Problemas             | Tipo_Problema           | Top_10_Reclamacoes         | Tipo_Problema           | Muitos → Um      | Única   | Ativo  |
| Base_com_Sentimento            | Metodo_Classificacao    | Confianca_por_Metodo       | Metodo_Classificacao    | Muitos → Um      | Única   | Ativo  |
| Sentimento_por_Confianca       | Faixa_Confianca         | Distribuicao_Confianca     | Faixa_Confianca         | Um → Um          | Ambas   | Ativo  |

---

# ⚠️ Observações de Modelagem

### **1. Many-to-Many (Muitos para Muitos)**
Relações como:

- `olist_produtos_pedidos_dataset` → `olist_pedidos_dataset`
- `olist_pagamentos_dataset` → `olist_pedidos_dataset`

foram criadas como **M2M** devido à natureza dos dados:

- um pedido tem vários itens  
- um pedido pode ter vários pagamentos  

### **2. Direção Bidirecional**
Utilizada em:

- Many-to-Many  
- Cliente ↔ Pedido  

Facilita a navegação de filtros, mas deve ser usada com cautela para evitar *filter loops*.

### **3. Relações Inativas**
As relações com o **dCalendario** ficam inativas para permitir:

- Data de compra como padrão  
- Outras datas ativadas via `USERELATIONSHIP()`  
