# Roteiro do projeto

Esta POC está em evolução. O roteiro abaixo separa a **implementação validada**, o **trabalho atual de testes**, as **alternativas exploradas** e as **etapas futuras**.

## Implementação validada

- Preparação do ambiente de integração / máquina virtual
- Configuração do ambiente Qlik Talend Cloud
- Conectividade com a origem MySQL local
- Conectividade com o destino Azure SQL Database
- Configuração do Qlik Data Movement
- Transferência bem-sucedida de dados do MySQL para o Azure
- Validação dos dados no destino Azure
- Investigação e resolução de problemas de conectividade e movimentação

## Etapa atual de testes

- Configurar o **SQL Server como destino de testes de menor custo**
- Manter o **MySQL local como origem**
- Configurar e validar o comportamento dos pipelines utilizando o SQL Server como destino de testes
- Testar a orquestração de pipelines e cenários de transformação
- Validar o fluxo de dados nas etapas seguintes

## Alternativa explorada

- Configuração / exploração do ambiente AWS
- Cenário de destino com Apache Iceberg
- **Status:** não finalizado devido ao custo adicional de infraestrutura para a POC

## Expansão planejada no Qlik Cloud

- Produtos de Dados (Data Products)
- Consumo analítico no Qlik Cloud
- Qlik Automate
- Fluxos de relatórios
- Qlik Answers

## Princípio de documentação

Somente etapas implementadas e validadas tecnicamente são marcadas como concluídas neste repositório. O trabalho atual de testes, as alternativas exploradas e as funcionalidades planejadas são explicitamente separados da implementação validada.
