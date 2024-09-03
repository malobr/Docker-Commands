# Docker-Commands

Claro! Aqui está um conjunto de comandos básicos do Docker para Linux Mint, organizados em uma ordem prática para te ajudar a começar a usar Docker. Vou incluir comandos para instalação, verificação, gerenciamento de contêineres e imagens, e outros aspectos básicos.

### 1. **Instalação do Docker**

Se ainda não tiver o Docker instalado, siga estes passos para instalar:

```sh
# Atualizar a lista de pacotes
sudo apt update

# Instalar pacotes necessários
sudo apt install apt-transport-https ca-certificates curl software-properties-common

# Adicionar a chave GPG oficial do Docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

# Adicionar o repositório do Docker
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

# Atualizar a lista de pacotes novamente
sudo apt update

# Instalar o Docker
sudo apt install docker-ce

# Verificar se o Docker foi instalado corretamente e está funcionando
sudo systemctl status docker
```

### 2. **Comandos Básicos para Gerenciamento de Docker**

#### **Verificar o Status do Docker:**

```sh
sudo systemctl status docker
```

#### **Verificar Versão do Docker:**

```sh
docker --version
```

#### **Verificar Imagens Disponíveis:**

```sh
docker images
```

#### **Baixar uma Imagem do Docker Hub:**

```sh
docker pull <nome-da-imagem>:<tag>
# Exemplo:
docker pull ubuntu:latest
```

#### **Verificar Contêineres em Execução:**

```sh
docker ps
```

#### **Verificar Todos os Contêineres (Executando e Parados):**

```sh
docker ps -a
```

#### **Iniciar um Novo Contêiner:**

```sh
docker run -d --name <nome-do-contêiner> <nome-da-imagem>:<tag>
# Exemplo:
docker run -d --name my-ubuntu-container ubuntu:latest
```

#### **Parar um Contêiner:**

```sh
docker stop <nome-do-contêiner>
```

#### **Remover um Contêiner:**

```sh
docker rm <nome-do-contêiner>
```

#### **Remover uma Imagem:**

```sh
docker rmi <nome-da-imagem>:<tag>
```

#### **Verificar Logs de um Contêiner:**

```sh
docker logs <nome-do-contêiner>
```

#### **Acessar o Terminal de um Contêiner em Execução:**

```sh
docker exec -it <nome-do-contêiner> /bin/bash
```

#### **Listar Volumes do Docker:**

```sh
docker volume ls
```

#### **Remover Volumes Não Usados:**

```sh
docker volume prune
```

### 3. **Gerenciamento com Docker Compose**

Se você estiver usando Docker Compose, você pode precisar instalar o Compose e usar alguns comandos específicos:

#### **Instalar Docker Compose:**

```sh
sudo curl -L "https://github.com/docker/compose/releases/download/$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep tag_name | cut -d '"' -f 4)/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

# Verificar versão do Docker Compose
docker-compose --version
```

#### **Iniciar Serviços com Docker Compose:**

```sh
docker-compose up
```

#### **Parar e Remover Serviços com Docker Compose:**

```sh
docker-compose down
```

Com esses comandos, você deve ter uma boa base para começar a trabalhar com Docker em seu sistema Linux Mint. Se precisar de mais detalhes sobre qualquer comando ou quiser explorar mais funcionalidades, sinta-se à vontade para perguntar!
