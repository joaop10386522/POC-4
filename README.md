# POC-4
index.html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>POC Fetch API</title>
</head>
<body>
    <h1>Usuários</h1>
    <button id="load-users">Carregar Usuários</button>
    <ul id="user-list"></ul>

    <script src="script.js"></script>
</body>
</html>

script.js
document.getElementById('load-users').addEventListener('click', async () => {
    const userList = document.getElementById('user-list');
    userList.innerHTML = ''; // Limpa a lista antes de carregar novos dados

    try {
        const response = await fetch('https://jsonplaceholder.typicode.com/users');
        
        if (!response.ok) {
            throw new Error('Erro ao buscar dados');
        }

        const users = await response.json();

        users.forEach(user => {
            const li = document.createElement('li');
            li.textContent = `${user.name} - ${user.email}`;
            userList.appendChild(li);
        });
    } catch (error) {
        console.error('Erro:', error);
        userList.innerHTML = '<li>Erro ao carregar usuários</li>';
    }
});
