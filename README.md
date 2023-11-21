# Aplicação PHP com Docker Compose

Este repositório contém uma configuração simples para executar uma aplicação PHP utilizando Docker Compose.

## Pré-requisitos

Certifique-se de ter o Docker e o Docker Compose instalados em sua máquina.

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Como usar

1. Clone este repositório:

    ```bash
    git clone https://github.com/vitor-jotave/docker-php-v2.git
    cd docker-php-v2
    ```

2. Execute o Docker Compose para construir e iniciar os serviços:

    ```bash
    docker-compose up -d
    ```

   Isso iniciará os containers necessários para a aplicação PHP.

3. Acesse a aplicação em seu navegador:

   - Aplicação PHP: [http://localhost:8080](http://localhost:8080)
   - PhpMyAdmin: [http://localhost:9001](http://localhost:9001)
   
## Estrutura do Docker Compose

### Serviços

- **app**: Container para a aplicação PHP.
- **nginx**: Servidor Nginx para roteamento e acesso à aplicação.
- **mysql_db**: Banco de dados MySQL (Você pode alterar para MariaDB ou Postgres).
- **phpmyadmin**: Interface web para gerenciamento do MySQL.

### Volumes

- `../src:/var/www`: Mapeamento do diretório de código-fonte para o container da aplicação e do Nginx.

## Configuração

- A aplicação PHP deve ser colocada no diretório `src`.
- A versão do PHP pode ser alterada no arquivo `Dockerfile`.
- Altere a diretiva `container_name` no `docker-compose.yml` para o nome do seu projeto.
- O arquivo de configuração do Nginx está em `./nginx`, altere a linha abaixo conforme a estrutura do seu projeto.

```
root /var/www/{diretório do index.php};
```

## Comandos úteis do Docker Compose

- Parar os serviços: `docker-compose down`
- Ver logs dos serviços: `docker-compose logs -f`
- Visualizar status dos serviços: `docker-compose ps`

## Observações

- Esta configuração é destinada para desenvolvimento e não para ambiente de produção.
- Certifique-se de ajustar a configuração para ambientes de produção.

---
**Importante**: Este é um modelo e pode não servir para todas as aplicações. Ajuste conforme necessário para o seu projeto.
