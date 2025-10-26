# Estudo de Caso: Análise de Vendas de Bicicletas

Este repositório contém um projeto de análise e visualização de dados focado em um conjunto de dados de vendas de uma loja de bicicletas. O projeto foi desenvolvido como atividade prática para a disciplina de Visualização de Dados, cobrindo o ciclo completo de análise: desde a limpeza dos dados até a geração de insights e relatórios visuais.

## 🎯 Objetivo da Análise

O objetivo principal é avaliar os padrões de preços, preferências de modelos e cores mais vendidas, identificar a sazonalidade das vendas e encontrar possíveis oportunidades para otimização de preços e estoque.

## 🛠️ Ferramentas Utilizadas

A análise foi conduzida inteiramente em Python, utilizando as seguintes bibliotecas:

* **Pandas:** Para manipulação, limpeza e transformação dos dados.
* **NumPy:** Para cálculos estatísticos e manipulação de arrays.
* **Matplotlib:** Para a criação das visualizações estáticas.

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3175a2?style=for-the-badge&logo=matplotlib&logoColor=white)

---

## 📈 O Processo de Análise

A análise seguiu um fluxo de trabalho padrão, dividido em três etapas principais:

### 1. Carga e Limpeza dos Dados (ETL)

Os dados brutos (`VendasBicicletas.csv`) apresentavam inconsistências que precisavam de tratamento antes da análise:

* **Valores Ausentes:** Havia registros de vendas com a `Data da Venda` faltando. Estes foram preenchidos com datas (23/04/2025 e 09/05/2025) para manter a consistência do conjunto de dados.
* **Erros de Digitação:** Na coluna `Cor`, foram identificados e padronizados os valores "Azula" (para "Azul") e "Cinzos" (para "Cinza").
* **Tipagem de Dados:** A coluna `Data da Venda` foi convertida de `object` (string) para `datetime64[ns]`, permitindo análises temporais.
* **Duplicatas:** Foi realizada uma verificação para garantir que não havia IDs de venda ou linhas duplicadas.

### 2. Análise Exploratória (EDA)

Com os dados limpos, foram extraídas as seguintes estatísticas e contagens:

**Estatísticas de Preço:**
* **Preço Médio:** R$ 2.589,75
* **Preço Mediano:** R$ 2.585,00
* **Preço Máximo:** R$ 3.299,00
* **Preço Mínimo:** R$ 1.890,00

**Contagem de Vendas por Modelo:**
| Modelo | Quantidade Vendida |
| :--- | :--- |
| Speedster 300 | 5 |
| Mountain Pro | 5 |
| Urban Lite | 5 |
| Adventure XT | 5 |

**Contagem de Vendas por Cor (Pós-Limpeza):**
| Cor | Quantidade Vendida |
| :--- | :--- |
| Azul | 4 |
| Branco | 4 |
| Preto | 3 |
| Vermelho | 3 |
| Verde | 3 |
| Cinza | 3 |

### 3. Visualização de Dados

Para comunicar os resultados, foram criados dois gráficos principais para responder às perguntas de negócio.

**Gráfico 1: Número de Vendas Mensais**
*Este gráfico de linhas mostra a sazonalidade das vendas, destacando um pico claro no mês de abril.*

<img src="Número de Vendas Mensais.png" alt="Número de Vendas Mensais">

**Gráfico 2: Preço Médio por Modelo de Bicicleta**
*Este gráfico de barras compara o preço médio de cada modelo, facilitando a identificação dos produtos de maior e menor valor agregado.*

<img src="Preço Médio por Modelo.png" alt="Preço Médio por Modelo">

---

## 💡 Principais Descobertas (Insights)

A partir da análise, foi possível concluir:

1.  **Sazonalidade:** Há um pico claro de vendas no mês de **Abril**, que registrou 7 vendas (35% do total). O período de Fevereiro e Março apresentou vendas mais baixas.
2.  **Demanda de Modelos:** A demanda é perfeitamente balanceada, com todos os quatro modelos registrando exatamente **5 vendas cada**.
3.  **Ticket Médio por Modelo:** O modelo **"Mountain Pro" (R$ 3.299,00)** é o de maior valor, enquanto o **"Urban Lite" (R$ 1.890,00)** é o modelo de entrada. Não há variação de preço dentro de um mesmo modelo, sugerindo preços fixos.
4.  **Preferência de Cor:** As cores **Azul e Branco** (4 vendas cada) são ligeiramente mais populares que as demais (3 vendas cada).
