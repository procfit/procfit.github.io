# Introdução a 'Cosmos Pro Web API' (V1)

## Sobre a API


1. **Restfull**  
A **Cosmos Pro Web API** é desenvolvida no padrão [RestFull](https://en.wikipedia.org/wiki/Representational_state_transfer).
2. **OData**  
A **Cosmos Pro Web API** é compatível com a versão 4 do protocolo [OData](http://www.odata.org/documentation/).
3. **Propósito**  
A **Cosmos Pro Web API** possui funcionalidades que proveem acesso a dados do módulo de Formulários Customizados do Portal Cosmos Pro, as requisições devem ser direcionadas ao endpoint *TableDataRows* da API, esse recurso OData possui a inteligencia de efetivar as operações CRUD em objetos do módulo de Formulários Customizados do portal Cosmos Pro de acordo com os parametros fornecidos para a API.

## Ambientes

* Produção
* Homologação


## Tenant (Empresa)

Para consumir a API de maneira adequada, na composição url de destino da requisição HTTP será necessário a utilização do nome do *tenant* do portal Cosmos Pro.Caso não possua o nome do *tenant* fornecido no momento da aquisição de acesso ao portal Cosmos Pro, contate o administrador de sua organização.

## Saiba mais ...

- [Autenticação.](Autenticação.md)
- [Operações Crud em Objetos Dinâmicos.](CRUD Objetos Dinamicos.md)
- [Consumindo Consultas Customizadas.](CustomViews.md)
- [Consumindo Ações Customizadas.](CustomActions.md)
- [Consulta de Cliente.](/Convenio Web/ConsultaCliente.md)
- [Saldo de Cliente.](/Convenio Web/SaldoCliente.md)
- [Vale Crédito.](/Convenio Web/ValeCredito.md)
