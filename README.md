# Documentação da Api de Games
Curso de NodeJs
## Endpoints
### GET /games
Listagem de todos os jogos cadastrados na base
#### Parâmetros
Nenhum parâmetro requerido
#### Respostas
##### 200
Lista de games cadastrados
```
[
    {
        "id": 25,
        "title": "Um jogo",
        "year": 2019,
        "price": 60
    },
    {
        "id": 26,
        "title": "Outro jogo",
        "year": 2018,
        "price": 50
    },
    {
        "id": 27,
        "title": "Mais um jogo",
        "year": 2021,
        "price": 80
    }
]
```
##### 401
Usuário não conectado ao sistema

```
{
    "resultado": "login expirado"
}
```

### POST /auth
Autentica o usuário no sistema
#### Parâmetros
login: nome de usuário
senha: chave do usuário
```
{
    "login": "nome de usuario",
    "senha": "chave"
}
```
#### Respostas
##### 200
token de autenticação
```
{
    "resultado": "usuário logado",
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ94"
}
```
##### 401
erro de credenciais:
```
{
    "resultado": "usuário não encontrado"
}
```
ou

```
{
    "resultado": "senha não confere"
}
```
