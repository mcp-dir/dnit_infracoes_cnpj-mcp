---
name: dnit_infracoes_cnpj-mcp
description: Skill da REST API do DNIT: Infrações (CNPJ) na MCP.AI: 1 endpoint em /api/dnit_infracoes_cnpj. DNIT: Infrações (CNPJ), consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# DNIT: Infrações (CNPJ) — REST API skill

Você tem acesso à **DNIT: Infrações (CNPJ)** REST API na MCP.AI.

> DNIT: Infrações (CNPJ), consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/dnit_infracoes_cnpj
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
curl -X POST https://api.mcp.ai/api/dnit_infracoes_cnpj/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"cnpj":"...","razao_social":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/dnit_infracoes_cnpj/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `dnit_infracoes_cnpj_consultar`

DNIT: Infrações (CNPJ), consulta em fonte oficial. _(POST /api/dnit_infracoes_cnpj/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `login_cpf` | string | Não | Parâmetro de consulta "login_cpf". |
| `login_senha` | string | Não | Parâmetro de consulta "login_senha". |
| `pkcs12_cert` | string | Não | Parâmetro de consulta "pkcs12_cert". |
| `pkcs12_pass` | string | Não | Parâmetro de consulta "pkcs12_pass". |
| `cnpj` | string | Sim | Parâmetro de consulta "cnpj". |
| `razao_social` | string | Sim | Parâmetro de consulta "razao_social". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_dnit_infracoes_cnpj` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
