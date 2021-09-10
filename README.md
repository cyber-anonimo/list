# list

html:<!DOCTYPE html>
<html lang="PT-BR">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- A div de adcionar tarefas -->
    <div id="divAdd">
        <textarea name="" id="descricaoTarefa" cols="30" rows="2"></textarea>
        <select name="" id="prioridadeTarefa">
            <option value="prioridade-minima">Baixa Prioridade</option>
            <option value="prioridade-mediana">Prioridade Normal</option>
            <option value="prioridade-urgente">Alta Prioridade</option>
        </select>
        <button onclick="fabricaTarefas()" >Adicionar</button>
    </div>

    <hr>

    <!-- A div de listar tarefas -->
    <div id="divLista">

        <!-- Representa um elemento da lista -->
        <!-- <div class="tarefa prioridade-alta">
            <p class="descTarefa"> Estudar para as  </p>
            <button>Excluir</button>
            <input type="checkbox" name="" id="">
        </div> -->

    </div>
    
    <script src="app.js"></script>
    
</body>
</html>

css:/* #divAdd {
    
}

#divLista {   
} */

.tarefa {
    margin-left: 20%;
}

.descTarefa {
    display: inline;
}

.prioridade-urgente{
    color: red;
    font-size: large;
}
.prioridade-mediana {
    color: black;
    font-size: large;
}

.prioridade-minima {
    color: green;
    font-size: large;
}

const listaTarefas = [];

let tarefa1 = {
    descricao: "Estudar para a prova de algoritmos",
    status: "emAberto",
    prioridade: "prioridade-minima"
};

let tarefa2 = {
    descricao: "Estudar para a prova de algoritmos",
    status: "emAberto",
    prioridade: "prioridade-normal"
};

let tarefa3 = {
    descricao: "Estudar para a prova de desenvolvimento",
    status: "emAberto",
    prioridade: "prioridade-urgente"
};

let tarefa4 = {
    descricao: "Estudar para a prova de software",
    status: "emAberto",
    prioridade: "prioridade-urgente"
};

listaTarefas.push(tarefa1);
listaTarefas.push(tarefa2);
listaTarefas.push(tarefa3);
listaTarefas.push(tarefa4);

renderLista();

function fabricaTarefas() {
    let descricao = document.getElementById('descricaoTarefa').value;
    let prioridade = document.getElementById('prioridadeTarefa').value;
    let tarefa = {
        descricao: descricao,
        status: "aberto",
        prioridade: prioridade
    };
    listaTarefas.push(tarefa);
    alert("Tarefa criada");
    renderLista();
}

function renderLista() {
    let divLista = document.getElementById('divLista');
    let template = '';
    for (let i = 0; i < listaTarefas.length; i++) {
        template += `<div class="tarefa ${listaTarefas[i].prioridade}">
                <p class="descTarefa"> ${listaTarefas[i].descricao}  </p>
                <button>Excluir</button>
                <input type="checkbox" name="" id="">
                </div>`;
    }
    divLista.innerHTML = template;
}
