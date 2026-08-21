# Consulta de Multas

### Consulta de Multas for Claude, ChatGPT and AI agents

Look up PUBLIC vehicle and traffic data from official sources, the same information a citizen accesses at DETRAN/PRF: debts (IPVA, licensing, open fines) and infractions by plate/RENAVAM, vehicles registered to an owner, and driver's license status. Built for the holder to check their own vehicle/license. Platform-hosted, no credentials, pay per query with prepaid credit.

- 📊 **5 tools**
- 🔒 **Read-only**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `Consulta de Multas`, URL `https://api.mcp.ai/p_multas`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=multas&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9tdWx0YXMifQ==)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=multas&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_multas%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_multas
```

---

## 5 tools

| Tool | Description |
|---|---|
| `multas_debitos_veiculo` | Consulta PÚBLICA de débitos e situação de um veículo pela placa em bases oficiais: IPVA, licenciamento, multas em aberto, restrições e dados do veículo (marca/modelo, ano). |
| `multas_infracoes_federais` | Consulta pública de infrações/multas de trânsito em rodovias federais (Polícia Rodoviária Federal) por placa + RENAVAM. |
| `multas_pontos_cnh` | Consulta a situação da CNH (Carteira Nacional de Habilitação) pelo CPF do próprio condutor em base oficial: número de registro, categoria, validade e situação. |
| `multas_veiculos_proprietario` | Lista os veículos registrados no nome de um CPF ou CNPJ em base oficial. |
| `multas_historico_veiculo` | Consulta o histórico veicular (SP) por CPF ou CNPJ do proprietário em base oficial. |

---

## Pricing

See [docs/precos.md](docs/precos.md) (PT-BR).

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_multas` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
