# Projeto: Concessão de Crédito por meio de um modelo de machine learning.

Este projeto realiza a construção de um modelo de concessão de crédito e finaliza com aplicação do modelo em um dashboard interativo da mesa de concessão, buscando pricipalmente agilidade, rapidez e explicação da tomada de decisão. 

Utilizamos a metodologia Crisp-DM que possui 6 passos:

## 00-BUSINESS_UNDERSTANDING
Nesta etapa iremos analisar os objetivos do negócio para utilizar e qual o status sem o modelo de ML. Ou seja, responder a questão: do que o negócio precisa?

## 01-DATA_UNDERSTANDING
Consiste em conhecer mais afundo os dados, selecionar algumas variáveis explicativas interessantes e definir a variável resposta, conhecido como target. Como resultado teremos um dataframe com as variáveis explicativas selecionadas e um arquivo de metadados que resume algumas caracteristicas das variaveis selecionadas para orientar o processo de preparação dos dados.
As variáveis selecionadas neste momento são:
- **loan_amnt:** O valor listado do empréstimo aplicado pelo tomador de empréstimo.
- **term:** Quantidade de pagamentos do empréstimo, onde os valores são em meses e podem ser 36 ou 60.
- **int_rate:** A taxa de juros do empréstimo
- **sub_grade:** Pontuação de subclasse de empréstimo atribuída com base no histórico de crédito do tomador de empréstimo
- **emp_length:** Tempo de emprego do tomador de empréstimo em anos.
- **home_ownership:** O status de propriedade fornecido pelo tomador de empréstimo (por exemplo, aluguel, próprio, hipoteca, etc.)
- **anual_inc:** A renda anual autodeclarada fornecida pelo tomador de empréstimo
- **addr_state:** O estado fornecido pelo tomador de empréstimo no pedido de empréstimo
- **dti:** Razão calculada utilizando o total dos pagamentos mensais da dívida do tomador de empréstimo sobre o total das obrigações da dívida, excluindo hipoteca, dividido pelo rendimento mensal do tomador de empréstimo.
- **mths_since_recent_inq:** Meses desde a consulta mais recente
- **revol_util:** Taxa de utilização da linha rotativa ou a quantidade de crédito que o tomador de empréstimo está usando em relação a todo o crédito rotativo disponível.
- **bc_open_to_buy:** Total aberto para compra em cartões bancários rotativos
- **bc_util:** Proporção entre o saldo atual total e o limite de crédito/crédito alto para todas as contas de cartão bancário
- **num_op_rev_tl:** Número de contas rotativas abertas
- **lend_status:** Situação atual do empréstimo (por exemplo, totalmente pago ou debitado), este é o rótulo que iremos prever com o modelo.

## 02-DATA-PREPARATION
Com o objetivo de fazer a validação cruzada no modelo nesta etapa separamos os dados em 3 datasets: treino, validação e teste. A partir do tratamento das variaveis numericas e categoricas do dataset de treino faremos os tratamentos das variáveis explicativas nos dataset de validação e treino. Teremos como resultado 3 datasets, treino, validação e teste prontos para o treino e validação do modelo.  

## 03-MODELING
Iremos modelar 6 modelos de ML de classifição diferentes e como resultado salvaremos todos os modelos treinados para a avaliação na próxima etapa.

## 04-EVALUATION
A avaliação dos modelos consiste em três etapas: avaliar as métricas de desempenho,  escollha do melhor modelo, realizar a explicação dos resultados do modelo e construção da política de risco de crédito. Para avaliar o desempenhos dos modelos do poder de discriminação utilizaremos algumas metricas como AUCROC e a matriz de Confusão para escolheremos o melhor modelo e atuaremos na parte de explicabidade dos resultados do modelo tanto a nivel macro como micro. E finalmente, construíremos uma politica de risco de crédito que nos ajudará na tomada de decisão e sinalizaremos também um score mínimo para a concessão de crédito.

## 05-DEPLOYMENT
Com os artefatos do modelo escolhido salvos utilizaremos a Streamlit Cloud fazer a implementação no ambiente cloud e servir o modelo sob uma interface feita utilizado a biblioteca streamlit e disponível em:  [Credit Scoring Dashboard](https://credit-scoring-project.streamlit.app/). Veja mais detalhes em como utilizar o simulador logo abaixo.

### Pré-requisitos

- Python 3.9

### Instalação

1. Clone o repositório do projeto:
  ```bash
      git clone https://github.com/rodrafanas/credit_score_project.git
  ```

2. Navegue até o diretório do projeto:
  ```bash
      cd credit_score_project
  ```

3. Instale as dependências necessárias:
  ```bash
      pip install -r requirements.txt
  ```
### Execução

Para rodar o dashboard, execute o seguinte comando no diretório do projeto:
  ```bash
      streamlit run streamlit.py
  ```
                      
### Uso do Simulador da Mesa de Crédito ou Credit Scoring Dashboard

1. **Acesse o Dashboard:** Clique no link: [Credit Scoring Dashboard](https://credit-scoring-project.streamlit.app/)
2. **Indique as informações do tomador de crédito:** Preenchendo os dados do cliente ou tomador de crédito no lado esquerdo.
3. **Calcule o Score de Crédito:** Calcular o score de crédito do tomador de crédito apertando o botão "Predict".
4. **Interprete e explique os resultados:** Interpetrar o score calculado pelo modelo visualizado a Política de Risco implementada e a contribuição de cada varíavel do cliente de maneira global e individual.


## Contribuindo

Contribuições são sempre bem-vindas! Para contribuir, por favor:
1. Faça um Fork do projeto.
2. Crie uma Branch para sua Feature (`git checkout -b feature/AmazingFeature`).
3. Faça o Commit de suas mudanças (`git commit -m 'Add some AmazingFeature'`).
4. Faça o Push para a Branch (`git push origin feature/AmazingFeature`).
5. Abra um Pull Request.

## Licença

Distribuído sob a licença MIT. Veja `LICENSE` para mais informações.

## Contato

Rafael Nascimento - [rodrafanas@gmail.com](mailto:rodrafanas@gmail.com)

Projeto Link: [https://github.com/rodrafanas/credit_score_project](https://github.com/rodrafanas/credit_score_project)
