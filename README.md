  #  Coffee Shop Sales Analytics
  <p align="center">
  <img src="https://github.com/user-attachments/assets/6feb7c62-bdb4-462e-b5c4-e2329fbe3f05" alt="Coffee Shop Logo" width="180" />
</p>

# Pipeline completo de Engenharia e Análise de Dados com MySQL e Power BI

---

## Sobre o Projeto

Este projeto foi desenvolvido como parte da minha jornada de aprendizado em **Engenharia de Dados e Business Intelligence (BI)**. A ideia surgiu de uma simples planilha de vendas — e evoluiu para um pipeline completo de dados corporativos, desde o CSV bruto até dashboards interativos no Power BI.

Ao longo do processo, percebi que engenharia de dados não é apenas sobre armazenar informações, mas sobre construir confiança nos dados e contar histórias com base neles.

## Objetivo

Construir uma base analítica robusta e escalável, aplicando boas práticas de:
- Modelagem em camadas (Staging → Clean → Analytics)
- Criação de modelo estrela (Kimball)
- Desenvolvimento de dashboards dinâmicos e intuitivos
- Geração de insights estratégicos de negócio
- 
  ## Créditos

- **Dataset Utilizado:** [Coffee Shop Sales – Kaggle](https://www.kaggle.com/datasets/ahmedabbas757/coffee-sales)    

##  Stack de Tecnologias

| Componente | Função |
|------------|--------|
| MySQL 8.0  | ETL, limpeza e modelagem dimensional |
| Power BI 2025 | Modelagem DAX e visualização interativa |
| Excel | Inspeção e verificação inicial dos dados |
| XAMPP / phpMyAdmin | Ambiente de desenvolvimento local |

## Estrutura do Projeto
  <p align="center">
  <img width="538" height="352" alt="image" src="https://github.com/user-attachments/assets/ca798388-5eef-4b86-9a27-d8379d3b68bf" alt="Estrutura do Projeto" width="320" />
</p>

## Arquitetura de Dados

### Fluxo de Dados Completo:
<img width="603" height="231" alt="image" src="https://github.com/user-attachments/assets/97683d63-4ecb-486c-b204-a708b400e489" />

> A arquitetura segue o modelo Kimball (esquema estrela) e boas práticas de separação entre camadas lógicas.

---

## Processo de ETL (Extract, Transform, Load)

1. **Extração** → Importação do CSV para o banco `coffee_shop_staging`.    
2. **Transformação** → Limpeza e padronização de campos no `coffee_shop_analytics`.  
3. **Carga** → Criação das tabelas dimensionais e fato.  

## Modelagem Analítica

### Estrutura Estrela
| Tipo | Tabela | Descrição |
|------|---------|-----------|
| **Fato** | fact_coffee_sales | Vendas, quantidades e preços |
| **Dimensão** | dim_products | Catálogo e categorias de produtos |
| **Dimensão** | dim_stores | Lojas e localizações |
| **Dimensão** | dim_time | Datas, meses e trimestres |

### Views Analíticas
- `v_vendas_completa` → base de dados principal  
- `v_kpis_mensais` → métricas e variação mês a mês  
- `v_top_produtos` → ranking dos produtos mais vendidos  

---

## Dashboard Power BI

### Estrutura de Abas
1. **Visão Geral** → KPIs e resumo executivo  
2. **Visão Temporal** → Análise mensal, semanal e sazonal  
3. **Visão Produtos** → Top 10 produtos, categorias e lucratividade  
4. **Visão Lojas** → Comparativo entre unidades  

### Principais Métricas DAX
- `Total Vendas = SUM([total_price])`
- `Total Pedidos = COUNT([transaction_id])`
- `Ticket Médio = DIVIDE([Total Vendas], [Total Pedidos])`
- `Variação Mensal (%) = ...`
- `Vendas Média por Dia = AVERAGEX(..., [Total Vendas])`

---

## Insights de Negócio

### Visão Geral
- **Receita total:** $809K  
- **Pedidos processados:** 149K  
- **Ticket médio:** $5,43  
- **Itens por pedido:** 1,66  

### Visão Temporal
- **Junho:** Melhor mês de vendas  
- **Segunda-feira:** Melhor dia da semana  
- **Fins de semana:** Apenas 28% do faturamento total → oportunidade de expansão  

### Visão de Produtos
- **Top 1:** *Barista Espresso* — $106K (13% da receita total)  
- **Top 3 produtos** = 34,5% da receita → risco de concentração  
- **Total:** 81 produtos em 10 categorias  

### Visão de Lojas
| Loja | Faturamento | Ticket Médio | Perfil |
|-------|-------------|--------------|---------|
| Hell’s Kitchen | $274K | $5,49 | Corporativo |
| Astoria | $269K | $5,38 | Comunitário |
| Lower Manhattan | $265K | $6,65 | Premium |

---

##  Lições Aprendidas

- Importância da arquitetura em camadas (Staging → Clean → Analytics).  
- Separar o que é ETL (SQL) do que é análise (DAX).  
- Melhorar performance no Power BI usando views SQL.  
- Documentar cada etapa e versionar scripts.  

---

##  Estrutura do Projeto para Portfólio

| Camada | Banco / Arquivo | Finalidade |
|--------|-----------------|-------------|
| Staging | `coffee_shop_staging.raw_coffee_sales` | Dados brutos |
| Clean | `coffee_shop_analytics.clean_coffee_sales` | Dados tratados |
| Analytics | `fact_coffee_sales`, `dims` e `views` | Base analítica |
| Visualization | Power BI (`.pbix`) | Dashboard interativo |

---

## Insight Final

> “O Barista Espresso sozinho gera mais receita que os 20 produtos menos vendidos juntos —  
> uma demonstração do poder dos produtos âncora, mas também um alerta sobre a importância da diversificação.”

---

### ⭐ Se este projeto te ajudou, deixe uma estrela no repositório!





