# StudIt

Uma api para o projeto StudIt onde geramos material de estudo para alunos de escola sob demanda.

## Endpoints

- [Usuários](#usuários)
    - [Cadastrar](#cadastrar-usuário)
    - [Listar todos](#listar-usuários)
    - [Mostrar detalhes](#listar-usuário)
    - [Apagar](#apagar-usuário)
    - [Alterar](#atualizar-usuário)
- [Foto](#foto)
    - [Cadastrar](#cadastrar-foto)
    - [Listar todos](#listar-fotos)
    - [Mostrar detalhes](#listar-foto)
    - [Apagar](#apagar-foto)
    - [Alterar](#atualizar-foto)
- [Resumo](#resumo)
    - [Cadastrar](#cadastrar-resumo)
    - [Listar todos](#listar-resumos)
    - [Mostrar detalhes](#listar-resumo)
    - [Apagar](#apagar-resumo)
    - [Alterar](#atualizar-resumo)


---

## Usuários

| Campo | Tipo | Obrigatório | Descrição 
|-------|------|-------------|-----------
| nome | String | Sim | Aqui vai o nome do usuário
| email | String | Sim | Aqui vai o email do usuário
| senha | String | Sim | Aqui vai o senha do usuário
| data | LocalDate | Não | Aqui vai a data de nascimento do usuário
| foto | Foto | Não | Aqui vai a foto do perfil

### Cadastrar Usuário

`POST` /studit/api/usuario

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
            },
            "id": "1"
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
            },
            "id": "2"
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
        },
        "id": "1"
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
        },
        "id": "1"
    }

```

**Códigos de Resposta**

| Código | Descrição
|--------|-----------
| 201 | Usuário atualizado com sucesso
| 400 | Erro na validação dos dados da requisição

---

## Foto

| Campo | Tipo | Obrigatório | Descrição 
|-------|------|-------------|-----------
| url | String | Sim | Aqui vai a url da foto
| descricao | String | Sim | Aqui vai a descrição da foto
| tamanhoBytes | int | Sim | Aqui vai o tamanho em bytes da foto
| dataCriacao | LocalDateTime | Sim | Aqui vai a data criação da foto

### Cadastrar Foto

`POST` /studit/api/foto

**Exemplo de corpo do request**

```js

    {
        "url": "http://example.com/foto.jpg",
        "descricao": "Minha foto de perfil",
        "tamanho": 1024,
        "dataCriacao": "2023-04-06T10:00:00Z"
    }

```

**Códigos de Repsosta**

| Código | Descrição
|--------|-----------
| 201 | Foto cadastrada com sucesso
| 400 | Erro na validação dos dados da requisição

---

### Listar Fotos

`GET` /studit/api/foto

```js

    {
        {
            "id": "1",
            "url": "http://example.com/foto.jpg",
            "descricao": "Minha foto de perfil",
            "tamanho": 1024,
            "dataCriacao": "2023-04-06T10:00:00Z"
        },
        {
            "id": "2",
            "url": "http://example.com/foto2.jpg",
            "descricao": "Minha segunda foto de perfil",
            "tamanho": 2048,
            "dataCriacao": "2023-04-06T11:00:00Z"
        }
    }

```

**Códigos de Resposta**

| Código | Descrição
|--------|-----------
| 200 | Dados retornados no corpo da resposta
| 404 | Dados não encontrado

---

### Listar Foto

`GET` /studit/api/foto/{id}

```js

    {
        "id": "1",
        "url": "http://example.com/foto.jpg",
        "descricao": "Minha foto de perfil",
        "tamanho": 1024,
        "dataCriacao": "2023-04-06T10:00:00Z"
    }

```

**Códigos de Resposta**

| Código | Descrição
|--------|-----------
| 200 | Dados retornados no corpo da resposta
| 404 | Dados não encontrado

---

### Apagar Foto

`DELETE` /studit/api/foto/{id}

**Códigos de Resposta**

| Código | Descrição
|--------|-----------
| 202 | Foto apagada com sucesso
| 404 | Foto não encontrado

---

### Atualizar Foto

`PUT` /studit/api/foto/{id}

```js

    {
        "url": "http://example.com/foto.jpg",
        "descricao": "Minha foto de perfil atualizada",
        "tamanho": 2048,
        "dataCriacao": "2023-04-06T10:00:00Z",
        "id": "1"
    }

```

**Códigos de Resposta**

| Código | Descrição
|--------|-----------
| 201 | Foto atualizada com sucesso
| 400 | Erro na validação dos dados da requisição

---

## Resumo

| Campo | Tipo | Obrigatório | Descrição 
|-------|------|-------------|-----------
| titulo | String | Sim | Aqui vai o título do resumo
| conteudo | String | Sim | Aqui vai o conteúdo do resumo
| dataCriacao | LocalDateTime | Sim | Aqui vai a data de criação do resumo
| materia | Materia | Sim | Aqui vai matéria que vai para o resumo

### Cadastrar Resumo

`POST` /studit/api/resumo

**Exemplo de corpo do request**

```js

    {
        "titulo": "Título do resumo",
        "conteudo": "Conteúdo do resumo",
        "dataCriacao": "2023-04-07T10:00:00",
        "materia": "MATEMATICA"
    }

```

**Códigos de Repsosta**

| Código | Descrição
|--------|-----------
| 201 | Resumo cadastrada com sucesso
| 400 | Erro na validação dos dados da requisição

---

### Listar Resumos

`GET` /studit/api/resumo

```js

    {
        {        
            "id": 1,        
            "titulo": "Título do resumo 1",        
            "conteudo": "Conteúdo do resumo 1",        
            "dataCriacao": "2023-04-07T10:00:00",        
            "materia": "MATEMATICA"    
        },    
        {        
            "id": 2,        
            "titulo": "Título do resumo 2",        
            "conteudo": "Conteúdo do resumo 2",        
            "dataCriacao": "2023-04-08T14:00:00",        
            "materia": "PORTUGUES"    
        }
    }

```

**Códigos de Resposta**

| Código | Descrição
|--------|-----------
| 200 | Dados retornados no corpo da resposta
| 404 | Dados não encontrado

---

### Listar Resumo

`GET` /studit/api/resumo/{id}

```js

    {        
        "id": 1,        
        "titulo": "Título do resumo 1",        
        "conteudo": "Conteúdo do resumo 1",        
        "dataCriacao": "2023-04-07T10:00:00",        
        "materia": "MATEMATICA"    
    }

```

**Códigos de Resposta**

| Código | Descrição
|--------|-----------
| 200 | Dados retornados no corpo da resposta
| 404 | Dados não encontrado

---

### Apagar Resumo

`DELETE` /studit/api/resumo/{id}

**Códigos de Resposta**

| Código | Descrição
|--------|-----------
| 202 | Resumo apagado com sucesso
| 404 | Resumo não encontrado

---

### Atualizar Resumo

`PUT` /studit/api/resumo/{id}

```js

    {
        "id": 1,
        "titulo": "Título do resumo 1",
        "conteudo": "Novo conteúdo do resumo 1",
        "dataCriacao": "2023-04-07T10:00:00",
        "materia": "MATEMATICA"
    }


```

**Códigos de Resposta**

| Código | Descrição
|--------|-----------
| 201 | Resumo atualizado com sucesso
| 400 | Erro na validação dos dados da requisição

---