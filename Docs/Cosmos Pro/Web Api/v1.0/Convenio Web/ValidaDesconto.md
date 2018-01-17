## Valida Desconto Cosmos Pro Web API

A validação de desconto da API Cosmos Pro é realizada utilizando o conceito de CustomAction.
É necessário o envio do Token no header, e os parâmetros com informações dos itens, descritas abaixo, no body da mensagem em formato JSON ou XML

##### :outbox_tray: Requisição


- **Url** 

	*http:// **[ambiente]**.cosmospro.com.br:**[porta]**/api/ExecuteCustomAction/ExecuteAction?ActionName=ValidaDesconto&api-version=1.0*
	
    > ### :grey_exclamation: Informação
    > Os valor **"ValidaDesconto"** fornecido para o parametro *Name* da ação *ExecuteAndReceive*.
	
---

- **Parametros URL Base**

    | Nome | Tipo | Observação
	| ------ | ------ | ------ |
	| Name | String | Nome da CustomAction a ser acionada. 

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


- **Parâmetros de Entrada(Request):**

|Campo|Descrição|Tipo|Valores|
|------|------|------|------|
|IDITEM|ID de identificação do item (Sequencial)|N||
|EAN|Ean do produto|N||
|PRECOBRUTO|Preço Bruto do produto|N||
|DESCONTO|Valor do desconto do produto|N||
|PRECOLIQUIDO|Preço líquido do Produto|N||


- **Parâmetros de Saída(Response):**

|Campo|Descrição|Tipo|Valores|
|------|------|------|------|
|IDITEM|ID de identificação do item (Sequencial)|N||
|EAN|Ean do produto|N||
|PRECOBRUTO|Preço Bruto do produto|N||
|DESCONTO|Valor do desconto do produto|N||
|PRECOLIQUIDO|Preço líquido do Produto|N||



- **Corpo**

	No corpo da requisição HTTP deve-se enviar um objeto JSON com uma elemento para cada parametro necessário para execução da CustomAction.

	Exemplo:

	```JSON
	{
        "Parameters":{
	      "IdItem":"1",
	      "Ean":"7896261013490",
		  "PrecoBruto":"10",
		  "Desconto":"1",
		  "PrecoLiquido":"9"
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

	Um objeto JSON que representa um *array* com a coleção de registros retornados pela execução da CustomAction é anexado ao corpo da resposta HTTP.

	Exemplo:

	```JSON
    {
    "@odata.count": 10,
    "value": [
        {
           "Parameters":{
	         "IdItem":"1",
	         "Ean":"7896261013490",
		     "PrecoBruto":"10",
		     "Desconto":"2",
		     "PrecoLiquido":"8"
           }
        }
    ]
}
	```
