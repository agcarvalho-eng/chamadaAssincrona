# chamadaAssincrona
Exercício de SOA - Chamada assíncrona

Considerando o código, responda.

<!DOCTYPE html>
<html lang="pt-br">
   <head>
       <title></title>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1">
   </head>
   <body>
       <h1>Usando o método fetch para requisição assíncronas em JavaScript</h1>
       <div id="dados"></div>   
   </body>
</html>


<script>
   async function request(){
       const response = await fetch('https://pokeapi.co/api/v2/pokemon/');
       const object = await response.json();
       document.querySelector("#dados").innerHTML = JSON.stringify(object);
   }
   request();
</script>


1. No vídeo anterior foi mostrado um código HTML/JavaScript para realizar requisições assíncronas usando recursos nativos e modernos de JavaScript, sem depender de nenhuma biblioteca.
Qual problema percebeu ao realizar tais alterações?

O problema que pode ser percebido é que a execução da aplicação ficará bloqueada durante a solicitação à URL 'https://jsonplaceholder.typicode.com/photos', tornando a interface da aplicação não responsiva até que a resposta seja recebida. Isso pode ser especialmente problemático em cenários nos quais a resposta demora muito para chegar.

2. Explique porque o problema ocorreu e o qual a relação com chamadas assíncronas.

A função fetch, que bloqueia a execução subsequente até que a resposta seja recebida. Chamadas assíncronas são usadas para evitar esse bloqueio, permitindo que a aplicação continue executando outras tarefas enquanto aguarda a resposta da solicitação. Nesse caso, o código não está aproveitando a natureza assíncrona do fetch, resultando em uma experiência de usuário não responsiva.
