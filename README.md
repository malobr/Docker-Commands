# Docker-Commands



# Guia Básico de Docker para Linux Mint

## 1. Instalação do Docker

Atualize a lista de pacotes:
```sh
  sudo apt update
```

Instale pacotes necessários:
```sh
  sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

Adicione a chave GPG oficial do Docker:
```sh
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

Adicione o repositório do Docker:
```sh
  sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

Atualize a lista de pacotes novamente:
```sh
  sudo apt update
```

Instale o Docker:
```sh
  sudo apt install docker-ce
```

Verifique se o Docker foi instalado corretamente e está funcionando:
```sh
  sudo systemctl status docker
```

## 2. Comandos Básicos para Gerenciamento de Docker

Verifique o status do Docker:
```sh
  sudo systemctl status docker
```

Verifique a versão do Docker:
```sh
  docker --version
```

Verifique as imagens disponíveis:
```sh
  docker images
```

Baixe uma imagem do Docker Hub:
```sh
  docker pull <nome-da-imagem>:<tag>
  # Exemplo:
  docker pull ubuntu:latest
```

Verifique contêineres em execução:
```sh
  docker ps
```

Verifique todos os contêineres (executando e parados):
```sh
  docker ps -a
```

Inicie um novo contêiner:
```sh
  docker run -d --name <nome-do-contêiner> <nome-da-imagem>:<tag>
  # Exemplo:
  docker run -d --name my-ubuntu-container ubuntu:latest
```

Pare um contêiner:
```sh
  docker stop <nome-do-contêiner>
```

Remova um contêiner:
```sh
  docker rm <nome-do-contêiner>
```

Remova uma imagem:
```sh
  docker rmi <nome-da-imagem>:<tag>
```

Verifique logs de um contêiner:
```sh
  docker logs <nome-do-contêiner>
```

Acesse o terminal de um contêiner em execução:
```sh
  docker exec -it <nome-do-contêiner> /bin/bash
```

Liste volumes do Docker:
```sh
  docker volume ls
```

Remova volumes não usados:
```sh
  docker volume prune
```

## 3. Gerenciamento com Docker Compose

Instale Docker Compose:
```sh
  sudo curl -L "https://github.com/docker/compose/releases/download/$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep tag_name | cut -d '"' -f 4)/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

Dê permissão de execução ao Docker Compose:
```sh
  sudo chmod +x /usr/local/bin/docker-compose
```

Verifique a versão do Docker Compose:
```sh
  docker-compose --version
```

Inicie serviços com Docker Compose:
```sh
  docker-compose up
```

Pare e remova serviços com Docker Compose:
```sh
  docker-compose down
```
