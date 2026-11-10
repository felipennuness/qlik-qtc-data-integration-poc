# Movimentação de dados com Qlik

## Marco atual: funcionando

O principal marco técnico alcançado até o momento nesta POC é a **movimentação bem-sucedida de dados de um banco MySQL local para o Azure SQL Database**, incluindo a replicação incremental de alterações por meio de **CDC (Change Data Capture, ou Captura de Dados Alterados)**.

## Origem

A origem operacional é um **banco de dados MySQL em execução em ambiente local (on-premises)**. O Qlik Data Gateway fornece a camada de integração necessária para que o Qlik Talend Cloud acesse e replique dados desse ambiente.

## Trabalho concluído

- Configuração da conexão com a origem MySQL local no Qlik Talend Cloud.
- Configuração da conexão com o destino Azure SQL Database.
- Definição do fluxo de movimentação de dados entre origem e destino.
- Execução da movimentação inicial de dados do MySQL para o Azure.
- Configuração e validação de **CDC / replicação incremental de alterações** posteriores na origem.
- Confirmação de que a transferência foi bem-sucedida na etapa atual da POC.
- Validação dos dados movimentados no destino Azure.
- Investigação e resolução de problemas de conectividade e configuração durante a implementação.

## Fluxo validado

```text
MySQL local (on-premises)
      ↓
Qlik Data Gateway
      ↓
Qlik Talend Cloud
      ↓
Carga inicial + CDC
      ↓
Qlik Data Movement
      ↓
Azure SQL Database
      ↓
Validação no destino
```

## CDC — Captura de Dados Alterados

O CDC permite que o fluxo de integração capture as alterações realizadas na origem após a carga inicial e as propague incrementalmente para o destino.

Nesta POC, o CDC é importante porque demonstra um padrão de replicação que evita executar uma carga completa sempre que os dados operacionais são alterados.

O portfólio **não afirma a existência de SLA de latência de produção nem comportamento estritamente em tempo real**. O resultado documentado é a implementação funcional e a validação da replicação incremental de alterações na prova de conceito.

## Exploração de AWS + Apache Iceberg

Um cenário separado de destino com AWS + Apache Iceberg foi configurado e explorado durante o projeto utilizando o Qlik Open Lakehouse. A exploração também incluiu uma **carga de trabalho de CDC**.

Essa alternativa **não foi finalizada devido ao custo adicional de infraestrutura para a POC** e, por isso, está documentada como exploração de arquitetura, e não como um fluxo de movimentação de dados concluído.

## Por que esta etapa é importante

Antes de desenvolver transformações, pipelines, análises, relatórios ou casos de uso com inteligência artificial, a arquitetura precisava primeiro movimentar os dados da origem operacional local para um ambiente de destino de forma confiável e propagar as alterações posteriores de maneira incremental.

O fluxo bem-sucedido de MySQL para Azure com CDC estabelece essa base.

## Próxima etapa técnica

A próxima etapa mantém o **MySQL local como origem** e utiliza o **SQL Server como destino de testes de menor custo**, enquanto o projeto avança nos testes de pipelines, orquestração, transformações e continuidade do CDC.
