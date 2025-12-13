# *Projeto1 Dashboard de estoque logistico*
## *Explicação do projeto*
O trabalho a seguir é uma visão de estoque nível nacional, primeiro buscasse nesse trabalho entender a atual questão do estoque, os números, saúde, visão ampla para depois podermos explorar os insights, este trabalho terá crescimento de tempo, é um projeto próprio: bases e analises todas criadas por mim.

## *Introdução a ideia do projeto e logística*
Na logística é muito importante saber a saúde do estoque isso se reflete na quantidade atual do estoque, na sua curva abc, seu giro de estoque, custo das mercadorias.
 	Tudo isso precisamos de algumas coisas importantes: histórico de estoque, histórico de vendas, base de sku atualizadas, KPI bem definidos, e é isso que mostro nesse primeiro pequeno trabalho.

## *Visão do Projeto1*
   Nessa projeção, estamos observando um estoque e período de vendas agitado, final de ano, e uma tentativa arriscada sobre o over do estoque olhamos os seguintes meses: Setembro, outubro, novembro, dezembro e janeiro.
Queremos obter resultado se a técnica de comprar o estoque geral acima da média geraria gargalos grandes ou pequenos impactos, sabendo que o estoque foi comprado anteriormente ao período de agitação da época de vendas  
![Alerta Excel Setembro](imagens/alerta_do_excel_setembro.png)

## *Etapas de criação*
  As bases que você vai encontrar já estão trabalhadas com formulas e em sua versão final, são bases xlsx, algumas estão apenas para guia em uso no sql ou python.
A estrutura dos skus foram criadas com prompt através de LLM como ChatGPT e deepseek, foi se pensado através de vivências minhas na logística como CLT e como consultora de pequenos negócios locais, usei de estruturas que foram vistas em períodos que estive frente a frente com demandas logísticas.
Bases de vendas foram feitas através de prompts usando o ChatGPT e o Claude para revisar as bases corretamente. 

## *Bases do projeto1*

Bases usadas para o Projeto1:  
estoquesGit,   
vendas_dezembro_com_clientes_git,   
vendas_novembro_2024_git,  
 vendas_outubro_com_clientes_git,  
 vendas_setembro_com_clientes_git  
## *Etapas de ETL*
•	 Organização das bases,  
•	Organização de nomenclaturas,  
•	Organização e limpeza,  
•	Governança de dados,  
•	Estruturação de medidas,  
•	Construção do dashboard,  
 1 – *organização das bases, governança de dados, nomenclatura *
 
 foi feito uma visão para garantir os dados corretos, normalmente em alguns WMS não se guarda a visão do estoque em (x) dia ou (x) mês, então se usa ferramentas como banco de dados: Excel ou sql, no nosso caso a “equipe” guardou os arquivos em Excel, foi usado algumas medidas dentro do Excel para se criar uma visão necessária como:  

 
  “ULTIMO_ABASTECIMENTO_DEZEMBRO” e “ESTOQUE_MES”  

  
  Garantindo assim que teríamos a visão correta do custo gasto no mês em questão e a o mês em questão para a visão mensal pois o estoque estava detalhado com o mês apenas pelas abas, esse trabalho poderia ser feito pelo Power querry facilmente, mas o intuito desde o inicio era fazer uma junção dos períodos de venda e estoque, que poderia se gerar várias partes de limpeza e manutenção das tabelas fazendo assim o PBI ficar lento e instável.
 também foi visado a troca de nomenclaturas das colunas e títulos agregando valor ao uso seguro no PBI, SQL e Python (a mesma base irá para o kaggle).  
Imagem aqui.  
2 - *Estruturação de medidas*

As medidas foram feitas em dax e divididas em pastas para cada necessidade:

imagem aqui

Imagem aqui


3 - *Construção de dashboard*  
Para essa parte de dashboard usamos o método estrela (star scherma), para controlar os relacionamentos:

Imagem aqui

Mantendo assim a qualidade dos dados nos meios de relacionamento 1 para muitos, tendo várias tabelas Dimensões e 2 fatos com as de vendas e as de estoque:

Imagem aqui

Em sua montagem final a imagem escolhida foi o balanceamento entre um dashboard sem tantas cores em um fundo mais panorâmico e o uso de suas cores em camadas parecidas usando apenas cores de realce em alguns itens que queremos ressaltar como: maiores e menores vendas e sua categoria de estoque:

Imagem aqui

O dashboard em si tem muitas informações que geram insights de como está o atual momento do estoque e sua visão já moldada de curva, giro, categoria, valor e quantidade no estoque, então pode se gerar a dúvida diária como valor de estoque em cada mês e quantidade de giro relacionada aos meses então utilizei de tooltips para trazer essa informação sem deixar o dashboard mais cheio de visões que já está: 

imagem aqui 

Imagem aqui

# *Resultado da Análise*
Com o dashboard concluído, conseguimos extrair insights importantes para a operação logística e comercial:
## *Curva ABC*
A curva ABC obtida não apresenta a distribuição típica esperada, indicando:
•	concentração irregular de itens no grupo A
•	possível distorção no mix de produtos
•	necessidade de revisar políticas de estoque, priorização e reposição
Esse comportamento reforça a necessidade de uma análise mais profunda sobre mix de vendas, giro e margem por categoria.
________________________________________
## *Giro e Custo de Estoque*
A análise temporal mostrou:
•	crescimento significativo no giro do estoque entre setembro e dezembro, sugerindo aumento de demanda ou melhoria nos processos de reposição
•	redução no custo total do estoque, indicando melhor controle de inventário ou maior assertividade nas reposições
Esses dois movimentos juntos sugerem ganho operacional.
________________________________________
# *Lucro e Descontos*
Apesar do lucro apresentado nas vendas, ainda não foram aplicados os descontos comerciais e promocionais fornecidos pela equipe comercial nos primeiros meses.
Isso reforça a importância de integrar informações logísticas com dados financeiros para obter uma visão de margem mais precisa.
________________________________________
# *Valor Analítico do Dashboard*
Este dashboard teve como objetivo produzir uma análise descritiva com foco em gerar perguntas, não apenas respostas.
Sem fazer as perguntas corretas, não conseguimos direcionar investigações futuras — é essa curiosidade que habilita análises diagnósticas e preditivas posteriores.
A visualização funciona como:
•	um guia estrutural das forças e fraquezas do estoque (SWOT operacional)
•	uma espinha dorsal de insights, orientando tomadas de decisão
•	uma base sólida para evoluir para modelos de previsão de demanda e otimização de estoque

| Tecnologia / Ferramenta                                   | Finalidade                                                                                   |
|-----------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| Claude, ChatGPT, Gemini, DeepSeek                         | Suporte à construção lógica do projeto, revisão textual e otimização das estruturas analíticas |
| Excel + Power Query (Linguagem M)                         | ETL completo: ingestão, limpeza, normalização e padronização dos dados                       |
| Excel                                                     | Análises descritivas, tabelas dinâmicas e visualizações preliminares                         |
| Power BI (DAX)                                            | Modelagem analítica, criação de medidas e desenvolvimento do dashboard final                 |




