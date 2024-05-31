# platform.race.redis

O código-fonte e a configuração dos nossos serviços estão disponíveis no GitHub no repositório [Platform.Race](https://github.com/st4pzz/platform.race).

## Descrição
Este projeto é parte de uma plataforma de gerenciamento de cache Redis em uma arquitetura de microserviços. Ele foi desenvolvido com foco em escalabilidade, flexibilidade e facilidade de manutenção.

## Arquitetura
A arquitetura do projeto utiliza uma abordagem de microserviços, onde cada componente é independente e comunica-se entre si. As tecnologias principais utilizadas incluem Kubernetes, Jenkins e Docker Compose.

## Tecnologias Utilizadas

- **Kubernetes**: Para orquestração de contêineres e gerenciamento de serviços em escala.
- **Jenkins**: Para integração contínua e entrega contínua (CI/CD).
- **Docker Compose**: Para definir e gerenciar multi-contêineres Docker.
- **Redis**: Para gerenciamento de cache distribuído.
- **React**: (considerado para o frontend).

## Estrutura do Projeto

```
platform.race.redis/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/
│   │   │       └── example/
│   │   │           └── redis/
│   │   │               ├── controller/
│   │   │               ├── model/
│   │   │               ├── repository/
│   │   │               └── service/
│   └── resources/
├── Jenkinsfile
├── docker-compose.yml
├── README.md
└── pom.xml
```

## Configuração e Execução

### Pré-requisitos

- Docker
- Kubernetes
- Jenkins
- Redis

### Passos para Configuração

1. Clone o repositório:
    ```bash
    git clone https://github.com/st4pzz/platform.race.redis.git
    cd platform.race.redis
    ```

2. Configure o Jenkins:
    - Crie um pipeline e aponte para o arquivo `Jenkinsfile` deste repositório.

3. Execute o Docker Compose para iniciar os serviços localmente:
    ```bash
    docker-compose up
    ```

4. Implemente no Kubernetes:
    - Certifique-se de que seu cluster Kubernetes está configurado.
    - Utilize os arquivos de configuração do Kubernetes presentes no repositório para implantar os serviços.
