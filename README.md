# Cancelamento de Títulos
Duepay
## Endpoint

### POST /publico/cancela_boleto
Cancela o título informado
#### Autorizaçao
no header da requisição, informar o token de autenticação
```
Authorization: onnNJXcE7C6JgSMbP7msy5gB7
```

#### Parâmetros
numberId: número gerado na criação do título
cliente: documento do pagador (cnpj ou cpf)
```
{
    "numberId":"00003424464",
    "cliente": "30340866000102"
}
```
#### Respostas
##### 200
título descarregado
```
{
    "message": "Mensagem de confirmação da baixa",
    "success": true
}
```
##### 400
erro no cancelamento junto à CIP
```
{
    "message": "razão do erro do cancelamento", 
    "success": false
}
```
ou quando a situação atual do título impeça o cancelamento

```
{
    "message": "Esse boleto já foi liquidado ou está em processo de liquidação e não pode ser removido."
    "success": false
}
```
