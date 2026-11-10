# Escopo validado do projeto

Este arquivo é a referência oficial da documentação pública deste projeto de prova de conceito (POC) com Qlik Talend Cloud, ainda em andamento.

## Implementação validada

- Origem operacional: **MySQL em execução em ambiente local (on-premises)**
- Plataforma de integração: **Qlik Talend Cloud (QTC)**
- Camada de integração local: **Qlik Data Gateway / ambiente de máquina virtual**
- Recurso de integração de dados: **Qlik Data Movement**
- Padrão de replicação: **carga inicial + CDC (Change Data Capture)**
- Destino validado: **Azure SQL Database**
- Resultado validado: **a movimentação de dados do MySQL local para o Azure SQL Database está funcionando**
- Alterações incrementais na origem foram propagadas por meio de CDC durante a validação da POC
- A transferência de dados e a validação no destino foram realizadas com sucesso
- A resolução de problemas de conectividade e configuração fez parte da implementação

Não se deve afirmar a existência de SLA de latência de produção ou desempenho estritamente em tempo real com base nesta POC.

## Próxima etapa atual

- Manter o **MySQL local** como origem
- Utilizar o **SQL Server como destino de testes**
- Motivo da mudança de destino: reduzir os custos de infraestrutura durante a continuidade da POC
- Principal objetivo técnico: configurar e validar **testes de pipelines / orquestração** no Qlik Talend Cloud
- Continuar validando o comportamento da replicação incremental / CDC à medida que a arquitetura de testes evoluir

O SQL Server deve ser descrito como destino da etapa de testes atual/próxima até que o novo fluxo e o comportamento dos pipelines sejam validados tecnicamente.

## Alternativas exploradas, mas não finalizadas

- Ambiente **AWS**
- **Qlik Open Lakehouse**
- Cenário de destino com **Apache Iceberg**
- Configuração / exploração de uma carga de trabalho de CDC na arquitetura Open Lakehouse
- Motivo da não finalização: custo adicional de infraestrutura para a prova de conceito

Esse caminho não deve ser descrito como uma implementação de movimentação de dados concluída.

## Etapas futuras após a validação dos pipelines

- Cenários adicionais de transformação / preparação de dados
- Produtos de Dados (Data Products)
- Consumo analítico no Qlik Cloud para esta POC
- Qlik Automate
- Fluxos de relatórios
- Qlik Answers

## Regra de documentação

A documentação pública só deve descrever um item como implementado ou funcionando quando ele tiver sido concluído e validado tecnicamente no projeto real. Direcionamentos atuais de testes, alternativas exploradas e funcionalidades planejadas devem sempre ser identificados separadamente.
