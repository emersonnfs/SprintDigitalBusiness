# StudIt

Uma api para o projeto StudIt onde geramos material de estudo para alunos de escola sob demanda.

## Endpoints

- Usuários
    - [Cadastrar](#cadastrar-usuário)
    - [Listar todos](#listar-usuários)
    - [Mostrar detalhes](#listar-usuário)
    - [Apagar](#apagar-usuário)
    - [Alterar](#atualizar-usuário)

---
### Cadastrar Usuário

`POST` /studit/api/usuario

| Campo | Tipo | Obrigatório | Descrição 
|-------|------|-------------|-----------
| nome | String | Sim | Aqui vai o nome do usuário
| email | String | Sim | Aqui vai o email do usuário
| senha | String | Sim | Aqui vai o senha do usuário
| data | LocalDate | Não | Aqui vai a data de nascimento do usuário
| foto | Foto | Não | Aqui vai a foto do perfil

**Exemplo de corpo do request**

```js

    {
        "nome": "Fulano de Tal",
        "email": "fulano@example.com",
        "senha": "senha123",
        "data": "1990-01-01",
        "foto": {
            "id": "1"
        }
    }

```

**Códigos de Repsosta**

| Código | Descrição
|--------|-----------
| 201 | Usuário cadastrada com sucesso
| 400 | Erro na validação dos dados da requisição

---

### Listar Usuários

`GET` /studit/api/usuario

```js

    {
        {
            "nome": "Fulano de Tal",
            "email": "fulano@example.com",
            "senha": "senha123",
            "data": "1990-01-01",
            "foto": {
                "id": "1",
                "url": "http://example.com/foto.jpg",
                "descricao": "Minha foto de perfil",
                "tamanho": 1024,
                "dataCriacao": "2023-04-06T10:00:00Z"
            }
        },
        {
            "nome": "Beltrano da Silva",
            "email": "beltrano@example.com",
            "senha": "senha456",
            "data": "1995-05-05",
            "foto": {
                "id": "2",
                "url": "http://example.com/foto2.jpg",
                "descricao": "Minha segunda foto de perfil",
                "tamanho": 2048,
                "dataCriacao": "2023-04-06T11:00:00Z"
            }
        }
    }

```

**Códigos de Resposta**

| Código | Descrição
|--------|-----------
| 200 | Dados retornados no corpo da resposta
| 404 | Dados não encontrado

---

### Listar Usuário

`GET` /studit/api/usuario/{id}

```js

    {
        "nome": "Fulano de Tal",
        "email": "fulano@example.com",
        "senha": "senha123",
        "data": "1990-01-01",
        "foto": {
            "id": "1",
            "url": "http://example.com/foto.jpg",
            "descricao": "Minha foto de perfil",
            "tamanho": 1024,
            "dataCriacao": "2023-04-06T10:00:00Z"
        }
    }

```

**Códigos de Resposta**

| Código | Descrição
|--------|-----------
| 200 | Dados retornados no corpo da resposta
| 404 | Dados não encontrado

---

### Apagar Usuário

`DELETE` /studit/api/usuario/{id}

**Códigos de Resposta**

| Código | Descrição
|--------|-----------
| 202 | Usuário apagado com sucesso
| 404 | Usuário não encontrado

---

### Atualizar Usuário

`PUT` /studit/api/usuario/{id}

```js

    {
        "nome": "Beltrano de Tal",
        "email": "beltrano@example.com",
        "senha": "senha123",
        "data": "1995-05-05",
        "foto": {
            "id": "1"
        }
    }

```

**Códigos de Resposta**

| Código | Descrição
|--------|-----------
| 201 | Usuário atualizado com sucesso
| 400 | Erro na validação dos dados da requisição

---