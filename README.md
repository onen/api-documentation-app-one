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

## Sessões Filmes

- **Uri's**: 
  
  Para todos os cinemas
   - */api/v1/filme/{filmeSlug}/sessao[/{cinema-slug}]*
   
  Para cinemas específicos
   - */api/v1/filme/{filmeSlug}/sessao/{cinema-slug}*

- **Method**: GET
- **Content Type**: application/json

```json
{
 "data": 
  [
   {
    "2019-10-03": 
     [
      {
       "nome": "Cine Gracher Havan Brusque",
       "endereco": "Rodovia Antônio Heil Brusque - SC",
       "maps": "https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3551.8257078094534!2d-48.914319784347825!3d-27.098791007518777!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x94df479851984c85:0x6a106d3cf5e7d502!2sAABB+-+Schmitt+Buffet+e+Eventos!5e0!3m2!1spt-BR!2sbr!4v1454757997460",
       "salas":
        [
         {
          "nome": "Sala 02",
          "sessoes": 
           [ 
            {
             "dataHora": "2019-10-04 21:15:00",
             "tela": "2D",
             "audio": "DUB",
             "legenda": "legendado",
             "expirado": false
            }
          ]
        }
      ]
     }
    ]
   }
  ],
 "status": "success",
 "messagem": ""
}
```
