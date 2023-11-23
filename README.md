# Projeto Edge Computing com ESP32

Este projeto utiliza um ESP32, sensores de temperatura, umidade e luz, um display LCD e servos para administrar medicamentos. Além disso, o dispositivo se conecta a um servidor MQTT para compartilhar informações ou para processamento remoto.

## Equipe:

- Felipe Arnus – RM: 550923
- João Pedro Chambrone – RM: 97857
  
## Descrição do Projeto:

O projeto visa criar um sistema de administração de medicamentos via servos. Adequado para ambientes hospitalares ou domiciliares. O seu intuito é simplificar a vida de enfermeiros com um sistema automatico que não requere que eles fiquem indo e voltando para administrar medicamentos. 

## Componentes Utilizados:

- 1 ESP32
- 1 Display LCD
- 4 Servos
- Fios de conexão
- Acesso a uma rede Wi-Fi para comunicação MQTT

## Funcionamento do Código:

O código monitora sensores continuamente e realiza operações, interagindo com servos e exibindo informações no LCD. Também utiliza MQTT para comunicação remota.

1. **Administração de Medicamentos:** O botão inicia a administração, movendo os servos conforme necessário.

2. **Comunicação MQTT:** Envia dados coletados para um servidor MQTT externo para informar o enfermeiro.
## Configuração Wi-Fi e MQTT:

- SSID da rede Wi-Fi: "Wokwi-GUEST"
- Senha da rede Wi-Fi: ""
- Servidor MQTT: "broker.hivemq.com"
- Porta MQTT: 1883

## Bibliotecas Usadas:

- ESP32Servo
- LiquidCrystal I2C
- WiFi
- PubSubClient

## Instruções de Uso:

1. Carregue o código no ESP32.
2. Conecte os sensores e componentes conforme as definições no código.
3. Verifique a conexão Wi-Fi do ESP32.
4. Inicie um cliente MQTT para receber dados dos tópicos correspondentes.

## Simulação:

Você pode simular este projeto no Wokwi usando o seguinte [link de simulação](https://wokwi.com/projects/382228788664436737).

## Caso deseje utilizar uma conexão via API segue as instruções de execução via Ubuntu: 

1. **Instalar o ifconfig para identificar o IP da máquina virtual:**
- sudo apt-get install net-tools

2. **Comando para ler o IP da VM (Virtual Machine):**
 - ifconfig

3. **Instalar o git**
- sudo apt install git

4. **Instale o docker(apenas o primeiro do site | ilustrado do 5. até 11.)**
- (https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04)

5. **Primeiro, atualize sua lista existente de pacotes:**
- sudo apt update 

6. **Pacotes de pré-requisitos que permitem aptusar pacotes via HTTPS:**
- sudo apt install apt-transport-https ca-certificates curl software-properties-common 

7. **Adicionar a chave GPG do repositório oficial do Docker ao seu sistema:**
- curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

8. **Adicionar o repositório Docker às fontes APT:**
- sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"

9. **Certifique-se de instalar a partir do repositório Docker em vez do repositório padrão do Ubuntu:**
- apt-cache policy docker-ce

10. **Instale o Docker**
- sudo apt install docker-ce

11. **Verificação se o docker esta ativo**
- sudo systemctl status docker

12. **Copiar os arquivos do repositório de Fiware Descomplicado**
- git clone https://github.com/fabiocabrini/fiware

13. **Entrar na pasta do Fiware[Colocar Codigo]**
- cd fiware

14. **Rodar os containers[Colocar Codigo]**
- sudo docker compose up -d

15. **status dos containers[Colocar Codigo]**
- sudo docker stats

16. **faça o download desse arquivo**
- (github.com/fabiocabrini/fiware/blob/main/FIWARE.postman_collection.json)

17. **Entrar em myWorkspace**
- importe o arquivo do passo 16.

18. **Clique em Health Check e reabra o terminal[Colocar Codigo]**
- ifconfig
- encontre a linha inet xxx.xxx.x.xx(copie esse numero(os 'x'))

19. **Substitua( {{url}} ) do get em Health Check pelo copiado**
- Repita em IOT Agent MQTT, Orion Context Broker e STH-Comet
