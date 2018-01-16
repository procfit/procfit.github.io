## Consulta de Cliente Cosmos Pro Web API

A consulta de consulta de cliente da API Cosmos Pro é realizada utilizando o conceito de CustomViews.
É necessário o envio do Token no header, e os parâmetros Loja e Busca no body da mensagem em formato JSON ou XML

##### :outbox_tray: Requisição


- **Url** 

*http:// **[ambiente]**.cosmospro.com.br:**[porta]**/odata/CustomViews(Name=**'ConsultaCliente'**)/ExecuteAndReceive()?api-version=1.0*

    > ### :grey_exclamation: Informação
    > Os valor **"ConsultaCliente"** fornecido para o parametro *Name* da ação *ExecuteAndReceive*.

---

- **Parametros URL Base**

|Nome|Tipo|Observação
|------ |------|------|
|Name|String|Nome da CustomView a ser acionada. 

---

- **Método** 

*Post*
---

- **Cabeçalhos(Headers):**

|Nome|Valor|Observação
|------|------|------|
|Content-Type|application/json| Tipo de Conteúdo da requisição.
|Authorization|Bearer [Token]| Token de Autenticação obtido junto ao Administrador do Inquilino Cosmos Pro

---

- **Parâmetros de Entrada(Request):**

|Campo|Descrição|Tipo|Valores|
|------|------|------|------|
|LOJA|Código do estabelecimento onde esta sendo realizada a busca|N||
|BUSCA|Informação de busca para localizar o cliente|A|pode ser informado: Nome, Telefone ou CPF do cliente|


- **Parâmetros de Saída(Response):**

|Campo|Descrição|Tipo|Valores|
|------|------|------|------|
|CLIENTE|Código do Cliente|N||
|TIPO|Tipo do Cliente|N|1 - Convênio / 2 - Cartão próprio / 3 - Faturado / 5 - Cliente identificado|
|NOME|Nome do Cliente|A||
|CODIGO_CONVENIO|Código da Empresa Conveniada|N||
|DESCRICAO |Nome da Empresa Conveniada|A||
|CONVENIO_CARTAO|Código do Conveniado ou Cartão próprio|N||
|CHAVE_PRINCIPAL|Chave principal|A||
|CHAVE_ALTERNATIVA|Chave Alternativa|A||
|MENSAGEM_1|Mensagem específica do cliente para ser exibida após seleção do mesmo|A||
|MENSAGEM_2 |Mensagem específica do cliente para ser exibida após seleção do mesmo|A||
|CONVENIO|Permite Pagamento em Convênio|A|S / N|
|BOLETO|Permite Pagamento em Boleto|A|S / N|
|CHEQUE|Permite Pagamento em Cheque|A|S / N|
|CHEQUE_PRE|Permite Pagamento em Cheque pré-datado|A|S / N|
|CARTAO_DEBITO|Permite Pagamento em Cartão Débito|A|S / N|
|CARTAO_CREDITO |Permite Pagamento em Cartão Crédito|A|S / N|
|FIADO|Permite Pagamento em Faturado|A|S / N|
|RECEITA|Exibir Receita|A|S / N|
|DESCONTO_MAXIMO|Assumir desconto máximo na venda|N||
|DESCONTO_VENDA |percentual de desconto|A||
|PREDATADO_PARCELAS|Máximo de Parcelas para pagamento pré-datado|N||
|BOLETO_PARCELAS|Máximo de Parcelas para pagamento para boleto|N||
|TIPO_TELEFONE|Tipo de Telefone|A|RESIDENCIAL / COMERCIAL / CELULAR|
|TELEFONE|Número do Telefone com DDD|A||
|CEP|CEP|A|Em caso de venda convênio, enviar dados de endereço da empresa conveniada / Para as demais vendas enviar os dados de endereço do cliente|
|TIPO_ENDERECO|Tipo do Endereço|A||
|ENDERECO|Endereço|A||
|NUMERO|Número do endereço|N||
|COMPLEMENTO|Complemento do Endereço|A||
|BAIRRO|Bairro|A||
|CIDADE|Cidade|A||
|ESTADO|UF|A||
|COBR_CEP|CEP|A|Em caso de venda convênio, enviar dados de endereço da empresa conveniada / Para as demais vendas enviar os dados de endereço do cliente|
|COBR_TIPO_ENDERECO|Tipo do Endereço|A||
|COBR_ENDERECO|Endereço|A||
|COBR_NUMERO|Número do endereço|N||
|COBR_COMPLEMENTO|Complemento do Endereço|A||
|COBR_BAIRRO|Bairro|A||
|COBR_CIDADE|Cidade|A||
|COBR_ESTADO|UF|A||
|ENTR_CEP|CEP|A|Em caso de venda convênio, enviar dados de endereço da empresa conveniada / Para as demais vendas enviar os dados de endereço do cliente|
|ENTR_TIPO_ENDERECO|Tipo do Endereço|A||
|ENTR_ENDERECO|Endereço|A||
|ENTR_NUMERO|Número do endereço|N||
|ENTR_COMPLEMENTO|Complemento do Endereço|A||
|ENTR_BAIRRO|Bairro|A||
|ENTR_CIDADE|Cidade|A||
|ENTR_ESTADO |UF|A||
|PARCELAS|Número máximo de parcelas para o convênio|N||
|VALOR_MINIMO|Valor mínimo da parcela do convênio|N||
|STATUS |Status do Conveniado|N|1 - Ativo / 2 - Inativo|
|LIMITE_MENSAL   |Limite Mensal do conveniado|N||
|INSCRICAO_FEDERAL  |Inscrição Federal|A||
|CARTAO_FIDELIDADE  |Número do Cartão Fidelidade|A||
|CODIGO_DEPARA  |Código de De/Para - Sistema de terceiros|A|Enviar ''|
|CARGO_CONVENIO_CARTAO  ||N|Enviar 0|
|CEP_CONVENIO  ||N|Enviar 0|
|TIPO_CARTAO  |CEP da Empresa conveniada|A|Enviar ''|
|OBSERVACAO  |Observação do Convênio|A|Enviar ''|
|FIDELIZE|Convênio possui integração com Fidelize|A|S / N|
|SOLICITAR_CRM_CONVENIO  |Solicitar CRM para vendas convênio|A|S / N|



