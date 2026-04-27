# 📊 Dashboard com Parâmetros de Campo — Power BI

## 📌 Descrição do Projeto

Este projeto é uma evolução do dashboard **Detalhes de Vendas**, desenvolvido como desafio do módulo de **Parâmetros de Campo** em um curso/bootcamp de Power BI.

O objetivo foi criar visuais dinâmicos utilizando **parâmetros de campo**, permitindo que o usuário escolha quais dimensões e métricas deseja visualizar — sem precisar editar o relatório.

---

## 🎯 Objetivo do Desafio

> Criar pelo menos **dois visuais com parâmetros de campo**, mantendo a estilização do relatório anterior.

| Visão | Tipo de Parâmetro | Descrição |
|---|---|---|
| **Visão 1** | Parâmetro por **Categoria** | O usuário escolhe a dimensão do eixo (ex: Produto, Segmento, País) |
| **Visão 2** | Parâmetro por **Valor** | O usuário escolhe a métrica exibida (ex: Profit, Sales, Units Sold) |

---

## 🛠️ Como Criar os Parâmetros

### Parâmetro 1 — Por Categoria (Dimensão)

1. Vá em **Modelagem → Novo parâmetro → Campos**
2. Nomeie como `Parâmetro Categoria`
3. Adicione os campos desejados:
   - `Product`
   - `Segment`
   - `Country`
4. Marque **"Adicionar segmentação a esta página"**
5. Clique em **Criar**

> O Power BI cria automaticamente uma tabela e uma medida para o parâmetro.

---

### Parâmetro 2 — Por Valor (Métrica)

1. Vá em **Modelagem → Novo parâmetro → Campos**
2. Nomeie como `Parâmetro Valor`
3. Adicione as medidas desejadas:
   - `Sales 2013`
   - `Sales 2014`
   - `Total Vendas`
   - `SUM(Financials[Profit])`
   - `SUM(Financials[Units Sold])`
4. Marque **"Adicionar segmentação a esta página"**
5. Clique em **Criar**

---

## 📊 Montando os Visuais

### Visual 1 — Gráfico por Categoria Dinâmica

1. Insira um **Gráfico de barras clusterizado**
2. Arraste os campos:

| Campo do gráfico | O que arrastar |
|---|---|
| **Eixo Y** | `Parâmetro Categoria` (campo gerado) |
| **Valores X** | `Total Vendas` |

3. A segmentação ao lado permite ao usuário trocar entre Produto, Segmento e País em tempo real ✅

---

### Visual 2 — Gráfico por Valor Dinâmico

1. Insira um **Gráfico de colunas agrupadas**
2. Arraste os campos:

| Campo do gráfico | O que arrastar |
|---|---|
| **Eixo X** | `Semestre` ou `Trimestre` |
| **Valores Y** | `Parâmetro Valor` (campo gerado) |

3. A segmentação permite ao usuário escolher entre Sales, Profit, Units Sold etc. ✅

---

## 🎨 Estilização

Manter o mesmo padrão visual do relatório anterior:

- Fundo da página: roxo escuro `#4A1472`
- Fundo dos visuais: transparente
- Títulos: branco, negrito
- Cores das barras: azul claro e amarelo dourado
- Segmentações: estilo **pílula/botão**, fundo escuro, texto branco

---

## 📐 Medidas DAX Utilizadas

```DAX
-- Vendas 2013
Sales 2013 = CALCULATE(SUM(Financials[Sales]), Financials[Year] = 2013)

-- Vendas 2014
Sales 2014 = CALCULATE(SUM(Financials[Sales]), Financials[Year] = 2014)

-- Total de Vendas
Total Vendas = SUM(Financials[Sales])
```

---



## 🛠️ Tecnologias Utilizadas

- [Power BI Desktop](https://powerbi.microsoft.com/)
- Linguagem **DAX** para medidas calculadas
- **Parâmetros de Campo** (Field Parameters)


> *Projeto desenvolvido para fins educacionais.*
