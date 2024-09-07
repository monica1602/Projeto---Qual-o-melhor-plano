# Projeto de Análise de Dados Qual o melhor plano?

## Descrição do Projeto
O projeto cosiste em analisar os dados da empresa de telecomunicação Megaline. A empresa oferece aos seus clientes dois planos pré-pagos, Surf e Ultimate. O departamento comercial quer saber quais dos planos dão mais receita para ajustar o orçamento de publicidade. Uma primeira análise será realizada em uma pequena seleção de clientes. Terá dados de 500 clientes da Megaline: que clientes são, de onde eles são, qual o plano usam, o número de chamadas que eles fizeram e mensagens que eles enviaram em 2018. 
O trabalho é analisar o comportamento dos clientes e determinar quais planos pré-pagos dão mais receita. Devemos determinar qual dos dois planos pré-pagos hoje utulziados, Surf e Ultimate, gera mais receita pata atender ao pedido do departamento de marketing de ajuste do orçamento de relações públicas.
Os dados foram coletados entre 1 de janeito de 2018 a 31 de dezembro de 2018.

## As tarfas são:
- Revisar a estrutura dos dataframes
- Modificar os dataframes conforme necessário: tipos de dados em cada coluna, valores ausentes, valores duplicados
- Por ter várias tabelas com dados diferentes em cada uma, é necessário unificar todas as informações em uma única tabela que permite fazer mais facilmente os cálculos tendo as informações de cada usuário, de acordo com seu plano, para cada mês que o serviço foi contratado
- Fazer uma análise através dos gráficos para observar o comportamento de cada plano
- Conferir as hipóteses estabelecidas pela Megaline
  - Hipótese 1: A receita média gerada pelos usuários dos planos Surf e Ultimate é diferente
  - Hipótese 2: Os usuários da região NY-NJ têm uma receita média diferente dos usuários de outras regiões

## Dicionário de dados
Há cinco tabelas no conjunto de dados. Abaixo está um dicionário que lista as colunas de cada tabela e descreve os dados contidos nelas.
- megaline_users.csv: dados sobre usuários
  - 'user_id': identificador exclusivo do usuário
  - 'first_name': nome do usuário
  - 'last_name': sobrenome do usuário
  - 'age': idade do usuário
  - 'reg_date': data da inscrição
  - 'churn_date': a data que o usuário parou de usar o serviço (se o valor estiver ausente, isso significa que o plano estava em uso quando o banco de dados foi extraído)
  - 'city': cidade de reseidência do usuário
  - 'plan': nome do plano
- megaline_calls.csv: dados sobre as chamadas
  - 'id': identificados de chamada exclusivo
  - 'call_date': data da chamada
  - 'duration': duração da chamada (em minutos)
  - 'user_id': identificador do usuário que faz a chamada
- megaline_messages.csv: dados sobre mensagens de texto
  - 'id': identificador exclusivo da mensagem de texto
  - 'message_date': data da mensagem de texto
  - 'user_id': identificador do usuário que envia a mensagem de texto
- megaline_internet.csv: dados sobre sessões web
  - 'id': identificador exclusivo da sessão
  - 'mb_used': volume de dados gasto durante a sessão (megabytes)
  - 'session_date': data da sessão web
  - 'user_id': identificador do usuário
- megaline_plans: dados sobre os planos
  - 'plan_name': nome do plano
  - 'usd_monthly_fee': preço mensal em dolares americanos
  - 'minutes_included': pacote mensal de minutos
  - 'messages_included': pacote mensal de mensagens de texto
  - 'mb_per_month_included': volume do pacote de dados (em megabytes)
  - 'usd_per_minute': preço por minuto depois de exceder o limite do pacote
  - 'usd_per_message': preço por mensagem de texto depois de exceder o limite do pacote
  - 'usd_per_gb': preço por gigabyte extra de dados após exceder o limite do pacote

## Ferramentas e Bibliotecas utilizadas
- Python: Linguagem principal utilizada para análise
- Pandas: Biblioteca para manipulação e análise de dados
- Matplotlib: Biblioteca para gerar gráficos
- Numpy: Biblioteca que permite trabakhar com objetos multidimensionais, como matrizes e sequências
- Math: Biblioteca que permite usar funções matemáticas

## Resultados
- É possível perceber que quem utiliza o plano Ultimate dificilmente gasta mais do que está incluso no plano
- A maioria dos usuários do plano Surf gasta mais que o incluso no plano, mas não chega a gastar mais o valor fixo do plano Ultimate
- É possível concluir que a pessoa só deve mudar de plano se o total gasto ultrapassar o valor fixo do outro plano
- Na hipótese 1 foi realizado um teste de hipótese com alpha de 5%, no qual resultou na informação de que a receita média dos usuários dos planos Surf e Ultimate são diferentes
- Na hipótese 2 foi confirmada via t-test que há evuidências estatísticas de que a receita média dos usuários da área de NY-NJ difere dos usuários das demais regiões

## Aprendizados
- Análise de dados
- Qualidade dos dados
- Tratar os dados modificando tipos de dados, nome das colunas, valores ausentes, valores duplicados
- Pré-processamento de dados
- Construção e análise de gráficos

## Como executar o Projeto
- Clone o repositório
- Navegue até o diretório do projeto
- Abra o proejto no seu IDE favorito
- Instale as dependências
- Execute o script principal
