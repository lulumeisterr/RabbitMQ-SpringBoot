# RabbitMQ-SpringBoot

Desenvolva uma solução para o agronegócio que coleta dados via sensores de temperatura
e umidade. Esses sensores ficarão instalados em um drone com uma altíssima autonomia
de energia.

A cada 10 segundos são enviados para o message broker os dados de temperatura e
umidade capturado naquele instante.
Além da primeira função também é possível acionar o rastreamento do drone. Esta
funcionalidade resulta na localização do equipamento em um map.


# Imagem RabbitMQ

Docker
  - docker run -d -p 15672:15672 -p 5672:5672 --name rabbitmq rabbitmq:3-management
 
Painel do RabbitMQ
  - http://localhost:15672/#/
  
  
# Exchange Direct 

- Ao Executar o Projeto as filas sao criadas automaticamente
- Criacao do Exchange do tipo Direct que recebe a mensagem enviada pelo Produtor e encaminha a mensagem para a fila destinada do produtor.
