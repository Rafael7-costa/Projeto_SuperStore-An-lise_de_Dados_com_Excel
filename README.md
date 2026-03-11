# Projeto SuperStore - Análise de Dados com Excel
## Sobre o Projeto
Este projeto aplica técnicas avançadas de Excel — análise de cohort, segmentação RFM e análise de desempenho — para identificar os principais vetores de crescimento e risco da SuperStore, uma das maiores redes de e-commerce do país. O objetivo foi transformar dados históricos de vendas em recomendações acionáveis com impacto direto no faturamento e na retenção de clientes.

## Problema de Negócio
A SuperStore possui base de clientes ativa e histórico rico de transações, mas sem visibilidade sobre três riscos críticos: quais clientes estão abandonando a plataforma, quais segmentos concentram o maior valor e onde estão as regiões e produtos com maior potencial inexplorado. A ausência dessa visão compromete decisões de marketing, mix de produtos e expansão geográfica.

## Premissas da Análise
Foram analisados dados históricos de transações de vendas contemplando:

* Informações de clientes (Customer ID, dados de compra)
* Pedidos (Order ID, Order Date, Sales)
* Produtos e categorias
* Localizações das lojas

## Contexto
A SuperStore identificou três áreas críticas que impactam diretamente o crescimento da receita:

1. Retenção de Clientes: Monitorar padrões de recompra para entender fidelização real versus compras esporádicas
2. Segmentação de Clientes: Identificar quais grupos concentram valor e quais estão em risco de churn
3. Desempenho de Produtos e Localizações: Mapear concentração de receita e oportunidades de expansão geográfica

O time de gestão necessita de uma análise para responder às seguintes perguntas:
#### Perguntas de Negócio

1. Qual é a taxa real de retenção por cohort e quais períodos apresentam deterioração crítica?
2. Quem são os clientes de maior valor e quais estão em risco ativo de abandono?
3. Como está distribuída a base entre os segmentos RFM e qual o impacto financeiro de cada um?
4. Quais produtos concentram receita e quais representam risco de dependência?
5. Existe concentração geográfica perigosa e quais regiões têm maior potencial inexplorado?

## Estratégia da Solução
#### Passo 1: Preparação e importação dos dados (orders.csv, location.csv)
#### Passo 2: Análise de Cohort — identificação do mês de aquisição, construção da tabela de cohort e heatmap de retenção
#### Passo 3: Segmentação RFM — cálculo de Recência, Frequência e Monetização, atribuição de notas em quintis e classificação por segmento
#### Passo 4: Análise de Produtos e Localizações — ranking por receita, análise regional e identificação de oportunidades
#### Passo 5: Criação de visualizações e dashboard interativo
#### Passo 6: Relatório consolidado com recomendações de negócio

### Ferramentas Utilizadas
* Microsoft Excel: Tabelas Dinâmicas, Power Query, Formatação Condicional
* Fórmulas Avançadas: TEXTO, MÁXIMOSE, ÍNDICE, CORRESP, PROCV, MÍNIMOSES, CONT.VALORES, PERCENTIL, ARRED
* Visualizações: Heatmaps, Tree Maps, Gráficos de Barras, Pizza, Rosca

## Hipóteses Analisadas
#### 1. Análise de Cohort

* Qual é a taxa de retenção por mês de aquisição?
* Quais cohorts apresentam maior fidelização?
* Existem padrões sazonais na retenção?

#### 2. Segmentação RFM

* Qual a distribuição de clientes entre os segmentos?
* Quais segmentos geram maior receita?
* Como identificar clientes prioritários para ações de marketing?

#### 3. Desempenho de Produtos e Localizações

* Quais produtos lideram em faturamento?
* Quais produtos têm baixo desempenho?
* Qual a performance de cada região?
* Existe concentração de vendas em regiões específicas?

## Insights da Análise
#### 1. Análise de Cohort
A retenção da SuperStore opera abaixo do limiar de sustentabilidade: apenas 0–8% dos clientes retornam no mês seguinte à primeira compra, com picos isolados de até 26% em cohorts específicos. Esse padrão indica que a empresa ainda não converteu aquisição em recorrência — o modelo atual depende de novos clientes para sustentar receita, o que eleva continuamente o custo de crescimento.

