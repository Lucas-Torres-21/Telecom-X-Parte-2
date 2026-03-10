# Telecom-X-Parte-2
Desafio Alura: Telecom X Parte 2

# 📊 Previsão de Evasão de Clientes (Churn Prediction) - Telecom X Parte 2

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)

## 📌 Visão Geral do Projeto
Este projeto tem como objetivo desenvolver modelos preditivos para identificar clientes com alta propensão a cancelar os serviços (Churn) da Telecom X. Através da construção de um pipeline de Machine Learning, analisamos os padrões de comportamento e consumo para propor estratégias de retenção baseadas em dados e projetar o impacto financeiro (ROI) das ações.

## 🛠️ Tecnologias e Técnicas Utilizadas
* **Linguagem:** Python
* **Bibliotecas:** Pandas, Scikit-Learn, Imbalanced-learn (SMOTE), Seaborn, Matplotlib
* **Modelos:** Regressão Logística e Random Forest Classifier
* **Pré-processamento:** One-Hot Encoding, StandardScaler e Balanceamento de Classes (SMOTE)

## 📈 Desempenho dos Modelos e Escolha Técnica
Em problemas de evasão, a métrica de **Recall (Sensibilidade)** é prioritária, pois o custo de não identificar um cliente que vai cancelar (Falso Negativo) é muito maior do que o custo de oferecer um incentivo a um cliente que ficaria (Falso Positivo).

Testamos diferentes abordagens, garantindo o balanceamento da classe minoritária (Churn) nos dados de treino:

| Modelo | Pré-processamento | Recall (Sensibilidade) | Status |
| :--- | :--- | :---: | :--- |
| **Regressão Logística** | SMOTE + StandardScaler | **78%** | 🏆 **Modelo Escolhido** |
| **Random Forest** | SMOTE | 65% | Descartado (Menor Recall) |

> **Nota Técnica:** A Regressão Logística foi escolhida para a estratégia de negócio por apresentar uma excelente sensibilidade, sendo capaz de identificar corretamente **435 potenciais evasões** no conjunto de teste.

## 🔍 Insights de Negócio (Feature Importance)
A análise exploratória e a importância das variáveis revelaram três gatilhos principais de evasão:

1. **Tenure (Tempo de Casa):** O risco de abandono é crítico nos primeiros meses de contrato. A mediana de permanência de quem cancela é de aproximadamente 10 meses.
2. **Tipo de Contrato:** Clientes com contratos de renovação mensal (`Month-to-month`) são os mais propensos a sair devido à falta de barreiras de saída.
3. **Serviço de Internet:** Usuários de Fibra Óptica apresentam uma correlação positiva com o Churn, indicando possíveis problemas técnicos ou insatisfação com o custo-benefício.

## 💡 Estratégias de Retenção Propostas
Com base na análise de dados, propomos o seguinte plano de ação:
* **Onboarding VIP:** Concentrar o atendimento proativo e suporte técnico nos primeiros 6 meses de assinatura.
* **Conversão de Fidelidade:** Campanhas de descontos progressivos para migrar clientes do plano mensal para contratos de 1 ou 2 anos.
* **Auditoria de Fibra Óptica:** Investigação técnica e pesquisa de mercado para reavaliar a qualidade e o preço do serviço de fibra.

## 💰 Impacto Financeiro Estimado (ROI)
Com a alta capacidade de detecção do modelo (435 clientes em risco identificados no teste) e considerando um ticket médio estimado de R$ 65,00/mês:
* Se a equipe de retenção recuperar apenas **20%** destes clientes com as estratégias propostas (aprox. 87 clientes), a empresa preserva **R$ 5.655,00/mês**.
* O impacto anual projetado desta retenção ultrapassa **+R$ 67.800,00** em faturamento salvo.
