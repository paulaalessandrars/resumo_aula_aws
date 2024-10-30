# Projeto: Criação de um Assistente de Delivery com AWS Step Functions e Amazon Bedrock

Participei de uma aula prática aprofundada sobre a criação de um Assistente de Delivery utilizando **AWS Step Functions** e **Amazon Bedrock**, focando na orquestração de serviços AWS para automatizar e gerenciar um fluxo de pedidos de delivery de ponta a ponta. A aula apresentou, passo a passo, como integrar diferentes componentes da AWS para construir uma solução escalável, eficiente e personalizável.

## 1. Introdução ao Projeto e Objetivos  
O instrutor iniciou explicando os objetivos do projeto, que incluíam a construção de um assistente capaz de gerenciar todas as etapas de um pedido de delivery, desde a recepção inicial até a entrega ao cliente. Foi destacado o papel das **AWS Step Functions** como orquestrador principal para organizar o fluxo de trabalho, coordenando a interação entre vários serviços AWS. Além disso, foi ressaltada a utilização do **Amazon Bedrock** para aplicar inteligência artificial e melhorar a experiência do usuário, através de personalização e automação.

## 2. Arquitetura do Projeto  
A aula prosseguiu com a apresentação da arquitetura geral do sistema. Foi mostrado um diagrama que explicava como as **AWS Step Functions** interagiam com outros serviços da AWS, como **AWS Lambda**, **Amazon S3**, **Amazon SNS**, **Amazon DynamoDB** e **Amazon Bedrock**. Cada serviço tinha um papel específico no fluxo, e o instrutor detalhou como o uso combinado dessas tecnologias tornava o assistente eficiente e escalável.

- **AWS Step Functions**: Serviço central responsável por coordenar as tarefas do fluxo de trabalho, como validação, pagamentos, notificações e atualizações de status.
- **AWS Lambda**: Funções criadas para executar lógicas específicas, como validação de estoque e cálculo de tarifas.
- **Amazon DynamoDB**: Utilizado para armazenar dados críticos dos pedidos, como informações do cliente, status atual do pedido e detalhes de pagamento.
- **Amazon SNS (Simple Notification Service)**: Configurado para enviar notificações em tempo real aos clientes sobre o status dos seus pedidos.
- **Amazon Bedrock**: Empregado para adicionar camadas de personalização e automação por meio de modelos de IA, fornecendo recomendações e respostas automatizadas.

## 3. Implementação do Fluxo de Pedidos com AWS Step Functions  
O instrutor mostrou, em detalhes, como criar e configurar um fluxo de trabalho usando **AWS Step Functions**. Foi ensinado como definir estados de tarefas (`Task States`) para cada etapa do fluxo, incluindo:

- **Recepção e Validação do Pedido**: Uma função Lambda era acionada para verificar se todos os itens estavam disponíveis em estoque.
- **Cálculo de Frete e Impostos**: Outra função Lambda realizava cálculos de frete e impostos com base na localização do cliente.
- **Integração com Serviço de Pagamento**: Foi detalhado como integrar com um serviço de pagamento para processar as transações.
- **Atualização do Status do Pedido**: Sempre que uma etapa era concluída, a Step Function atualizava o status do pedido em uma tabela do DynamoDB e disparava uma notificação via SNS para informar o cliente.
- **Entrega**: A última etapa do fluxo era coordenar a logística da entrega, enviando atualizações em tempo real para o cliente.

## 4. Utilização do Amazon Bedrock para Personalização e IA  
A aula demonstrou como o **Amazon Bedrock** foi utilizado para aprimorar o assistente com inteligência artificial. O instrutor mostrou como integrar modelos de IA que ofereciam recomendações personalizadas com base nas preferências anteriores dos clientes. Além disso, o Bedrock foi empregado para configurar respostas automatizadas a perguntas comuns, como o status do pedido ou o horário estimado de entrega.

O Amazon Bedrock foi fundamental para aplicar técnicas de **Machine Learning** e **Natural Language Processing (NLP)**, o que resultou em um assistente mais dinâmico e envolvente para o cliente.

## 5. Configuração da Persistência e Monitoramento  
O instrutor também abordou como configurar o armazenamento dos dados dos pedidos utilizando o **Amazon DynamoDB**. Foi mostrado como criar tabelas com chaves de partição adequadas para garantir acesso rápido e eficiente às informações dos pedidos. Além disso, foi abordada a configuração de logs e monitoramento com o **Amazon CloudWatch**, permitindo a detecção de falhas e acompanhamento do desempenho do fluxo.

## 6. Demonstração Completa do Projeto  
Na etapa final, o instrutor executou o fluxo completo, simulando um pedido de delivery real. A demonstração cobriu desde a inserção dos detalhes do pedido até o processamento do pagamento, atualização dos status, envio de notificações e, finalmente, a conclusão da entrega. A integração entre os serviços foi exibida em tempo real, ilustrando como cada serviço desempenhava seu papel em coordenação com os outros.

## 7. Melhores Práticas e Lições Aprendidas  
Ao final da aula prática, foram discutidas as melhores práticas para projetar fluxos com Step Functions, como o uso de estados de espera (`Wait States`) para sincronizar tarefas, a importância de lidar com falhas e exceções (`Catch` e `Retry`), e a necessidade de monitorar e otimizar o desempenho usando o **Amazon CloudWatch**. Além disso, o instrutor compartilhou insights sobre como escolher os modelos adequados no **Amazon Bedrock** para atender às necessidades específicas de personalização e automação.

---

Essa aula prática proporcionou uma visão completa sobre como desenvolver e integrar um Assistente de Delivery utilizando os serviços da AWS, demonstrando o poder das **Step Functions** na coordenação de fluxos complexos e o potencial do **Amazon Bedrock** para adicionar inteligência e personalização ao sistema.
