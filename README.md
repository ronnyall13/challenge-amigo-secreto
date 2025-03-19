# Aplicativo de Sorteio de Amigo Secreto

## Descrição
Esta aplicação permite que usuários insiram nomes em uma lista e realizem um sorteio aleatório para determinar quem será o "amigo secreto". O sistema garante uma interação intuitiva e responsiva, proporcionando uma experiência simples e eficiente.

## Funcionalidades
1. **Adicionação de Nomes**: Usuários podem inserir nomes através de um campo de entrada e adicioná-los à lista.
2. **Validação de Entrada**: O sistema impede a adição de entradas vazias e exibe mensagens de erro apropriadas.
3. **Exibição da Lista de Participantes**: Todos os nomes inseridos são exibidos em tempo real em uma lista dinâmica.
4. **Sorteio Aleatório**: Um nome é selecionado aleatoriamente da lista e exibido ao usuário.

## Implementação
A aplicação utiliza JavaScript para manipulação da DOM e execução das funcionalidades. Abaixo estão os principais componentes do código:

### 1. Estrutura de Dados
A lista de nomes é armazenada em um array:
```javascript
let amigos = [];
```

### 2. Função para Adicionar Nomes
Essa função captura a entrada do usuário, valida-a e atualiza o array:
```javascript
function adicionarAmigo() {
    let nome = document.getElementById("nomeInput").value.trim();
    if (nome === "") {
        alert("Por favor, insira um nome válido.");
        return;
    }
    amigos.push(nome);
    document.getElementById("nomeInput").value = "";
    atualizarLista();
}
```

### 3. Atualização da Lista de Participantes
Os nomes armazenados são exibidos dinamicamente:
```javascript
function atualizarLista() {
    let lista = document.getElementById("listaAmigos");
    lista.innerHTML = "";
    amigos.forEach(amigo => {
        let item = document.createElement("li");
        item.textContent = amigo;
        lista.appendChild(item);
    });
}
```

### 4. Sorteio de Amigo Secreto
A função sorteia aleatoriamente um nome da lista:
```javascript
function sortearAmigo() {
    if (amigos.length === 0) {
        alert("A lista está vazia. Adicione nomes antes de sortear.");
        return;
    }
    let indiceSorteado = Math.floor(Math.random() * amigos.length);
    document.getElementById("resultado").innerText = `Amigo Secreto: ${amigos[indiceSorteado]}`;
}
```

## Como Utilizar
1. Insira um nome no campo de entrada.
2. Clique no botão "Adicionar" para incluí-lo na lista.
3. Repita o processo para adicionar mais participantes.
4. Clique em "Sortear Amigo" para selecionar aleatoriamente um nome.

## Tecnologias Utilizadas
- HTML
- CSS
- JavaScript

## Autor
Desenvolvido por Israel como parte de um desafio de programação.

---

Este README foi estruturado para garantir clareza e facilitar a compreensão do funcionamento da aplicação.

