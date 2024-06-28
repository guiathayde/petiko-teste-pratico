### Caso de Uso Fictício: Controle de Estoque em Tempo Real

#### Contexto:

Imagine que na Petiko, os clientes precisam manter o controle de estoque atualizado em tempo real para gerenciar eficientemente os recursos da empresa. O sistema ERP usado pelos clientes será integrado com uma API REST que permite verificar a disponibilidade de itens e atualizar o estoque.

#### Operações da API:

1. **Consulta de Itens**: Verificar a disponibilidade de um item específico no estoque.
2. **Atualização de Estoque**: Registrar a entrada ou saída de itens no estoque.

### Configuração no Postman:

#### Passo 1: Consulta de Itens

- **Método HTTP**: GET
- **URL**: `https://api.petiko.com/estoque/consulta`
- **Parâmetros**:
  - `item_id` (ID do item a ser consultado, por exemplo, `12345`)
- **Cabeçalhos**:
  - `Content-Type: application/json`
  - `Authorization: Bearer <token_de_acesso>`

#### Execução:

1. Abra o Postman e configure uma nova solicitação GET.
2. Insira a URL e os parâmetros conforme especificado acima.
3. Adicione os cabeçalhos necessários.
4. Envie a solicitação e observe a resposta. A resposta esperada seria algo como:
   ```json
   {
     "item_id": "12345",
     "nome": "Ração para Cães",
     "quantidade_disponível": 100
   }
   ```

#### Passo 2: Atualização de Estoque

- **Método HTTP**: POST
- **URL**: `https://api.petiko.com/estoque/atualizacao`
- **Corpo da Solicitação**:
  ```json
  {
    "item_id": "12345",
    "quantidade": -20
  }
  ```
  (Este exemplo assume que 20 unidades do item foram vendidas.)
- **Cabeçalhos**:
  - `Content-Type: application/json`
  - `Authorization: Bearer <token_de_acesso>`

#### Execução:

1. Configure uma nova solicitação POST no Postman.
2. Insira a URL e prepare o corpo da solicitação conforme descrito.
3. Adicione os cabeçalhos.
4. Envie a solicitação e verifique a resposta. Uma resposta bem-sucedida seria:
   ```json
   {
     "item_id": "12345",
     "quantidade_atualizada": 80
   }
   ```
