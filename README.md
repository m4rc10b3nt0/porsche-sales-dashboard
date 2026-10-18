# 🏎️ Porsche Sales Performance Dashboard

> **Projeto prático do Curso "Criando Agentes de Tratamento de Dados" — DIO (Digital Innovation One)**
> **Expert:** Felipe Aguiar (Felipão)

---

## 📌 Links do Projeto

* 🌐 **Dashboard Publicada (GitHub Pages):** `https://m4rc10b3nt0.github.io/porsche-sales-dashboard/`
* 📁 **Repositório do Código:** `https://github.com/m4rc10b3nt0/porsche-sales-dashboard`

---

## 📊 Perguntas de Negócio Escolhidas

Para garantir uma análise relevante e estratégica para a gestão de vendas da Porsche, foram definidas três perguntas principais:

### 1. Quais modelos de Porsche geram a maior receita total e volume de vendas?
* **Por que perguntar:** Identifica os modelos "carro-chefe" que sustentam o volume de vendas versus os modelos de edição limitada e alta margem de lucro (ex: 911 GT3, 911 Turbo S), auxiliando no planejamento de estoque e marketing.
* **Visualização:** Gráfico de Barras com ordenação dos modelos por faturamento bruto.

### 2. Qual é a distribuição e preferência dos Métodos de Pagamento?
* **Por que perguntar:** Permite ao setor financeiro entender o perfil de pagamento dos clientes de alto padrão (ex: Transferência Bancária, Cartão, Financiamento, Criptomoedas), permitindo negociar melhores taxas de intermediação bancária.
* **Visualização:** Gráfico de Rosca (Doughnut) com percentual de participação de cada método.

### 3. Qual é a eficiência logístico-operacional e o status das entregas?
* **Por que perguntar:** Acompanha o funil pós-venda para detectar gargalos operacionais e evitar cancelamentos, garantindo a satisfação do cliente VIP.
* **Visualização:** Gráfico de Barras Horizontais por status (*Delivered, In Transit, Pending, Cancelled*).

---

## 🧹 Tratamento e Sanitização dos Dados

A planilha original possuía variações nos nomes de modelos, símbolos de moeda, datas inválidas e formatações de números por extenso. Antes da construção da dashboard, a base passou pelos seguintes tratamentos:

1. **Remoção de Fórmulas e Colunas Brutas:** Mantidas apenas as colunas com sufixo `Sanitized`.
2. **Conversão do Preço (`SalesPriceSanitized`):** Remoção de caracteres de moeda (\$, USD, dollars) e conversão para formato decimal puro (*float*).
3. **Padronização de Modelos (`PorscheModelSanitized`):** Unificação de nomenclaturas (ex: *718 Cayman, 911 Turbo S, Taycan 4S*).
4. **Padronização de Pagamentos e Estados:** Siglas em caixa alta (*CA, TX, FL*) e categorias financeiras padronizadas.

---

## 🤖 Ferramentas Utilizadas

* **Tratamento de Dados:** Python (`pandas`) e Agente de Sanitização de Dados.
* **Geração e Refinamento do Código:** Gemini / ChatGPT (Canvas) com prompts de desenvolvimento Frontend.
* **Tecnologias Frontend:** HTML5, Tailwind CSS (CDN), Chart.js (CDN) e FontAwesome.
* **Hospedagem:** GitHub Pages.

---

## 📝 Prompt Utilizado

```text
Atue como um Engenheiro de Dados e Desenvolvedor Frontend Sênior. 
Tenho uma planilha sanitizada com 100 vendas da Porsche contendo as colunas: 
PorscheModelSanitized, ModelYearSanitized, SalesPriceSanitized, PayMethodSanitized, CitySanitized, StateSanitized e DeliveryStatusSanitized.

Crie uma dashboard interativa web em um arquivo ÚNICO de HTML ('index.html') que responda a 3 perguntas de negócio estratégicas.