**Cohorts de Melhor Performance:**
* **Setembro/2015**: 18% de retenção após 24 meses (maior longevidade)
* **Abril/2016**: Pico de 26% de retenção no 5º mês
* **Junho/2016**: Retenção consistente de 15-19% entre meses 15-17
* **Janeiro/2014**: 13% de retenção após 22-23 meses

**Cohorts de Pior Performance:**
* **Dezembro/2017**: 0% de retenção em todos os períodos subsequentes
* **Novembro/2017**: Apenas 7% no mês 1, seguido de abandono total
* **Período 2017**: Deterioração generalizada comparado a anos anteriores

![Análise 1](img/img1.png)

#### 2. Análise de Segmentação RFM
A base de clientes apresenta desequilíbrio estrutural: a pirâmide está invertida, com excesso de clientes em estágios intermediários e insuficiência nos extremos — tanto no topo (alto valor) quanto na entrada (novos clientes).

**Distribuição por Segmento:**

**Segmentos de Maior Valor:**
  * **Campeões (4%)**: Elite da base — compras frequentes, alto ticket e alta recência. O ideal de mercado é 10–15%; estar em 4% representa receita potencial não capturada
  * **Promissores (1%)**: Pipeline crítico para o crescimento do segmento Campeões — volume insuficiente compromete renovação da base de elite

**Segmentos Intermediários:**
  * **Fiéis Potencial (40%)**: Maior oportunidade de alavancagem financeira da análise. Converter mesmo 10% desse grupo em Fiéis geraria ganho expressivo de LTV sem incremento de custo de aquisição
  * **Fiéis (27%)**: Base estável e recorrente — necessitam estratégias de manutenção e upgrade para Campeões

**Segmentos em Risco(27% da base):**
  * Perdidos (10%), Risco (8%), Quase Dormentes (4%), Hibernando (2%), Precisam Atenção (2%), Não Perder (1%)
  * Para cada cliente Fiel, existe um cliente em processo ativo de saída — vazamento que corrói silenciosamente o faturamento

**Segmento de Crescimento:**
  * **Novos Clientes (2%)**: Novos Clientes representam apenas 2% da base (benchmark ideal: 5–10%) — pipeline de crescimento comprometido

![Análise 2](img/img2.png)

#### 3. Análise de Produtos
O portfólio apresenta concentração de risco extrema em SKUs individuais, com paradoxo claro entre volume e valor.

**Desempenho por Produto:**

**Concentração de Receita:**
  * **Produto Líder (TEC-CO-10004722)**: $61,599.82 em faturamento — mais que o dobro do segundo colocado
  * Dependência crítica de um único SKU: qualquer instabilidade nesse produto impacta diretamente o resultado

**Top 10 Produtos:**
  * **Technology**: 3 produtos (alto ticket médio)
  * **Office Supplies**: 5 produtos (volume equilibrado, ticket menor)
  * **Furniture**: 2 produtos (melhor equilíbrio entre ticket médio e volume — maior oportunidade de crescimento prioritário)

**Paradoxo Volume vs. Valor:**
  * **Produtos de maior faturamento ≠ Produtos de maior volume**
  * Alto faturamento = Baixo volume + Alto ticket (Technology)
  * Alto volume = Baixo ticket (Office Supplies)

**Produtos de Baixo Desempenho:**
  * 10 produtos venderam apenas 1-2 unidades no período analisado
  * **Recomendação**: Avaliar descontinuação ou liquidação
  * Potencial estoque parado representando custo de oportunidade

![Análise 3](img/img3.png)
![Análise 4](img/img4.png)

#### 4. Análise de Localizações
A distribuição geográfica concentra risco em mercados urbanos consolidados enquanto deixa regiões inteiras subexploradas.

**Desempenho por Cidade:**

**Concentração Urbana Crítica:**
  * **New York City**: $256,368 (25-30% do faturamento total)
  * 915 pedidos (12% do volume)
  * **RISCO MÁXIMO**: Dependência perigosa de uma única cidade
  * Qualquer instabilidade em NYC impacta significativamente o negócio

