# Projeto-Aplicado-IV
Esse repositório refere-se ao trabalho criado para a disciplina de Projeto Aplicado IV da UMP
Previsão de Casos de Dengue no Brasil por Meio de Séries Temporais
Este projeto de Ciência de Dados propõe o desenvolvimento de um modelo analítico preditivo para estimar o número de casos de dengue no Brasil, utilizando técnicas avançadas de análise de séries temporais. O trabalho visa fornecer informações úteis para órgãos públicos de saúde e gestores municipais, auxiliando no planejamento de ações preventivas e no enfrentamento de surtos.


🎯 Objetivo
Desenvolver um produto analítico que preveja o número de casos de dengue no Brasil, utilizando técnicas de séries temporais, a fim de apoiar gestores públicos e instituições de saúde.

Objetivos Específicos
Coletar e organizar dados históricos de casos de dengue a partir da base pública InfoDengue.


Analisar e identificar padrões de tendência e sazonalidade nas séries temporais.

Aplicar e comparar modelos de previsão (Prophet e XGBoost) e avaliar seu desempenho.


Desenvolver visualizações e relatórios que subsidiem a tomada de decisão em saúde pública.


⚙️ Metodologia e Pipeline da Solução
O projeto segue um pipeline estruturado, desde a ingestão dos dados até a geração do forecast final.

1. Fonte de Dados
A base de dados é proveniente do InfoDengue, uma iniciativa da Fundação Oswaldo Cruz (Fiocruz) em parceria com o Ministério da Saúde. Para o estudo, foram selecionadas as capitais de São Paulo, Curitiba, Manaus, Goiânia e Salvador para compor uma série temporal "mini-nacional" agregada.




2. Pré-processamento e Engenharia de Features
Os dados brutos em formato CSV foram limpos, padronizados e agregados em uma série temporal de frequência semanal.



Agregação: Soma dos casos e média das variáveis climáticas das cinco capitais selecionadas.


Feature Engineering: Criação de variáveis temporais (mês, semana do ano) e componentes autorregressivos (lags de casos anteriores) e estatísticos (média móvel) para capturar a autocorrelação temporal.




Divisão Temporal: O conjunto de dados foi dividido cronologicamente em treino e teste (corte em 2024-01-01) para evitar data leakage.


3. Modelagem e Comparação
Dois modelos base foram implementados e comparados:

Modelo	Abordagem	Vantagem
Prophet	Estatístico (Aditivo)	
Ideal para séries com forte sazonalidade.


XGBoost	Aprendizado de Máquina (Regressão Supervisionada)	
Capaz de capturar relações não lineares complexas e incorporar múltiplas features (lags, variáveis climáticas).



Exportar para as Planilhas

O desempenho foi avaliado pelas métricas Mean Absolute Error (MAE) e Root Mean Squared Error (RMSE).


4. Seleção e Refinamento
O modelo com melhor desempenho foi submetido à otimização de hiperparâmetros (GridSearchCV com TimeSeriesSplit) e retreinado com a totalidade dos dados históricos para gerar a previsão final.


📊 Resultados Principais
O modelo XGBoost demonstrou um desempenho superior ao Prophet, validando sua escolha para o forecast final.




Modelo	MAE (Mean Absolute Error)	RMSE (Root Mean Squared Error)
Prophet	
1.152,38 



2.022,78 


XGBoost	

454,40 


866,13 



Exportar para as Planilhas

O XGBoost reduziu o erro em aproximadamente 60% (MAE) e 57% (RMSE) em relação ao Prophet, mostrando maior acurácia na previsão da magnitude dos picos, como o surto de 2024.



A feature mais importante para o modelo foi o cases_lag_1 (casos da semana imediatamente anterior), reforçando a forte autocorrelação temporal típica de processos epidemiológicos.


📈 Previsão Final
O modelo XGBoost, retreinado com todos os dados, gerou uma previsão (forecast) de 12 semanas futuras, utilizando uma estratégia recursiva. A projeção indica a manutenção de baixa incidência para o curto prazo, seguindo a tendência de declínio observada ao final da série histórica.




🔗 Acesso e Reprodução
Você pode acessar e interagir com o projeto completo por meio dos seguintes links:

Recurso	Descrição	Link
Notebook do Google Colab	
Permite a execução interativa das análises e modelos.


Notebook Colab 

Vídeo de Apresentação	
Visão geral audiovisual das etapas, metodologia e resultados.


YouTube 

Artigo / Relatório	Documento completo do projeto (este arquivo no repositório).	A4 PROJ APLIC IV.pdf (ou similar)
🧑‍💻 Equipe
ANTÔNIO CARLOS DOMANSKI DA SILVA - 10424144 

BRUNA ALMEIDA DA SILVA - 10263278 

LAURA ELOISE FERREIRA - 10424754 


Professor: GUSTAVO SCALABRINI SAMPAIO  Instituição: UNIVERSIDADE PRESBITERIANA MACKENZIE | CIÊNCIA DE DADOS 


Licença
Este projeto é desenvolvido para fins acadêmicos.

Gostaria de adicionar alguma seção extra, como os requisitos de bibliotecas (Dependencies), ou refinar alguma descrição?