- **Corpo**

No corpo da requisição HTTP deve-se enviar um objeto JSON com uma elemento para cada parametro necessário para execução da CustomView.

Exemplo:

```JSON
{
  "Parameters":
  {
    "Loja":"1",
    "Buscao":"Maria da Silva"
  }
}
```

```JSON
{
  "Parameters":
  {
    "Loja":"1",
    "Buscao":"000.000.000-00"
  }
}
```

```JSON
{
  "Parameters":
  {
    "Loja":"1",
    "Buscao":"1338770770"
  }
}
```


##### :outbox_tray: Resposta

- **Códigos de Estado Possíveis**


| HTTP Status Code | Motivo | Observação
| ------ | ------ | ------ |
| 200 | Query Executada com Sucesso. |
| 400 | Requisição não processada | O elemento **message** do objeto JSON retornado possui mais detalhes sobre a resposta.


- **Corpo**

Um objeto JSON que representa um *array* com a coleção de registros retornados pela execução da CustomView é anexado ao corpo da resposta HTTP.

Exemplo:

```JSON
    {
    "@odata.count": 10,
    "value": [
        {
"CLIENTE":"10",
"TIPO":"1",
"NOME":"Jose Souza",
"CODIGO_CONVENIO":"102030",
"DESCRICAO ":"Convênio Nissei",
"CONVENIO_CARTAO":"1234",
"CHAVE_PRINCIPAL":"9987",
"CHAVE_ALTERNATIVA":"",
"MENSAGEM_1":"",
"MENSAGEM_2 ":"",
"CONVENIO":"S",
"BOLETO":"N",
"CHEQUE":"N",
"CHEQUE_PRE":"N",
"CARTAO_DEBITO":"N",
"CARTAO_CREDITO ":"N",
"FIADO":"N",
"RECEITA":"N",
"DESCONTO_MAXIMO":"S",
"DESCONTO_VENDA ":"30",
"PREDATADO_PARCELAS":"0",
"BOLETO_PARCELAS":"0",
"TIPO_TELEFONE":"CELULAR",
"TELEFONE":"999999999",
"CEP":"11045003",
"TIPO_ENDERECO":"Avenida",
"ENDERECO":"Pedro I",
"NUMERO":"1000",
"COMPLEMENTO":"Esquina",
"BAIRRO":"Centro",
"CIDADE":"São Paulo",
"ESTADO":"SP",
"COBR_CEP":"11045003",
"COBR_TIPO_ENDERECO":"Avenida",
"COBR_ENDERECO":"Pedro I",
"COBR_NUMERO":"1000",
"COBR_COMPLEMENTO":"Esquina",
"COBR_BAIRRO":"Centro",
"COBR_CIDADE":"São Paulo",
"COBR_ESTADO":"SP",
"ENTR_CEP":"11045003",
"ENTR_TIPO_ENDERECO":"Avenida",
"ENTR_ENDERECO":"Pedro I",
"ENTR_NUMERO":"1000",
"ENTR_COMPLEMENTO":"Esquina",
"ENTR_BAIRRO":"Centro",
"ENTR_CIDADE":"São Paulo",
"ENTR_ESTADO        ":"SP",
"PARCELAS       ":"3",
"VALOR_MINIMO       ":"50",
"STATUS        ":"1",
"LIMITE_MENSAL   ":"0",
"INSCRICAO_FEDERAL  ":"00.000.000/0001-00",
"CARTAO_FIDELIDADE  ":"",
"CODIGO_DEPARA  ":"555555",
"CARGO_CONVENIO_CARTAO  ":"",
"CEP_CONVENIO  ":"",
"TIPO_CARTAO  ":"0",
"OBSERVACAO  ":"Obs",
"FIDELIZE":"N",
"SOLICITAR_CRM_CONVENIO  ":"N"
        }
    ]
}
```
