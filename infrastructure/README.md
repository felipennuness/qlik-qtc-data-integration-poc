# Infraestrutura e conectividade

## Escopo

Esta seção documenta o trabalho de infraestrutura e conectividade realizado durante a etapa atual da POC.

## Ambiente validado

- **Qlik Talend Cloud**
- **Máquina virtual / ambiente de integração**
- **MySQL local (on-premises)** como origem
- **Azure SQL Database** como destino

## Trabalho concluído

- Preparação do ambiente de integração necessário para a POC.
- Utilização de uma máquina virtual como parte da arquitetura de integração.
- Configuração da conexão com a origem MySQL local.
- Configuração da conexão com o destino Azure SQL Database.
- Validação da conectividade entre o ambiente local, o Qlik Talend Cloud e o Azure.
- Diagnóstico e correção de problemas de conectividade e configuração encontrados durante a preparação.
- Confirmação de que o ambiente suportava o fluxo de movimentação de dados do MySQL para o Azure.

## Abordagem para validação da conectividade

```text
MySQL local disponível
        ↓
Conectividade com a origem validada
        ↓
Conexão com Qlik Talend Cloud configurada
        ↓
Conexão com Azure SQL Database configurada
        ↓
Origem e destino testados
        ↓
Data Movement configurado
        ↓
Transferência para o Azure validada
```

## AWS + Apache Iceberg

Uma arquitetura alternativa com AWS e Apache Iceberg também foi configurada e explorada. Ela não foi finalizada porque a manutenção dos recursos AWS necessários acrescentaria custos à prova de conceito.

Portanto, esse caminho com AWS não é apresentado como parte de um fluxo concluído e pronto para produção.

## Observação para o portfólio público

Strings de conexão, credenciais, endereços IP, informações do tenant, nomes de servidores, portas específicas do cliente, nomes de bancos de dados e detalhes da rede interna são intencionalmente omitidos deste repositório.
