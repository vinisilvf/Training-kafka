﻿# Training-kafka

Inicializado um curso de aprendizado do kafka CLI, o projeto tem como objetivo na criação de produtores e consumidores em JAVA.

## 🚀 Começando

Essas instruções permitirão que você obtenha uma cópia do projeto em operação na sua máquina local para fins de desenvolvimento e teste.

### 📋 Comandos 

<!--ts-->
   * [Criar tópico](#Criar-tópico)
     * kafka-topics --bootstrap-server localhost:9092 --topic <nome_topico> --create --partitions 3 --replication-factor 1
   * [Acrescentar partições em um tópico](#Acrescentar-partições-em-um-tópico)
     * kafka-topics --alter --bootstrap-server localhost:9092 --topic <nome_topico> --partitions <qtd>
   * [Listar tópicos](#Listar-tópicos)
     * kafka-topics --bootstrap-server localhost:9092 --list
   * [Detalhes do tópico](#Detalhes-do-tópico)
     * kafka-topics --bootstrap-server localhost:9092 --topic <nome_topico> --describe
   * [Deletar tópico (não funciona no Windows)](#Deletar-tópico(não-funciona-no-Windows))
     * kafka-topics --bootstrap-server localhost:9092 --topic <nome_topico> --delete
   * [Enviar mensagem via linha de comando](#Enviar-mensagem-via-linha-de-comando)
     * kafka-console-producer --broker-list 127.0.0.1:9092 --topic <nome_topico>
   * [Consumir mensagens via linha de comando](#Consumir-mensagens-via-linha-de-comando)
     * kafka-console-consumer --bootstrap-server 127.0.0.1:9092 --topic <nome_topico>
   * [Consumir mensagens via linha de comando (desde o inicio)](#Consumir-mensagens-via-linha-de-comando-(desde-o-inicio))
     * kafka-console-consumer --bootstrap-server 127.0.0.1:9092 --topic <nome_topico> --from-beginning
   * [Consumir mensagens em grupo](#Consumir-mensagens-em-grupo)
     * kafka-console-consumer --bootstrap-server 127.0.0.1:9092 --topic <nome_topico> --group <group-name>
   * [Mostrar grupos](#Mostrar-grupos)
     * kafka-consumer-groups --bootstrap-server localhost:9092 --list
   * [Visualizar status das entregas (lag) por grupo](#Visualizar-status-das-entregas-(lag)-por-grupo)
     * kafka-consumer-groups --bootstrap-server localhost:9092 --describe --group <group-name>
   * [Reiniciar o offset do grupo para tópico específico](#Reiniciar-o-offset-do-grupo-para-tópico-específico)
     * kafka-consumer-groups --bootstrap-server localhost:9092 --group <group-name> --reset-offsets --to-earliest --execute --topic <nome_topico>
   * [Reiniciar o offset do grupo para todos os tópicos](#Reiniciar-o-offset-do-grupo-para-todos-os-tópicos)
     * kafka-consumer-groups --bootstrap-server localhost:9092 --group <group-name> --reset-offsets --to-earliest --execute --all-topics

<!--te-->

## 📋 Problemas enfrentados

  - Ao apagar um tópico no windows via Kafka CLI, os arquivos do Kafka ficam corrompidos e a unica solução para retomar é apagar os arquivos contidos da pasta __data__ e inicializar/criar novamente os tópicos.
  
