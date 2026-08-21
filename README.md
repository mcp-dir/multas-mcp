# Consulta de Multas

### Consulta de Multas para Claude, ChatGPT e agentes de IA

Consulta de dados PÚBLICOS de veículos e trânsito em bases oficiais, a mesma informação que o cidadão acessa no DETRAN/PRF: débitos (IPVA, licenciamento, multas em aberto) e infrações por placa/RENAVAM, veículos no nome do proprietário e situação da CNH. Feito para o titular consultar o próprio veículo/habilitação. Hospedado pela plataforma, sem credenciais, pague por consulta com crédito pré-pago.

- 📊 **5 ferramentas**
- 🔒 **Somente leitura**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `Consulta de Multas` e **URL** `https://api.mcp.ai/p_multas`.

### Cursor

[➕ Instalar Consulta de Multas no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=multas&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9tdWx0YXMifQ==)

### VS Code (Copilot Chat)

[➕ Instalar Consulta de Multas no VS Code](vscode:mcp/install?name=multas&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_multas%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_multas
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Quais os débitos e multas do meu carro, placa ABC1D23?
Meu veículo tem multas em rodovia federal? Placa ABC1D23, RENAVAM 12345678901
Quais veículos estão registrados no meu CPF?
```

---

## 5 ferramentas disponíveis

| Tool | Descrição |
|---|---|
| `multas_debitos_veiculo` | Consulta PÚBLICA de débitos e situação de um veículo pela placa em bases oficiais: IPVA, licenciamento, multas em aberto, restrições e dados do veículo (marca/modelo, ano). |
| `multas_infracoes_federais` | Consulta pública de infrações/multas de trânsito em rodovias federais (Polícia Rodoviária Federal) por placa + RENAVAM. |
| `multas_pontos_cnh` | Consulta a situação da CNH (Carteira Nacional de Habilitação) pelo CPF do próprio condutor em base oficial: número de registro, categoria, validade e situação. |
| `multas_veiculos_proprietario` | Lista os veículos registrados no nome de um CPF ou CNPJ em base oficial. |
| `multas_historico_veiculo` | Consulta o histórico veicular (SP) por CPF ou CNPJ do proprietário em base oficial. |

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Pré-pago (carteira de créditos), paga por uso. Veja [docs/precos.md](docs/precos.md).

---

## Privacidade & LGPD

- **Somente leitura**, nenhuma ferramenta altera dados na origem.
- **Sub-processadores**: o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_multas`.


---

## Suporte

- 📧 [multas@mcp.ai](mailto:multas@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/multas-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_multas` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
