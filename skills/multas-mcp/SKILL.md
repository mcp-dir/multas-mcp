---
name: multas-mcp
description: Skill da REST API do Consulta de Multas na MCP.AI: 5 endpoints em /api/multas. Consulta de dados PÚBLICOS de veículos e trânsito em bases oficiais, a mesma informação que o cidadão acessa no DETRAN/PRF: débitos (IPVA, licenciamento, multas em aberto) e infrações por placa/RENAVAM, veículos no nome do proprietário e situação da CNH. Feito para o titular consultar o próprio veículo/habilitação. Hospedado pela plataforma, sem credenciais, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Consulta de Multas — REST API skill

Você tem acesso à **Consulta de Multas** REST API na MCP.AI.

> Consulta de dados PÚBLICOS de veículos e trânsito em bases oficiais, a mesma informação que o cidadão acessa no DETRAN/PRF: débitos (IPVA, licenciamento, multas em aberto) e infrações por placa/RENAVAM, veículos no nome do proprietário e situação da CNH. Feito para o titular consultar o próprio veículo/habilitação. Hospedado pela plataforma, sem credenciais, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/multas
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/multas/debitos/veiculo \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"PLACA":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/multas/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (5)

#### `multas_debitos_veiculo`

Consulta PÚBLICA de débitos e situação de um veículo pela placa em bases oficiais: IPVA, licenciamento, multas em aberto, restrições e dados do veículo (marca/modelo, ano). _(POST /api/multas/debitos/veiculo)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `PLACA` | string | Sim | Placa do veículo (Mercosul ou antiga), com ou sem formatação. |
| `completo` | boolean | Não | Opcional. Por padrão (false) listas longas vêm resumidas aos primeiros itens, com a contagem total preservada. Use true para a resposta COMPLETA na mesma consulta. |

#### `multas_historico_veiculo`

Consulta o histórico veicular (SP) por CPF ou CNPJ do proprietário em base oficial. _(POST /api/multas/historico/veiculo)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | CPF do proprietário, com ou sem formatação. |
| `CNPJ` | string | Não | CNPJ do proprietário, com ou sem formatação. |
| `completo` | boolean | Não | Opcional. Por padrão (false) listas longas vêm resumidas aos primeiros itens, com a contagem total preservada. Use true para a resposta COMPLETA na mesma consulta. |

#### `multas_infracoes_federais`

Consulta pública de infrações/multas de trânsito em rodovias federais (Polícia Rodoviária Federal) por placa + RENAVAM. _(POST /api/multas/infracoes/federais)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `PLACA` | string | Sim | Placa do veículo, com ou sem formatação. |
| `RENAVAM` | string | Sim | RENAVAM do veículo (11 dígitos numéricos). |
| `TIPO` | string | Sim | Tipo de consulta de infrações a retornar. |
| `completo` | boolean | Não | Opcional. Por padrão (false) listas longas vêm resumidas aos primeiros itens, com a contagem total preservada. Use true para a resposta COMPLETA na mesma consulta. |

#### `multas_pontos_cnh`

Consulta a situação da CNH (Carteira Nacional de Habilitação) pelo CPF do próprio condutor em base oficial: número de registro, categoria, validade e situação. _(POST /api/multas/pontos/cnh)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Sim | CPF do condutor, com ou sem formatação. |
| `completo` | boolean | Não | Opcional. Por padrão (false) listas longas vêm resumidas aos primeiros itens, com a contagem total preservada. Use true para a resposta COMPLETA na mesma consulta. |

#### `multas_veiculos_proprietario`

Lista os veículos registrados no nome de um CPF ou CNPJ em base oficial. _(POST /api/multas/veiculos/proprietario)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | CPF do proprietário, com ou sem formatação. |
| `CNPJ` | string | Não | CNPJ do proprietário, com ou sem formatação. |
| `completo` | boolean | Não | Opcional. Por padrão (false) listas longas vêm resumidas aos primeiros itens, com a contagem total preservada. Use true para a resposta COMPLETA na mesma consulta. |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_multas` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
