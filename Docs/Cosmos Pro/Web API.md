# Api Web Portal Cosmos Pro

## Sobre a API

A API Web do Portal Cosmos Pro segue as diretivas da vers�o 4 do protocolo [OData](http://www.odata.org/).

## Vers�es

Atualmente uma unica vers�o (V1) da API est� d�sponivel.

## Ambientes

#### Produ��o



#### SandBox

## Autentica��o

A autentica��o da API Cosmos Pro se da atrav�s de envio de token de identifica��o no cabe�alho de todas as requisi��es enviadas ao endere�o da API.

## Rotas

### Rota para Recursos Gerais do Portal

HDSHDJSHDJKSHDJHDJKSHDJKSHDSJKhDKS

### Rota para dados de Formul�rios Customizados no Portal

O Comos Data
Para utiliza��o da API para acesso a recursos do m�dulo de Formul�rios Customizados no Portal Cosmos Pro, as requisi��es devem 
ser direcionadas ao recurso TableDataRows, esse recurso Odata possui a inteligencia de efetivar as opera��es CRUD nos objetos customizados de acordo com os parametros
fornecidos para a API.

#### Post

Requisi��es com m�todo post devem ser utilizados para a inser��o de novos dados em uma entidade do Cosmos Pro.

##### Requisi��o


- **Url** 

	http:// **[ambiente]**.cosmospro.com.br/api/**[Vers�o]**/odata/custom/**[tenant]**/TableDataRows

- **Parametros da Query:**

	| Nome | Tipo | Observa��o
	| ------ | ------ |
	| TableName | string | Nome da Tabela para Opera��o de Inser��o.


- **M�todo** 

	Post

- **Cabe�alhos(Headers):**

	| Nome | Valor | Observa��o
	| ------ | ------ |
	| Content-Type | application/json | Tipo de Conte�do da requisi��o.
	| Authorization | Bearer [Token] | Token de Autentica��o obtido junto ao Administrador do Inquilino Cosmos Pro


- **Corpo**

	No corpo da requisi��o deve-se enviar um objeto JSON com um n� para cada propriedade que se deseja inserir na entidade alvo da requisi��o.O Nome do elemento JSON deve
	corresponder ao nome da propriedade existente na entidade alvo da inser��o.

	Exemplo:

	```JSON
	{
		"UniqueKeyId": 0,
		"TableId": 1,
		"N_CampoTeste": 958787.56,
		"A_CampoTeste": "Teste",
		"DT_CampoTeste": "2017-07-24T18:05:59.977",
		"L_CampoTeste": true,
		"BI_CampoTeste": 1
	}
	```

##### Resposta

- **C�digos de Estado Poss�veis**


	| HTTP Status Code | Motivo | Observa��o
	| ------ | ------ | ------ |
	| 201 | Dados criados com Sucesso. | Tipo de Conte�do da requisi��o.
	| 400 | Requisi��o mau Formatada | O elemento **message** do objeto JSON retornado possui mais detalhes sobre a resposta.


- **Corpo**

	Um objeto JSON que representa os dados inseridos na entidade s�o retornados no corpo da requisi��o do Tipo Post.

	Exemplo:

	```JSON
	{
		"@odata.context": "http://sandbox.cosmospro.com.br/odata/Inquilino%20Padr%C3%A3o/$metadata#TableDataRows/$entity",
		"UniqueKeyId": 115,
		"TableId": 1,
		"InTransactionState": "Unchanged",
		"Id": 115,
		"N_CampoTeste": 958787.56,
		"BI_CampoTeste": 1,
		"A_CampoTeste": "Teste",
		"DT_CampoTeste": "2017-07-24T18:05:59.977Z",
		"L_CampoTeste": true
	}
	```

> **Nota**
O objeto JSON retornado pela opera��o POST possui um elemento com nome **UniqueKeyId**, esse elemento possui o valor da chave primaria gerada para os dados inseridos no armazenamento de dados do Cosmos Pro.


#### Get


API's que implementam o protocolo [OData](http://www.odata.org/) s�o [RestFull](https://en.wikipedia.org/wiki/Representational_state_transfer) por natureza, e por padr�o, requisi��es que utilizam o m�todo GET s�o destinadas a opera��o de leitura em recursos na API.Utilize metodo GET para receber dados de Entidades da Portal Cosmos Pro.

##### Requisi��o


- **Url** 

	http:// **[ambiente]**.cosmospro.com.br/api/**[Vers�o]**/odata/custom/**[tenant]**/TableDataRows

- **Parametros da Query:**

	| Nome | Tipo | Observa��o
	| ------ | ------ |
	| TableName | string | Nome da Tabela para Opera��o de Inser��o.


- **M�todo** 

	Post

- **Cabe�alhos(Headers):**

	| Nome | Valor | Observa��o
	| ------ | ------ |
	| Content-Type | application/json | Tipo de Conte�do da requisi��o.
	| Authorization | Bearer [Token] | Token de Autentica��o obtido junto ao Administrador do Inquilino Cosmos Pro


- **Corpo**

	No corpo da requisi��o deve-se enviar um objeto JSON com um n� para cada propriedade que se deseja inserir na entidade alvo da requisi��o.O Nome do elemento JSON deve
	corresponder ao nome da propriedade existente na entidade alvo da inser��o.

	Exemplo:

	```JSON
	{
		"UniqueKeyId": 0,
		"TableId": 1,
		"N_CampoTeste": 958787.56,
		"A_CampoTeste": "Teste",
		"DT_CampoTeste": "2017-07-24T18:05:59.977",
		"L_CampoTeste": true,
		"BI_CampoTeste": 1
	}
	```