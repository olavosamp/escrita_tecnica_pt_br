# Exemplo 1:
- Original:
# asset Recommendation: Debug de Variáveis Impactadas

Debug notebook para o cálculo das **variáveis impactadas** de
`ATIVORecommendationSingle.predict()`
, passo a passo, para uma ATIVO e um timestamp
específicos.

**Objetivo**: dado um timestamp em que uma workpack ou experimento de recomendação foi
gerada/o (`plant_workpack_gtg_turnoff.ipynb`) e o nome do modelo de recomendação
vencedor daquele desempate (ex.: `plant_ATIVO_Recommendation_OFF_3`), recalcular
os valores `_after` de cada ATIVO remanescente (ATIVO que fica on no cenário), facilitando o entendimento dos cálculos.

Este notebook **não** reextrai dados nem refita nada — busca as predições e o
`ATIVORecommendationSingle` já fitted diretamente do modelo **já publicado**, via
`DebugPredict`, para a janela de tempo  de interesse.

**Como usar**
1. `recommendation_model_name` — o cenário vencedor daquele instante (ex.:
   `"plant_ATIVO_Recommendation_OFF_3"`, se o cenário vencedor foi "desligar C").
2. `target_time` — o timestamp da workpack a explicar (ex.: o `end_datetime`
   usado em `plant_workpack_gtg_turnoff.ipynb` para gerar aquela recomendação).
3. `gtg_of_interest` — qual das ATIVOs remanescentes (ON) detalhar passo a passo
   nos gráficos/tabelas. 

- Reescrito:

# ATIVO Recommendation: Debug de Variáveis Impactadas

Notebook de debug para o cálculo das variáveis impactadas do modelo
`ATIVORecommendationSingle`. Cobre o pipeline, passo a passo, para uma ATIVO e um timestamp específico.

**Objetivo**: Recalcular os valores das variáveis calculadas (com sufixo `_after`) de cada ATIVO ON no cenário, de modo a facilitar o entendimento dos cálculos para validação. O notebook usa como entrada um timestamp de uma recomendação (por exemplo, em `plant_workpack_gtg_turnoff.ipynb`) e o nome de um modelo de recomendação (ex.: `plant_ATIVO_Recommendation_OFF_3`).

Este notebook **não** reextrai dados nem refita nada. Ele apenas busca, via `DebugPredict`, as predições e o modelo 
`ATIVORecommendationSingle` já treinado e publicado para a janela de tempo de interesse.

**Como usar**
Definir os seguintes parâmetros:
1. `target_time`: o timestamp da recomendação a detalhar (ex.: o `end_datetime` usado em `plant_workpack_gtg_turnoff.ipynb` para gerar a recomendação).

2. `recommendation_model_name`: o nome do modelo associado ao cenário vencedor da recomendação (ex.:
   `"plant_ATIVO_Recommendation_OFF_3"`, se o cenário vencedor foi "desligar C").

3. `gtg_of_interest`: o nome do ativo associado ao modelo vencedor (`recommendation_model_name`), para o qual se deseja detalhar os cálculos. (ex: "ATIVO-0321B")
