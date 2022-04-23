# Elife-Mini-projeto-Everton-Thiago

const express = require('express');

const server = express();

server.use(express.json());

const usuario = ['userName, password, email']

// Retorna um usuario
server.get('/usuario/:index', (req, res) => {
    const { index } = req.params;

    return res.json(usuario[index]);
});

// Retornar todos os usuarios 
server.get('/usuario', (req, res) => {
    return res.json(usuario)
});

// Criar um novo usuario 
server.post('/usuario', (req, res) => {
    const { name } = req.body;
    usuario.push(name);

    return res.json(usuario);
});

//Atualizar um usuario 
server.put('/usuario/:index', (req, res) => {
    const { index } = req.params;
    const { name } = req.body;

    usuario [index] = name; 
    return res.json(usuario);
 });

 // Arquivar um usuario 
server.delete('/usuario/:index', (req, res) => {
    const { index } = req.params;

    usuario.splice(index, 1);
    return res.json({ message: "O usuario foi deletado" });