**Top 5 Cidades:**
  1. New York City: $256K | 915 pedidos **Maior volume**
  2. Los Angeles: $176K | 747 pedidos
  3. Seattle: $120K | 428 pedidos **Ticket médio ALTO**
  4. San Francisco: $113K | 510 pedidos
  5. Philadelphia: $109K | 537 pedidos **Ticket médio BAIXO**

**Insight Crítico - Ticket Médio por Cidade:**
  * Seattle fatura mais que Philadelphia com 109 pedidos a menos — indicativo de mix de produtos de maior valor (Technology).

![Análise 5](img/img5.png)

#### Análise Regional Profunda:
**West (Melhor Performance):**
  * Menos pedidos, mais faturamento
  * Clientes compram produtos de maior valor
  * Concentração de Technology e Furniture premium
  * Manter estratégia atual

**East (Alto Volume, Baixo Retorno):**
  * 37% dos pedidos, apenas 31% do faturamento
  * Predominância de Office Supplies (baixo ticket)
  * **Oportunidade**: Estratégias de upsell e cross-sell
  * Introduzir produtos Technology de entrada

**Central (Performance Equilibrada):**
  * Proporção balanceada volume/faturamento
  * Potencial de crescimento em todas as categorias
  * Replicar estratégias de sucesso de West e East

**South (Oceano Azul):**
  * **MENOR** faturamento (18%)
  * Região menos explorada
  * **MAIOR OPORTUNIDADE DE CRESCIMENTO**
  * Potencial de duplicar faturamento com estratégia focada

![Análise 6](img/img6.png)

## Resultado

A análise integrou cohort, RFM e desempenho de produtos e regiões para mapear os principais vetores de crescimento e risco da SuperStore, traduzindo dados históricos em decisões de negócio com impacto direto no faturamento.

**Retenção:** Menos de 10% dos clientes desenvolvem hábito de recompra, indicando que o modelo atual opera sobre demanda esporádica — não sobre uma base fidelizada. Cohorts adquiridos até 2016 sustentam retenção de até 26%, enquanto 2017 registra colapso próximo a 0%. Isso sinaliza uma ruptura na experiência pós-compra que, se corrigida, representa potencial de expansão significativa da receita recorrente sem necessidade de aumento de aquisição.

**Segmentação RFM:** A base de clientes apresenta desequilíbrio estrutural crítico: apenas 5% estão nos segmentos de maior valor (Campeões + Promissores), enquanto 27% já estão em processo ativo de saída. Converter 10% do segmento Fiéis Potencial (40% da base) em Fiéis representaria ganho expressivo de LTV sem incremento de custo de aquisição — o maior alavancador financeiro identificado na análise.

**Produtos e Regiões:** Um único SKU (TEC-CO-10004722) concentra o dobro da receita do segundo colocado, expondo o portfólio a risco operacional elevado. Geograficamente, New York City responde por até 30% do faturamento total, criando vulnerabilidade estrutural. Em contrapartida, a região South, com apenas 18% de participação, representa o maior potencial de crescimento orgânico — com estratégia focada, há espaço para duplicar receita regional sem canibalizar mercados já estabelecidos.

## Visualize a Análise Completa
**Você pode acessar a planilha completa e interativa através do link abaixo:**
(https://docs.google.com/spreadsheets/d/1sAUNAI6uL2pktMvUCrdM42YWWmtNn9QS/edit?usp=sharing&ouid=110374129430590839789&rtpof=true&sd=true)

## Próximos Passos

1. **Programa de progressão RFM:** Desenvolver régua de comunicação segmentada para migrar clientes de Fiéis Potencial → Fiéis → Campeões, priorizando os 40% da base com maior potencial de conversão
2. **Modelo preditivo de churn:** Construir modelo de propensão ao abandono com base nos padrões identificados nos cohorts de 2017, antecipando saídas antes que se tornem irreversíveis
3. **Estratégia de expansão South:** Desenhar plano de entrada na região com mix de produtos calibrado para replicar o ticket médio de West, a região de melhor performance relativa
4. **Diversificação de portfólio:** Reduzir dependência do SKU líder desenvolvendo produtos complementares em Technology e expandindo Furniture — categoria com melhor equilíbrio ticket/volume
5. **Dashboard de monitoramento contínuo:** Automatizar atualização das métricas RFM e cohort para permitir decisões em tempo real, eliminando o gap entre dado e ação
