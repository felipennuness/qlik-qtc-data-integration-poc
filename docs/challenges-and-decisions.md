# Desafios e decisões técnicas

Este documento resume as decisões técnicas tomadas durante a atual prova de conceito com Qlik Talend Cloud. Ele considera apenas atividades que foram efetivamente realizadas ou explicitamente planejadas no projeto.

## 1. Conexão de uma origem local ao Qlik Cloud

A origem do projeto é um **banco de dados MySQL em execução em ambiente local (on-premises)**. Antes de validar qualquer movimentação de dados para a nuvem, o ambiente de integração precisava fornecer conectividade confiável entre o banco de dados local e o Qlik Talend Cloud.

### Trabalho realizado

- Preparação da máquina virtual / ambiente de integração.
- Instalação e configuração do Qlik Data Gateway para Data Movement.
- Validação de que o serviço do gateway estava em execução corretamente.
- Configuração e teste da conexão com a origem MySQL.
- Investigação e resolução de problemas de conectividade e configuração antes de habilitar a replicação.

## 2. Primeiro destino validado: Azure SQL Database

O primeiro fluxo de movimentação de dados de ponta a ponta utilizou o **Azure SQL Database** como destino na nuvem.

### Fluxo validado

```text
MySQL local (on-premises)
        ↓
Qlik Data Gateway / Ambiente de integração
        ↓
Qlik Talend Cloud
        ↓
Qlik Data Movement
        ↓
Azure SQL Database
```

O fluxo de replicação foi criado e executado com sucesso, e os dados transferidos foram validados diretamente no Azure SQL Database.

## 3. Exploração de AWS + Apache Iceberg

Uma segunda arquitetura foi explorada utilizando **infraestrutura AWS com Qlik Open Lakehouse / Apache Iceberg**.

A exploração incluiu atividades relacionadas a:

- Configuração de VPC e sub-redes na AWS
- Integração de rede com o Qlik
- Funções e permissões do IAM
- Preparação do armazenamento no S3
- Configuração do KMS
- Criação de cluster do Qlik Open Lakehouse
- Configuração de carga de trabalho de lakehouse orientada a CDC

O caminho AWS / Iceberg **não foi finalizado**, pois a continuidade da infraestrutura necessária para a POC aumentaria os custos. Portanto, permanece como uma arquitetura explorada, e não como uma implementação concluída.

## 4. Direcionamento atual: SQL Server para testes de pipelines

Para dar continuidade à POC controlando os custos de infraestrutura, o próximo destino de testes será o **Microsoft SQL Server**.

O objetivo desta etapa é utilizar o SQL Server como destino de testes de menor custo e avançar em:

- configuração de pipelines
- orquestração de pipelines
- cenários de transformação
- validação dos dados nas etapas seguintes

Esta etapa é o próximo marco técnico do projeto e não deve ser descrita como concluída até que tenha sido implementada e validada.

## 5. Princípio de documentação

Este portfólio diferencia claramente três situações:

- **Validado:** implementado e verificado tecnicamente no projeto.
- **Explorado:** configurado ou investigado, mas não concluído de ponta a ponta.
- **Planejado / em andamento:** próximas etapas pretendidas, ainda não validadas.

Essa distinção é mantida em todo o repositório para que o estudo de caso público permaneça tecnicamente correto.
