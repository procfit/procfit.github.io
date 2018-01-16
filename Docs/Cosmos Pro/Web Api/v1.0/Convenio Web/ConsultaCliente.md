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

    | Nome | Tipo | Observação
| ------ | ------ | ------ |
| Name | String | Nome da CustomView a ser acionada. 

---

- **Método** 

*Post*
---

- **Cabeçalhos(Headers):**

| Nome | Valor | Observação
| ------ | ------ | ------ |
| Content-Type | application/json | Tipo de Conteúdo da requisição.
| Authorization | Bearer [Token] | Token de Autenticação obtido junto ao Administrador do Inquilino Cosmos Pro

---

- **Corpo**

No corpo da requisição HTTP deve-se enviar um objeto JSON com uma elemento para cada parametro necessário para execução da CustomView.

Exemplo:

```JSON
{
        "Parameters":
{
    "Loja":"1",
    "Buscao":"Maria da Silva"
        },
{
    "Loja":"2",
    "Buscao":"00.000.000-00"
        },
{
    "Loja":"2",
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
