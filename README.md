# Exame PL-300

# Analista de Dados do Microsoft Power BI

## Visão Geral de Análise de Dados

- **Análise Descritiva**

A análise descritiva *ajuda a responder perguntas sobre o que aconteceu com base em dados históricos*. As técnicas de análise descritiva resumem grandes conjuntos de dados para descrever os resultados para os stakeholders.

Ao desenvolver KPIs (indicadores chave de desempenho), essas estratégias podem ajudar a acompanhar o sucesso ou a falha dos objetivos principais. Métricas como ROI (retorno sobre o investimento) são usadas em muitos setores e métricas especializadas são desenvolvidas para acompanhar o desempenho em setores específicos.

Um exemplo de análise descritiva é a geração de relatórios para fornecer uma exibição dos dados financeiros e de vendas de uma organização.

- **Análise de Diagnóstico**

A análise de diagnóstico *ajuda a responder perguntas sobre por que eventos aconteceram*. As técnicas de análise de diagnóstico complementam a análise descritiva básica e usam as conclusões de análises descritivas para descobrir a causa desses eventos. Em seguida, os indicadores de desempenho são investigados mais detalhadamente para descobrir por que esses eventos ficaram melhores ou piores. Esse processo geralmente ocorre em três etapas:

1. Identificar anomalias nos dados. Essas anomalias podem ser alterações inesperadas em uma métrica ou em um mercado específico.

2. Coletar dados relacionados a essas anomalias.

3. Usar técnicas estatísticas para descobrir relações e tendências que explicam essas anomalias.

- **Análise Preditiva**

A análise preditiva *ajuda a responder perguntas sobre o que acontecerá no futuro*. As técnicas de análise preditiva usam dados históricos para identificar tendências e determinar se é provável que elas se repitam. As ferramentas analíticas preditivas fornecem insights valiosos sobre o que pode acontecer no futuro. As técnicas incluem uma variedade de técnicas de machine learning e estatísticas, como redes neurais, árvores de decisão e regressão.

- **Análise Prescritiva**

A análise prescritiva *ajuda a responder perguntas sobre quais ações devem ser executadas para atingir uma meta ou um objetivo*. Usando insights da análise preditiva, as organizações podem tomar decisões controladas por dados. Essa técnica permite que as empresas tomem decisões informadas em meio às incertezas. As técnicas de análise prescritiva contam com as estratégias de machine learning para encontrar padrões em grandes conjuntos de dados. Analisando decisões e eventos anteriores, as organizações podem estimar a probabilidade de diferentes desfechos.

- **Análise Cognitiva**

A análise cognitiva *tenta extrair inferências de padrões e dados existentes, derivar conclusões de bases de conhecimento existentes e adicionar essas descobertas de volta à base de conhecimento para futuras inferências, um loop de comentários de autoaprendizado*. A análise cognitiva ajuda você a aprender o que poderá acontecer se as circunstâncias mudarem e a determinar como será possível lidar com essas situações.

As inferências não são consultas estruturadas com base em um banco de dados de regras; elas são hipóteses não estruturadas obtidas de várias fontes e expressas com diferentes graus de confiança. A análise cognitiva eficaz depende de algoritmos de machine learning e usará vários conceitos de processamento de idioma natural para compreender fontes de dados não exploradas anteriormente, como logs de conversa de call center e análises de produtos.

## Modos de Armazenamento

- **Modo de Importação**

O modo de Importação *permite que você crie uma cópia local do Power BI de seus conjuntos de dados provenientes da sua fonte de dados*. Você pode usar todos os recursos de serviço do Power BI com esse modo de armazenamento, incluindo P e R e Insights Rápidos. As atualizações de dados podem ser agendadas ou sob demanda. O modo de Importação é o padrão para a criação de relatórios do Power BI.

- **Modo DirectQuery**

A opção DirectQuery é útil quando você não deseja salvar cópias locais de seus dados, pois *seus dados não serão armazenados em cache*. Em vez disso, você pode consultar as tabelas específicas que serão necessárias usando consultas nativas do Power BI e os dados necessários serão recuperados da fonte de dados subjacente. Essencialmente, você está criando uma conexão direta com a fonte de dados. O uso desse modelo garante que você sempre veja os dados mais atualizados e que todos os requisitos de segurança sejam satisfeitos. Além disso, esse modo é adequado para quando você tem grandes conjuntos de dados para efetuar pull. Em vez de reduzir o desempenho, tendo que carregar grandes quantidades de dados no Power BI, você pode usar o DirectQuery para criar uma conexão com a fonte, resolvendo problemas de latência de dados também.

- **Duplo (modo composto)**

No modo Duplo, *você pode identificar alguns dados a serem importados diretamente e outros dados que devem ser consultados*. Qualquer tabela que é colocada em seu relatório é um produto dos modos de Importação e DirectQuery. O uso do modo Duplo permite que Power BI escolha a forma mais eficiente na recuperação de dados.

