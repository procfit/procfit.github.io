## Saldo de Cliente Cosmos Pro Web API

A consulta de saldo de cliente da API Cosmos Pro é realizada utilizando o conceito de CustomViews.
É necessário o envio do Token no header, e os parâmetros Tipo e Cliente no body da mensagem em formato JSON ou XML

##### :outbox_tray: Requisição


- **Url** 

	*http:// **[ambiente]**.cosmospro.com.br:**[porta]**/odata/CustomViews(Name=**'SaldoCliente'**)/ExecuteAndReceive()?api-version=1.0*
	
    > ### :grey_exclamation: Informação
    > Os valor **"SaldoCliente"** fornecido para o parametro *Name* da ação *ExecuteAndReceive*.
	
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
        "Parameters":{
	    "Tipo":"1",
	    "Cliente":"102030"
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
            "Tipo": "1",
            "Cliente": "102030",
            "Ultimo_Limite": "100.00",
			"Saldo": "100.00",
			"Estado_Cartao": 1
        }
    ]
}
	```
