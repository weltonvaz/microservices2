## microservices2 ##

Vou tentar criar um exemplo de microserviços com Python usando o framework Nameko.👍

Vamos supor que queremos construir uma aplicação que fornece informações sobre o clima de diferentes cidades. Para isso, vamos criar dois microserviços: um que consulta uma API externa de clima (Weather Service) e outro que fornece uma interface web para o usuário (Web Service).

O Weather Service é responsável por fazer a requisição à API externa de clima e retornar os dados em formato JSON. Ele utiliza o protocolo HTTP para se comunicar com a API externa e o protocolo AMQP para se comunicar com o Web Service. Ele também utiliza um cache para armazenar os dados já consultados e evitar chamadas desnecessárias à API externa.

O Web Service é responsável por fornecer uma interface web para o usuário, onde ele pode digitar o nome de uma cidade e obter as informações sobre o clima. Ele utiliza o protocolo HTTP para se comunicar com o usuário e o protocolo AMQP para se comunicar com o Weather Service. Ele também utiliza um template para renderizar a página web com os dados do clima.

Para executar os microserviços, vamos precisar de um message broker (RabbitMQ) que vai intermediar a troca de mensagens entre eles. Vamos também precisar de um servidor web (Gunicorn) que vai hospedar o Web Service.

A seguir, vou mostrar o código de cada microserviço e explicar como eles funcionam.