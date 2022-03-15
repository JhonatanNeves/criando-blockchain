# Blockchain

## Endpoints

### GET /get_chain

Esse endpoint é responsável por retornar o blockchain gerado.

#### Parametros

Nenhum

#### Respostas

##### OK! 200

Caso essa resposta aconteça , você receberá o retordo do blockchain
Exemplo de resposta:

```
{
    "chain": [
        {
            "index": 1,
            "previous_hash": "0",
            "proof": 1,
            "timestamp": "2022-03-15 18:05:55.902127"
        }
    ],
    "length": 1
}
```
### POST /mine_block

Esse endpoint é responsável por fazer a mineraçao.

#### Parametros

Nenhum
#### Respostas

##### OK! 200

Caso essa resposta aconteça , retornará o block com uma mensagem.
Exemplo de resposta:

```
{
    "index": 2,
    "message": "Congratulations, you have mined a block!",
    "previous_hash": "1eaafc15fab5fec4cbe84539d44dff8c657f46c77bcbe878d7509c61d39da8d9",
    "proof": 2,
    "timestamp": "2022-03-15 18:14:46.159530"
}
```

##### Falha na mineração!

Caso essa resposta aconteça, isso siginifica que aconteceu alguma falha durante o processo da requisição.

Exemplo de resposta:

```
{'message': 'Not Valid!'}

```

### POST /is_valid

Esse endpoint é responsável por fazer a validação do blockchain.

#### Parametros

Nenhum
#### Respostas

##### OK! 200

Caso essa resposta aconteça , você receberá uma mensagem.
Exemplo de resposta:

```
{
    "message": "Its Ok, Valid Blockchain!"
}
```

##### Falha na autenticação! 401

Caso essa resposta aconteça, isso siginifica que aconteceu alguma falha durante o processo de validação.

Exemplo de resposta:

```
{
    "message": "Not Valid!"
}

```
