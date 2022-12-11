# The-Cat-API
The Cat API é uma API pública de gerenciamento de informações e imagens de gatinhos.
> Nesta API é possível:
> 
 - Criar registros 
 - Buscar registro de imagens por ID ou todas
 - Excluir registros
 ____________________________________________________

**Premissas**
-   Necessário obter chave API, para isso registre-se em  [https://thecatapi.com/signup](https://thecatapi.com/signup)  e receba sua API key por email.
-   Essa API key deve ser informada no header das chamadas através da variável  `x-api-key`.
-   Utilize o path de chamadas https://api.thecatapi.com/v1 
___________________________________________________________
**Endpoints**

Veja a seguir como funcionam os endpoints relacionados ao recurso images do The Cat API.

**Passo 1**

 1. Crie o registro POST/Criar imagens/upload para incluir a imagem e utilize a URL https://api.thecatapi.com/v1/images/upload.
 2. As imagens sem gatos ou inapropriadas serão rejeitadas.
 3. Neste caso o preenchimento do campo *body é obrigatório.

**OBS:** Quando criado com sucesso é exibido o status **201 Created** e o um código de id da imagem.

Exemplo de resposta do *body*:

{
"id":  "PZDZ4dxRo",
"url":  "https://cdn2.thecatapi.com/images/PZDZ4dxRo.jpg",
"width":  474,
"height":  355,
"original_filename":  "Gatinhos.jpg",
"pending":  0,
"approved":  1
}
_____________________________________________________________
**Passo 2**

 1. Crie o registro GET/images para buscar a imagem correspondente ao *path param*, `image id`, utilize a URL https://api.thecatapi.com/v1/images/PZDZ4dxRo

**OBS:** O image id PZDZ4dxRo * é um _path param_  obrigatório.
 
 2. Quando criado com sucesso é exibido o status **200 OK**.

Exemplo de resposta do *body*:
[
{
"breeds":  [],
"id":  "PZDZ4dxRo",
"url":  "https://cdn2.thecatapi.com/images/PZDZ4dxRo.jpg",
"width":  474,
"height":  355,
"sub_id":  null,
"created_at":  "2022-12-11T14:55:50.000Z",
"original_filename":  "Gatinhos.jpg",
"breed_ids":  null
}
]
_____________________________________________________________
**Passo 3**

 1. Crie o registro GET/upload images para buscar todas as imagens, utilize a URL https://api.thecatapi.com/v1/images?limit=1
 2. O `limit 1` é um *path param*  **obrigatório**.
 3. Quando criado com sucesso é exibido o status **200 OK**.
Exemplo de resposta do *body*:
[
{
"breeds":  [],
"id":  "PZDZ4dxRo",
"url":  "https://cdn2.thecatapi.com/images/PZDZ4dxRo.jpg",
"width":  474,
"height":  355,
"sub_id":  null,
"created_at":  "2022-12-11T14:55:50.000Z",
"original_filename":  "Gatinhos.jpg",
"breed_ids":  null
}
]
____________________________________________________________
**Passo 4** 
  
 1. Crie o registro DELETE para excluir o registro correspondente ao *path param* `image_id`, utilize a URL https://api.thecatapi.com/v1/images/PZDZ4dxRo.
 2. O `image_id` PZDZ4dxRo é um path param  obrigatório.
 3. Quando criado com sucesso é exibido o status **204 No content.**
