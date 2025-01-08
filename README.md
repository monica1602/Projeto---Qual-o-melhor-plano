# Projeto de Análise de Dados Qual o melhor plano?

## Descrição do Projeto
O projeto consiste em analisar os dados da empresa de telecomunicação Megaline. A empresa oferece aos seus clientes dois planos pré-pagos, Surf e Ultimate. O departamento comercial quer saber quais dos planos dão mais receita para ajustar o orçamento de publicidade. Uma primeira análise será realizada em uma pequena seleção de clientes. Terá dados de 500 clientes da Megaline: que clientes são, de onde eles são, qual o plano usam, o número de chamadas que eles fizeram e mensagens que eles enviaram em 2018. 
O trabalho é analisar o comportamento dos clientes e determinar quais planos pré-pagos dão mais receita. Devemos determinar qual dos dois planos pré-pagos hoje utulziados, Surf e Ultimate, gera mais receita pata atender ao pedido do departamento de marketing de ajuste do orçamento de relações públicas.
Os dados foram coletados entre 1 de janeito de 2018 a 31 de dezembro de 2018.
Observação: a Megaline arredonda segundos para minutos e megabytes para gigabytes. Para chamadas, cada chamada individual é arredondada para cima, mesmo que uma chamada tenha durado apenas um segundo, um minuto será contado. Para tráfego da web, sessões individuais da web não são arredondadas para cima. Ao invés disso, o total do mês é arredondado para cima. Se alguém usar 1025 megabytes no mês, a cobrança será de 2 gigabytes.

## As tarefas são:
- Revisar a estrutura dos dataframes
- Modificar os dataframes conforme necessário: tipos de dados em cada coluna, valores ausentes, valores duplicados
- Por ter várias tabelas com dados diferentes em cada uma, é necessário unificar todas as informações em uma única tabela que permite fazer mais facilmente os cálculos tendo as informações de cada usuário, de acordo com seu plano, para cada mês que o serviço foi contratado
- Fazer uma análise através dos gráficos para observar o comportamento de cada plano
- Conferir as hipóteses estabelecidas pela Megaline
  - Hipótese 1: A receita média gerada pelos usuários dos planos Surf e Ultimate é diferente
  - Hipótese 2: Os usuários da região NY-NJ têm uma receita média diferente dos usuários de outras regiões
- É necessário explicar como foi formulado as hipóteses alternativas e nulas e qual critério foi utilizado para testar as hipóteses e por quê
  
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

## Imagens

### Comparação do número de minutos de que os usuários de cada plano necessitam a cada mês
<img src="https://github.com/user-attachments/assets/d53446bb-75d5-4e5c-87ba-f7ba0d7c958d" alt="Projeto 4" width="200"/>

### Diagrama de caixa para visualizar a distribuição da duração mensal das chamadas
<img src="https://github.com/user-attachments/assets/aaae64ae-4784-4c85-92ef-633b093d539b" alt="Projeto 4" width="200"/>

### Comparação do número de mensagens que os usuários de cada plano tendem a enviar a cada mês
<img src="https://github.com/user-attachments/assets/24461775-1b78-4e85-9292-589ae112dfb5" alt="Projeto 4" width="200"/>

### Comparação da quantidade de tráfego de internet consumido pelos usuários por plano
<img src="https://github.com/user-attachments/assets/919333f1-d189-42f8-9486-226ff6911b64" alt="Projeto 4" width="200"/>

### Receita por plano
<img src="https://github.com/user-attachments/assets/94ca0d5b-850a-4d53-b664-56f93f33c4ea" alt="Projeto 4" width="200"/>

### Hipótese 1
<img src="https://github.com/user-attachments/assets/3c2c9816-159f-41f9-bb87-166d2b6f1ba9" alt="Projeto 4" width="200"/>

### Hipótese 2 
<img src="https://github.com/user-attachments/assets/0dfd282a-02fc-4142-994b-7be613754b64" alt="Projeto 4" width="200"/>

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

## Contexto real
- Clientes que desejam entender melhor cada plano
- Empresas que desejam entender melhor o comportamento dos clientes
- Novas empresas que desejam lançar novos planos e para isso analisar seus possíveis novos clientes
- Empresas que desejam oferecer novos planos para seus clientes e desejam mostrar suas vantagens
  
## Como executar o Projeto
- Clone o repositório
- Navegue até o diretório do projeto
- Abra o proejto no seu IDE favorito
- Instale as dependências
- Execute o script principal
