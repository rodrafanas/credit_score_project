# loan-bank-model-project

## Projeto: Concessão de Crédito por meio de um modelo de machine learning.

Teremos 6 passos na metodoligia Crisp-DM

00-BUSINESS_UNDERSTANDING
Nesta etapa iremos analisar os objetivos do negócio para utilizar e qual o status sem o modelo de ML. Ou seja, responder a questão: do que o negócio precisa?

01-DATA_UNDERSTANDING
Consiste em conhecer mais afundo os dados, selecionar algumas variáveis explicativas interessantes e definir a variável resposta, conhecido como target. Como resultado teremos um dataframe com as variáveis explicativas selecionadas e um arquivo de metadados que resume algumas caracteristicas das variaveis selecionadas para orientar o processo de preparação dos dados.

02-DATA-PREPARATION
Com o objetivo de fazer a validação cruzada no modelo nesta etapa separamos os dados em 3 datasets: treino, validação e teste. A partir do tratamento das variaveis numericas e categoricas do dataset de treino faremos os tratamentos das variáveis explicativas nos dataset de validação e treino. Teremos como resultado 3 datasets, treino, validação e teste prontos para o treino e validação do modelo.  

03-MODELING
Iremos modelar 6 modelos de ML de classifição diferentes e como resultado salvaremos todos os modelos treinados para a avaliação na próxima etapa.

04-EVALUATION
A avaliação dos modelos consiste em três etapas: avaliar as métricas de desempenho,  escollha do melhor modelo, realizar a explicação dos resultados do modelo e construção da política de risco de crédito. Para avaliar o desempenhos dos modelos do poder de discriminação utilizaremos algumas metricas como AUCROC e a matriz de Confusão para escolheremos o melhor modelo e atuaremos na parte de explicabidade dos resultados do modelo tanto a nivel macro como micro. E finalmente, construíremos uma politica de risco de crédito que nos ajudará na tomada de decisão e sinalizaremos também um score mínimo para a concessão de crédito.

05-DEPLOYMENT