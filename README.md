<div align="center">
  <img src="https://github.com/ChristopherHauschild/bootcamp-gostack-13-rocketseat/blob/master/gostack.png?raw=true">
</div> <br />

<div align="center">
  <img src="https://img.shields.io/static/v1?label=nodejs&message=backend&color=success&style=for-the-badge&logo=NODE.JS"/>
</div>

# <p align="center">Desafio - Iniciando backend da aplicação</p>

:information_source: <i>Códigos desenvolvidos durante o desafio Iniciando backend da aplicacão, na segunda semana do Bootcamp GoStack 13, ofertado pela plataforma de ensino [Rocketseat](https://rocketseat.com.br/).</i>

<p align="justify">
Esse desafio tem como objetivo fixar os conhecimentos aprendidos em Node.js junto ao TypeScript, utilizando o conceito de models, repositories e services, tudo isso incluindo o uso de banco de dados com o TypeORM e envio de arquivos com o Multer!. A mesma consiste numa aplicação para armazenar transações financeiras de entrada e saída, permitindo o cadastro e a listagem dessas transações.
</p>

## :twisted_rightwards_arrows: Rotas da aplicação:

- **`POST /transactions`**: A rota deve receber `title`, `value`, `type`, e `category` dentro do corpo da requisição, sendo o `type` o tipo da transação, que deve ser `income` para entradas (depósitos) e `outcome` para saídas (retiradas). Ao cadastrar uma nova transação, ela deve ser armazenada dentro do seu banco de dados, possuindo os campos `id`, `title`, `value`, `type`, `category_id`, `created_at`, `updated_at`.

```json
{
  "id": "uuid",
  "title": "Salário",
  "value": 3000,
  "type": "income",
  "category": "Alimentação"
}
```

- **`GET /transactions`**: Essa rota deve retornar uma listagem com todas as transações que você cadastrou até agora, junto com o valor da soma de entradas, retiradas e total de crédito. Essa rota deve retornar um objeto o seguinte formato:

```json
{
  "transactions": [
    {
      "id": "uuid",
      "title": "Salário",
      "value": 4000,
      "type": "income",
      "category": {
        "id": "uuid",
        "title": "Salary",
        "created_at": "2020-04-20T00:00:49.620Z",
        "updated_at": "2020-04-20T00:00:49.620Z"
      },
      "created_at": "2020-04-20T00:00:49.620Z",
      "updated_at": "2020-04-20T00:00:49.620Z"
    },
    {
      "id": "uuid",
      "title": "Freela",
      "value": 2000,
      "type": "income",
      "category": {
        "id": "uuid",
        "title": "Others",
        "created_at": "2020-04-20T00:00:49.620Z",
        "updated_at": "2020-04-20T00:00:49.620Z"
      },
      "created_at": "2020-04-20T00:00:49.620Z",
      "updated_at": "2020-04-20T00:00:49.620Z"
    },
    {
      "id": "uuid",
      "title": "Pagamento da fatura",
      "value": 4000,
      "type": "outcome",
      "category": {
        "id": "uuid",
        "title": "Others",
        "created_at": "2020-04-20T00:00:49.620Z",
        "updated_at": "2020-04-20T00:00:49.620Z"
      },
      "created_at": "2020-04-20T00:00:49.620Z",
      "updated_at": "2020-04-20T00:00:49.620Z"
    },
    {
      "id": "uuid",
      "title": "Cadeira Gamer",
      "value": 1200,
      "type": "outcome",
      "category": {
        "id": "uuid",
        "title": "Recreation",
        "created_at": "2020-04-20T00:00:49.620Z",
        "updated_at": "2020-04-20T00:00:49.620Z"
      },
      "created_at": "2020-04-20T00:00:49.620Z",
      "updated_at": "2020-04-20T00:00:49.620Z"
    }
  ],
  "balance": {
    "income": 6000,
    "outcome": 5200,
    "total": 800
  }
}
```

- **`DELETE /transactions/:id`**: A rota deve deletar uma transação com o `id` presente nos parâmetros da rota;

* **`POST /transactions/import`**: A rota deve permitir a importação de um arquivo com formato `.csv` contendo as mesmas informações necessárias para criação de uma transação `id`, `title`, `value`, `type`, `category_id`, `created_at`, `updated_at`, onde cada linha do arquivo CSV deve ser um novo registro para o banco de dados, e por fim retorne todas as `transactions` que foram importadas para seu banco de dados. O arquivo csv, deve seguir o seguinte [modelo](./assets/file.csv)
## :pushpin: Maiores informações:

Para encontrar maiores informações sobre o desafio, como por exemplo o template utilizado e a bateria de testes implementadas, você pode acessar este [link](https://github.com/rocketseat-education/bootcamp-gostack-desafios/tree/master/desafio-database-upload).

<hr>

Códigos desenvolvidos por Christopher Hauschild Schott

