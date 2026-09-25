# Narrativa para portfólio

## Contexto

Orquestração fiscal com aplicativo Power Apps, fila no Dataverse, orquestrador em nuvem e robô RPA. O projeto de origem está **em produção**, numa versão simplificada: um lote por disparo, selecionado por três status, um robô desacompanhado no portal nacional de NFS-e e deduplicação por chave alternativa por nota.

## Papel

Com meu time, fiz a importação, o aplicativo, o modelo de dados no Dataverse e o contrato de status com o robô. O orquestrador e o robô são de outra equipe (time de automação).

## O que este repositório é

A arquitetura-alvo da próxima evolução, reconstruído sem dado de cliente: fila de trabalhos com reserva com prazo, workers por categoria de portal, evidências protegidas e retorno automático à fila de reserva vencida. O contrato da fila, a amostra e os cenários de teste descrevem esse alvo, não a versão em produção.

## Evidências verificáveis

- [Diagrama e estados](architecture.md)
- [Schema do job](../models/fiscal_job.schema.json)
- [Amostra sintética](../samples/fiscal_job.sample.json)
- [Cenários de teste](test_scenarios.md)
- [Checklist de segurança](public_safety.md)

## Limitação explícita

O case não publica aplicativo, fluxos, robôs, credenciais, portais, arquivos ou resultados de uma operação real. Volume e tempo de ciclo não são divulgados.
