
# Tarefa 4.2

Como pedido, desenvolvi os endpoints de forma a criar as entidades **Experts** e **Sponsors**. O código desenvolvido para esse efeito está contido neste repositório. 

De forma a testar o desenvolvimento, criei duas coleções na base de dados mongodb disponibilizada pelo autores do livro da "Desenvolvimento Avançado para a Web.". 
Nomes das coleções:
- experts_2001506
- sponsors_2001506 

*Visto ser uma base de dados pública não é garantido a estabilidade e coerencia dos dados mantidos nela.* 

Para ver o estado da base de dados na altura de desenvolvimento, criei uma basta chamada _bd_teste_ que contém todas as coleções da base de dados do Animalec em json.

# Documentação da API base

https://documenter.getpostman.com/view/3754041/SW7exkHe?version=latest

# Instalar

Com o node.js instalado, basta executar o comando:

> node app.js

Se não conster a pasta node_modules execute:

> npm install

# Testes 

Utilizei a ferramenta Postman para testar os endpoints desenvolvidos. Neste repositório encontra-se o ficheiro com a estrutura testada: **PWA - Animalec.postman_collection.json** , basta importá-lo e executar os testes. 

De seguida, exemplos de testes criados e os seus resultados.

## Sponsor

### Criação de sponsor:

**Endpoint**: {{base}}/sponsors

**Método**: POST

**Request**:

```json
{
	"name": "Tapada de Mafra",
	"type": "mamiferos"
}
```

**Response**:

```json
{
    "code": "SponsorCreated",
    "http": 201,
    "type": "success",
    "body": {
        "active": true,
        "_id": "60a93914dc861b83c0bfc419",
        "name": "Tapada de Mafra",
        "type": "mamiferos",
        "__v": 0
    }
}
```

### Obtenção dos sponsors:

**Endpoint**: {{base}}/sponsors

**Método**: Get

**Response**:

```json
{
    "code": "SponsorCreated",
    "http": 201,
    "type": "success",
    "body": {
        "active": true,
        "_id": "60a93914dc861b83c0bfc419",
        "name": "Tapada de Mafra",
        "type": "mamiferos",
        "__v": 0
    }
}
```


## Expert

### Criação de expert:

**Endpoint**: {{base}}/experts

**Método**: POST

**Request**:

```json
{
	"name": "joao",
	"species": "aves",
	"birth_date": "1997-03-19",
	"description": "Gosto de aves.",
	"location": {
        "city": "Coimbra",
        "district": "Coimbra",
        "country": "Portugal"
    },
    "auth": {
        "username": "joao",
        "password": "123"
    }
}
```

**Response**:

```json
{
    "code": "ExpertCreated",
    "http": 201,
    "type": "success",
    "body": {
        "active": true,
        "_id": "60a9387cdc861b83c0bfc418",
        "name": "joao",
        "species": "aves",
        "birth_date": "1997-03-19T00:00:00.000Z",
        "description": "Gosto de aves",
        "location": {
            "city": "Coimbra",
            "district": "Coimbra",
            "country": "Portugal"
        },
        "__v": 0
    }
}
```

### Obtenção dos experts:

**Endpoint**: {{base}}/experts

**Método**: Get

**Response**:

```json
{
    "http": 200,
    "code": "ExpertFound",
    "type": "success",
    "body": [
        {
            "location": {
                "city": "Coimbra",
                "district": "Coimbra",
                "country": "Portugal"
            },
            "active": true,
            "_id": "60a9387cdc861b83c0bfc418",
            "name": "joao",
            "species": "aves",
            "birth_date": "1997-03-19T00:00:00.000Z",
            "description": "Gosto de aves",
            "__v": 0
        }
    ]
}
```

