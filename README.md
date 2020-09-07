# RabbitMQ-SpringBoot

Desenvolva uma solução para o agronegócio que coleta dados via sensores de temperatura
e umidade. Esses sensores ficarão instalados em um drone com uma altíssima autonomia
de energia.

A cada 10 segundos são enviados para o message broker os dados de temperatura e
umidade capturado naquele instante.
Além da primeira função também é possível acionar o rastreamento do drone. Esta
funcionalidade resulta na localização do equipamento em um map.


# Imagem RabbitMQ

Instale a imagem do RabbitMQ com docker
  - docker run -d -p 15672:15672 -p 5672:5672 --name rabbitmq rabbitmq:3-management
 
Painel do RabbitMQ
  - http://localhost:15672/#/
  
  - User e senha : guest
  
  
# Exchange Direct 

- Ao Executar o Projeto as filas sao criadas automaticamente
- Criacao do Exchange do tipo Direct que recebe a mensagem enviada pelo Produtor e encaminha a mensagem para a fila destinada do produtor.


# Mensagerias ajudam em :

 - Problema de comunicacao de servicos causando timeout
 
 - Distribuicao de requisicoes , vamos supor que um servidor nao esteja aguentando o excesso de requisicao entao a mensageria
    tem o papel de processar as informacoes de acordo com a capacidade de processamento do servidor. Se o servidor cair nos podemos utilizar um conceito chamado
    DeadLetters para jogar as mensagens para essa fila para que quando o sistema volte ele comece a pegar essas informacoes que nao foram requisitadas atraves da       fila deadLetter.
 
 - Diminui o acoplamento de informacoes.

