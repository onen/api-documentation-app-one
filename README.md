# api-documentation-app-one
Documentação aberta para a integração One

---
## Formato de retorno

- **data**: O corpo dos dados;
- **status**: Status da resposta;
- **messages**: Menssagem da resposta;

*Exemplo*
```json
{
 "data": {"a": "Hello Wolrd"},
 "status": "success",
 "messagem": "Ola Mundo",
}
```
---
## Listagem de filmes

- **Uri**: */api/v1/filmes*
- **Method**: GET
- **Content Type**: application/json

**Suporte para multiplas cidades**

`/api/v1/filmes/em-cartaz?cidades[]=porto-uniao&cidades[]=brusque`

**Suporte para uma unica cidade**

`/api/v1/filmes/em-cartaz?cidades=brusque`

**Query Parâmeters**

- **estado**: Sigla dos estados ex (SC, SP, RS);

- **cidades**: Utiliza slug do nome da cidade:
 - Slug de cidades suportadas:
  - `arapongas`;
  - `brusque`;
  - `idaial`;
  - `joacaba`;
  - `pato-branco`;
  - `porto-belo`;
  - `porto-uniao`;
  - `sao-bento-do-sul`;

```json
{
  "data":[
    {
      "nome": "Abigail e a Cidade Proibida",
      "slug": "abigail-e-a-cidade-proibida",
      "genero": "Aventura \/ Ação \/ Fantasia",
      "classificacao": 12,
      "pre_estreia": true,
      "capa_src": "http:\/\/localhost\/images\/filme\/cb46d7f9855fe1ab735d31e1a4aeac32-99b6ed56.jpg",
      "estreia": false
    }
  ],
  "status": "success",
  "messages": null,
}
```
---
## Detalhes de filmes

- **Uri**: */api/v1/filme/{filmeSlug}/detalhes*
- **Method**: GET
- **Content Type**: application/json

```json
{
  "data":[
    {

    }
  ],
  "status": "success",
  "messages": null,
}
```
---
