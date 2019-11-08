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
`
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

- **cinemaSlug**: Utiliza slug do nome do cinema:
- Slug dos cinemas:
 - `cine-gracher-havan-brusque`
 - `cine-gracher-shopping-brusque`
 - `cine-gracher-havan-pato-branco`
 - `cine-gracher-havan-arapongas`
 - `cine-gracher-havan-indaial`
 - `cine-gracher-havan-joacaba`
 - `cine-gracher-havan-porto-belo`
 - `cine-gracher-havan-sao-bento-do-sul`

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
      "estreia": false,
      "data_estreia": "2019-10-24",
      "data_pre_estreia": "2019-09-04"
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
      "classificao": 16,
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

  Para todas as requisições é necessário a data das exibições
  - */api/v1/filme/{filmeSlug}/sessao?dataInicio=2019-10-10&dataFim=2019-11-30*
  
  Para todos os cinemas
   - */api/v1/filme/{filmeSlug}/sessao*
   
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
 "messages": ""
}
```
---

## Minha conta

**Para conseguir acessar estas actions você precisa estar autenticado!**

*Aqui vai ter o link para o end-point de autenticação*

---

## Listagem de pedidos

- **Uri**: */api/v1/minha-conta/pedidos/cinema*
- **Method**: GET
- **Content Type**: application/json

```json
{
 "data":[
   {
    "dataFilme": "2019-09-16",
    "sessaoFilme": "19:00",
    "pedidoId": "1111111",
    "sala": "Sala 1",
    "audio": "DUB",
    "tela": "2D",
    "cinema": "Cine Gracher Havan Arapongas",
    "filme": "Angry Birds O Filme 2",
    "dataHoraCompra": "2019-09-03 14:30:00",
    "capa": "http:\/\/localhost\/images\/filme\/cb46d7f9855fe1ab735d31e1a4aeac32-99b6ed56.jpg"
   }
  ],
  "status": "success",
  "messages": ""
}
```
---

## Listagem de ingressos

- **Uri**: */api/v1/minha-conta/pedido/cinema/{pedidoId}/detalhes*
- **Method**: GET
- **Content Type**: application/json

```json
 "data": 
   [
     {
       "ingressoId": 1616161,
       "tipoIngresso": "Inteira",
       "nome": "José Maria",
       "email": "josemaria@maria.com.br",
       "cpf": "10120104903",
       "poltrona": "15B",
       "barCode": 1111111111111111111111111
     }
   ]
 "status": "success",
 "messages": ""
```
---

## Edição de ingresso

- **Uri**: */api/v1/minha-conta/pedido/ingresso*
- **Method**: POST
- **Content Type**: application/json

```json
 {
   "id": 1616161,
   "nome": "Maria Aurorra",
   "email": "maria@ma.com.br",
   "cpf": "101012121201"
 }
```


