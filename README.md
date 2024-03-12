# Config Server

Aplicação para ler em repositório de arquivos e disponibilizar via endpoint propriedades de outras APIS/Serviços.

Esse serviço lê o [repositório](https://github.com/brunovschettini/bvss-config-server-repo.git) de configurações com propriedades.

É possível realizar o apontamento através API do cliente a label (branch) que será lida, por default é carregada sempre a main.

Assim facilita a consulta e centraliza as configuraçoes.

Essa API tem fins de estudo e de apresentar partes do meu conhecimento como desenvolvedor.

### Ref. name: *bvss-es6-api-estoque*.

- bvss: Abrevição da marca.
- config-server: Indica que essa aplicação de config-server.
- estoque: Informa que essa aplicação da sigla (es6) é relacionada ao serviço de negócio de estoque 

### Example

Esse serviço contém nível de segurança básico dotado de usuário e senha.

Para o caso aqui temos dados simples configurados no arquivo de configuração da aplicação:

- name: developer
- password: developer

#### CURL
##### Request

```
curl --location 'http://developer:developer@localhost:8888/bvss-es6-api-estoque/development/main' \
```

##### Response
```json
{
    "name": "bvss-es6-api-estoque",
    "profiles": [
        "development"
    ],
    "label": "main",
    "version": "5387994c636eb236c5e0d9504a669221bb676560",
    "state": null,
    "propertySources": [
        {
            "name": "https://github.com/brunovschettini/bvss-config-server-repo.git/bvss-es6-api-estoque/bvss-es6-api-estoque-development.yml",
            "source": {
                "spring.datasource.url": "jdbc:h2:mem:db-bvss",
                "spring.datasource.driverClassName": "org.h2.Driver",
                "spring.datasource.username": "sa",
                "spring.datasource.password": "password",
                "spring.jpa.database-platform": "org.hibernate.dialect.H2Dialect",
                "server.port": 5000,
                "server.servlet.context-path": "/bvss-es6-api-estoque",
                "openapi.info.title": "API Estoque ES6",
                "openapi.info.version": "1.0.0",
                "openapi.info.description": "?? - API Swagger documentation",
                "openapi.info.license.name": "Apache 2.0",
                "openapi.info.license.url": "http://springdoc.org"
            }
        },
        {
            "name": "https://github.com/brunovschettini/bvss-config-server-repo.git/bvss-es6-api-estoque/bvss-es6-api-estoque.yml",
            "source": {
                "spring.application.name": "bvss-es6-api-estoque",
                "h2.console.enabled": true,
                "h2.console.path": "/h2-console"
            }
        }
    ]
}
```