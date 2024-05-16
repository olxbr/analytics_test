# Data Analyst Test

Este teste é composto por duas etapas: A análise exploratória de dados e o teste de SQL. Você terá 7 dias para concluir as duas tarefas. Divirta-se e bom teste! ;) 

# **Parte 1 - Análise Exploratória de Dados**

## Contexto

A Olx Brasil é o fruto da fusão de duas empresas, Olx, o portal ZAP Imóveis e o portal Viva Real. Como resultado da fusão, somos a maior plataforma de serviços do mercado imobiliário do Brasil, e além dos portais, temos as marcas DataZAP, Suahouse, Geoimovel e Sub100. Estamos presentes em todo o Brasil, com escritórios espalhados pelo país. 

Tanto o ZAP Imóveis quanto o portal Viva Real são marketplaces que conectam oferta e demanda através de anúncios de imóveis. Estes anúncios são administrados por imobiliárias e corretores, que possuem total controle sobre como as características de um determinado anúncio estão preenchidas, não existindo qualquer tipo de validação que confronte as características do imóvel real com as de um anúncio. 

Ainda dentro do contexto de informações de um anúncio, é importante dizer que preencher e/ou exibir o endereço de um imóvel não é obrigatório para cadastrar um anúncio. Ou seja, ainda que o anunciante envie todas as informações de endereço, ele ainda pode optar em exibir o conteúdo de maneira parcial. 

Apesar desse tipo de informação ser valiosa para as análises baseadas em localização, sabe-se que existe bastante desconfiança por parte das imobiliárias e corretores em preencher ou exibir informações completas de endereço do anúncio. Os anunciantes acreditam que usuários podem buscar diretamente os proprietários do imóvel para concluir a transação, tirando os anunciantes do processo.

## Objetivo

Você é o analista de dados que está alocado dentro do time de **Qualidade do Anúncio**. Foi levantada a hipótese de que **anúncios com endereço incompleto possuem um melhor desempenho** pelo fato dos usuários iniciarem um contato apenas com a intenção de tirar dúvidas sobre a localização do imóvel, e não por estarem com o interesse em negociar com o anunciante em cima daquele anúncio. **Sua missão é dizer se essa hipótese está correta ou não.** 

## Metodologia

Você definiu que **um anúncio com endereço completo é aquele que possui CEP, rua e número, e que exibe todas essas informações para os usuários do site**. Já o desempenho é dado pela **quantidade de leads recebidos** para o anúncio.

### Sobre o conteúdo da base

Faça o download dos arquivos em: 

* https:../analytics/leads.csv.gz
* https:../analytics/listings.csv.gz

A Base de Anúncios (`listings.csv.gz`) é composta por anúncios que estavam ativos nos portais ZAP e Viva Real no dia 31 de maio de 2019. São imóveis verticais (flats, apartamentos, coberturas e kitnets) das seguintes cidades: Santo André, São Bernardo do Campo e São Caetano do Sul - que fazem parte da região do ABC paulista. Nessa base temos tanto imóveis de aluguel como de venda que podem ter preços variados entre R$ 900 e R$ 1,500 para o primeiro grupo e R$ 120,000 e mais de R$ 1 milhão para o segundo grupo.

A Base de Leads (`leads.csv.gz`), por sua vez, é composta por leads que são a soma dos leads de mensagem, leads de ver telefone e leads de ligação que um anúncio recebeu do dia 01 de maio de 2019 até 31 de maio de 2019.

Recomendamos a você dar uma olhada nos nossos dois portais para entender o conteúdo de um anúncio e a interface para a geração de leads.

### Sobre os campos da base

##### Base de Anúncios (`listings.csv.gz`)

