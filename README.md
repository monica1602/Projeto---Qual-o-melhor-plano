# Projeto de Análise de Dados - Qual o melhor plano?

## Descrição do Projeto
A empresa de telecomunicações Megaline oferece aos seus clientes dois planos pré-pagos: Surf e Ultimate. O departamento comercial da empresa busca determinar qual dos dois planos gera maior receita, com o objetivo de otimizar o orçamento destinado às estratégias de publicidade e relações públicas. 
O presente estudo tem como finalidade analisar o comportamento dos clientes e avaliar a receita gerada pelos planos Surf e Ultimate. A análise será realizada a partir de uma amostra de 500 clientes da Megaline, considerando dados sobre suas chamadas telefônicas, mensagens enviadas e uso de tráfego de internet ao longo do ano de 2018.
Os dados utilizados para esta análise foram coletados no período de 1º de janeiro de 2018 a 31 de dezembro de 2018. A amostra inclui informações sobre a localização dos clientes, o plano contratado e os serviços utilizados. A Megaline adota um sistema específico de arredondamento para cobrança de chamadas e tráfego de internet: para chamadas, cada chamada individual é arredondada para cima, de forma que, mesmo que uma chamada dure apenas um segundo, será contabilizado um minuto completo para efeito de cobrança. No caso do tráfego de internet, o arredondamento ocorre mensalmente sobre o total utilizado. Caso um cliente utilize, por exemplo, 1025 megabytes ao longo do mês, o consumo será arredondado para 2 gigabytes.
A análise fornecerá insights sobre qual dos planos pré-pagos, Surf ou Ultimate, proporciona maior receita para a Megaline, permitindo que o departamento comercial ajuste suas estratégias de marketing e publicidade de forma mais eficiente.


## As tarefas são:
- Revisar a estrutura dos DataFrames
- Modificar os DataFrames conforme necessário: tipos de dados em cada coluna, valores ausentes, valores duplicados
- Unificar as tabelas: consolidar todas as informações em um único DataFrame que permita cálculos mais fáceis, associando os dados de cada usuário ao seu plano para cada mês do serviço contratado
- Fazer uma análise através dos gráficos: observar o comportamento de cada plano com relação ao uso de chamadas, mensagens e internet
- Conferir as hipóteses estabelecidas pela Megaline
  - Hipótese 1: A receita média gerada pelos usuários dos planos Surf e Ultimate é diferente
  - Hipótese 2: Os usuários da região NY-NJ têm uma receita média diferente dos usuários de outras regiões
- Explicar a formulação das hipóteses e os critérios utilizados para os testes
- Definir hipóteses nula e alternativa
- Explicar a escolha do teste t para amostras independentes
- Justificar o nível de significância utilizado e interpretação dos resultados
  
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
- Python: Linguagem principal utilizada para a análise de dados e implementação dos processos estatísticos.
- Pandas: Biblioteca essencial para manipulação, limpeza e análise de dados estruturados em formato tabular.
- Matplotlib: Biblioteca utilizada para a criação de visualizações gráficas, facilitando a interpretação dos dados por meio de gráficos e representações visuais.
- NumPy: Biblioteca que simplifica o manuseio de vetores e matrizes, acelerando cálculos matemáticos e estatísticos nos dados.
- Math: Biblioteca que disponibiliza funções matemáticas fundamentais, como operações de arredondamento, cálculos trigonométricos e exponenciais, entre outras.

## Imagens

### Gráfico - Comparação do número de minutos de que os usuários de cada plano necessitam a cada mês
<img src="https://github.com/user-attachments/assets/d53446bb-75d5-4e5c-87ba-f7ba0d7c958d" alt="Projeto 4" width="800"/>

### Gráfico - Diagrama de caixa para visualizar a distribuição da duração mensal das chamadas
<img src="https://github.com/user-attachments/assets/aaae64ae-4784-4c85-92ef-633b093d539b" alt="Projeto 4" width="800"/>

### Gráfico - Comparação do número de mensagens que os usuários de cada plano tendem a enviar a cada mês
<img src="https://github.com/user-attachments/assets/24461775-1b78-4e85-9292-589ae112dfb5" alt="Projeto 4" width="800"/>

### Gráfico - Comparação da quantidade de tráfego de internet consumido pelos usuários por plano
<img src="https://github.com/user-attachments/assets/919333f1-d189-42f8-9486-226ff6911b64" alt="Projeto 4" width="800"/>

### Gráfico - Receita por plano
<img src="https://github.com/user-attachments/assets/94ca0d5b-850a-4d53-b664-56f93f33c4ea" alt="Projeto 4" width="800"/>

### Código - Hipótese 1
<img src="https://github.com/user-attachments/assets/3c2c9816-159f-41f9-bb87-166d2b6f1ba9" alt="Projeto 4" width="1000"/>

### Código - Hipótese 2 
<img src="https://github.com/user-attachments/assets/0dfd282a-02fc-4142-994b-7be613754b64" alt="Projeto 4" width="1000"/>

## Resultados
- Os usuários do plano Ultimate raramente excedem os benefícios incluídos no plano, indicando que a maioria deles não gera custos adicionais além da mensalidade fixa.
- A maioria dos usuários do plano Surf ultrapassa a franquia do plano, mas seus gastos adicionais geralmente não chegam ao valor fixo do plano Ultimate.
- A troca de plano só é vantajosa se o total gasto no plano atual superar o custo fixo do outro plano, sugerindo que os usuários devem avaliar seus padrões de consumo antes de mudar de plano.
- Hipótese 1: Foi realizado um teste de hipótese com um nível de significância de 5% (α = 0,05), confirmando que há uma diferença estatisticamente significativa entre a receita média dos usuários dos planos Surf e Ultimate.
- Hipótese 2: O teste t indicou evidências estatísticas de que a receita média dos usuários da região de NY-NJ é significativamente diferente da receita média dos usuários de outras regiões.

## Aprendizados
- Análise exploratória de dados: compreensão inicial do conjunto de dados, identificando padrões, tendências e possíveis inconsistências.
- Avaliação da qualidade dos dados: Inspeção da totalidade, consistência e exatidão das informações para assegurar a confiança nas análises.
- Tratamento de dados: ajustes necessários, incluindo a modificação de tipos de dados, padronização dos nomes das colunas, tratamento de valores ausentes e remoção de registros duplicados.
- Pré-processamento dos dados: preparação e transformação dos dados para análises futuras, garantindo estrutura adequada para modelagem e interpretação.
- Construção e análise de visualizações gráficas: elaboração de gráficos e representações visuais para facilitar a interpretação dos dados e a identificação de padrões significativos.

## Contexto real
- Clientes que buscam compreender melhor as características e benefícios de cada plano: necessitam de uma análise detalhada para tomar decisões informadas sobre qual plano atende melhor às suas necessidades.
- Empresas que buscam entender o comportamento dos clientes: necessitam de uma análise detalhada dos dados dos usuários para identificar padrões de consumo e aprimorar suas ofertas.
- Novas empresas que pretendem lançar novos planos e precisam analisar seu público-alvo potencial: requerem uma análise do perfil e comportamento dos consumidores para desenvolver ofertas alinhadas às suas preferências e necessidades.
- Empresas que desejam oferecer novos planos para seus clientes e evidenciar suas vantagens: necessitam de dados analíticos que permitam destacar os benefícios dos novos planos, ajudando na comunicação das vantagens de forma clara e convincente.
  
## Como executar o Projeto
- Clone o repositório
- Navegue até o diretório do projeto
- Abra o proejto no seu IDE favorito
- Instale as dependências
- Execute o script principal
