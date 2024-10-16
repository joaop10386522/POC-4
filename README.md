# POC-4
Estrutura do JavaScript
1. document.getElementById('load-users').addEventListener('click', ...): Adiciona um evento ao botão "Carregar Usuários". Quando o botão é clicado, a função assíncrona é executada.
2. 
2.async () => { ... }: Define uma função assíncrona, permitindo o uso do await dentro dela.

3.const userList = document.getElementById('user-list');: Seleciona o elemento da lista onde os usuários serão exibidos.

4.userList.innerHTML = '';: Limpa a lista antes de carregar novos dados.

5.try { ... } catch (error) { ... }: Usa um bloco try...catch para lidar com erros durante a busca de dados
.
6.const response = await fetch(...): Faz uma requisição assíncrona à API usando fetch para obter a lista de usuários. await é usado para esperar a resposta.

7.if (!response.ok) { ... }: Verifica se a resposta da API foi bem-sucedida (status 200). Se não, lança um erro.

8.const users = await response.json();: Converte a resposta em formato JSON para um objeto JavaScript.

9.users.forEach(user => { ... }): Itera sobre cada usuário retornado da API.

10.const li = document.createElement('li');: Cria um novo elemento de lista (li).
li.textContent = ${user.name} - ${user.email};: Define o conteúdo do elemento como o nome e o e-mail do usuário.
userList.appendChild(li);: Adiciona o elemento li à lista.
catch (error) { ... }: Captura qualquer erro que ocorra durante o processo.
console.error('Erro:', error);: Imprime o erro no console.
userList.innerHTML = '<li>Erro ao carregar usuários</li>';: Exibe uma mensagem de erro na lista.

