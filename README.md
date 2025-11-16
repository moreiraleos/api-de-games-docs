# API de games
## Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games no cadastrados no banco de dados
#### Parâmetros
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games!

Exemplo de resposta!
```
{
    "games": [
        {
            "id": 1,
            "title": "Call of Duty: Modern Warfare",
            "year": 2019,
            "price": "60",
            "createdAt": null,
            "updatedAt": null
        },
        {
            "id": 2,
            "title": "The Witcher 3: Wild Hunt",
            "year": 2015,
            "price": "40",
            "createdAt": null,
            "updatedAt": null
        }]
}
```



##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Token inválido, Token expirado.

Exemplo de resposta
```
{
    "error": "Token inválido"
}
```


### POST  /auth
Esse endpoint é responsável por fazer o processo de login.

### Parâmentros
email: E-mail do usuário cadastrado no sistema.


password: Senha do usuário cadastrado no sistema, com aquele determinado e-mail.

Exemplo:
```
{
   "email":"email@email.com.br",
    "password":"1234"
}
```

###Respostas
### OK! 200
Caso essa resposta aconteça você vai receber o JWT para conseguir acesssar endpoints protegidos na API.
Exemplo de resposta
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MjEsImVtYWlsIjoidXNlcjFAdGVzdGUuY29tIiwiaWF0IjoxNzYzMzM0MDg5LCJleHAiOjE3NjM1MDY4ODl9.i1MU_2dBZ0tWW2yON-bBMagu5sl7JPNe8lgDXwz5v30"
}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Senha ou e-mail incorretos.

Exemplo de resposta
```
{
    "error": "Credenciais inválidas"
}
```















