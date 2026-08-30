# Narrativa para portfólio

## Contexto

Arquitetura em evolução para processar documentos fiscais por meio de uma fila rastreável, com importação, distribuição de trabalho, execução RPA e acompanhamento operacional.

## Responsabilidade representada

Recriação pública da arquitetura, do contrato de fila e das regras de idempotência, retentativa e observabilidade para demonstrar o padrão técnico sem divulgar ativos internos.

## Solução

O fluxo separa a importação de um lote do processamento assíncrono. O orquestrador seleciona jobs pendentes, reserva cada job para um worker compatível e consolida o retorno em uma fila monitorável.

## Evidências verificáveis

- [Diagrama e estados](architecture.md)
- [Schema do job](../models/fiscal_job.schema.json)
- [Amostra sintética](../samples/fiscal_job.sample.json)
- [Cenários de teste](test_scenarios.md)
- [Checklist de segurança](public_safety.md)

## Limitação explícita

O case não publica aplicativo, fluxos, robôs, credenciais, portais, arquivos ou resultados de uma operação real. Portanto, permanece classificado como **Em evolução**.
