# Ferramentas

Consulta de Multas expõe 5 ferramentas (todas somente leitura).

### 1. `multas_debitos_veiculo`
**Input**: `PLACA`, `completo` (opcional)

Consulta PÚBLICA de débitos e situação de um veículo pela placa em bases oficiais: IPVA, licenciamento, multas em aberto, restrições e dados do veículo (marca/modelo, ano).

### 2. `multas_infracoes_federais`
**Input**: `PLACA`, `RENAVAM`, `TIPO`, `completo` (opcional)

Consulta pública de infrações/multas de trânsito em rodovias federais (Polícia Rodoviária Federal) por placa + RENAVAM.

### 3. `multas_pontos_cnh`
**Input**: `CPF`, `completo` (opcional)

Consulta a situação da CNH (Carteira Nacional de Habilitação) pelo CPF do próprio condutor em base oficial: número de registro, categoria, validade e situação.

### 4. `multas_veiculos_proprietario`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `completo` (opcional)

Lista os veículos registrados no nome de um CPF ou CNPJ em base oficial.

### 5. `multas_historico_veiculo`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `completo` (opcional)

Consulta o histórico veicular (SP) por CPF ou CNPJ do proprietário em base oficial.

## Prompts de exemplo

```
Quais os débitos e multas do meu carro, placa ABC1D23?
Meu veículo tem multas em rodovia federal? Placa ABC1D23, RENAVAM 12345678901
Quais veículos estão registrados no meu CPF?
```
