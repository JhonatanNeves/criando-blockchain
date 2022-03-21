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
            "timestamp": "2022-03-15 18:05:55.902127",
            "transactions": []
        }
    ],
    "length": 1
}
```
### GET /mine_block

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
    "previous_hash": "9479216c7db155b4bc8bba795d1e0a9df85ccf92a1f444e9d2b0d8d8198cf741",
    "proof": 2,
    "timestamp": "2022-03-21 10:32:47.981576",
    "transaction": [
        {
            "amount": 1,
            "receiver": "Neves",
            "sender": "5b21ae31761d472aae2afac7cb6d2fe4"
        }
    ]
}
```

##### Falha na mineração!

Caso essa resposta aconteça, isso siginifica que aconteceu alguma falha durante o processo da requisição.  
Exemplo de resposta:

```
{'message': 'Not Valid!'}

```

### GET /is_valid

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
### POST /add_transaction

Esse endpoint é responsável por adicionar transação.

#### Parametros
Nenhum

#### Respostas

##### OK! 201

Caso essa resposta aconteça , você receberá uma mensagem.  
Exemplo de resposta:

```
{
    "message": "Esta transação será adicionada ao bloclo 3"
}
```

##### Falha na autenticação! 400

Caso essa resposta aconteça, isso siginifica que aconteceu alguma falha durante o processo.  
Exemplo de resposta:

```
{
    "message": "Alguns elementos estão faltando!"
}

```
### POST /connect_node

Esse endpoint é responsável pela conexão.

#### Parametros
Nenhum

#### Respostas

##### OK! 201

Caso essa resposta aconteça , você receberá uma mensagem.  
Exemplo de resposta:

```
{
    "message": "Todos nós conectados, blockchain contem os seguintes nós:",
    "total_nodes": [
        "http://127.0.0.1:5001",
        "http://127.0.0.1:5002",
        "http://127.0.0.1:5003"
    ]
}
```

##### Falha ! 400

Caso essa resposta aconteça, isso siginifica que aconteceu alguma falha durante o processo.  
Exemplo de resposta:

```
{
    "message": "Vazio!"
}

```
### GET /replace_chain

Esse endpoint é responsável por substituir a cadeia se necessário.

#### Parametros
Nenhum

#### Respostas

##### OK! 200

Caso essa resposta aconteça , você receberá uma mensagem.  
Exemplo de resposta:

```
{
    "actual_chain": [
        {
            "index": 1,
            "previous_hash": "0",
            "proof": 1,
            "timestamp": "2022-03-21 10:19:17.813744",
            "transactions": []
        },
        {
            "index": 2,
            "previous_hash": "9479216c7db155b4bc8bba795d1e0a9df85ccf92a1f444e9d2b0d8d8198cf741",
            "proof": 2,
            "timestamp": "2022-03-21 10:32:47.981576",
            "transactions": [
                {
                    "amount": 1,
                    "receiver": "Neves",
                    "sender": "5b21ae31761d472aae2afac7cb6d2fe4"
                }
            ]
        }
    ],
    "message": "OK , não houve substituição!"
}
```

