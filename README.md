# Auditoria de Pedidos

Em um ecommerce é fundamental o monitoramento dos pedidos(compras) realizados pelos cliente, para que possamos corrigir eventuais problemas ocorridos.

Dessa forma, se faz necessário um serviço de auditorio de pedidos. Utilizando a tecnologia .Net com o banco de dados NoSql, desenvolva uma api que atenda os seguintes requisitos:


<h4>Desenvolva um endpoint do tipo POST que receba o seguinte json e persista as informações em uma base MongoDB.</h4>

![image](https://user-images.githubusercontent.com/76007795/135312716-af84fa71-61a9-409d-99ea-dada1f2d1c97.png)

{
  "orderId": "o123456",
  "eventDate": "2020-12-03T16:28:42.700Z",
  "description": "Pedido Criado",
  "api" : "Order-Submitted",
  "content": {}
}

orderId: ID do pedido no OCXC;

eventDate: Data e hora que o evento ocorreu;

description: Descrição do evento;

api: API que executou o evento;

content: objeto livre para informações adicionais sobre o evento.


<h4>Desenvolva um endpoint do tipo GET com páginação que receba as query string pageNumber (número da página) e pageSize (total de registros).</h4>

![image](https://user-images.githubusercontent.com/76007795/135312966-a12c1c22-81c3-49bf-96e4-8a7b90593133.png)

{
"pageNumber": 1,
"pageSize": 2,
 "items" : [
  {
    "orderId": "o123456",
    "eventDate": "2020-12-03T16:28:42.700Z",
    "description": "Pedido finalizado",
    "api" : "order-submitted",
    "content": {}
  },
  {
    "orderId": "o123456",
    "eventDate": "2020-12-03T18:28:42.700Z",
    "description": "Alerta de fraude",
    "api": "clear-sale-integration",
    "content": {
       "statusCode" : "1"
    }
  }
 ]
}
