# Imagem RabbitMQ

Instale a imagem do RabbitMQ com docker

  - docker run -d -p 15672:15672 -p 5672:5672 --name rabbitmq rabbitmq:3-management
  - docker exec -it rabbitmq bash -> Ativar o plugin para poder mover mensagens para outras filas 
  	- $ rabbitmq-plugins enable rabbitmq_shovel rabbitmq_shovel_management
  
Painel do RabbitMQ
  - http://localhost:15672/#/
  
  - user e password : guest
 
# Usando o Exchange Direct 

- Ao Executar o projeto as filas sao criadas automaticamente
- Criacao do exchange do tipo direct que recebe a mensagem enviada pelo produtor e encaminha a mensagem para a fila destinada do produtor.

# EndPoint para publicar na fila

- localhost:8001/send
- Body / Method Post
  {
	  "text":"Teste Agora , 123 , opa"
  }


# Mensagerias ajudam em :

 - Problema de comunicacao de servicos causando timeout
 
 - Distribuicao de requisicoes , vamos supor que um servidor nao esteja aguentando o excesso de requisicao entao a mensageria
    tem o papel de processar as informacoes de acordo com a capacidade de processamento do servidor. Se o servidor cair nos podemos utilizar um conceito chamado
    DeadLetters para jogar as mensagens para essa fila para que quando o sistema volte ele comece a pegar essas informacoes que nao foram requisitadas atraves da       fila deadLetter.
 
 - Diminui o acoplamento de informacoes.

