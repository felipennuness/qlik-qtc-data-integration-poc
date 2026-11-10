# Arquitetura

## Objetivo

Esta seção documenta a arquitetura da POC de integração de dados com Qlik Talend Cloud, contemplando as etapas já validadas e as etapas de testes atuais.

A documentação pública abstrai intencionalmente os detalhes específicos do cliente, preservando o fluxo técnico real que foi implementado e o próximo ambiente em preparação.

## Etapa 1 — Arquitetura validada

```text
+-----------------------------+
| Ambiente local               |
|-----------------------------|
| Banco de dados MySQL         |
| Origem operacional           |
+-------------+---------------+
              |
              v
+-----------------------------+
| Qlik Data Gateway / VM      |
| Ambiente de conectividade   |
+-------------+---------------+
              |
              v
+-----------------------------+
| Qlik Talend Cloud           |
| Configuração das conexões   |
+-------------+---------------+
              |
              v
+-----------------------------+
| Carga inicial + CDC         |
| Captura de dados alterados  |
+-------------+---------------+
              |
              v
+-----------------------------+
| Qlik Data Movement          |
| Replicação incremental      |
+-------------+---------------+
              |
              v
+-----------------------------+
| Azure SQL Database          |
| Destino validado            |
+-------------+---------------+
              |
              v
+-----------------------------+
| Validação                   |
+-----------------------------+
```

Este fluxo de **MySQL local → Azure SQL Database** é a arquitetura validada como funcional na Etapa 1.

### Papel do CDC na arquitetura

O desenho da replicação utiliza **CDC (Change Data Capture, ou Captura de Dados Alterados)** após a carga inicial, permitindo capturar e propagar incrementalmente para o destino as mudanças realizadas na origem operacional MySQL.

Assim, cada alteração na origem não exige uma nova carga completa de todo o conjunto de dados. A POC valida o comportamento funcional da replicação, mas não estabelece um SLA de latência de produção nem uma garantia de processamento estritamente em tempo real.

## Etapa 2 — Direcionamento atual dos testes

Para dar continuidade à POC com menor custo de infraestrutura, a próxima arquitetura de testes utilizará o **SQL Server como destino**, mantendo o MySQL local como origem.

O principal objetivo desta etapa é configurar e validar **pipelines do Qlik Talend Cloud, orquestração, transformações e a continuidade dos testes de CDC / replicação incremental**.

```text
MySQL local (on-premises)
      |
      v
Qlik Data Gateway / VM
      |
      v
Qlik Talend Cloud
      |
      v
Testes de Data Movement / CDC / Pipelines
      |
      v
SQL Server
```

Esta etapa não deve ser descrita como totalmente implementada até que o destino SQL Server e o comportamento dos pipelines tenham sido validados tecnicamente.

## Arquitetura alternativa explorada

Um caminho separado utilizando **AWS + Qlik Open Lakehouse + Apache Iceberg** foi configurado e explorado durante a POC. A configuração do Open Lakehouse incluiu uma carga de trabalho de **CDC**.

Essa alternativa não foi finalizada devido ao custo adicional necessário para manter a infraestrutura.

```text
MySQL local (on-premises)
      |
      v
Qlik Talend Cloud
      |
      v
Qlik Open Lakehouse / CDC
      |
      v
AWS + Apache Iceberg
      |
      v
Não finalizado devido aos custos da POC
```

## Limites e status atuais

- **Validado:** MySQL local → Azure SQL Database por meio do Qlik Data Movement, com CDC / replicação incremental.
- **Próxima etapa atual de testes:** MySQL local → SQL Server, com foco em pipelines e continuidade dos testes de CDC.
- **Explorado, mas não finalizado:** AWS + Qlik Open Lakehouse + Apache Iceberg.
- **Etapas futuras:** Produtos de Dados (Data Products), consumo analítico, Qlik Automate, relatórios e Qlik Answers.
