![Magento 2](https://miro.medium.com/max/2404/1*JUOITpaBdlrMP9D__-K5Fw.png)

#  Magento 2 Docker para desenvolvimento

### Apache 2.4 + PHP 7.2 + MariaDB + N98 Magerun 2 + XDebug

### Requisitos

**Linux:**

Instalar [Docker](https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/) e [Docker-compose](https://docs.docker.com/compose/install/#install-compose).

### Como usar

Execute no seu terminal:

```
git clone https://github.com/daniloaldm/DockerDragStar.git DockerDragStar
cd DockerM2
docker-compose build
```

Após isso basta clonar o repositório do seu projeto magento2 para dentro de src/

### Painéis

**Web server:** http://localhost/

**PHPMyAdmin:** http://localhost:8080

**Local emails:** http://localhost:8025

### Comandos

| Comandos  | Descrição  | Opções e exemplos |
|---|---|---|
| `./start`  | Iniciar seu contêiner manualmente  | |
| `./stop`  | Pare os contêineres do seu projeto  | |
| `./kill`  | Para contêineres e remove contêineres, volumes e imagens criadas para o projeto específico  | |
| `./shell`  | Acesse seu contêiner  | `./shell root` | |
| `./n98`  | Use os comandos Magerun como quiser | |
| `./xdebug`  |  Ativar / desativar o XDebug | |
<!---
| `./magento`  | Use o poder do Magento CLI  | |
| `./grunt-init`  | Prepare-se para usar o Grunt  | |
| `./grunt`  | Use o Grunt especificamente em seu tema ou completamente, ele fará a implantação e o observador.  | `./grunt luma` |
| `./xdebug`  |  Ativar / desativar o XDebug | |
| `./composer`  |  Use os comandos do Composer | `./composer update` |
| `./init`  | Se você não usou o comando CURL setup acima, use este comando alterando o nome do projeto.  | `./init MYMAGENTO2` |
-->

### Magento Cloud
Acesse seu container:
```
./shell
```
Após isso acesse o diretório do seu projeto e execute para visualizar os comandos:
```
magento-cloud list
```
Obs: A autenticação por login não está funcionando no momento, logo você precisa utilizar a por token
```
magento-cloud auth:api-token-login
```

### Elasticsearch 

Para usar a pesquisa elástica, você pode usar este comando abaixo:

`$ docker-compose -f docker-compose.yml -f docker-compose.elasticsearch.yml up`

ou para executar em segundo plano usando o modo separado

`$ docker-compose -f docker-compose.yml -f docker-compose.elasticsearch.yml up -d`

**Elasticsearch:** http://localhost:9200
