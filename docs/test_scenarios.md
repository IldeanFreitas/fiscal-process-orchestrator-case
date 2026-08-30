# Cenários de teste

| ID | Cenário | Resultado esperado |
| --- | --- | --- |
| FP-01 | Importar um job estruturalmente válido | Job é criado em `pending` com `job_key` e `correlation_id` |
| FP-02 | Reimportar o mesmo `job_key` | Nenhum segundo job lógico é criado |
| FP-03 | Worker compatível reserva um job | Estado muda para `claimed` e o bloqueio ganha expiração |
| FP-04 | Worker incompatível tenta reservar | Reserva é recusada sem alterar o job |
| FP-05 | Worker inicia e conclui | Estado evolui de `running` para `succeeded` |
| FP-06 | Falha recuperável antes do limite | Estado muda para `retry_pending`, tentativa é incrementada |
| FP-07 | Falha após o limite | Estado final é `failed`; o job não retorna automaticamente à fila |
| FP-08 | Worker fica indisponível após reserva | Expiração do bloqueio devolve o job a `pending` |
| FP-09 | Operador cancela job pendente | Estado muda para `cancelled`, sem exclusão física |
| FP-10 | Registro de evidência | Apenas referência protegida e metadados permitidos são registrados |