* `advertiser_id`: Identificador único do anunciante nos nossos portais;
* `listing_id`: Identificador único do anúncio nos nossos portais;
* `portal`: Portal em que o anúncio ficou ativo (ZAP/VIVAREAL);
* `bedrooms`: Total de quartos cadastrados para o anúncio;
* `suites`: Total de suítes cadastradas para o anúncio;
* `parking_spaces`: Total de garagens cadastradas para o anúncio;
* `unit_type`: Qual o tipo do imóvel - Apartamento, flat, cobertura; 
* `year_delivered_at`: Ano de construção do anúncio;
* `display_address_type`: Qual o grau de exibição do endereço de um anúncio: ALL (exibe todos os campos de endereço); STREET (exibe até a rua do endereço); NEIGHBORHOOD (exibe apenas o bairro do endereço);
* `city`: Cidade cadastrada para o anúncio;
* `state`: Estado cadastrado para o anúncio;
* `neighborhood`: Bairro cadastrado para o anúncio;
* `street`: Rua cadastrada para o anúncio; 
* `street_number`: Número do imóvel cadastrado para o anúncio;
* `CEP`: CEP cadastrado para o anúncio;
* `usable_areas`: Metros quadrados úteis cadastrados para o anúncio;
* `price`: Preço do imóvel;
* `created_date`: Data de criação do anúncio;
* `snapshot_date`: Data de extração da base de anúncios ativos.

##### Base de Leads (`leads.csv.gz`)

* `listing_id`: Identificador único do anúncio nos nossos portais. Chave para cruzar esta base com os anúncios.
* `leads`: Total de leads recebido pelo anúncio dentro do período.

## Resultados esperados

Elabore:

1. Racional e resultados que embasem sua resposta;
2. Crie uma apresentação com a sua conclusão que será apresentada para o gerente da área.

No primeiro item você poderá ser bastante técnico e deverá apresentar como explorou os dados (gráficos, cálculos e racionais) para embasar a sua conclusão. O segundo item, por sua vez, deverá ser voltada para o time de produto que são responsáveis pela criação das estratégias do negócio. Para o primeiro item você deverá usar **Jupyter Notebook com Python, R, Julia ou Scala para registrar o seu racional analítico - Não esqueça de criar comentários para melhorar a compreensão dos arquivos**. Vale ressaltar que apesar de considerarmos essas quatro linguagens para a prova, no dia a dia utilizamos Python.  Já para o segundo item, você poderá criar uma apresentação/dashboard com uma ferramenta de visualização, como Tableau, Qlik, Power BI ou usando python, de uma forma que sintetize sua conclusão.


Algumas perguntas que poderão te ajudar a criar o racional:

1. Quantos anúncios ativos no site exibem endereço completo?
2. Quantos anúncios ativos no site receberam leads?
3. O desempenho é uniforme para todos os segmentos de anúncios?
4. Quais outras variáveis tem relação com a quantidade de leads?

Algumas perguntas que poderão te ajudar a criar a conclusão:

1. De fato anúncios com endereço incompleto possuem um melhor desempenho?
2. Ressalvas e problemas nos dados que prejudicaram a análise;
3. Próximos passos que você vislumbra para esse estudo.

# **Parte 2 - SQL**

Sua tarefa será utilizar o script fornecido para criar uma base de dados e fazer algumas consultas em cima dos dados. O script pode ser baixado aqui: https://grupozap-code-challenge.s3.amazonaws.com/analytics/ddl.sql. O dialeto deste script é **PostgreSQL**. Uma sugestão para evitar subir um banco local é o de utilizar o [www.db-fiddle.com](https://www.db-fiddle.com/). Configure o input como **PostgreSQL 9.3 ou 9.6**, cole os dados na caixa da esquerda e clique em "Build Schema". Escreva as queries que respondam às perguntas abaixo e salve-as em um único arquivo de texto, separando-as por `;`.

1. Qual o total de leads que o Viva Real e o ZAP Imóveis trouxeram para essa base? A query deverá retornar: portal e total de leads para cada portal.
2. Qual a proporção de anúncios que um determinado bairro tem em relação à cidade em que está situado? A query deverá retornar: a cidade, o bairro, o total de anúncios do bairro, o total de anúncios da cidade e a proporção em porcentagem.

# Como entregar

Esperamos receber um arquivo `.zip` com o seu nome (ex.: `NomeSobrenome.zip`) contendo: 

1. O arquivo com o racional da sua análise

2. O formato em que a conclusão da análise será apresentada. 

3. O arquivo de texto contendo as queries da parte 2.
