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
