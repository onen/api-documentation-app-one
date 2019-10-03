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
  "data":
    {
      "urlVideo": "https://youtu.be/Zs0hLEHAoSs",
      "capa_src": "http:\/\/localhost\/images\/filme\/cb46d7f9855fe1ab735d31e1a4aeac32-99b6ed56.jpg",
      "genero": "Aventura \/ Ação \/ Fantasia",
      "nome": "Abigail e a Cidade Proibida",
      "tempoDuracao": 169,
      "descricao": "Hebe Camargo (Andréa Beltrão) se consagrou como uma das maiores apresentadoras da televisão brasileira. Nos anos 80, durante o processo de redemocratização do país",
      "elenco": "Danton Mello, Gabriel Braga Nunes, Otávio Augusto, Daniel Boaventura, Andréa Beltrão",
      "distribuidora": "Warner Bros",
      "diretor": "Mauricio Farias",
    },
  "status": "success",
  "messages": null,
}
```
---