## Otimizar o Desempenho no Power Query

- **Dobragem de Consultas**

A dobragem de consultas *é o processo pelo qual as transformações e edições feitas no Editor do Power Query são controladas simultaneamente como consultas nativas ou como instruções SQL Select simples, enquanto você está ativamente fazendo transformações*. O motivo para implementar esse processo é garantir que essas transformações ocorram no servidor da fonte de dados original e não sobrecarreguem os recursos de computação do Power BI.

- **Diagnóstico de Consulta**

Esse recurso permite que você determine quais gargalos (se houver) existem durante o carregamento e a transformação dos dados, durante a atualização dos dados no Power Query, durante a execução de instruções SQL no Editor de Consultas e assim por diante.

- **Processar o Máximo de Dados Possível na Fonte de Dados Original**

O Power Query e o Editor do Power Query permitem processar os dados; no entanto, a capacidade de processamento necessária para concluir essa tarefa pode reduzir o desempenho em outras áreas de seus relatórios. *Em geral, uma boa prática é processar o máximo possível na fonte de dados nativa*.

- **Use Consultas SQL Nativas**

Ao usar o DirectQuery para bancos de dados SQL, como o caso do nosso cenário, não efetue pull de dados de procedimentos armazenados ou de CTEs (Expressões de Tabela Comum).

- **Separe Data e Hora, se Combinadas**

Se qualquer uma das tabelas tiver colunas que combinem data e hora, separe-as em colunas distintas antes de importá-las para o Power BI. *Essa abordagem aumentará as capacidades de compactação*.

## Erros de Importação

- **O Tempo Limite da Consulta Expirou**

Os sistemas de fonte de dados relacionais geralmente têm muitas pessoas que usam os mesmos dados simultaneamente no mesmo banco de dados. Alguns sistemas relacionais e seus administradores buscam limitar o monopólio de todos os recursos de hardware por um usuário definindo um tempo limite de consulta. Esses tempos limite podem ser configurados para qualquer intervalo de tempo, de cinco segundos a até 30 minutos ou mais.

- **Erro de Consulta do Power Bi: O Tempo Limite Expirou**

Esse erro indica que você efetuou pull de muitos dados, de acordo com as políticas da sua organização. Os administradores incorporam essa política para evitar a lentidão de um aplicativo ou conjunto de aplicativos diferentes que também possam usar esse banco de dados.

Você pode resolver esse erro efetuando pull de menos colunas ou linhas em uma única tabela. Embora você esteja escrevendo instruções SQL, pode ser uma prática comum incluir agrupamentos e agregações. Você também pode unir várias tabelas em uma única instrução SQL. Além disso, você pode executar subconsultas complicadas e consultas aninhadas em uma única instrução. Essas complexidades são adicionadas aos requisitos de processamento de consultas do sistema relacional e podem prolongar muito o tempo de implementação.

Se você precisar das linhas, das colunas e da complexidade, considere obter pequenas partes de dados e, em seguida, juntá-las novamente usando o Power Query. Por exemplo, você pode combinar metade das colunas em uma consulta e a outra metade em uma consulta diferente. O Power Query pode mesclar essas duas consultas novamente depois que você terminar.

- **Não Foi Possível Localizar Nenhum Dado Formatado Como Uma Tabela**

Ocasionalmente, você pode encontrar o erro "Não foi possível localizar nenhum dado formatado como uma tabela" ao importar dados do Microsoft Excel. Felizmente, esse erro é auto-explicativo. O Power BI espera encontrar dados formatados como uma tabela do Excel.

- **Não Foi Possível Localizar o Arquivo**

Normalmente, esse erro é causado pela mudança de local do arquivo ou pela alteração das permissões do arquivo. Se a causa for a primeira, você precisará localizar o arquivo e alterar as configurações de origem.

- **Erros de Tipo de Dados**

Às vezes, quando você importa dados para o Power BI, as colunas aparecem em branco. Essa situação ocorre devido a um erro na interpretação do tipo de dados no Power BI. A resolução para esse erro é exclusiva da fonte de dados. Por exemplo, se você estiver importando dados do SQL Server e vir colunas em branco, poderá tentar converter para o tipo de dados correto na consulta.

Em vez de usar esta consulta:

`SELECT CustomerPostalCode FROM Sales.Customers`

Use esta consulta:

`SELECT CAST(CustomerPostalCode as varchar(10)) FROM Sales.Customers`

Ao especificar o tipo correto na fonte de dados, você elimina muitos desses erros comuns de fonte de dados.

Você pode encontrar diferentes tipos de erros no Power BI, que são causados por diversos sistemas de fonte de dados nos quais os dados residem. Se você encontrar um erro que não foi discutido nas seções anteriores, pesquise a mensagem de erro na documentação da Microsoft para encontrar a resolução necessária.
